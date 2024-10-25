# Report Builder

The report builder is the central piece to data visualization in HockeyStack. Each report consists of the following top-level components:

- Name
- Type
- Date range
- Filter
- Data
- User grouping
- Data grouping

# Report Types

All report types and their caveats are listed below.

- **Table**
- **Bar Chart**
- **Line Chart**
    
    Line charts do not allow data groupings. They are inherently grouped by date. The date truncation changes depending on the date range of the report. For ≤48 hours, data is reported hourly. For ≤60 days, data is reported daily. Anything beyond, data is reported monthly.
    
- **Pie Chart**
    
    Pie charts only allow a single data source.
    
- **Number**
    
    Number reports only show total aggregated data; data groupings are not allowed.
    
- **Funnel**
    
    Funnel reports allow you to bring funnels you’ve already defined into dashboards. They are different than all other types of reports.
    

# Report Data

Report pull their data based on a combination of 3 main parameters:

- The action
- The datapoint related to the action
- The aggregation method for the datapoint

These are defined, in order, in the 3 main data dropdowns.

All report types, except the pie chart, allow multiple data sources.

## The Action

The action dropdown can take the following values:

- **any action:** All actions
- **enter site:** Any session start
- **view page:** Any pageview
- **touchpoint:** Used to combine sales & marketing touchpoints. Currently denotes sessions, calls, meetings, and emails.
- **Goals:** Goals you have already defined
- **Pages:** Views to specific pages

## The Datapoint

The datapoint defines which aspect of the chosen action to analyze. It can take the following values:

- **Uniques:** Number of unique users that have taken the chosen action. The way this is calculated changes according to the user grouping you select. If you group users according to *company_domain*, for example, this will count unique s that have done the chosen action.
- **Sessions:** Number of sessions that include the chosen action
- **Pageviews:** Number of pages views that include the chosen action
- **Times done:** Number of times the chosen action was done
- **Bounces:** Number of bounced sessions that include the chosen action
- **Session duration:** The duration of sessions that include the chosen action
- **Time on page:** The duration of page views that include the chosen action
- Paid Ads
    
    The following options pertain to ads integrations. Selecting one of them will hide the action dropdown.
    
    - **Impressions**
    - **Clicks**
        
        The definition of “clicks” depends on the ad network itself, so we don’t recommend using this metric for analysis over multiple networks. 
        
    - **Ad Spend**
        
        The total spend on the campaign/creative. The output of this datapoint is formatted using the main currency of your account. You can change your main currency in the settings.
        
- Action Properties
    
    All your numerical action properties can be used in the report. Make sure you choose the action accordingly, as the property will be pulled from the chosen action. As an example, if you want to sum *deal_amount* for won deals, you should choose “Deal Moved to Closed Won” or a similar goal for the action dropdown.
    
    The output for the *revenue* property will be formatted using the main currency of your account and the currency that was passed through with the action with the *currency* property. You can change your main currency in the settings.
    

## The Aggregation

The aggregation defines how to roll up the datapoints collected from the action.

- **Total**
- **Average per hour**
- **Average per day**
- **Average per week**
- **Average per month**

The averaging aggregations calculate the total for every possible averaging range, and then average those values. For example, if you average per week over 30 days, it will calculate the value for all possible 7-day ranges (there are 24 of them in a 30-day range), and then output the average of those values.

---

Apart from these options, you can perform 2 other functions:

- **Add a ratio**
    
    Clicking the “Ratio” button opens up another set of 3 dropdowns that allow you to define the denominator of the ratio. 
    
- **Add an attribution model**
    
    In certain cases (outlined in the Attribution section below), you can click the “Attribution model” button to attribute the selected data to the selected data grouping.
    

## Attribution

HockeyStack’s attribution function depends on the following models.

- **First Touch:** All value is assigned to the first touch
- **Last Touch:** All value is assigned to the last touch
- **Linear:** The total value is divided and distributed equally among all touches
- **Uniform:** The total value is assigned to each touch
- **Position-Based:** The first and last touches get 40% of the total value each, and the remaining 20% is distributed among the remaining touches
- **Time Decay:** The time decay model is the only model where the total value attributed doesn’t add up to the total actual value. It is designed to attribute less value to a touchpoint the further away it’s from the conversion action. Specifically, the value halves every 7 days.
    
    For fellow nerds, the formula is $v \times 2^{-{i\over7}}$ (where $v$ is total value and $i$ is days from the conversion action).
    

The attribution function can be used on a data source if:

- The report grouping is one of: *Source, Page URL, UTM Source, UTM Medium, UTM Campaign, UTM Term, UTM Content, Ref, Touchpoint, Date, Action Name, Form Name, Action Element, Action Type and all other Action Properties.*
- The datapoint is not one of: *Bounces, Pageviews, Time on page, Session duration*

### Caveats

- Using attribution with a Page URL grouping will also attribute value to the page that the conversion happens on. If you don’t want this to happen, filter the last page out using group by filters (explained in the Report Grouping section below).

# Report Grouping

The report grouping breaks results down by the property or properties you select. It can take the following values:

- **Date**
- **Touchpoint**
    
    Used to combine sales & marketing touchpoints. Currently denotes sessions, calls, meetings, and emails.
    
- **Page URL**
- **Source**
    
    The referrer collected by our web tracker. **Does not** include UTMs / paid referrers. If you need to see paid and organic referrers together, group by UTM Source in addition to Source.
    
- **UTM Source**
- **UTM Medium**
- **UTM Campaign**
- **UTM Term**
- **UTM Content**
- **Ref**
    
    The ?ref parameter in the URL
    
- **Form Name**
    
    The form name that you have defined in your form builder (HubSpot, Pardot, Marketo, etc.)
    
- **Action Type**
    
    Takes the following values: *onsearch, onsubmit, onclick, start-session, enter-page, custom*.
    
- **Action Name**
    
    The name of custom actions collected using the API or integrations.
    
- **Action Element**
    
    The CSS selector collected from click and form submit actions
    
- **Device**
- **OS**
- **Browser**
- **Country**
- **Language**
- Custom User Properties
    
    All user properties that were either collected using the API or integrations are available in report groupings.
    
    The selected property might be a shared property, meaning it relates to an object that is not native to HockeyStack. An example is company_domain, because it relates to the Company object from CRM integrations. If only one user that carries a certain company_id has a company_domain defined, but there are 10 users that carry the same company_id, all users are able to inherit the same company_domain when analyzing data. If you would like this behavior in your report grouping, you need to group by the main property (which is company_id in our example) in addition to the shared property (which is company_domain in our example).
    
- Action Properties
    
    All action properties that were either collected using the API or integrations are available in report groupings.
    

## Custom groups

In some cases, you might want to combine multiple groups together when analyzing their data. An example to this would be content clusters, where you would have to group multiple page URLs together. 

You can do this by clicking the target icon next to the property you are grouping by.

![Screen Shot 2022-11-06 at 15.04.57.png](Report%20Builder%20230bbdd0e44b493d9f3ab64b619799c5/Screen_Shot_2022-11-06_at_15.04.57.png)

Then, you will be able to create custom groups using certain filters. The report will go through the groups **in order** when calculating the custom groups, so if a property matches two filters in your custom groups, it will be assigned to the first one.

![Screen Shot 2022-11-06 at 15.06.23.png](Report%20Builder%20230bbdd0e44b493d9f3ab64b619799c5/Screen_Shot_2022-11-06_at_15.06.23.png)

## Filtering groups

In some cases, you might want to filter out groups that are not relevant to the report. An example to this would be when trying to figure out blog posts’ influence on revenue, where you would want to discard non-blog pages.

You can do this by clicking the filter icon next to the property you are grouping by.

![Screen Shot 2022-11-06 at 15.10.29.png](Report%20Builder%20230bbdd0e44b493d9f3ab64b619799c5/Screen_Shot_2022-11-06_at_15.10.29.png)

The filters you define are combined together by “and”, so every new filter will narrow down the result set. Filters are applied after custom groups are applied, so if your custom group includes a specific value you want to filter out, you will need to exclude it from that group by defining another group for it that precedes and overrides the current group.

# User Grouping

When you start receiving custom user properties in your data, the user grouping dropdown will appear in the report builder. This selection tells the report what definition it should use for a user. 

For example, selecting company_id will group all users who have the same company_id together, and use that to calculate metrics. If you’re using attribution with the company_id grouping the first touch will be the entire user group’s first touch, rather than each individual user’s first touch.