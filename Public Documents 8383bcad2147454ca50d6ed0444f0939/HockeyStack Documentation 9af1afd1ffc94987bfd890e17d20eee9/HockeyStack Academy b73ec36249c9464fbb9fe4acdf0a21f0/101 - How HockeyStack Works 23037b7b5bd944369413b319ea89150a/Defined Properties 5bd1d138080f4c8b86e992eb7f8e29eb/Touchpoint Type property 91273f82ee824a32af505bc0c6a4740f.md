# Touchpoint Type property

Touchpoint Type is an action property that helps distinguish between different categories of sales and marketing actions.

Below is a full list:

| Touchpoint Type | Conditions |
| --- | --- |
| Website Session | Action Type = "start-session" |
| Pageview | Action Type = "enter-page" |
| Form Submission | Action Type = "onsubmit" |
| Ad Impression | Action Name = "LinkedIn Ads Impressions Changed" AND Action Type = "custom" |
| Ad Engagement | Action Name = "LinkedIn Ads Ad Engagements Changed" AND Action Type = "custom" |
| Campaign Subscription | (
  Action Name = "Campaign Subscription Created" OR 
  Action Name = "Campaign Subscription Updated"
) AND Action Type = "custom" |
| Call | Action Name = "Call Created" AND Action Type = "custom" |
| Meeting | Action Name = "Meeting Created" AND Action Type = "custom" |
| Send Sales Email | (
   Action Name = "Email Created" OR 
   (Action Name = "Email Sent" AND Integration = "Salesforce")
) AND Action Type = "custom" |
| Send Marketing Email | Action Name = "Email Sent" AND Action Type = "custom" |
| Open Marketing Email | (Action Name = "Email Opened" OR Action Name = "Open Email") AND Action Type = "custom" |