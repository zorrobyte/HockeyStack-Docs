# HubSpot historical website data

If you have HubSpot analytics running on your website, your HubSpot account has website activity for known contacts that HockeyStack can pull to backfill website data.

1. To get started you need to create a Google Sheet of emails that HockeyStack will pull website data for. The limit for the number of contacts you can pull website data for is 100k. We recommend pulling a list of contacts that might be relevant to your main KPIs. For example, any MQLs, SQLs, etc. within the past year should be included. Any contact related to any company that has an opportunity created within the past year should also be included. The Google Sheet should have the word “email” on the A1 cell, followed by a list of emails on the A column.
    
    <aside>
    ❗ Important:
    - The spreadsheet must only have one column with emails
    - The spreadsheet must not have any blank rows in between two emails. For example, if A2 is test@test.com, A3 is blank, A4 is test2@test2.com, this won’t work.
    
    </aside>
    
2. Once you create the Google Sheet, you should get the URL of the spreadsheet that you can plug into HockeyStack. 
Click File on the top left, hover over Share, and select Publish to Web
    
    ![Screenshot 2024-03-30 at 00.07.52.png](../../101%20-%20How%20HockeyStack%20Works%2023037b7b5bd944369413b319ea89150a/Sync%20Spend%207ae0043cd1d74d8fb705a5b2d3b49594/Screenshot_2024-03-30_at_00.07.52.png)
    
    On the screen that comes up, change “Web page” to “CSV”, and click Publish
    
    ![Screenshot 2024-03-30 at 00.09.22.png](../../101%20-%20How%20HockeyStack%20Works%2023037b7b5bd944369413b319ea89150a/Sync%20Spend%207ae0043cd1d74d8fb705a5b2d3b49594/Screenshot_2024-03-30_at_00.09.22.png)
    
3. Click Configure next to HubSpot in the HockeyStack [Settings > API & Integrations](https://hockeystack.com/dashboard/settings?tab=5). Paste the URL into the Sync Historical Website Data form, and click Sync.
    
    ![Screenshot 2024-03-30 at 00.10.41.png](HubSpot%20historical%20website%20data%20ec8b06e147f046d9a4495786dda0eabb/Screenshot_2024-03-30_at_00.10.41.png)
    
    You will only be able to do this once, so double check that the URL is working and is up to the above specifications before submitting.