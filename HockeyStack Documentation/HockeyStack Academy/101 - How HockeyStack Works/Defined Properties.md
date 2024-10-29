# Defined Properties

We discussed that each action and entity in HockeyStack can have properties. If goals are nicknames for a group of actions, defined properties are nicknames for a group of properties.

Let’s go back to our Actions table.

| Timestamp | Entity | Action Name | Source | UTM Source | UTM Medium |
| --- | --- | --- | --- | --- | --- |
| … | bugra@hockeystack.com | start-session | linkedin | linkedin | paid_social |
| … | michael@dundermifflin.com | start-session | linkedin | linkedin | organic_social |
| … | richard@piedpiper.com | start-session | facebook | facebook | paid_social |
| … | gilfoyle@piedpiper.com | start-session | facebook.com |  |  |

This table depicts a list of website sessions from various sources. The properties Source, UTM Source, and UTM Medium have meanings on their own. But they have a much larger meaning when looked at together. For example, a UTM Source = linkedin and UTM Medium = paid_social might mean LinkedIn Ads, and a UTM_Source = empty and Source = [facebook.com](http://facebook.com) might mean Facebook Organic.

Let’s say we want to add another column to our table to depict this meaning, which will be called “Channel” Our ruleset will be:

- If UTM Source contains “linkedin” and UTM Medium contains “paid” → LinkedIn Ads
- If UTM Source contains “linkedin” and UTM Medium contains “organic” → LinkedIn Organic
- If UTM Source is empty and Source contains “facebook”, or if UTM Source contains “facebook” and UTM Medium contains “organic” → Facebook Organic

| Timestamp | Entity | Action Name | Source | UTM Source | UTM Medium | **Channel** |
| --- | --- | --- | --- | --- | --- | --- |
| … | bugra@hockeystack.com | start-session | linkedin | linkedin | paid_social | **LinkedIn Ads** |
| … | michael@dundermifflin.com | start-session | linkedin | linkedin | organic_social | **LinkedIn Organic** |
| … | richard@piedpiper.com | start-session | facebook | facebook | organic_social | **Facebook Organic** |
| … | gilfoyle@piedpiper.com | start-session | facebook.com |  |  | **Facebook Organic** |

This Channel property doesn’t actually exist in our dataset, but it can be inferred from the list of other properties that our actions have. This is called a “Defined Property”. You can apply the same thing on any Shared Property as well.

For example, a common Defined Company Property to define is “Region”. If your CRM only stores countries, you can create a Defined Company Property that groups relevant countries into regions.

For a ruleset like Country = “Canada” or Country = “United States” → NAM, you can imagine the below Company Properties:

| Key | Value | Country | **Region** |
| --- | --- | --- | --- |
| company_id | 12387 | Canada | **NAM** |
| company_id | 12354629 | United States | **NAM** |

---

In HockeyStack, navigate to [Definitions > Properties](https://hockeystack.com/dashboard/properties/?utm_source=hockeystack_academy).

This page is your property dictionary.

You can click on the + icon on the top right corner to create a new defined property.

[https://app.arcade.software/share/F7tElYD1xnmBiZLY2dqy](https://app.arcade.software/share/F7tElYD1xnmBiZLY2dqy)

Each mapping in a defined property will have:

- A ruleset
- And a value that the ruleset maps to

The ruleset can be constructed using and/or logic using any property in the HockeyStack dataset.

The mapped value can either be:

- A static value
    - For example: I want to map Canada and United States to “NAM”

[https://app.arcade.software/share/PEeEL0osacdQIt083usK](https://app.arcade.software/share/PEeEL0osacdQIt083usK)

- A dynamic value
    - For example: I want to create a property called Resources that stores all my resource interactions. This property will show 1- the URL of the page if the action is a pageview on a resource page, 2- the name of the email, if the action is an email open on an email with a specific subject schema, 3- blank if it’s neither.

[https://app.arcade.software/share/M5azNJoGIqkMiZxGmEkd](https://app.arcade.software/share/M5azNJoGIqkMiZxGmEkd)

High level filters like Action Name, Action Type, or Touchpoint Type are often overlooked by beginners to HockeyStack. In the above case, we wanted to add a specific filter to only include pageview actions, because clicks and form fills might also have a page url. The significance of this becomes clearer when you are doing attribution, where the number of touchpoints is really important.

[Touchpoint Type property](Defined%20Properties%205bd1d138080f4c8b86e992eb7f8e29eb/Touchpoint%20Type%20property%2091273f82ee824a32af505bc0c6a4740f.md)