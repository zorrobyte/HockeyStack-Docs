# Goals

HockeyStack ingests data from many different sources, and transforms it into the unified data model we discussed in the previous guide. As a result, there will be thousands of variations of actions. To be able to make these actions usable, and to create some order out of chaos, HockeyStack allows you to define the most important ones as **Goals.**

**Goals** are nicknames you give to actions based on a specific ruleset. This can be used to define anything from KPIs like MQL, SQL, Opportunity Creation, to marketing & sales touchpoints like emails opened, calls made, ad clicks.

Let’s say you want to define Newsletter Opens as a Goal.

A Newsletter Open would refer to Emails Opened with a subject line containing “Newsletter: ”, and that were sent using HubSpot.

In HockeyStack terms, we want to find all actions where:

- Action Name = “Email Opened”
- The property “Email Subject” contains “Newsletter: ”
- The property “Integration” is “HubSpot”

You can think of this as a 5th column in our actions table.

| Timestamp | Entity | Action Name | Action Properties | Is this a “Newsletter Open”? |
| --- | --- | --- | --- | --- |
| … | bugra@hockeystack.com | Email Opened | **Email Subject:** “Newsletter: 2024 SaaS trends“ | Yes |
| … | michael@dundermifflin.com | Email Opened | **Email Subject:** “Thank you for signing up!“ | No |
| … | richard@piedpiper.com | Email Sent | **Email Subject:** “Newsletter: 2024 SaaS trends“ | No |

If I were to create a report that counts Newsletter Opens, the only action that would be taken into account would be the action done by bugra@hockeystack.com, since that is the one matching all criteria.

---

In HockeyStack, navigate to [Definitions > Goals](https://hockeystack.com/dashboard/actions/?utm_source=hockeystack_academy).

This page is your main data dictionary.

You can click on the + icon on the top right corner to create a new goal.

[https://app.arcade.software/flows/pjUPPDu776SQUEfSxrjV/view](https://app.arcade.software/flows/pjUPPDu776SQUEfSxrjV/view)

# The Goal Definition

To start defining a goal, click on the first dropdown and choose a **goal type.** There are 4 types you can choose from:

- **View:** Pageviews
- **Click:** Clicks on the website
- **Form Submit:** Form submissions on the website
- **Custom Goals:** Any goal that is not coming from the website tracking script

## View

Pageview goals track all pageviews *(regardless of whether the pageview was the session starting / landing page or not)* that are matching a specific URL schema. This can be an exact match, a contains / not contains match, or a regex match. For more technical context, this will be all actions with `action_type = enter-page` , filtered using `page_url` .

You can also filter a pageview using the source of the session that the it happened in, using the auto-captured referrer, or the UTM parameters.

**Referrer:** The referring website automatically detected from the page visits. This will be “direct” if it’s a direct visit, and empty if the URL had UTMs. Otherwise it will show the domain of the referring website, including the TLD (.com, .tr, .ai, etc.)

**UTM Parameters:** The company-defined UTM parameters pulled directly from the page visit URL.

[https://app.arcade.software/share/LWhuOCgKTUqOnOTMQPzb](https://app.arcade.software/share/LWhuOCgKTUqOnOTMQPzb)

## Click

Most other analytics tools ask you to “tag” clicks before you are able to track them. Then, the tracking begins from the moment you tag them. 

HockeyStack tracks all clicks on your website by default. So, you can create a click goal whenever you want, and you will still have the full history of clicks on it.

Click goals can be defined using the clicked element’s text, its [CSS selector](../../Goals/Finding-Out-a-Button's-CSS-Selector.md), or the URL the clicked link leads to. You can filter a click goal using the page where it happened.

[https://app.arcade.software/share/T99owoMCQxfdfzJ0QDQN](https://app.arcade.software/share/T99owoMCQxfdfzJ0QDQN)

## Form Submit

Similar to clicks, HockeyStack also tracks all form submissions on your website. Form submission goals can only be defined using the [CSS selector](../../Goals/Finding-Out-a-Button's-CSS-Selector.md) of the form element. Similar to click goals, form submission goals can be filtered using the page where it happened.

So, here’s a pro tip: Every CSS selector for a form element contains the word “form”. Therefore, a quick “Form submission contains form” goal would select all form submissions in your entire website. A “Form submission contains form, in page /xyz“ goal would select all form submission in a given page. 

[https://app.arcade.software/share/25B10p0zNiEog3MMY2lL](https://app.arcade.software/share/25B10p0zNiEog3MMY2lL)

## Custom Goal

“Custom Goal” means any action that is not a default website action. For more technical context, these actions have an `action_type = custom` .

Custom goals can be filtered using any of their **action properties.** Huge emphasis on this, because this is often confused with filtering via shared properties. Here’s an example to the difference:

You create an opportunity with Amount = 0 in Salesforce. HockeyStack receives a custom goal with the name Deal Created, with an action property `deal_amount = 0` . You update the opportunity amount to $100k. HockeyStack receives a Deal Updated action with an action property `deal_amount = 100000` .

In this case, if you were to define an goal that denotes all Deal Created actions with deal_amount ≥ 100k, the opportunity above would not be included because at the time of Opportunity creation, this opportunity had a deal amount of 0. The updated Amount is stored in Shared Properties, which currently can only be filtered inside a report. For more information about Shared Properties vs Action Properties, refer back to the [data model article](The-HockeyStack-data-model.md).

# The Marketer’s Guide to AND / OR

AND / OR logic can be quite unfamiliar for most marketers, but it’s crucial to be able to create the correct filters in HockeyStack. Read more below.

[The Marketer’s Guide to AND / OR](Goals/The-Marketers-Guide-to-AND-OR.md)

In goals, the top-level logical operator is always OR. All page, source, property etc. filters added to blocks are AND blocks.

# The Marketer’s Guide to Using Regex

Regex is an immensely powerful tool to search in text, and can be used to create goals and filters quickly without adding too many and/or blocks. Read more below.

[The Marketer’s Guide to Using Regex](Goals/The-Marketers-Guide-to-Using-Regex.md)

# Track Date Properties

Sometimes, actions that you want in HockeyStack are not really stored as actions in your systems. The most common example date fields in CRM and Marketing Automation systems. Read more below.

[Track Date Properties](Goals/Track-Date-Properties.md)

# Examples of Goals

[Any Form Submission](Goals/Any-Form-Submission.md)

[Step 2.2 - Create your KPI goals](../102-Implementation-Guide/Step-2-2-Create-your-KPI-goals.md)