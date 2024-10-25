# Customer Account Reset

Just like spring cleaning, sometimes your HockeyStack account needs to be swept out and reset. Account reset may be needed for many reasons. If you’re experiencing one of the following, it may be time for to shake things out:

- You can’t find the report you need, when you need it, even though you’ve built it multiple times
- You have a whole new exec team
- Your core KPIs have changed

Below is the HockeyStack Team’s recommended process to audit and reset your account. 

1. Create a list of your KPIs
    1. Follow this guide: 
    [https://docs.hockeystack.com/hockeystack-academy/102-implementation-guide/step-3-create-your-kpi-goals#block-3e4b7875827a44ed8a17cc79149bdda2](https://docs.hockeystack.com/hockeystack-academy/102-implementation-guide/step-3-create-your-kpi-goals#block-3e4b7875827a44ed8a17cc79149bdda2)
2. Create a list of CRM properties needed
    1. HockeyStack ingests all of the CRM properties that it has permission for. We want to group these properties into 2 groups 
        1. Properties we need for reporting
        2. Properties we don’t need and will just confused everyone else in the system
3. Hide all non-defined properties that are not needed for reporting
    1. Follow this Guide:
    [https://docs.hockeystack.com/hockeystack-academy/102-implementation-guide/step-1-complete-the-technical-implementation/hiding-showing-properties#block-3d0cd43761824d488cb474d6b99896a5](https://docs.hockeystack.com/hockeystack-academy/102-implementation-guide/step-1-complete-the-technical-implementation/hiding-showing-properties#block-3d0cd43761824d488cb474d6b99896a5)
4. Create a list of dashboards that will initially be used
5. Make sure Unified Channel is properly built
    1. Follow This Guide:
    [https://docs.hockeystack.com/hockeystack-academy/102-implementation-guide/step-23-create-your-unified-channel-property](https://docs.hockeystack.com/hockeystack-academy/102-implementation-guide/step-23-create-your-unified-channel-property)
6. Make sure Unified Campaigns Defined Property is properly built
    1. **Please Note:**  Please ensure this exactly matches unified channel
    2. Follow this step by step guide: 
        
        [https://www.notion.so/hockeystack/Building-Unified-Campaign-Property-b95595d1aae34d29ad34e69663ee442f](How%20to%20Build%20a%20Unified%20Campaign%20Property%20b95595d1aae34d29ad34e69663ee442f.md)
        
    3. Reference this Video Guide:
    [https://www.loom.com/share/520f143433a2485c9fb6d16e24bfc931?sid=8eb64ac6-efdb-4aad-a740-123923c6b4c1](https://www.loom.com/share/520f143433a2485c9fb6d16e24bfc931?sid=8eb64ac6-efdb-4aad-a740-123923c6b4c1)
7. Create campaign groups properties. Follow this guide: [https://www.notion.so/hockeystack/Building-Campaign-Tactic-Defined-Properties-080072e0af6c40acb92bfcfdd47b7321](Building%20Campaign%20Segments%20Defined%20Properties%20080072e0af6c40acb92bfcfdd47b7321.md)
    1. Tactic
    2. Region
    3. TOFU MOFU BOFU
8. Create the Asset Type property. Follow this guide: [https://www.notion.so/hockeystack/How-To-Build-an-Asset-Type-Defined-Property-d448ebfd5b94429e97bef760e3e10092](How%20To%20Build%20an%20Asset%20Type%20Defined%20Property%20d448ebfd5b94429e97bef760e3e10092.md)
9. Create assets property. Follow this Guide: [https://www.notion.so/hockeystack/How-to-Build-an-Asset-Defined-Property-a7976183a8454f97888fc998ec7c336e](How%20to%20Build%20an%20Asset%20Defined%20Property%20a7976183a8454f97888fc998ec7c336e.md)
10. Build a Business Overview Dashboard and compare your KPIs to the source reports from your CRM that you referenced for your HockeyStack KPI definitions
    1. Follow this Guide: [https://www.notion.so/hockeystack/Business-Overview-Dashboard-b33cef6a17e34535ae2c92ce5224218e](Template%20Guides%207ae7d55f281b468f8aa1bee35f38ecae/Business%20Overview%20Dashboard%20b33cef6a17e34535ae2c92ce5224218e.md)
    2. When comparing your KPIs to your source reports, select a date range in the past like, last quarter or last month 
11. Delete goals that are not or should not be used
    1. If they are being used somewhere, do the excruciating work of deleting where they are used and then delete the goal
12. Goals should be pulled from defined properties wherever possible
    1. Goals built from defined properties are linked to the defined property mapping. If the defined property mapping is updated, the goal will also update, and every report that the goal is used in will update. It is best practice to build goals from defined properties to minimize the number of places you need to update when a definition changes. 
    2. Follow this guide: [https://www.loom.com/share/c59498b31362455ea96b8550821150e1?sid=5572129a-9bcb-4f7c-b4e8-98689ce958bc](https://www.loom.com/share/c59498b31362455ea96b8550821150e1?sid=5572129a-9bcb-4f7c-b4e8-98689ce958bc)
13. Delete defined properties that are not or should not be used
    1. Click the three dots to the right of the property name, then select “Remove”
    
    ![Untitled](Customer%20Account%20Reset%2075bade8bf4c3412c9821899a4565bf88/Untitled.png)
    
14. Create Segments for common filters
    1. Follow this guide: [https://docs.hockeystack.com/filtering](https://docs.hockeystack.com/filtering)
15. Clean dashboards
    1. Remove unused reports
    2. Remove unused columns from large tables
    3. Combine reports that are redundant
        1. a report that is exactly the same except for a breakdown filter can be combined
    4. Ask for report requests / questions from whoever consumes this dashboard and add them
16. Add new features that the account has not used yet 
    1. Attribution weights: [https://docs.hockeystack.com/guides/defining-custom-attribution-weights](https://docs.hockeystack.com/guides/defining-custom-attribution-weights)
    2. Attribution funnel: [https://docs.hockeystack.com/hockeystack-academy/report-examples/attribution-funnel#block-a90d608cc52741dab2170a086fd9270b](https://docs.hockeystack.com/hockeystack-academy/report-examples/attribution-funnel#block-a90d608cc52741dab2170a086fd9270b)
    3. Company bar graph: [https://www.loom.com/share/9e06b8c1619f4284b44050ee6664f12b?sid=647f65ee-b9f4-41cf-af2e-4fd4258b7096](https://www.loom.com/share/9e06b8c1619f4284b44050ee6664f12b?sid=647f65ee-b9f4-41cf-af2e-4fd4258b7096)
    4. Company feed (breakdown by date, important moments, company name)  -
        1. Build the important moments property first: [https://www.loom.com/share/ce884c19ccea4dc2a1c273729666a187?sid=17cbb076-266c-4e17-9c24-0c5017e19a11](https://www.loom.com/share/ce884c19ccea4dc2a1c273729666a187?sid=17cbb076-266c-4e17-9c24-0c5017e19a11) ****
        2. Build the company feed report: [https://www.loom.com/share/771e1edd81a348e7bfef87bdb8f39573?sid=91250c11-2131-4a1a-8599-2a9ca3d9c12a](https://www.loom.com/share/771e1edd81a348e7bfef87bdb8f39573?sid=91250c11-2131-4a1a-8599-2a9ca3d9c12a)
    5. Lift reports: [https://docs.hockeystack.com/data-visualization/lift-reports#block-0c2e99bf1d13480d9686987f526b1997](https://docs.hockeystack.com/data-visualization/lift-reports#block-0c2e99bf1d13480d9686987f526b1997)
    6. Lookback window -  **GUIDE TO COME**