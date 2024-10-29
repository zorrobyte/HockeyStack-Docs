# Amazon S3

Amazon S3 (Simple Storage Service) is an object storage service used for high-scale data storage and reliability. Due to its flexibility, organizations can use it to store all kinds of data related to their marketing and sales efforts.

As a data platform, our primary goal is to be able to ingest any data from any source you might have. Our S3 integration is designed with the same goal of flexibility.

# What does the data pull look like?

We generally recommend using a format like CSV or Parquet to store the data in S3 that you want HockeyStack to pull.

HockeyStack internally records a Last Sync Date, and it will only sync objects where the Last Sync Date is lesser than the Timestamp. If you plan on inserting rows in the past, include an Added or Updated At column. This way, HockeyStack can sync rows where the Last Sync Date is lesser than the Added or Updated At date.

We first need to pull historical data for the last couple years depending on your needs and then on a daily basis, pull the delta/difference of the data since yesterday.

There are multiple ways to pull data from S3 that we can build depending on the customer needs:

## 1. Exposing S3 Buckets Directly

The first method is exposing the S3 buckets directly for us to ingest through [ClickHouse S3 connector](https://clickhouse.com/docs/en/integrations/s3). ClickHouse is our main analytical database to store every datapoint about your customers.

The table should ideally have some specific columns, including a Timestamp, Identity (Email), and any Other Action Data that you wish to track.

## 2. Using Amazon Athena

The second method is using [Amazon Athena](https://aws.amazon.com/athena/) to connect to S3 and query the data using SQL. For this method, we use the [athena-express package](https://github.com/ghdna/athena-express) from NPM to handle the connection for us.

The caveat with this solution is Athena charges you based on the amount of queries you make which means we would need to set certain limits on how much HockeyStack should be able to query.

<aside>
⚠️ For both of these methods, we suggest creating an IAM User for HockeyStack to be able to read data from S3. We need an AccessKeyID and a SecretAccessKey to facilitate the connection.

For permissions, we would need AmazonS3FullAccess or granular bucket-level read access, and also AmazonAthenaFullAccess if we are using the Athena service.

</aside>

Once we’ve designated which method we would use and have tested our access to be able to pull the right data, you should send a short description of each object type and property in your bucket - however you store the data. This information will enable HockeyStack to correctly interpret and utilize the data from your S3 buckets.

<aside>
💡 There is also a third way where you can create a custom data pipeline to push data into a ClickHouse cluster we create for you so you have control over when and how much data you send.

This method is recommended for more technical customers that want more control and less overhead. However keep in mind that it requires more custom development and engineering resources from your side to implement.

We would also need to have a separate call to go over our own schema and requirements.

</aside>