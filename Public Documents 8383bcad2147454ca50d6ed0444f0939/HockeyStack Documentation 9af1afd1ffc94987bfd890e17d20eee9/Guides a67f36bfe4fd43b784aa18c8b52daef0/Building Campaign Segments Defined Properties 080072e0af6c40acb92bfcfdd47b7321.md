# Building Campaign Segments Defined Properties

We recommend a few campaign groupings to get a deeper level of analysis of marketing performance.  Grouping Campaigns based on:

- Tactics (competitor, brand, customer)
- Regions
- Funnel positions (TOFU, MOFU, BOFU)

 allows the analyst to uncover actionable insights to deploy in the field. 

In this example, we’ll focus on Paid Campaigns. This same methodology can be used across all marketing channels that use campaigns (i.e. Events, Emails).

Important Best Practices - Pre Reqs

1. Map campaign name into UTM Campaign 
2. Build a Unified Campaigns Property: [https://hockeystack.notion.site/How-to-Build-a-Unified-Campaign-Property-b95595d1aae34d29ad34e69663ee442f](How%20to%20Build%20a%20Unified%20Campaign%20Property%20b95595d1aae34d29ad34e69663ee442f.md)

Let’s use Region Grouping for our example → How To Video: [https://www.loom.com/share/fc40927e9e3f419abb6ac60cefeab7f4?sid=f7fce67d-8f20-42e1-bd36-06324f6c1d01](https://www.loom.com/share/fc40927e9e3f419abb6ac60cefeab7f4?sid=f7fce67d-8f20-42e1-bd36-06324f6c1d01)

1. Duplicate your Unified Campaigns Property 
2. Delete all mappings that do not relate to Paid Campaigns
3. Add an additional piece of logic to each mapping which specifies ‘“campaign” contains [REGION]’ 
    
    ![Screenshot 2024-07-22 at 1.54.49 PM.png](Building%20Campaign%20Segments%20Defined%20Properties%20080072e0af6c40acb92bfcfdd47b7321/Screenshot_2024-07-22_at_1.54.49_PM.png)
    
    1. The “Campaign” Value will match whatever your Unified Campaign Mapped Value is for example:
        1. LinkedIn ads with website sessions get mapped to Ad Group
        2. Google Ads, Facebook Ads, and other ads channels get mapped to Campaign or UTM Campaign
        3. LinkedIn ads impressions and engagements,(data from the Ad Integration directly) get mapped to linkedin_campaign_name
        4. Salesforce campaigns get mapped to campaign_name
        5. Marketo data gets mapped to marketo_program_name
        6. Hubspot email campaigns get mapped to email_campaign_name
        7.  Any other website session gets mapped to UTM Campaign.
4. Change the Mapping Type from “Property” to “Value” 
    1. Update the Mapped Value to reflect the logic in the mapping above. 
        1. You can group all types of paid campaigns into one or break out different types of channels for further filtering. You could even go as far as to include the channel name for example:
            1. Paid Social - LinkedIn - EMEA
            2.  Paid Social - Facebook - EMEA
            3. Paid Search - Google - EMEA
            4. Paid Search - Bing - EMEA
        
        ![Screenshot 2024-07-22 at 1.55.50 PM.png](Building%20Campaign%20Segments%20Defined%20Properties%20080072e0af6c40acb92bfcfdd47b7321/Screenshot_2024-07-22_at_1.55.50_PM.png)
        
5. Duplicate the mapping you created and swap out the region specification in the campaign logic and mapped value for the next region you want to track.
6. Repeat step 5 for until all regions have been mapped. 

This same logic can be applied to different segments like funnel positions or tactics.