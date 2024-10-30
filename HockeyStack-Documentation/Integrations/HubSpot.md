# HubSpot

HockeyStack's HubSpot integration pulls your sales data into HockeyStack and connects it with the rest of your customer data. This includes Companies, Contacts, Deals, Engagements and more.

# How It Works

When you integrate HubSpot, HockeyStack pulls certain actions and properties from it. Each action comes with action properties that give more information about it.

For objects like company and contact, we also pull all of their properties which are added to that object’s profile on HockeyStack and can be used for segmentation.

For a full list of the custom actions we pull from HubSpot, see [HubSpot Pulled Actions List](HubSpot/HubSpot-Pulled-Actions-List.md) .

<aside>
💡 Apart from the CRM data, we also track HubSpot form submissions and meeting scheduling through the website automatically. See [HubSpot Website Tracking](HubSpot/HubSpot-Website-Tracking.md) for more information.

</aside>

# Caveats

- We pull the data from HubSpot on a daily basis.