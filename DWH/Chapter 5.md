## Data Warehouse Modeling
### Modeling Methodology:
Real world --> Symbolic world (Conceptual model) --> Data structure world (Logical model) --> Specific database (Physical model)

- Conceptual model: Abstraction of the real world into a symbolic system (ER diagram: Entity, Attribute, Relationship)
- Logical model: Abstraction of the symbolic system into a data structure (Relational model: Table | Hierarchical model: Document | Network model: Graph)
- Physical model: Implementation of the logical model

### Data Warehouse Modeling Methods:
- Normalized modeling: ER diagram
- Dimensional modeling: Star schema, Snowflake schema
- Data Vault: It emphasizes the establishment of an auditable foundation data layer, which emphasizes the historical, traceable, and atomic nature of data, without requiring excessive consistency processing and integration of data; at the same time, it organizes enterprise data into a structured manner based on the theme concept and introduces further occurrence processing to optimize the model to cope with the scalability of the contingency system, Hub, Link, Satellite.
### Hierarchy and Theme
#### Reasons for hierarchy:

- Decompose tasks
- Encapsulate reuse
- Isolate coupling
- Trace data lineage

#### Data buffer layer (ODS)
Incremental storage: Incremental storage on a daily basis, with business date as partition, each partition stores daily incremental business data
Full storage: Full storage on a daily basis, with business date as partition, each partition stores full snapshot
Zipper storage: The zipper storage records all change data with a daily granularity by adding two timestamp fields (start_dt and end_dt), and the partition field is usually these two timestamp fields.

#### Data Warehouse layer (DW)
Detailed granularity fact layer (DWD): Divided into topics, the finest granularity (business perspective)
Common granularity summary layer (DWS): Aggregated by time granularity (metric perspective)

#### Data application layer (APP)
Specific customized data applications

#### Common Theme Model:
- FS-LDM
- Broker Modeling Method IBR:The abstract model uses the "Identity-Behavior-Relevance" (IBR) design method to design.
The identity (Identity) is the core, and all kinds of market behaviors (Behavior) are extended, and the relevant relationships (Relevance) are summarized.