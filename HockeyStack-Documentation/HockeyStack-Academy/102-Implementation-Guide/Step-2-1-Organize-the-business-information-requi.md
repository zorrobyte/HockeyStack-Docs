# Step 2.1 - Organize the business information required to create dashboards

The first step to setting up your HockeyStack dashboards is translating your business language into HockeyStack. Before doing this translation in the HockeyStack interface, most users find it helpful to create a document outlining the below information. 

Please make a copy of the template below. When the document is completed, send it over to your HockeyStack CSM for them to keep it in records and refer to it as they guide you.

<aside>
💡 You can copy our spreadsheet template to use in this step: [Business Information for HockeyStack](https://docs.google.com/spreadsheets/d/1xTzSJtcIeYzmiJzh0ROIuIlg1I7ZOKwQbB2G_WPMfi0/edit?usp=sharing)

</aside>

- **A map of the key stakeholders involved in the project**
    1. Select one or multiple HockeyStack Admins. The HockeyStack Admin is responsible for
        1. being hands-on trained by the CSM team during the initial onboarding
        2. setting up the data dictionary (channel and kpi definitions)
        3. completing the initial dashboard setup
        4. co-ordinating with the company leadership and marketing subteams to create specific dashboards for specific purposes, and guiding each stakeholder to adopt the product
    2. A list of marketing subteams and their leaders
        1. (Optional, but recommended) If you have capacity, select one person from each marketing subteam to build out that team’s initial dashboards. This doesn’t have to be decided ahead of time — it can be decided while onboarding each subteam. 
        
        A lot of companies also prefer to have the HockeyStack Admin manage building all dashboards. However, we found that the most successful HockeyStack users are organizations where each subteam has enough knowhow within the team to build reports and get insights for themselves without relying on the HockeyStack Admin.
- **A table of the KPIs you will be tracking in the initial dashboards**
    
    
    | **KPI Name** | **CRM Object** | **CRM Date Field** | **CRM Filters** | **Count for Last Month** |
    | --- | --- | --- | --- | --- |
    | Example: MQL | Lead AND Contact   | MQL_Date__c | LeadSource is any of “Marketing”,”Paid”,”Events” | 2378 (deduplicated between Lead and Contacts) |
    | Example: Inbound Opportunity | Opportunity | Opportunity_Stage_2_Date__c | (Opportunity_Source__c = “Inbound” OR Primary_Campaign_Source = “Partner”) AND Type = “New Business” | - 178 opportunities
    
    - $18M pipeline value as measured by the SaaS_ARR_Amount__c field |
    
    <aside>
    ❗ HockeyStack’s Goal builder is looking at KPIs to see if records have *ever* been in a stage, and not only the current objects within a stage.
    
    </aside>
    
    Refer to the guide below to see how this will be used later on:
    
    [Step 2.2 - Create your KPI goals](Step-2-2-Create-your-KPI-goals.md)
    
    ### Common mistakes when creating this table
    
    - For opportunity related KPIs, do not use a proxy field, like an Opportunity_Date__c on the Lead object
        - If you do this, you won’t be able to see Opportunity amounts on your dashboard. We **strongly, strongly** recommend using the standard Deal or Opportunity object for opportunity related KPIs.
    - Not having date fields. Date fields can either be:
        - A custom date field on a specific object
        - The Create Date of the object
        - The change date of a field, where the field has history tracking turned on
    - Having too many filters.
        - A lot of companies blindly set filters on their CRM reports in favor of getting a slightly more accurate number. Doing this on HockeyStack might cause unforeseen problems in your numbers — we recommend using the simplest form of filtering possible.
            - For example, a lot of companies set filters on their opportunities that are based on the rep that owns the opportunity. The list of reps might change very frequently, so this is not recommended.
    - Not being specific enough
        - If you don’t know a field’s API name, or what filters are required, or the specific ARR field that you are using, or what specific KPIs the marketing team measures, you need to learn these in this step.
- **A table of your Channel definitions**
    
    For context, we see marketing touchpoints in 4 categories: **Channels** that use **Campaigns** to drive prospects to a group of **Assets** in order to get a **Conversion Action.**
    
    For the initial setup, we recommend starting by running attribution on **Channels**.
    
    What may be a channel: Paid Search, Paid Social, Direct, Email Marketing, Events, Organic Search
    
    What is not really a channel: Website, Chatbot, Content, Contact Us — These are closer to Assets or Conversion Actions than Channels.
    
    | **Channel Name** | **Tracking details** |
    | --- | --- |
    | Paid Search — Google Ads | Website visit where utm_source = adwords OR utm_medium = google_paid |
    | Email Marketing | Email Opened from Marketo OR Email Clicked from Marketo OR Website visit where utm_medium **contains** email |
    | Events | Salesforce CampaignMember where status is one of Attended, Responded, Scanned, Booth AND (Campaign Type **contains** Event OR Campaign Name **contains** EVT-) |
    | Other Referral Traffic | Run through all the other rules, and if it doesn’t match any and Source is not direct and Source is not empty, count that as Referral traffic. |
    
    Refer to the guide below to see how this will be used later on, and a suggested list of channels:
    
    [Building the Unified Channel property](https://www.notion.so/Building-the-Unified-Channel-property-f1f5e6cdda7f47e0a17cd0854b451af5?pvs=21)
    
    ### Common mistakes when creating this table
    
    - Not knowing your UTM notation, or trusting the internal documentation about what UTMs you are using. Always check the actual website data flowing into HockeyStack using the guide below. The actual data is almost always different than what teams know to be their UTM notation.
        
        [Finding UTM and Source patterns in the website data](Step-2-1-Organize-the-business-information-requi/Finding-UTM-and-Source-patterns-in-the-website-dat.md)
        
    
    ### Things to consider
    
    - The touchpoints you include here will affect your attribution numbers. For example, if you decide to include Marketing Emails being Sent in your Channel definition, marketing emails might get too much credit due to the high volume nature of this activity. Similarly, if you decide to include LinkedIn Impressions in your Channel definition, LinkedIn might get too much credit. Some companies may also decide to remove Direct traffic from their attribution.
        
        Read more about attribution models below:
        
        [Attribution Models](../101-How-HockeyStack-Works/Attribution-Models.md)
        
- **(If you are doing ABM) The fields & filters that denote your target accounts**
    
    
    | **CRM Object** | **CRM Target Account Field Name and Value** | **Relevant Target Account Segment** |
    | --- | --- | --- |
    | Account | Is_Tam_100__c = TRUE | TAM 100 |
    | CampaignMember | [Campaign.Name](http://Campaign.Name) = “TAM 100” | TAM 100 |
    | Account | ICP_Tier = “Tier 1” | Tier 1 ICPs |
    
    You should usually either:
    
    - use fields from the opportunity or deal objects
    - or use a Salesforce campaign subscription / Marketo program enrollment to denote target accounts