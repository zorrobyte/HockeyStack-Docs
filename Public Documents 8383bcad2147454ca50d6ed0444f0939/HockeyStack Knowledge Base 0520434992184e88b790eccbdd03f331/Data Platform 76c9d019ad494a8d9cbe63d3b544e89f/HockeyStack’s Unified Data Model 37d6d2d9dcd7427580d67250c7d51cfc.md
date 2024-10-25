# HockeyStack’s Unified Data Model

The HockeyStack data model was built to store any type of data that can be used by a revenue-facing department in a single unified data format.

Most revenue tooling feature a data model that is based on objects. Take Salesforce as the example: all contacts are stored in the format of the Contact object, and all opportunities are stored in the format of the Opportunity object. This works well when you are working with simple data elements like contacts and opportunities, but it starts to break down when you want to measure complex behavioral data, such as marketing touchpoints or ad spend. To be able to combine data from many sources with vastly different data formats, you need a different model.

## **Actions**

The HockeyStack data model is event-based. Every single interaction and state change is encoded as individual time-stamped events that we call **actions.** All actions are tied to a single **identity**, which denotes the entity (person or a company) that executed the action or was affected by the action.

Actions can have a set of **action properties** that specify their qualities. Most other revenue tooling require you to keep a specific set of properties for each object. In the Salesforce example, each object has a list of fields they can take, and to add a new field you have to first configure it. In HockeyStack, action properties are completely flexible, with no pre-configuration required. The only thing that defines whether an action property exists or not, is whether or not some datapoint was collected at some point that contains that action property. That means, whenever you add a new field in one of your integrated platforms, HockeyStack is able to automatically pull it without you having to configure anything.

## **Shared Properties**

Even though they are very rigid and low-resolution when used on their own, objects are a great way of modeling complex entities that can be updated over time. For example, an Opportunity is a complex entity that might have a stage and an amount that can be updated over time. If we were to only record an opportunity with actions, each action would hold a different stage and amount for the opportunity. To store the latest state of the opportunity, we still need an object. However, if we define specific objects with specific fields, we lose the flexibility required to integrate different data sources together. To model complex entities, HockeyStack uses **shared properties.**

Shared properties model the latest state of an "object", where the existence of the object is defined by a certain property. Similar to how you don't have to pre-configure action properties, you also don't have to configure shared properties, because their existence is defined by whether or not a datapoint about that shared property has ever been collected.

Shared properties consist of:

- **key:** A matching key
- **value:** The value to the matching key
- **properties:** The properties associated with that specific value of the matching key

### Users

For example, let's think of Users as shared properties. (The HockeyStack terminology for any entity representing an individual, whether it be leads, contacts, website visitors, etc. is a "user"). In this case, the matching key is the identity tied to the action. Let's say we have some properties attached to jim@dundermifflin.com, like their location, job title, and their company. A representation of their user shared property would look like below:

| Key | identity |
| --- | --- |
| Value | jim@dundermifflin.com |
| Properties | country: UK
job_title: Sales Director
company_name: Dunder Mifflin
company_id: 001XUS647HN |

Now, in HockeyStack, under User Properties, wherever you see Job Title, it will equal to Sales Director for Jim. And whenever a data source updates this shared property, the reports will also update to reflect a new job title.

### Companies

We can also think of Companies as shared properties. The matching key for companies is "company_id" that exists in another shared property: user properties. The reason for that is that a user's company may be updated over time.

| Key | company_id |
| --- | --- |
| Value | 001XUS647HN |
| Properties | region: EMEA
segment: Enterprise
industry: Paper |

Now, in HockeyStack, under Company Properties, wherever you see Region, it will equal to EMEA for Jim.

### Deals

We can also think of Deals as shared properties. The matching key here is deal_id, which exists in action properties.

| Key | deal_id |
| --- | --- |
| Value | 005JSG6328B |
| Properties | amount: $10,000
stage: Discovery |

Now, in HockeyStack, under Deal Properties, wherever you see Amount, it will equal to $10,000 for this specific deal.

### Identities

In the beginning of the article, we mentioned that each action is tied to an identity. It might not be immediately obvious, but Identities also represent complex entities that can be updated over time. Think of a website visitor who fills out a form using the email jim@gmail.com. The identity associated with all of their website visits will be jim@gmail.com. If Jim starts working at Dunder Mifflin and fills out a form using their Dunder Mifflin email, the identity associated with Jim's website visits from that point onward will be tied to jim@dundermifflin.com. But we still need a way to associate the actions on jim@gmail.com to the actions on jim@dundermifflin.com. So, identity is also a shared property. In this case, the identity jim@gmail.com is matched to the shared identity jim@dundermifflin.com.

---

On the HockeyStack UI, you might some properties that exist on both action properties and shared properties. While action properties represent the state of an entity at the time of that action being performed, shared properties represent the latest state of the entity. In HockeyStack, if you see a property under Company Properties, User Properties, or Deal Properties, this refers to a shared property, which is the latest state of the company, user, or deal. But if you see it under Action Properties, it refers to the property's value at the time of that action being performed.

## **Metadata**

All data that exists in the relationship between a person and the company can be modeled as actions. However, there are some data types that exist without a person-company relationship. We call these **metadata.**

The most common metadata used in HockeyStack is paid advertising data. Ad spend, clicks, and impressions are not tied to a specific person. So we cannot represent them as actions. But we can match them to certain reports. An action has a utm_campaign, and that utm_campaign is tied to a certain amount of spend, clicks, and impressions on a certain date. So if you build a report in HockeyStack that references utm_campaign, and queries for ad spend, HockeyStack will automatically match that to the metadata recorded. 

Note that metadata is not tied to any specific action like shared properties are, but they can be called into reports based on a common property they have with actions. (In this case, the common property is UTMs)