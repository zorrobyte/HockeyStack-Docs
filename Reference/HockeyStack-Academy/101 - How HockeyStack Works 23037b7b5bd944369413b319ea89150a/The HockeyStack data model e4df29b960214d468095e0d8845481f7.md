# The HockeyStack data model

HockeyStack’s power and flexibility comes from the fact that we’re able to transform any type of data into a unified data model. 

Our unified data model is fundamentally different than the object-based (Salesforce, HubSpot, Marketo, etc.) data model that a lot of people are used to before starting to use HockeyStack.

In the object-based model, you have every type of entity recorded as objects with pre-defined fields. You would have an Opportunity object, a Lead object, a Contact object, each having a list of possible fields, with some of those fields defining relationships between the different objects. 

This model was put in place at a time when the customer journey was less complex, and companies had less types of interactions with customers.

In the modern era, customers can interact with a company in thousands of different ways. If you wanted to store all of those interactions in an object-based model, each of those types of interactions would be represented either by a separate object or by a combination of fields. Reporting would be a huge mess, the data volume would be unmanageable for any CRM or marketing automation system, and each type of interaction would need to be completely thought through beforehand.

This is the reason why:

1- CRMs and marketing automation systems are not good at complex data problems such as attribution and intent modeling — their data model is too low resolution and silo’ed to make this work.

2- Attempts to make multi-touch work within those object-based systems always result in a very very crude and inaccurate version of multi-touch that nobody wants to use, or a complete migration from a CRM system to a data warehouse that renders business users completely incapable of using analytics without hand-holding from technical folks. 

---

To solve this problem, HockeyStack’s unified data model is **action-based.**

An **Action** is a **timestamped interaction** along the customer’s journey.

An action can be performed by a customer: Visiting the website, clicking an email, filling out a form, etc.

But it can also be performed by you, the company: creating a Lead in the CRM, sending an email, calling, etc.

The customer might be an individual, in the case of a website visit, or it might be an organization, in the case of a LinkedIn Ad Engagement where we don’t know who the individual is.

The interaction can have infinite number of different qualities. For example, a website visit might be qualified using its source, but an email might be qualified using the campaign name or the subject. Furthermore, an outreach email might have different qualities than a marketing email. The list goes on and on.

Considering all of the above, an action is represented using 4 key pieces of information:

- **Timestamp**
- **Entity**
    - Either an individual in the customer company, or the entire customer company
- **Action Name**
    - A short description of what the interaction is
- **Action Properties**
    - An infinitely extensible list of properties relating to the action.

You can see some examples by reading up on the website actions documentation or integration documentations:

[A list of all website actions](The%20HockeyStack%20data%20model%20e4df29b960214d468095e0d8845481f7/A%20list%20of%20all%20website%20actions%208a42a56c8c0a485590f0480427c538f5.md)

[Integrations](../../Integrations%2042cfee82e46b412792a90e73fe508246.md)

---

To make it more clear, let’s visualize actions as a table of information.

Let’s say we are representing the creation of an Opportunity inside Salesforce as an action in HockeyStack. This row in the table would look like below:

| **Timestamp** | **Entity** | **Action Name** | **Action Properties** |
| --- | --- | --- | --- |
| 2024-01-01 00:00:00 in Pacific Time | Pied Piper, Inc. | Deal Created | **Deal Id:** 321732
**Deal Name:** Pied Piper - Upsell
**Deal Amount:** $10,000
**Deal Stage:** Discovery
**Deal_Qualified__c:** false |

Now, let’s say this opportunity becomes qualified, and progresses to a stage called POC. A new action is created with the stage change. 

| **Timestamp** | **Entity** | **Action Name** | **Action Properties** |
| --- | --- | --- | --- |
| 2024-02-01 00:00:00 in Pacific Time | Pied Piper, Inc. | Deal Moved to POC | **Deal Id:** 321732
**Deal Name:** Pied Piper - Upsell
**Deal Amount:** $10,000
**Deal Stage:** POC
**Deal_Qualified__c:** true |

If I do any reporting on this opportunity based on the action called “Deal Created”, I will see that the opportunity is unqualified, and is in Discovery stage, which is inaccurate.

For example, let’s say I want to count the number of qualified deals created last month. The report would be defined as “the number of Deal Created actions where Deal_Qualified__c is true”. In the above case, since the Deal Created action has Deal_Qualified__c set as false, this opportunity won’t show up in the report even though it should.

The solution is to have a data structure separate from actions, which will store the latest state of entities like deals, companies, campaigns, and will connect to actions via properties like "deal id", "company id", "campaign id", etc.

Then, HockeyStack would allow you to pull the Deal_Qualified__c property from this separate data structure (which shows the new value of the property), instead of pulling it from the action itself (which shows the old value of the property). The value of Deal_Qualified__c = true would effectively be shared across multiple actions by connecting to this new data structure.

This data structure is called **Shared Properties,** and it is represented as below:

- **Key**
    - The matching key that will be used to group multiple actions together
- **Value**
    - The value of the matching key in those actions
- **Properties**
    - The latest properties that are stored in relation to these actions

For example, both of the above actions have a property called “Deal Id”. So, HockeyStack creates a shared property with the key “Deal Id” to store the latest state of this opportunity. It looks like below:

| **Key** | **Value** | **Properties** |
| --- | --- | --- |
| Deal Id | 321732 | **Deal Id:** 321732
**Deal Name:** Pied Piper - Upsell
**Deal Amount:** $10,000
**Deal Stage:** POC
**Deal_Qualified__c:** true
**Contact Id:** 2467194 |

Now, whenever you are using any action relating to this deal, HockeyStack can use the latest state of the property. This is similar to the object-based model, in the sense that you are storing a special type of object with their latest properties. But the key differences are that 1- it will always be tied to an action, and 2- HockeyStack can store infinitely many shared properties without predefining what the shared properties are and what actual properties they have.

**If you see any mention of Deal Properties, Company Properties, User Properties, etc. on the HockeyStack interface, this will refer to Shared Properties. Otherwise, if you see Action Properties, it will refer to the point-in-time properties of the interaction.**

---

Shared properties can be tied to other shared properties.

Think of a contact that you have in your marketing automation tool. This can be represented with the below shared property:

| **Key** | **Value** | **Properties** |
| --- | --- | --- |
| Contact Id | 2467194 | **Contact Id:** 2467194
**Contact Name:** John Smith
**Company Id:** 5362 |

This contact is tied to a company with the id 5362. This can also be a shared property.

| **Key** | **Value** | **Properties** |
| --- | --- | --- |
| Company Id | 5362 | **Company Id:** 5362
**Company Name:** Pied Piper, Inc. |

If a deal is tied to a contact, and a contact is tied to a company, then by proxy, that deal is tied to the company.

Similarly, if the deal is tied to a company, and the company has 20 different contacts tied to it, those 20 contacts’ actions can be analyzed in relation to the company.

That’s why HockeyStack can really work well even with messy datasets that has duplicates and/or no defined relations.

---

There is one more data structure that is useful to learn about, which is the **metadata** structure.

The metadata structure is used to connect data into HockeyStack that cannot be put onto the account or individual timeline. The biggest example of this is the spend data that HockeyStack ingests. Spend data cannot be tracked at an individual or company level — it is tracked at the campaign level. Therefore, spend data cannot be placed on the timeline, but it is still useful for reporting purposes. If a datapoint cannot be put onto the timeline, it cannot live as an “action”.

Metadata has specific matching key with actions. For example, spend data has a set of UTMs, and it connects with the set of UTMs that come in through the website script. If you have any report that is broken down by UTM Source, you are able to pull in the Spend related to that UTM Source.