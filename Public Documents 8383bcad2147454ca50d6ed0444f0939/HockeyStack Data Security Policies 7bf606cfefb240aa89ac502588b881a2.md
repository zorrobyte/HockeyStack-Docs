---
hidden: true
---

# HockeyStack Data Security Policies

At HockeyStack, we put our data’s privacy and security above anything else. This document outlines the measures we put in place to ensure our customers’ data is securely stored and accessed.

## Data Hosting

We use AWS’s IaaS platform to host customer data. Our servers are located in AWS’s eu-central-1 region in Frankfurt, Germany. The hosting complies with [international security guidelines such as SOC1, SOC2, SOC3, and more](https://aws.amazon.com/compliance/programs/).

## Multi-Tenancy and Data Isolation

Our cloud data is isolated from other tenants in the AWS cloud. We also isolate customer data logically using API key-secret combinations and account authentication controls.

## Access Control

At the time of writing, logical access to the production database is only available to C-Level executives in the company, and is governed by non-disclosure and confidentiality agreements. The production application servers can be logically accessed using IAM controls and authentication certificates by senior engineers and higher roles. Access attempts are logged with IP information for tracing and auditing purposes. Physical access to our servers is governed by AWS's [terms](https://aws.amazon.com/service-terms/) and [privacy policy](https://aws.amazon.com/privacy/).

## Application Design & Implementation Controls

All inputs & outputs are sanitized before interacting with customer data. We have an additional layer of checks for data validity & security on every entry into our database to prevent any unauthorized access, data leaks, and malicious insertions. Our code is up to modern standards on protection against common vulnerabilities such as injections, XSS, CSRF etc. Sensitive information such as secret keys and passwords are stored with strong encryption.

All requests to our servers are encrypted with modern standards and are HTTPS-only. All data is also encrypted at rest using AES-256. We use CORS controls to ensure data can only be accessed from our own application through our own validations. All operations on the database and on the application are logged with identifying information so that we can handle unauthorized operations if any arise.

## Incident Management

We have monitors set up for incidents in every part of our application and servers. In the case of an incident, our alerting system notifies the on-call engineer to start an immediate incident response. The team writes up a post-mortem after recovery and shares it with customers on demand.

We take regular backups of our production environment to ensure we can recover data in the event of a data incident. We take out-of-cycle backups before changes that are higher in likelihood to affect the production database, so that we are more ready for recovery.

***

If you have any other questions or issues, you can always reach us through the live support or just sending an email to [hello@hockeystack.com](mailto:hello@hockeystack.com)!
