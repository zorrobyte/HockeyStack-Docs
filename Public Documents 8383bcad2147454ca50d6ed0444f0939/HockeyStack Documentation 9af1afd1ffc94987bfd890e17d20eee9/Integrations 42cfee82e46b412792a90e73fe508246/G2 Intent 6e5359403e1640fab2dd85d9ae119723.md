# G2 Intent

HockeyStack’s G2 Intent integration allows you to understand G2 views’ impact on revenue, see a trend of your performance on G2 for ICP companies, and give your Sales team high intent leads based on the data.

# Connection

Prerequisites:

- A compatible G2 paid subscription

Navigate to [HockeyStack > Settings > API & Integrations](https://hockeystack.com/dashboard/settings?tab=5) and click “Connect” next to G2 Intent. This will ask you for an API key. You can obtain your API key by going to API Tokens & Apps in your G2 admin panel, and creating a new token or reusing an existing one.

![Screenshot 2024-03-29 at 09.26.38.png](G2%20Intent%206e5359403e1640fab2dd85d9ae119723/Screenshot_2024-03-29_at_09.26.38.png)

# Data Pull Frequency

Data is pulled every 24 hours.

# Pulled Data

## G2 Company Profile

Internally, G2 stores information on each prospective company and scores them based on their engagement with your company. These are pulled as Company Properties into HockeyStack.

- **Action Name: Company Updated**
    - **Action Date:** Last Seen At Date
    - **User Properties:**
        
        
        | **Property** |
        | --- |
        | Company ID |
    - **Shared Properties:**
        - **Companies**
            
            
            | **Property** |
            | --- |
            | G2 Activity Level |
            | G2 Buying Stage |
            | G2 Category Pageviews |
            | G2 Company Annual Revenue |
            | G2 Company Country |
            | G2 Company Description |
            | G2 Company Domain |
            | G2 Company Id |
            | G2 Company Name |
            | G2 Company Number Of Employees |
            | G2 Company State |
            | G2 Comparison Pageviews |
            | G2 Competitor Pageviews |
            | G2 Direct Pageviews |
            | G2 Intent Score |
            | G2 Last Seen At |
            | G2 Pricing Pageviews |
            | G2 Product Profile Pageviews |
            | G2 Sponsored Content Pageviews |
            | G2 Total Pageviews |
            | G2 Visitor Count |
            | Company Id |
            | Company Name |
            | Company Domain |
            | Company Country |
    

## Intent Events

G2 shares data with HockeyStack about prospects visiting a category page, a competitor page, your company’s profile, etc. These are pulled in as actions.

Note: Intent Events are only available from the point you connect the integration, and not historically.

- **Action Name: Event Created**
    - **Action Date:** Event Date
    - **Action Properties:**
        
        
        | Property |
        | --- |
        | G2 Visitor ID |
        | G2 Event ID |
        | G2 Event Tag |
        | G2 Event Title |
        | G2 Event URL |
        | G2 Event Products |
        | G2 Event Categories |
        | G2 Company ID |
        
        **G2 Event Tag** refers to the type of intent signal (i.e. type of page visited). 
        It may include the below and more:
        
        | Event Tag | Description |
        | --- | --- |
        | categories.show | Viewing a category page |
        | categories/products.free | Viewing the free products list in a category |
        | categories/products.highest_rated | Viewing the highest rated products list in a category |
        | products.competitors | Viewing the competitors of your product |
        | ad.sponsored.product_page_header | Clicking the sponsored ad for your product in a product page |
        | products.reviews
         | Viewing your product’s reviews |
        | products.discussions | Viewing your product’s discussions |
        
        **G2 Event Title** shows the title of the page where the signal was received, whereas **G2 Event URL** shows the URL.
        
        **G2 Event Products** shows any specific products related to the signal (competitive, or your own product).
        
        **G2 Event Categories** shows any specific categories related to the signal.
        
    - **User Properties:**
        
        
        | **Property** |
        | --- |
        | Company ID |
    - **Shared Properties:**
        - **Companies**
            
            
            | **Property** |
            | --- |
            | G2 Activity Level |
            | G2 Buying Stage |
            | G2 Category Pageviews |
            | G2 Company Annual Revenue |
            | G2 Company Country |
            | G2 Company Description |
            | G2 Company Domain |
            | G2 Company Id |
            | G2 Company Name |
            | G2 Company Number Of Employees |
            | G2 Company State |
            | G2 Comparison Pageviews |
            | G2 Competitor Pageviews |
            | G2 Direct Pageviews |
            | G2 Intent Score |
            | G2 Last Seen At |
            | G2 Pricing Pageviews |
            | G2 Product Profile Pageviews |
            | G2 Sponsored Content Pageviews |
            | G2 Total Pageviews |
            | G2 Visitor Count |
            | Company Id |
            | Company Name |
            | Company Domain |
            | Company Country |