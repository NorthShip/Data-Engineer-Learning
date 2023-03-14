## Top-level design

### Basic principles  
   #### High cohesion and low coupling  
   - Mainly consider from two perspectives of data business characteristics and access characteristics.
   - Design data with similar or related businesses and the same granularity as a logical or physical model.
   - Store data that is accessed at the same time with a high probability together and store data that is accessed at the same time with a low probability.
   
   #### Separation of core model and extension model
   - Establish the core model and extended model system. The fields included in the core model support commonly used core services, and the fields included in the extended model support the needs of individualization or a small number of applications. Do not let the fields of the extended model invade the core model too much, so as not to damage the structure of the core model Simplicity and maintainability.
   #### Submergence and Singularity of Common Processing Logic
   - The lower-level common processing logic should be encapsulated and implemented at the bottom level of data scheduling dependence. Do not expose common processing logic to the application layer, and do not allow common logic to exist in multiple places simultaneously.
   #### Balance between Cost and Performance
   - Appropriate data redundancy can be used to exchange query and refresh performance, but excessive redundancy and data replication should be avoided.
   #### Data Rollback
   - The processing logic remains unchanged, and the data results are determined to be unchanged if run multiple times at different times.
   #### Consistency, Clear and Understandable Naming
   - Fields with the same meaning in different tables must have the same name, and the names defined in the specification must be used.
   - Table naming must be clear and consistent, and table names must be easy for users to understand and use.
### Architecture Planning
   #### Architecture Methodology
   - TOGAF
   #### Construction Planning
   - Analyze the Current Situation
   - Determine Future Goals
   - Evaluate the Gap
   - Set Action Goals
   - Develop Construction Plans
   - Evaluate Costs and Benefits
   - Make Decisions、
### Evaluation Methods
   #### Benefit Indicators
   - Internal Rate of Return (IRR) and Risk
   - Costs: hardware costs, software costs, personnel costs, maintenance costs
   - Benefits: data assets, core indicators
   - Risk: risk assessment
   #### Technical Indicators
   ##### Performance and Completeness
   - Query performance, loading performance, permission function, monitoring function
   - Integration of databases, FTP, cloud services, and support for multiple interfaces
   ##### Model
   - Data reliability: stability, robustness, and security
   - Data reusability
   - Data accuracy: consistency
   - Response agility
   - Model efficiency: response speed, storage space
   ##### Usability
   - Data warehouses need to be able to connect to common software such as Excel and Tableau.
   - Users can flexibly develop and design reports independently.
   ##### Scalability
   - When data volume and users grow rapidly, the cost and convenience of upgrading hardware.
   ##### Reliability
   - High availability
   - Vendor support
   ##### Data Value
   - Query frequency (popularity), value coefficient
   