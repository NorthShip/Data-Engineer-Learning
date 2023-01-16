## DWH Definition

A Data Warehouse is a **subject-oriented**, **integrated**, **non-volatile**, and **time-variant** collection of data in support of management’s decisions.”Sean Kelly, another leading data warehousing practitioner defines the data warehouse in the following way.
- subject-oriented：Data warehouses are all based on a specific theme, and only data related to the theme are needed, and other irrelevant detailed data will be excluded.  


- integrated：The data in the data warehouse is obtained through systematic processing, summarization and arrangement on the basis of extracting and cleaning the source business system data. Inconsistencies in the source data must be eliminated to ensure that the information within the data warehouse is a consistent global picture of the entire enterprise.


- time-variant：The data in the data warehouse usually contains historical information. The system records the information of the enterprise from a certain point in the past (such as the time when the data warehouse was started) to the current stage. Through this information, the development process and future trends of the enterprise can be analyzed. Make quantitative analysis and forecasts.


- non-volatile：The data in the data warehouse is mainly used for enterprise decision-making and analysis, and the data operations involved are mainly data queries. Once a certain data enters the data warehouse, it will generally be retained for a long time, that is, there are generally a large number of query operations in the data warehouse. , but there are few modification and deletion operations, usually only regular loading and refreshing are required.