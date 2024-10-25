# Trend of Engagement Score (weighted Touchpoints)

This is a guide to creating two different reports that are used by marketing to develop a top notch ABM strategy. 

The first report helps Marketing understand an account engagement score over time, which illustrates the progress of many of their ABM activities. 

The second report helps Marketing support Sales in their outreach and conversation with target account accounts. 

ABM is a team sport - let the games begin 👏 👏

Report Number 1

1. PRE WORK - gather your intent signals
    1. Open up a google doc - Write list of intent signals ex:
        1. BOFU page visit like pricing, demo page, etc.
        2. Product page visits
        3. Content visits
        4. Interactions with marketing emails
        5. Interactions with other campaigns
        6. Responding to a sales email
        7. etc etc
2. Create a defined property from the intent signals and add custom weighting that reflects the intent level of each signal.
    1. Make sure to add Action Type correctly. It has to be enter-page for pageviews, add property = CreatedDate for salesforce campaigns
    2. Watch this Video: [https://www.loom.com/share/6171cfa33ff14baeb95d90ca6d100a3b?sid=8e44caf9-ff71-4d4e-8f2a-e05d0c0ff110](https://www.loom.com/share/6171cfa33ff14baeb95d90ca6d100a3b?sid=8e44caf9-ff71-4d4e-8f2a-e05d0c0ff110)
3. Create goals from all mappings under the defined property using the "defined property mapping" goal type.
    1. Build a goal from a defined property mapping 
    
    ![Untitled](Trend%20of%20Engagement%20Score%20(weighted%20Touchpoints)%20672a6c73d3a54db5925b2c4a01731ea4/Untitled.png)
    
4. Create the report in Hockeytack to get Account engagement data. 
    1.  broken down by company name. The columns are our intent signals (which you’ve turned into goals from the defined property mapping. The metric to analyze is “times done”.
    2. Export this report to a CSV
5. Map the data into a trend line report in Excel

Report Number 2

1. Create a new defined property that is Intent Signals — Details:
    1. This is a duplicate of intent signals. The mapped value is changed from value to property. 
        1. Pageviews map to Page URL. 
        2. Campaigns map to campaign name. 
        3. Sales emails map to email subject. 
        4. etc.
    2. Whatch this Video: [https://www.loom.com/share/81a994597c6542cbb495c2d9fcfb1c82?sid=369bb491-f2da-4eb3-9cc8-00398a38e805](https://www.loom.com/share/81a994597c6542cbb495c2d9fcfb1c82?sid=369bb491-f2da-4eb3-9cc8-00398a38e805)
2. Create the second report:
    1. Create a table 
        1. Breakdowns are Date, Identity, Company name, Intent Signals, Intent Signals -- Details
        2. The Column is “Any Action”.  The metric to analyze is “Times Done”
        3. The report Time Range is “the last 7 days”. 
        4. Before saving this report, sort your table by date descending.

The first report will be exported and reviewed by marketing weekly to develop a line chart of engagement score per company based on a scoring schema that they define.

 The second report will be reviewed by marketing weekly to develop talking points for each account every week to send to Sales.