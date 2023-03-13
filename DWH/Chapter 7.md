## OLAP
### Definition
OLAP (Online Analytical Processing) is a process of extracting a subset of detailed data from a data warehouse, aggregating it as necessary, and storing it in an OLAP server for analysis by front-end tools.

### Classification:

- ROLAP (Relational OLAP) stores multidimensional data for analysis in a relational database, and selectively defines a set of real views for storage in the relational database according to application needs.
- MOLAP (Multidimensional OLAP) physically stores multidimensional data required for OLAP analysis in the form of multidimensional arrays, forming a "cube" structure.
- Currently, no OLAP system can meet the query needs of all scenarios. The fundamental reason is that no system can achieve perfection in terms of data volume, performance, and flexibility at the same time. Each system needs to make trade-offs between these three aspects during design.

### Common OLAP engines:
- MapReduce-based: Hive
- Cross-data-source in-memory: Presto, Spark SQL
- Pre-aggregation: Kylin
- Real-time ingestion: Druid (consumes data from Kafka queue)
- Single-table performance: ClickHouse