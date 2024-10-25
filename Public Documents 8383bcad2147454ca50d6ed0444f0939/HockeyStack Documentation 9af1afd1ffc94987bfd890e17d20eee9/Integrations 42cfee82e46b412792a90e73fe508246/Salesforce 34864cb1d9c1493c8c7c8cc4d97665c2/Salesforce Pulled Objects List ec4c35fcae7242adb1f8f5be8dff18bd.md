# Salesforce Pulled Objects List

See also:

[Properties Pulled from Salesforce](Salesforce%20Pulled%20Objects%20List%20ec4c35fcae7242adb1f8f5be8dff18bd/Properties%20Pulled%20from%20Salesforce%209528239ff8fa4017a0a50b270e21df49.md)

Below is a list of common objects we pull from Salesforce. This includes all of their properties, both pre-defined and custom. However, upon request, we are also able to pull custom objects directly along with their properties.

# Account

## Company Created

Corresponds to a new Account being created.

## Company Property Changed

Corresponds to a tracked property change in the Account object.

# Contact

## Contact Created

Corresponds to a new Contact being created.

## Contact Property Changed

Corresponds to a tracked property change in the Contact object.

# Lead

## Lead Created

Corresponds to a new Lead being created.

## Lead Property Changed

Corresponds to a tracked property change in the Lead object.

# Deal

## Deal Created

Corresponds to a new deal being created.

## Deal Moved to `X`

These are pulled from deal stages, where `X` is the stage name. Each stage change is recorded as an action.

## Deal Property Changed

Corresponds to a tracked property change in the Deal object.

# Event

## Call Created

Corresponds to a new event being logged, which is automatically determined to be a call.

## Meeting Created

Corresponds to a new event being logged, which is automatically determined to be a meeting.

## Meeting Completed

Corresponds to a meeting event being completed, determined by its `StartDateTime` property.

## Event Created

Corresponds to a new event being logged, which couldn’t be determined as either a meeting or a call.

# Task

## Email Sent

Corresponds to a new email being sent to a user.

## Call Created

Corresponds to a call being logged

# Campaign Member

## Campaign Subscription Created

Corresponds to a contact being added as a subscribed to a campaign.

## Campaign Subscription Updated

Corresponds to a contact changing its status in a campaign.