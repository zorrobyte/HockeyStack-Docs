# Sync Spend

HockeyStack has native integrations to the most widely used advertising platforms. If there is an advertising platform you use that doesn’t have a native integration, you might benefit from syncing the spend on that platform using a CSV.

1. To get started, navigate to [Settings > Reporting & Tracking](https://hockeystack.com/dashboard/settings?tab=1).
    
    ![Screenshot 2024-04-28 at 02.35.28.png](Sync%20Spend%207ae0043cd1d74d8fb705a5b2d3b49594/Screenshot_2024-04-28_at_02.35.28.png)
    
2. Sync Spend will ask you to add the URL of a CSV file.
    
    <aside>
    👉 You can copy our Google Sheets template to start populating it: [HockeyStack Template - Sync Spend](https://docs.google.com/spreadsheets/d/16NHBul2BAU1sLilmZFtGFSMnm3zTTvCqli6S5zrhfC0/edit?usp=sharing)
    
    </aside>
    
    You can copy the below Google Sheets template to start populating it.
    
    https://docs.google.com/spreadsheets/d/16NHBul2BAU1sLilmZFtGFSMnm3zTTvCqli6S5zrhfC0/preview?usp=sharing
    
    **The yellow marked columns are required.**
    
    - Date needs to be in the YYYY-MM-DD format.
    - Cost needs to be a number in US Dollars, with no other characters. No Currency Symbols, no commas.
    - If you need to use a different currency, you can do the following:
        
        ![Screenshot 2024-10-18 at 9.26.16 AM.png](Sync%20Spend%207ae0043cd1d74d8fb705a5b2d3b49594/Screenshot_2024-10-18_at_9.26.16_AM.png)
        
    - Impressions and Clicks also have to be numbers with no other characters.
    - You need to input at least one of the UTM parameters, regardless of the spend being connected to a website visit or not.
    
3. Once you create the Google Sheet, you should get the URL of the spreadsheet that you can plug into HockeyStack. 
    
    Click File on the top left, hover over Share, and select Publish to Web
    
    ![Screenshot 2024-03-30 at 00.07.52.png](Sync%20Spend%207ae0043cd1d74d8fb705a5b2d3b49594/Screenshot_2024-03-30_at_00.07.52.png)
    
    On the screen that comes up, change “Web page” to “CSV”, and click Publish
    
    ![Screenshot 2024-03-30 at 00.09.22.png](Sync%20Spend%207ae0043cd1d74d8fb705a5b2d3b49594/Screenshot_2024-03-30_at_00.09.22.png)
    
4. Then, copy this URL, and add it into HockeyStack from the Add input:
    
    ![Screenshot 2024-04-28 at 02.38.12.png](Sync%20Spend%207ae0043cd1d74d8fb705a5b2d3b49594/Screenshot_2024-04-28_at_02.38.12.png)
    

# How It Works

- The added spreadsheet is automatically synced to HockeyStack daily. Any changes made in past data is also reflected.
- The sync requires that the inputed spend is connected to a UTM parameter
- You can validate the sync by creating a table report like below:
    
    ![Screenshot 2024-04-28 at 02.45.47.png](Sync%20Spend%207ae0043cd1d74d8fb705a5b2d3b49594/Screenshot_2024-04-28_at_02.45.47.png)
    
- You can follow this guide to sync offline spend:
    
    [Syncing spend from offline channels and campaigns](Syncing%20spend%20from%20offline%20channels%20and%20campaigns%20261784b46d7242b780074827800468d8.md)
    

# Caveats

- Deleted rows will not be deleted in HockeyStack, and modified rows will not be modified in HockeyStack. Therefore, we recommend creating a staging spreadsheet that is copied over to the master spreadsheet once it is completely validated.
    - If you need to reset your spend data, message or send an email to your Customer Advisor / CSM.