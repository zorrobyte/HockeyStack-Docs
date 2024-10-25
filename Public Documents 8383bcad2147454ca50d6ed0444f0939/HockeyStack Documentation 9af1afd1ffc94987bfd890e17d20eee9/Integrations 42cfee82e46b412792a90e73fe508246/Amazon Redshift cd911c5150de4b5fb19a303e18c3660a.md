# Amazon Redshift

## Connecting HockeyStack to Amazon Redshift

Connecting HockeyStack to Amazon Redshift is a straightforward process that involves preparing a table for sync and providing access credentials. Here's a step-by-step guide to help you get started.

### Step 1: Prepare the Table

The first step is to set up the table you want to sync with HockeyStack. The table should have specific columns, including a Timestamp, Identity (Email), and any Other Action Data that you wish to track.

HockeyStack internally records a Last Sync Date, and it will only sync rows where the Last Sync Date is lesser than the Timestamp. If you plan on inserting rows in the past, include an Added or Updated At column. This way, HockeyStack can sync rows where the Last Sync Date is lesser than the Added or Updated At date.

### Step 2: Provide Access Credentials

Once you've prepared the table, the next step is to provide HockeyStack with access credentials. Along with the access details, include a short description of each column in your table. This information will enable HockeyStack to correctly interpret and utilize the data from your Amazon Redshift database.