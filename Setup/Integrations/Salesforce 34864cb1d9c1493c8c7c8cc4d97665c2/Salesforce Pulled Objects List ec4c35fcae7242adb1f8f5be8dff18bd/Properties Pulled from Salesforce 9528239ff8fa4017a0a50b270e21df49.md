# Properties Pulled from Salesforce

# **Account**

### Action: Company Created / Updated

- **Action Name:** "Company Created" / "Company Updated"
- **Action Date:** Salesforce Field **`CreatedDate`** / **`LastModifiedDate`**

| **HockeyStack Property** | **Salesforce Field** |
| --- | --- |
| company_id | Id |
| company_name | Name |
| company_domain | Website |
| company_industry | Industry |
| company_type | Type |
| company_number_of_employees | NumberOfEmployees |
| company_annual_revenue | AnnualRevenue |
| company_country | BillingCountryCode, BillingCountry, BillingAddress.country |
| company_description | Description |
| company_owner_email | Owner.Email |
| company_owner_id | Owner.Id |
| company_owner_name | Owner.Name |

### Action: Company Property Changed

- **Action Name:** "Company Property Changed"
- **Action Date:** Salesforce Field **`PropertyChangeDate`**

| **HockeyStack Property** | **Salesforce Field** |
| --- | --- |
| new_value | NewValue |
| old_value | OldValue |
| property | Property |

# **Salesforce Object: Lead**

### Action: Lead Created / Updated

- **Action Name:** "Lead Created" / "Lead Updated"
- **Action Date:** Salesforce Field **`CreatedDate`** / **`LastModifiedDate`**

| **HockeyStack Property** | **Salesforce Field** |
| --- | --- |
| contact_id | Id |
| contact_name | Name |
| contact_email | Email |
| contact_title | Title |
| contact_created_at | CreatedDate |
| contact_source | LeadSource |
| contact_status | Status |
| contact_owner_email | Owner.Email |
| contact_owner_id | Owner.Id |
| contact_owner_name | Owner.Name |
| company_id | (Derived from email domain and internal matching logic) |

### Action: Lead Property Changed

- **Action Name:** "Lead Property Changed"
- **Action Date:** Salesforce Field **`PropertyChangeDate`**

| **HockeyStack Property** | **Salesforce Field** |
| --- | --- |
| new_value | NewValue |
| old_value | OldValue |
| property | Property |

# **Salesforce Object: Opportunity**

### Action: Deal Created / Updated

- **Action Name:** "Deal Created" / "Deal Updated"
- **Action Date:** Salesforce Field **`CreatedDate`** / **`LastModifiedDate`**

| **HockeyStack Property** | **Salesforce Field** |
| --- | --- |
| deal_id | Id |
| deal_name | Name |
| deal_amount | Amount |
| deal_close_date | CloseDate |
| deal_expected_revenue | ExpectedRevenue |
| deal_source | LeadSource |
| deal_probability | Probability |
| deal_stage | StageName |
| deal_type | Type |
| deal_owner_email | Owner.Email |
| deal_owner_id | Owner.Id |
| deal_owner_name | Owner.Name |
| salesforce__opportunity_record_type_id | RecordType.Id |
| salesforce__opportunity_record_type_name | RecordType.Name |

### Action: Deal Stage Updated

- **Action Name:** "Deal Moved to <StageName>"
- **Action Date:** Salesforce Field **`LastStageChangeDate`** / **`CreatedDate`**

| **HockeyStack Property** | **Salesforce Field** |
| --- | --- |
| deal_stage | StageName |
| deal_is_won | IsWon |
| deal_is_closed | IsClosed |

### Action: Deal Property Changed

- **Action Name:** "Deal Property Changed"
- **Action Date:** Salesforce Field **`PropertyChangeDate`**

| **HockeyStack Property** | **Salesforce Field** |
| --- | --- |
| new_value | NewValue |
| old_value | OldValue |
| property | Property |

# **Salesforce Object: Campaign Member**

### Action: Campaign Subscription Created / Updated

- **Action Name:** "Campaign Subscription Created" / "Campaign Subscription Updated"
- **Action Date:** Salesforce Field **`CreatedDate`** / **`LastModifiedDate`**

| **HockeyStack Property** | **Salesforce Field** |
| --- | --- |
| campaign_member_id | Id |
| campaign_member_responded | HasResponded |
| campaign_member_status | Status |
| campaign_id | CampaignId |
| campaign_name | Campaign.Name |
| campaign_type | Campaign.Type |
| campaign_status | Campaign.Status |
| campaign_member_currency | CurrencyIsoCode |
| campaign_currency | Campaign.CurrencyIsoCode |

# **Salesforce Object: Task**

### Action: Email / Call / Task Created

- **Action Name:** "Email / Call / Task Created"
- **Action Date:** Salesforce Field **`CompletedDateTime`**

| **HockeyStack Property** | **Salesforce Field** |
| --- | --- |
| task_id | Id |
| email_subject / call_subject | Subject |
| call_disposition | CallDisposition |
| call_type | CallType |
| task_owner_id | OwnerId.Id |
| task_owner_email | OwnerId.SenderEmail |
| task_owner_name | OwnerId.Username |

# **Salesforce Object: Contact**

### Action: Contact Created / Updated

- **Action Name:** "Contact Created" / “Contact Updated”
- **Action Date:** Salesforce Field **`CreatedDate`** / **`LastModifiedDate`**

| **HockeyStack Property** | **Salesforce Field** |
| --- | --- |
| contact_id | Id |
| contact_name | Name |
| contact_email | Email |
| contact_title | Title |
| contact_created_at | CreatedDate |
| contact_source | LeadSource |
| contact_owner_email | Owner.Email |
| contact_owner_id | Owner.Id |
| contact_owner_name | Owner.Name |
| company_id | AccountId |

### Action: Contact Property Changed

- **Action Name:** "Contact Property Changed"
- **Action Date:** Salesforce Field **`PropertyChangeDate`**

| **HockeyStack Property** | **Salesforce Field** |
| --- | --- |
| new_value | NewValue |
| old_value | OldValue |
| property | Property |

# **Salesforce Object: Event**

### Action: Event Created / Updated

- **Action Name:** "Event Created" / “Event Updated”
- **Action Date:** Salesforce Field **`CreatedDate`** / **`LastModifiedDate`**

| **HockeyStack Property** | **Salesforce Field** |
| --- | --- |
| event_id | Id |
| event_description | Description |
| event_duration | DurationInMinutes |
| event_type | Type |
| event_subtype | EventSubtype |
| event_location | Location |
| event_subject | Subject |
| event_owner_id | OwnerId.Id |
| event_owner_email | OwnerId.SenderEmail |

### Action: Event Completed

- **Action Name:** "Event Completed"
- **Action Date:** Salesforce Field **`StartDateTime`**

| **HockeyStack Property** | **Salesforce Field** |
| --- | --- |
| event_id | Id |
| event_duration | DurationInMinutes |
| event_subject | Subject |