## Development preparation
### policy making
#### Table Naming Convention
| layer | Naming convention                                 |
|-------|---------------------------------------------------|
| stg   | stg_{source_db}_{source_table}                    |
| ods   | ods_{source_db}_{source_table}                    |
| dw    | dwd/dws_{domain}_{business_describe}_di/df        |
| dm    | dm_{domain}_{business_describe}_xd/xm/xy          |
| ads   | ads_{business_owner}_{business_describe}_xd/xm/xy |

"di" indicates that the data is incrementally written, and "df" indicates that the data is fully written each time.

"xd/xm/xy" generally refers to the update cycle, for example, "1d" means the update cycle is one day, "1m" is one month, and "7d" is seven days.

#### Field Naming Convention

Generally, a field name should consist of two parts: a prefix and a suffix. The prefix modifies the meaning of the suffix, and there can be multiple prefixes, but only one suffix. The prefix and suffix should be written in camel case with all lowercase letters, with words separated by underscores. Both the prefix and suffix should be written in English words or abbreviations, with the prefix being a verb, adjective, or noun, and the suffix being a noun. Except for specific English abbreviations, full English words should be used as much as possible for field names, and field length should be considered if it is too long. Also, the correct data type should be chosen for different fields, and sensitive fields should be encrypted.


#### Storage Convention

The data in the STG layer is stored in textfile format and retained for 7 days for easy data tracing.
Other layers use orc format for storage.

#### Development Process Specification

- Requirement Application: The demand side submits an application description, which describes the business demand scope, data scope, statistical caliber, data quality requirements, etc. according to the document specification.
- Requirement Research: Conduct business research and data analysis on the content of the requirement application.
- Data Exploration: Based on the requirement research and the content of the requirement application, investigate the entities and attribute content, business processes, data processes, etc. in the business demand. Data exploration runs through the entire process of model design, continuously improving the rationality of model design, and ultimately generating a data exploration report.
- Model Design: It includes three parts: conceptual model design, logical model design, and physical model design.
- ETL Design: Based on the physical model, business logic, and data exploration results, write the data extraction and processing process, including field mapping, conversion methods, association conditions, etc.
- Script Development and Testing: It is the specific program implementation of the MAPPING process completed in accordance with the prescribed script writing specifications.
- Online Application: Please submit an online application on JIRA.
- Model Online: Refers to the model versioning and online operation.
- Model Operation: Refers to the maintenance, changes, and optimization of the model after it is online.

### Equipment Selection
- First-generation data warehouses: Oracle, share disk/share everything (RAC limit: 3-15)
- Second-generation data warehouses: MPP/Vertica, share nothing (MPP limit: 200*15T per node)
- Third-generation data warehouses: Hadoop (Hadoop limit: about 5000 for commercial use)
- Fourth-generation data warehouses: Snowflake, cloud-native, storage and computing separation