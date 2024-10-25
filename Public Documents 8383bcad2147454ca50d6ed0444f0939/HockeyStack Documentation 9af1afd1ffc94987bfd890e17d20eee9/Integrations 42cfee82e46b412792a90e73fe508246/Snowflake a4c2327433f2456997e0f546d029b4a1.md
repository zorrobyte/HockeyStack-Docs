# Snowflake

HockeyStack’s Snowflake connector is usually custom built around the customer’s own infrastructure and pulls data specific to the customer’s system from Snowflake into our own database.

This usually includes pulling certain user profile data or mapping revenues from offline opportunities to the main CRM activity etc. Depending on your needs, we can arrange a call to go over what data is necessary to pull and what is the process of making it available.

<aside>
💡 All we need from the customer’s relevant tech team is where we can find the requested data in Snowflake and a way to connect to the instance.

</aside>

## Connecting to Snowflake

In order to connect to your Snowflake instance, we need some credentials and permissions.

- If you are using email based identification, you can invite `dev@hockeystack.com` to your instance.
- If you have an IP whitelist in place,  you should add the following IP addresses: `3.68.172.249` and `35.157.54.242`.
- Depending on your use case, you can give our connector either `read-only` or also `write` permissions to specific tables and databases.

We are using Node.js to facilitate the connection and host the workers. You can find the necessary documentation for how the connection works for Node.js here: [https://docs.snowflake.com/en/developer-guide/node-js/nodejs-driver-connect](https://docs.snowflake.com/en/developer-guide/node-js/nodejs-driver-connect)

## Pulling data from Snowflake

In order to pull data from your Snowflake instance, we have workers in place that run based on a cron schedule. This is usually configured to run on a daily basis but it is customizable per customer.

The workers will query the right Snowflake tables and process it in our own servers to be inserted into our own database.

We need to first have a backfill of the historical data that takes more time but is required to have all the necessary data in our system. Afterwards, the cron based jobs will query the data until the connection to Snowflake is closed.

## Pushing data to Snowflake

In order to push data to your Snowflake instance, we have workers in place that run based on a cron schedule. This is usually configured to run on a daily basis but it is customizable per customer.

The workers will query our own database and process it in the correct format before pushing it to the designated destination in your Snowflake instance. You will be able to choose what data you want sent and in what format. All we need beforehand is validating that the table and the columns have the correct data types.

We have the option to either append new rows to the Snowflake tables or clear and rewrite to it depending on your use case.