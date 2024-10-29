---
hidden: true
---

# HockeyStack Raw Data Access

## HockeyStack Raw Data Access

As part of your contract, you may have direct access to the raw data that HockeyStack tracks and unifies about your business. This means that you can directly query the data for your own reporting and BI use cases instead of going through the HockeyStack UI.

⚠️ Beware that this is only intended for technical data analysts to handle for very specific use cases and/or accuracy controls. Otherwise, you are advised to use our dashboard product and export the data through the UI.

We hold this data in a database solution called [ClickHouse](https://clickhouse.com/), hosted by [Altinity Inc](https://altinity.com/). So in order to access it and query the data, you will need to connect to a ClickHouse instance and write its SQL syntax.

## Connecting

You can connect to the ClickHouse instance in two ways:

* Connect through the terminal
* Use the web UI

#### Connect through the terminal

In order to connect through the terminal, you should first download the `clickhouse-client` package. You can follow this link here: [https://clickhouse.com/docs/en/interfaces/cli](https://clickhouse.com/docs/en/interfaces/cli)

After downloading the package, you can write the below command in your terminal to connect. Paste your username to where it says `YOUR_USER_NAME`, given to you by HockeyStack support.

```sql
clickhouse-client -h prod.hockeystack-c7bb.altinity.cloud --port 9440 -s --multiquery --user=YOUR_USER_NAME --password
```

It will then prompt you to enter a password. Enter the password given to you by HockeyStack support.

#### Use the web UI

You can go to this url to directly interface with the ClickHouse instance: [https://prod.hockeystack-c7bb.altinity.cloud:8443/play](https://prod.hockeystack-c7bb.altinity.cloud:8443/play)

Once you arrive, you’ll be prompted to enter your username and password given to you by HockeyStack support.

![Screenshot 2024-01-04 at 11.28.03.png](<HockeyStack Raw Data Access 8ff16975ead443648d9583530943f694/Screenshot\_2024-01-04\_at\_11.28.03.png>)

You can write your queries in the below text input and click Run to see its results.

## Querying

We use ClickHouse as the underlying database for our analytics engine so you should be familiar with the ClickHouse SQL to use this data in your reporting.

You have access to a single table that includes all the necessary metadata (properties for users and companies alike) pre-joined to it.

Here’s the detailed schema of the table:

[Schema](<HockeyStack Raw Data Access 8ff16975ead443648d9583530943f694/Schema 455a6cff1d8940fc9fca9a6d0fbcb169.md>)

❔ If you have any questions regarding the raw data access, you can reach out to us through your Slack channel or email us at hello@hockeystack.com
