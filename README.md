# Advanced Database

My notes from the "Advanced Database" subject at UTS. Will be evolving over time - hopefully. Will likely be useful for anyone with a similar level of existing database/SQL knowledge as me, but completely useless for anyone with more/less knowledge. No refunds.

## Key Terms

**OLTP** On-Line Transaction Processing - typically used to drive applications e.g. website databases, CRMs, banking platforms, etc. Queries are typically very simple e.g. `select`, `insert`, `update` but high volume. Throughput, multi-user, concurrency, efficiency are all important. Performance measured in transactions per second. Typically stored in 3NF format, and typically up-to-date at all times as it is likely a system of record.

**OLAP** On-Line Analytical Processing - typically used to support analytical workflows e.g. reporting, dashboarding, analytics, model training, etc. Queries are typically very complex and involve joins, aggregations, etc but low in volume. Performance measured in response time. Typically stored in STAR schema, and typically lags the source system (loaded via a batch ETL job)

**Data Warehouse** Fancy name for an OLAP database aimed at analytical users, with a schema supporting analytics workflows rather than transactional workflows. Typically hosted as it's own platform, isolated from the source systems (which are likely OLTP). "Subject-oriented, integrated, time-variant and non-volatile collection of data in support of managements decision making process." Designed well, data warehouses should lower the cost of information access and support the business. The ETL process should be thorough, robust and well documented, and metadata should be available to tell the end-user about the meaning of the information as well as any transformations and key assumptions.

**ACID Properties** Atomicity, Consistency, Isolation, and Durability. 

> *Atomicity* - This property states that a transaction must be treated as an atomic unit, that is, either all of its operations are executed or none. There must be no state in a database where a transaction is left partially completed. States should be defined either before the execution of the transaction or after the execution/abortion/failure of the transaction.

> *Consistency* − The database must remain in a consistent state after any transaction. No transaction should have any adverse effect on the data residing in the database. If the database was in a consistent state before the execution of a transaction, it must remain consistent after the execution of the transaction as well.

> *Isolation* − In a database system where more than one transaction are being executed simultaneously and in parallel, the property of isolation states that all the transactions will be carried out and executed as if it is the only transaction in the system. No transaction will affect the existence of any other transaction.

> *Durability* − The database should be durable enough to hold all its latest updates even if the system fails or restarts. If a transaction updates a chunk of data in a database and commits, then the database will hold the modified data. If a transaction commits but the system fails before the data could be written on to the disk, then that data will be updated once the system springs back into action.

Databases have a **Transaction Management System**, which is responsible for enforcing and implementing the ACID properties - which is how they can maintain concurrency. SQLite perhaps doesn't have one? Excel definitely doesn't have one. Data warehousing requires *dilution* of the ACID properties, which is part of the point of the course.
