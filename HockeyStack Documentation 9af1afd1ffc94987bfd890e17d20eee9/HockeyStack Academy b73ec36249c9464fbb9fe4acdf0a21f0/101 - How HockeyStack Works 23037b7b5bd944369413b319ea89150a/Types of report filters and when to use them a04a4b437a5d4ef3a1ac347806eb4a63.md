# Types of report filters and when to use them

## Global Report **Filter (Top-level Filter Section)**

**Located on the “report details panel”**

- **Very Important:** Global report filter only applies to UNIQUE USERS and COMPANIES and not specific data points
    - To filter a COMPANY or a UNIQUE USER is to filter those objects (we call them entities) by their properties and, in HockeyStack, by their actions. When you see “who have done” this is filtering a Unique User of a Company by an Action that they/it performed.
- **Function**: Global filters apply to the entire report; it is the last filter one would add to the report. These are high-level filters that restrict the data shown across all columns of the report.
- **Use Case**: You use global filters to **include or exclude specific user actions (user in HockeyStack is an umbrella term for Unique Users and Companies)**, time-periods, behaviors, filtering a set of accounts like region-specific accounts or target accounts etc at a universal level.
- **Example**: In the screenshot below, the filter is set to **Users who have done "enter site" Last Month**, meaning that the entire report will only show data related to users who have performed the action "enter site" on last month. **Reminder**: “Users” is an umbrella term that can mean either Unique Users or Companies. One would choose either option based on the properties the goal is built from - this is specifc to using “who have done”.
Otherwise you’d select User properties or Companies properties to specify the type of user

![Screenshot 2024-09-07 at 12.59.27 AM.png](Types%20of%20report%20filters%20and%20when%20to%20use%20them%20a04a4b437a5d4ef3a1ac347806eb4a63/Screenshot_2024-09-07_at_12.59.27_AM.png)

![Screenshot 2024-09-12 at 3.49.48 PM.png](Types%20of%20report%20filters%20and%20when%20to%20use%20them%20a04a4b437a5d4ef3a1ac347806eb4a63/Screenshot_2024-09-12_at_3.49.48_PM.png)

## **Column-level Filters (In Columns Section)**

- **Function**:  The Column-level filters are used to filter data points. What is a data point you ask? A data point is an Action often represented by a goal (but not always). An example of a data points is an MQL. An MQL is a goal that represents the action of “becoming an MQL”. Another example is a Website Session or Amount of Ad Spend. These are not goals in your library but are still Actions in the HockeyStack System.
- **Use Case**:
    - Main use case: filtering datapoints
    - Secondary Use Case: filter on a particular metric or segment within a column while allowing other columns to remain unfiltered or differently filtered. Unlike the “top level filter” the column-level filter can be used to filter anything, deal, users, companies, sessions etc
- **Example**: Suppose in one column you’re counting the MQA, you could add a filter to that specific column to just include users who had not submitted any form. A subsequent column might include all MQAs, those who had submitted forms, and those who had not.
    
    ![Screenshot 2024-09-12 at 4.04.36 PM.png](Types%20of%20report%20filters%20and%20when%20to%20use%20them%20a04a4b437a5d4ef3a1ac347806eb4a63/Screenshot_2024-09-12_at_4.04.36_PM.png)
    

![image.png](Types%20of%20report%20filters%20and%20when%20to%20use%20them%20a04a4b437a5d4ef3a1ac347806eb4a63/image.png)

## **Breakdown Filters**

- The Breakdwon filter filters the touchpoints represented by various defined properties. During set up, you organized your touchpoints into defined properties for 2 reasons:
    1. to group them by category according to the touchpoint hierarchy for easy reporting 
    2. to attach an action to the object-based model data, thus converting it to an action-based data model so it can be used in attribution
    
    *Best practice is to set up your defined properties in a way to be easily filterable by adding prefix to group types of data. Ex: all paid mapping start with “Paid-[channel]”*
    
- **Use Case**: This is useful for drilling down into details and segmenting the data into more meaningful insights by UTM source, action types, and integration data.
- **Example**: You could break down the report by **Unified Channel**, which would give you data segmented by the channels you’ve defined in your channel property.

![Monosnap HockeyStack 2024-09-10 03-00-45.png](Types%20of%20report%20filters%20and%20when%20to%20use%20them%20a04a4b437a5d4ef3a1ac347806eb4a63/Monosnap_HockeyStack_2024-09-10_03-00-45.png)

### Summary of Differences:

- **Global Filters**: Apply to the entire report and filter all the data based on the criteria set (e.g., time period, specific actions). This can only be used to filter Actions from Unique Users or Companies.
- **Column-Specific Filters**: Only apply to the data in the selected column, allowing for granular filtering of specific metrics or actions within that column. This can be used to filter all types of actions not just users and companies.
- **Breakdown Filters**: Group and segment the data into categories based on attributes such as source, UTM medium, or action type.

# Dashboard Filter:

**Dashboard filters** act as **global filters** that apply to every report on the dashboard. These filters are placed at the top of the dashboard and allow you to filter all the data shown across multiple reports at once, providing a broader view. You can use these filters to explore different timeframes, [segments](https://docs.hockeystack.com/segments), or user behaviors across various reports simultaneously.

### Example of Dashboard Filter:

Let’s say you have multiple reports tracking different user actions, such as page views, conversions, and form submissions. You can apply a dashboard filter to show only data from users who came through a specific UTM source (e.g., Facebook). This would narrow down the data across **all reports on the dashboard** to focus solely on users from Facebook, without the need to filter each individual report separately.

![Screenshot 2024-09-10 at 2.52.11 AM.png](Types%20of%20report%20filters%20and%20when%20to%20use%20them%20a04a4b437a5d4ef3a1ac347806eb4a63/Screenshot_2024-09-10_at_2.52.11_AM.png)

Another common use of dashboard filters is applying a **date range**. For instance, if you want to see the performance data for just this week, you can apply a dashboard filter with a date range of "This Week." This filter would then affect all reports and give you a unified view for the selected timeframe.

![Monosnap Customers - HockeyStack 2024-09-10 02-52-50.png](Types%20of%20report%20filters%20and%20when%20to%20use%20them%20a04a4b437a5d4ef3a1ac347806eb4a63/Monosnap_Customers_-_HockeyStack_2024-09-10_02-52-50.png)

This functionality is particularly useful for keeping a high-level perspective when managing large amounts of data across multiple reports.

# Filtering within Goals:

In HockeyStack, **filtering within goals** is a powerful way to refine and define specific actions that you consider essential for your KPIs or other metrics. A goal is essentially a named action that matches a particular set of conditions or properties. You can filter goals by different attributes depending on the type of goal you're creating.

### Types of Goals:

1. **View Goals**: Used to track pageviews based on the URL, source (e.g., UTM parameters), or referrer. For example, you can create a goal to track all pageviews that came from a specific referrer like “Google” or a UTM campaign.
2. **Click Goals**: Click goals track specific user interactions such as clicks on particular elements (e.g., buttons or links). You can filter these by the text of the element clicked, the URL it leads to, or the CSS selector of the clicked element. For instance, you can set a goal for tracking clicks on a CTA button with a specific label.
3. **Form Submission Goals**: These track form submissions. Filters can be applied based on the page where the form is submitted or its CSS selector. For example, if you want to track all form submissions on a specific landing page, you can apply a filter for that page.
4. **Custom Goals**: Custom goals are more advanced and can track any action outside standard website actions (e.g., data from a CRM system). You can filter these using action properties like `deal_amount` for Salesforce deals. For instance, you could create a custom goal that tracks all deals where the `deal_amount` is greater than $100,000.

### Example:

Let’s say you want to define a goal for tracking users who open newsletters. You might set filters such as:

- **Action Name** = “Email Opened”
- **Email Subject** contains “Newsletter”
- **Integration** = “HubSpot”

![Screenshot 2024-09-10 at 2.49.11 AM.png](Types%20of%20report%20filters%20and%20when%20to%20use%20them%20a04a4b437a5d4ef3a1ac347806eb4a63/Screenshot_2024-09-10_at_2.49.11_AM.png)

With these filters, only users who opened an email with “Newsletter” in the subject, sent via HubSpot, would be counted toward this goal.

Filters in goals allow you to precisely define what data gets tracked under a specific goal, helping you to focus on the most relevant actions for your KPIs.

For more details on Goals, check this: [https://docs.hockeystack.com/hockeystack-academy/101-how-hockeystack-works/goals](https://docs.hockeystack.com/hockeystack-academy/101-how-hockeystack-works/goals#block-493a34a1a7b04a29bd343c0c8bfaa278)