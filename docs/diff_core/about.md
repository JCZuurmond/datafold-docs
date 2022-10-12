---
sidebar_position: 1
title: About
---

_data-diff is in shape to be run in production, but also under development._

Formatting option 1:
| 🐞Bugs? 💡Issues?                                                                 | 💬 Prefer to chat live?                                                                                                                                                                                                                                                                           | 💸💸 **Looking for paid contributors!** 💸💸                                                                                                                                                                             |
| :------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Please [open an issue](https://github.com/datafold/data-diff/issues/new/choose)! | Find us in [#tools-data-diff](https://locallyoptimistic.slack.com/archives/C03HUNGQV0S) in the [Locally Optimistic Slack][slack], or [reach out to the product team](https://calendly.com/jp-toor/customer-interview-oss) share any product feedback or feature requests! | We're looking for developers with a deep understanding of databases and solid Python knowledge. [**Apply here!**](https://docs.google.com/forms/d/e/1FAIpQLScEa5tc9CM0uNsb3WigqRFq92OZENkThM04nIs7ZVl_bwsGMw/viewform) | 

Formatting option 2:
- 🐞Bugs? 💡Issues? 
  - Please [open an issue](https://github.com/datafold/data-diff/issues/new/choose)!
- 💬 Prefer to chat live? 
  - Find us in [#tools-data-diff](https://locallyoptimistic.slack.com/archives/C03HUNGQV0S) in the [Locally Optimistic Slack][slack] or
  - [Please reach out to the product team](https://calendly.com/jp-toor/customer-interview-oss) share any product feedback or feature requests!
- 💸💸 **Looking for paid contributors!** 💸💸
  - We're looking for developers with a deep understanding of databases and solid Python knowledge. [**Apply here!**](https://docs.google.com/forms/d/e/1FAIpQLScEa5tc9CM0uNsb3WigqRFq92OZENkThM04nIs7ZVl_bwsGMw/viewform)

----

**data-diff** enables data professionals to detect differences between any two tables.

![](../../static/img/gitlab_access_token.png)

* ⇄  Verifies across [many different databases][dbs] (e.g. PostgreSQL ⇄ Snowflake) or within a database
* 🔍 Outputs [diff of rows](#example-command-and-output) in detail
* 🚨 Simple CLI/API to create monitoring and alerts
* 🔁 Bridges column types of different formats and levels of precision (e.g. Double ⇆ Float ⇆ Decimal)
* 🔥 Verify 25M+ rows in <10s, and 1B+ rows in ~5min.
* ♾️  Works for tables with 10s of billions of rows

# Common use-cases

## Validation of replication, migration, and pipelines

* **Verify data migrations.** Verify that all data was copied when doing a
  critical data migration. For example, migrating from Heroku PostgreSQL to Amazon RDS.
* **Verify data pipelines.** Moving data from a relational database to a
  warehouse/data lake with Fivetran, Airbyte, Debezium, or some other pipeline.
* **Maintain data integrity SLOs.** You can create and monitor
  your SLO of e.g. 99.999% data integrity, and alert your team when data is
  missing.
* **Debug complex data pipelines.** Data can get lost in pipelines that
  may span a half-dozen systems. **data-diff** helps you efficiently track down 
  where a row got lost without needing to individually inspect intermediate datastores. 
* **Detect hard deletes for an `updated_at`-based pipeline**. If you're
  copying data to your warehouse based on an `updated_at`-style column, **data-diff** 
  can find any hard-deletes that you may have missed.
* **Make your replication self-healing.** You can use **data-diff** to
  self-heal by using the diff output to write/update rows in the target
  database.

## Comparing tables within one database to validate successful transformaitons

* **Inspect differences between branches**. Make sure your code results in only expected changes.
* **Validate stability of critical downstream tables.** When refactoring a data pipeline, rest assured
that the changes you make to upstream models has not impacted critical downstream models depended on
by users and systems.
* **Conduct better code reviews.** No matter how thoughtfully you review the code, run a diff to 
ensure that you don't accidentally approve an error.