# What is an attribution touchpoint?

An attribution report assigns credit for a KPI to certain engagements along the customer journey.

There are tens of thousands of actions recorded by HockeyStack for each company. Therefore we have to have a way of filtering to the exact engagements we want to receive credit. **Attribution touchpoints** are the engagements along the customer journey selected for credit distribution towards a KPI.

To give an example, see the below table for actions that a company has recorded. The red actions are ones that a HockeyStack user might want to filter out. The green actions are ones that a HockeyStack user might want to keep. The action at the end is our KPI.

| Timestamp  | Action Name  |
| --- | --- |
| 2024-04-06 09:21:30 | Marketing Email Sent |
| **2024-04-05 09:15:32** | **Website Session Started** |
| 2024-04-05 09:16:05 | Scrolled down on webpage |
| 2024-04-05 09:16:45 | Website Session Ended |
| 2024-04-05 10:00:30 | Outbound Email Sent |
| **2024-04-06 09:23:13** | **Marketing Email Clicked** |
| 2024-04-07 07:07:00 | Tradeshow Invited |
| **2024-04-07 10:27:50** | **Tradeshow Attended** |
| 2024-04-08 11:00:00 | Deal Created (Pipeline) - $100k |

Looking at the above journey, we need to distribute $100k in total credit into actions along the journey.

If we weren’t filtering out touchpoints, the credit distribution would be:

| Action Name  |  |
| --- | --- |
| Marketing Email Sent | $12.5k |
| **Website Session Started** | $12.5k |
| Scrolled down on webpage | $12.5k |
| Website Session Ended | $12.5k |
| Outbound Email Sent | $12.5k |
| **Marketing Email Clicked** | $12.5k |
| Tradeshow Invited | $12.5k |
| **Tradeshow Attended** | $12.5k |
| Deal Created (Pipeline) - $100k | → This is our KPI |

But it doesn’t make sense for a “scroll down” action to be attributed $12.5k, so we instead want the below distribution:

| Action Name  |  |
| --- | --- |
| Marketing Email Sent | 0 |
| **Website Session Started** | $33.3k |
| Scrolled down on webpage | 0 |
| Website Session Ended | 0 |
| Outbound Email Sent | 0 |
| **Marketing Email Clicked** | $33.3k |
| Tradeshow Invited | 0 |
| **Tradeshow Attended** | $33.3k |
| Deal Created (Pipeline) - $100k | → This is our KPI |

HockeyStack does this filtering using “**breakdowns**” in reports.

**If the property that is selected as the breakdown is not empty *and* the action it is tied to has a timestamp that is before the timestamp of the KPI chosen for attribution, then that property is** **used as an attribution touchpoint.**

If your breakdown does not have an associated timestamp, it won’t be usable in attribution. Examples include company properties & user properties. For example, many HockeyStack users try to use Lead Source in their breakdown using an attribution model. This doesn’t make sense because Lead Source is not attached to any timestamp, and does not exist on the customer journey — it’s just a property.