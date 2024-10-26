# Step 1 - Complete the technical implementation

1. Choose one person from your organization to [sign up for an account](https://hockeystack.com/signup) and [invite team members.](https://hockeystack.com/dashboard/settings?tab=2)
2. If you’d like to use SSO, notify the HockeyStack team immediately to do the necessary configuration. 
    1. Otherwise, if you’d like to enable MFA, you can do so for your own account in [Settings > Account Settings](https://hockeystack.com/dashboard/settings?tab=6), and you can enforce MFA for all users in [Settings > Team Sharing](https://hockeystack.com/dashboard/settings?tab=2).
3. Navigate to the [integration page](https://hockeystack.com/dashboard/integration). 
4. Make sure you enter your domain details correctly.
    1. Domain Name will be the name of the workspace this account is associated with.
    2. Domain URL will be the primary domain associated with this workspace.
    3. Connected domains are secondary domains associated with this workspace. You can associate as many domains as you want with the same workspace, including both subdomains and other completely different domains. Website data from each domain will be tracked and reported on the same dashboard. **HockeyStack will only track data from the domains you add here.**
    
    Some companies also choose to create a separate workspace for their domains, which will completely isolate all data and all setup between the two domains. This is usually not the best option, so consult with the HockeyStack team before going for this option.
    
    ![Screenshot 2024-03-29 at 16.46.36.png](Step%201%20-%20Complete%20the%20technical%20implementation%20f7a3b542b1634c50803b4ea8e3ebb91f/Screenshot_2024-03-29_at_16.46.36.png)
    
5. Add the tracking script to each of your domains from the previous step.  Make sure to test that the script works on each domain.
    
    [Testing the website tracking script](Step%201%20-%20Complete%20the%20technical%20implementation%20f7a3b542b1634c50803b4ea8e3ebb91f/Testing%20the%20website%20tracking%20script%20a9b946de21fc454e99ec2ae385bca4de.md)
    
6. (If you have a self-serve motion) Add the script inside your application and on your signup and login pages. Use the [user identification guide](../../Advanced%20Features%20db30cc843c1340ad8021a35a3a4237f3/Identifying%20Users%2025e40d56e1fd4275bf78430d6a88de8b.md) to identify application users inside HockeyStack.
    
    ```jsx
    if (typeof HockeyStack === 'undefined') {
      if (!Array.isArray(window.hockeystackQueue)) window.hockeystackQueue = [];
      window.hockeystackQueue.push(function () {
        HockeyStack.identify(email);
      });
    } else HockeyStack.identify(email);
    
    // make sure to replace "email" with the actual email of each logged-in user. So the script should read like HockeyStack.identify('michael@dundermifflin.com') for the specific visitor.
    ```
    
7. Click Test Integration in the next step so that HockeyStack validates your script integration.
    
    ![Screenshot 2024-03-29 at 23.57.02.png](Step%201%20-%20Complete%20the%20technical%20implementation%20f7a3b542b1634c50803b4ea8e3ebb91f/Screenshot_2024-03-29_at_23.57.02.png)
    
8. Navigate to [Settings > API & Integrations](http://hockeystack.com/dashboard/settings?tab=5), and click the Connect button next to all your desired data sources.
    1. For Ads integrations, make sure to choose all your ad accounts after authenticating with the ad platform
    2. For HubSpot, we recommend starting a historical website data pull.
        
        [HubSpot historical website data](Step%201%20-%20Complete%20the%20technical%20implementation%20f7a3b542b1634c50803b4ea8e3ebb91f/HubSpot%20historical%20website%20data%20ec8b06e147f046d9a4495786dda0eabb.md)
        
    3. We can also pull historical website data from Marketo. Notify your HockeyStack CSM if you want this enabled.
    4. If you use Pardot forms, use the below guide to integrate:
        
        [Connecting Pardot Forms to HockeyStack](Step%201%20-%20Complete%20the%20technical%20implementation%20f7a3b542b1634c50803b4ea8e3ebb91f/Connecting%20Pardot%20Forms%20to%20HockeyStack%20901c27cc72de4b69bba41075e35658f3.md)
        
9. If you use a non-default revenue field from CRMs, select the revenue field in [Settings > Report & Tracking](https://hockeystack.com/dashboard/settings?tab=1)
10. Configure your Main Currency in [Settings > Report & Tracking](https://hockeystack.com/dashboard/settings?tab=1)
11. Sync any spend from digital platforms that don’t integrate with HockeyStack. (Most commonly, display spend that is not on Google Ads)
    
    [Sync Spend](../101%20-%20How%20HockeyStack%20Works%2023037b7b5bd944369413b319ea89150a/Sync%20Spend%207ae0043cd1d74d8fb705a5b2d3b49594.md)
    

(Optional)

1. HockeyStack pulls in all fields from all objects in your connected systems. Set your business users for success by hiding the ones that you think will not be used.
    
    [Hiding / showing properties](Step%201%20-%20Complete%20the%20technical%20implementation%20f7a3b542b1634c50803b4ea8e3ebb91f/Hiding%20showing%20properties%20caa7de1d669c4b528ba276a4e85ae05c.md)