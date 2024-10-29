# My email sent, open, click numbers look weird

There are some quirks with email data that you should be aware of.

1. Open Rate is calculated as unique opens on unique email campaigns divided by unique sends on unique email campaigns. An individual might open an email multiple times, but it should only be counted once. So if you use Times Done or Unique Users as your count in your email reports, you will see wrong numbers. You should use Unique Action Properties > Email Campaign Name (or similar property). The Unique Action Properties options allow you to count the unique users per unique action property that have done the specified goal.
2. Another common mistake is to breakdown a report by Email Campaign Name (or similar property), count the number of emails sent, and enable attribution.