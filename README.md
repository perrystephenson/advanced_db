# Advanced Database

My notes from the "Advanced Database" subject at UTS. Will be evolving over time - hopefully. Will likely be useful for anyone with a similar level of existing database/SQL knowledge as me, but completely useless for anyone with more/less knowledge. No refunds.

## Key Terms

**OLTP** On-Line Transaction Processing - typically used to drive applications e.g. website databases, CRMs, banking platforms, etc. Queries are typically very simple e.g. `select`, `insert`, `update` but high volume. Throughput, multi-user, concurrency, efficiency are all important. Performance measured in transactions per second. Typically stored in 3NF format, and typically up-to-date at all times as it is likely a system of record.

**OLAP** On-Line Analytical Processing - typically used to support analytical workflows e.g. reporting, dashboarding, analytics, model training, etc. Queries are typically very complex and involve joins, aggregations, etc but low in volume. Performance measured in response time. Typically stored in STAR schema, and typically lags the source system (loaded via a batch ETL job)

**Data Warehouse** Fancy name for an OLAP database aimed at analytical users, with a schema supporting analytics workflows rather than transactional workflows. Typically hosted as it's own platform, isolated from the source systems (which are likely OLTP). "Subject-oriented, integrated, time-variant and non-volatile collection of data in support of managements decision making process." Designed well, data warehouses should lower the cost of information access and support the business. The ETL process should be thorough, robust and well documented, and metadata should be available to tell the end-user about the meaning of the information as well as any transformations and key assumptions.



