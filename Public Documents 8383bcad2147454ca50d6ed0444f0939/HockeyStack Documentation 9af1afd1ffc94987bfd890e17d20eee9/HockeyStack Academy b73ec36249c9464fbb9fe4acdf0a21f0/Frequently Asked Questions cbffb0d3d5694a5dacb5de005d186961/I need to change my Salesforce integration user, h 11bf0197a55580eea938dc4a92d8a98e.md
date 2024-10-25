# I need to change my Salesforce integration user, how can I do it?

1. Take a screenshot of Track Date Properties and the Settings > API & Integrations > Salesforce > Configure screen.
2. Disconnect your Salesforce user, and reconnect.
    1. Here you will be met with Keep Data and Delete Data options. Delete Data would run a full resync once reconnected. Keep Data would continue incremental syncs from where it left off.
3. You will see that Track Date Properties and the Salesforce Configure screen have been cleared out. Install the configurations once again based on the screenshots you took in step 1.
4. Monitor the configurations and the numbers over the next day or so to make sure it is stable and data is pulling.