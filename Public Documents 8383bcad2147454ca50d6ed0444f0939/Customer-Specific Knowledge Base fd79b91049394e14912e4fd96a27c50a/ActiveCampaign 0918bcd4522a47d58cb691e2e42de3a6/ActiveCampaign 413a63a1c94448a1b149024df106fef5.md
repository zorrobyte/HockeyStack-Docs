# ActiveCampaign

**Sync schedule:** 1am UTC Daily

# Contacts

## Contact Created

**Action Data**

| **Column** | **Value** | **Type** |
| --- | --- | --- |
| user_id | `contact.id` | String |
| identity | `contact.email` | String |
| action_date | `contact.cdate` | DateTime |
| action_name | “Contact Created” | String |

**Action Properties**

| **Property** | **Value** | **Type** |
| --- | --- | --- |
| integration | “ActiveCampaign” | String |

**User Properties**

| **Property** | **Value** | **Type** |
| --- | --- | --- |
| contact_id | `contact.id` | String |
| contact_name | `contact.firstName + " " + contact.lastName`   | String |
| contact_title | `contact.jobTitle` | String |
| activecampaign__contact_id | `contact.id` | String |
| company_id | `contact.orgId` | String |

**On Update:**

When any of the above fields are updated, a hidden “Contact Updated” action is inserted, which updates User Properties with the new values.

# Deals

<aside>
💡 The only synced deal pipelines are:

- AMER Outbound Auto
- APAC Outbound Auto
- SSA Outbound Auto
- EMEA Outbound Auto
- BRAZIL Outbound Auto

If you want to sync any other pipelines, please let us know.

</aside>

## Deal Created

**Action Data**

| **Column** | **Value** | **Type** |
| --- | --- | --- |
| user_id | `deal.organization`, fallback to `deal.contact` | String |
| identity | `deal.contact.email` | String |
| action_date | `deal.cdate` | DateTime |
| action_name | “Deal Created” | String |

**Action Properties**

| **Property** | **Value** | **Type** |
| --- | --- | --- |
| integration | “ActiveCampaign” | String |
| …All properties in **Shared Properties** | …All properties in **Shared Properties** | …All properties in **Shared Properties** |

**User Properties**

| **Property** | **Value** | **Type** |
| --- | --- | --- |
| contact_id | `deal.contact` | String |
| company_id | `deal.organization` | String |

**Shared Properties - Deal**

**Key:** deal_id from Action Properties

**Value:** `deal.id`

| **Property** | **Value** | **Type** |
| --- | --- | --- |
| deal_id | `deal.id` | String |
| deal_name | `deal.title` | String |
| deal_amount | `deal.value / 100` | String |
| currency | `deal.currency` | String |
| deal_probability | `deal.winProbability` | String |
| deal_pipeline | `deal.group.title` | String |
| deal_pipeline_id | `deal.group.id` | String |
| deal_forecasted_close_date | `deal.forecasted_close_date` | DateTime |
| deal_stage | `deal.stage.title` | String |
| deal_stage_id | `deal.stage` | String |
| deal_is_won | `deal.status === ‘1’` | Boolean |
| deal_is_closed | `deal.status === ‘1’ || deal.status === ‘2’` | Boolean |

**On Update:**

When any of the above fields are updated, a hidden “Deal Updated” action is inserted, which updates Shared Properties with the new values. Action properties remain the same.

## Deal Moved to *<Stage Name>*

**Action Data**

| **Column** | **Value** | **Type** |
| --- | --- | --- |
| user_id | `deal.organization`, fallback to `deal.contact` | String |
| identity | `deal.contact.email` | String |
| action_date | `if(deal.deal_forecasted_close_date ≤ dealActivities.cdate, deal.deal_forecasted_close_date, dealActivities.cdate)` | DateTime |
| action_name | “Deal Moved to *<Stage Name>*” | String |

**Action Properties**

| **Property** | **Value** | **Type** |
| --- | --- | --- |
| integration | “ActiveCampaign” | String |
| deal_previous_stage | `dealActivities.dataOldval.title` | String |
| deal_previous_stage_id | `dealActivities.dataOldval` | String |
| …All properties in **Shared Properties** | …All properties in **Shared Properties** | …All properties in **Shared Properties** |

**User Properties**

| **Property** | **Value** | **Type** |
| --- | --- | --- |
| contact_id | `deal.contact` | String |
| company_id | `deal.organization` | String |

**Shared Properties - Deal**

**Key:** deal_id from Action Properties

**Value:** `deal.id`

| **Property** | **Value** | **Type** |
| --- | --- | --- |
| deal_id | `deal.id` | String |
| deal_name | `deal.title` | String |
| deal_amount | `deal.value / 100` | String |
| currency | `deal.currency` | String |
| deal_probability | `deal.winProbability` | String |
| deal_pipeline | `deal.group.title` | String |
| deal_pipeline_id | `deal.group.id` | String |
| deal_forecasted_close_date | `deal.forecasted_close_date` | DateTime |
| deal_stage | `deal.stage.title` | String |
| deal_stage_id | `deal.stage` | String |
| deal_is_won | `deal.status === ‘1’` | Boolean |
| deal_is_closed | `deal.status === ‘1’ || deal.status === ‘2’` | Boolean |