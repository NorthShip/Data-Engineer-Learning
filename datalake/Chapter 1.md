## Definition
### Trends in the Development of Data Analysis Systems

#### Shift from descriptive to predictive analysis
Instead of displaying the current state of data through reports and visualizations, the use of artificial intelligence, machine learning, and other techniques has enabled the prediction of future data patterns.

#### Shift from non-real-time to real-time analysis
Business decision-makers require faster access to data to adjust their strategies in response to market changes. Real-time analysis is achieved through big data analytics methods such as in-memory computing and message queues.

#### Shift from structured to multimodal data
Combining structured and unstructured data using natural language processing, speech recognition, and image recognition technologies.

#### Shift from isolated systems to data integration
Integrating data storage from multiple heterogeneous systems to create a unified view.

### Key points
- Storage of raw data, support for multimodal data, and a unified external access interface. 
- According to the definition of data lakes in the paper, HDFS is itself a data lake. 
- Hudi, Iceberg, and Delta Lake are middleware for organizing data between storage and computing engines, providing higher real-time capabilities and transaction support for streaming and batch computing on HDFS data.

### Lakehouse
- Solving the problems of data silos and improving real-time performance in MPP and Hadoop systems.
- Key components: Metadata Gateway, Presto.