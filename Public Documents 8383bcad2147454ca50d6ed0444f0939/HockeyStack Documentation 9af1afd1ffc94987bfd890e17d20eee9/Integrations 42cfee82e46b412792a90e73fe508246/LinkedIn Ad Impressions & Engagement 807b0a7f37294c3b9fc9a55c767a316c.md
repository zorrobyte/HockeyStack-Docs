# LinkedIn Ad Impressions & Engagement

HockeyStack’s LinkedIn Account List Integration add-on pulls account-based ad impression and engagement data from LinkedIn Ads. You can use this data in your attribution reporting, segmentation, or when viewing a single account’s journey.

# How It Works

HockeyStack can pull impression data daily by company & campaign to capture changes in impressions and engagement over time. If it detects a change in any of the metrics, it inserts a Goal related to that change.

**Goals:**

- LinkedIn Ads Impressions Changed
- LinkedIn Ads Ad Engagements Changed

Don’t be confused that it says “Changed”, this just means the impressions since the last time we pulled the data (ie yesterday). All 3 of these goals use the same action property and user property schema.

**Action Properties:**

| Property | Type | Description |
| --- | --- | --- |
| *impression_change* or *ad_engagement_change* | Number | The change in the relevant metric since the last pull |

**User Properties:**

| Property | Type | Description |
| --- | --- | --- |
| company_id | String | The associated CRM company ID, if found. |
| linkedin_company_id | String | The company’s ID on LinkedIn |
| company_name | String | The company’s name |
| company_domain | String | The company’s website domain |
| company_number_of_employees | String | The range of employees the company has |
| company_industry | String | The industry the company is associated with on LinkedIn |

# Caveats

LinkedIn only provides impression & engagement data if the metric is greater than 2 due to privacy. This might cause slight accuracy issues.