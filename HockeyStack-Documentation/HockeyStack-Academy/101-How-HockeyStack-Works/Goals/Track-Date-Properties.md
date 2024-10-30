# Track Date Properties

Sometimes, actions that you want in HockeyStack are not really stored as actions in your systems. The most common example being date fields in CRM and Marketing Automation systems. 

HockeyStack can translate date fields into actions using a setting called “Track Date Properties”

Currently, this setting is only available for Salesforce, HubSpot and Marketo integrations.

Navigate to [Settings > Reporting & Tracking](https://hockeystack.com/dashboard/settings?tab=1) to find the Track Date Properties section.

You will need 3 pieces of information:

- The integration to pull the data from
- The object where the date field resides
    - Available objects for Salesforce:
        - **Lead:** This will pull from both Lead and Contact.
        - **Deal:** This will pull from Opportunity
        - **Company:** This will pull from Account
        - **Campaign Member:** This will pull from CampaignMember
    - Available objects for HubSpot:
        - **Contact**
        - **Company**
        - **Deal**
    - Available objects for Marketo:
        - **Lead**
- The **API name** of the date field
    - Salesforce: [https://help.salesforce.com/s/articleView?id=000385500&language=en_US&type=1](https://help.salesforce.com/s/articleView?id=000385500&language=en_US&type=1)
    - HubSpot:
        
        [Finding Internal Field Names in HubSpot](Track-Date-Properties/Finding-Internal-Field-Names-in-HubSpot.md)
        
    - Marketo: [https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/field-management/export-a-list-of-all-marketo-api-field-names](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/field-management/export-a-list-of-all-marketo-api-field-names)

[https://app.arcade.software/share/7fnCJ8U7Rlu0INZgGorc](https://app.arcade.software/share/7fnCJ8U7Rlu0INZgGorc)

Date properties are synced every 24 hours, so the data from the date property will not be immediately available.

When it is available it will be inserted as an action with the below convention:

| Timestamp | Entity | Action Name | Action Properties |
| --- | --- | --- | --- |
| The value of the date property | … | <Object Name> Property Changed | **property:** <API Name of the property>
**old_value:** empty
**new_value:** <The value of the date property> |

Then, to use it in reports, you can create a new goal with this information.

[https://app.arcade.software/share/CRTFAiBHcEl0tJIwbs7B](https://app.arcade.software/share/CRTFAiBHcEl0tJIwbs7B)