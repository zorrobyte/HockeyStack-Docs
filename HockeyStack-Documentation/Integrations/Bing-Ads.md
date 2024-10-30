# Bing Ads

HockeyStack's Bing Ads integration pulls your campaign data into HockeyStack and connects it with your marketing, revenue, and product data. This allows you to track through your ad spend and ad insight data.

A Microsoft 365 Admin account is required to approve the Bing Ads integration with HockeyStack.

The data comes into HockeyStack's **metadata** table structure, with the following information pulled in.

| account_id |  |
| --- | --- |
| network |  |
| campaign_id |  |
| adgroup_id |  |
| ad_id |  |
| campaign_name |  |
| adgroup_name |  |
| ad_name |  |
| keyword |  |
| utm_source | UTM_Source is by default set as “bing” if the campaign has no UTM Source applied |
| utm_campaign |  |
| utm_medium |  |
| utm_content |  |
| utm_term |  |
| impressions |  |
| clicks |  |
| cost |  |
| currency |  |
| date | Daily granularity |

For more information about metadata, check out our documentation article on the HockeyStack Data Model: [The HockeyStack data model](../HockeyStack-Academy/101-How-HockeyStack-Works/The-HockeyStack-data-model.md)