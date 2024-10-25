# Step 2.2 - Create your KPI goals

<aside>
❗ Read the below guide on goals before proceeding:

[Goals](../101%20-%20How%20HockeyStack%20Works%2023037b7b5bd944369413b319ea89150a/Goals%2004b8e7d5b7f1472aa6d10767214c88c7.md)

</aside>

Before this step, you organized all information needed for your KPI goals like below:

| **KPI Name** | **CRM Object** | **CRM Date Field** | **CRM Filters** | **Count for Last Month** |
| --- | --- | --- | --- | --- |
| Lead | Lead | CreateDate |  | 10234 |
| MQL | Lead AND Contact   | MQL_Date__c | LeadSource is any of “Marketing”,”Paid”,”Events” | 2378 (deduplicated between Lead and Contacts) |
| SQL | CampaignMember | CreateDate | Campaign Name contains “Handraisers”, Responded = True | 810 |
| Closed Won | Opportunity | CloseDate | Lead_Source_Detail__c = “Inbound” AND Type = “New Business” | - 178 opportunities

- $18M pipeline value as measured by the SaaS_ARR_Amount__c field |

<aside>
❗ HockeyStack’s Goal builder is looking at KPIs to see if records have *ever* been in a stage, and not only the current objects within a stage.

</aside>

Now, we will translate each KPI into a Goal in HockeyStack. We will use the above table as an example. 

---

If your KPI definition contains date field that is:

- Create date of an object
- The date of a deal stage change, tracked in deal histories
- The date of a lead status change in Salesforce, or a lifecycle stage change in HubSpot
- The Opportunity CloseDate from Salesforce, which is converted into “Deal Moved to Closed Won” and “Deal Moved to Closed Lost” actions out of the box

you can build it as a goal without any additional configuration. If your KPI definition contains a custom date field, follow the below guide to be able to convert the date field into an action:

[Track Date Properties](../101%20-%20How%20HockeyStack%20Works%2023037b7b5bd944369413b319ea89150a/Goals%2004b8e7d5b7f1472aa6d10767214c88c7/Track%20Date%20Properties%205dfbe6af4bc64ef48849edd7bd0973ac.md)

---

Navigate to [Definitions > Goals](https://hockeystack.com/dashboard/actions) from the sidebar to get started after you complete the previous step.

Click on the + icon on the top right to create a new goal.

Let’s take Lead from our KPIs above as the example. This KPI uses the CreateDate of the lead object. Therefore it can be tracked using the Lead Created action.

[https://app.arcade.software/share/XuSJQDCVBBVHwjjHteSz](https://app.arcade.software/share/XuSJQDCVBBVHwjjHteSz)

The MQL definition above is a bit more complex, with a custom date field and some filters attached. 

- Refer back to the Track Date Properties guide. The custom date field will be converted to an action named “Lead Property Changed”.
- Refer to the Salesforce fields list below to see that LeadSource on the Lead object is being mapped to a property called “contact_source”.
    
    [Properties Pulled from Salesforce](../../Integrations%2042cfee82e46b412792a90e73fe508246/Salesforce%2034864cb1d9c1493c8c7c8cc4d97665c2/Salesforce%20Pulled%20Objects%20List%20ec4c35fcae7242adb1f8f5be8dff18bd/Properties%20Pulled%20from%20Salesforce%209528239ff8fa4017a0a50b270e21df49.md)
    
- Refer to the Regex guide below to quickly do the “contains one of” filtering.
    
    [The Marketer’s Guide to Using Regex](../101%20-%20How%20HockeyStack%20Works%2023037b7b5bd944369413b319ea89150a/Goals%2004b8e7d5b7f1472aa6d10767214c88c7/The%20Marketer%E2%80%99s%20Guide%20to%20Using%20Regex%20ec0c77006902440ebccb6fb684ec91fa.md)
    

[https://app.arcade.software/share/E8GBzsmTx6n2pAyIOzNT](https://app.arcade.software/share/E8GBzsmTx6n2pAyIOzNT)

The SQL definition above, similar to the Lead, uses the CreateDate for CampaignMember.

- Refer to the Salesforce fields list documentation below to see that CampaignMember creation is recorded as an action called “Campaign Subscription Created”, and there is a “campaign_member_status” property and “campaign_member_responded” property attached. We can use either of them to filter.

[https://app.arcade.software/share/cnALc5HRkXeev5HmccA2](https://app.arcade.software/share/cnALc5HRkXeev5HmccA2)

The Closed Won definition above relies on the CloseDate, so we can use the “Deal Moved to Closed Won” action.

[https://app.arcade.software/share/uxXin2SXGbAgypsvTOBN](https://app.arcade.software/share/uxXin2SXGbAgypsvTOBN)

Congrats! You have all the KPI definitions created as goals!