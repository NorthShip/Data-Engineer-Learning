## DWH Top-level design

1. Basic principles  
   1.1 High cohesion and low coupling  
   - Mainly consider from two perspectives of data business characteristics and access characteristics.
   - Design data with similar or related businesses and the same granularity as a logical or physical model.
   - Store data that is accessed at the same time with a high probability together and store data that is accessed at the same time with a low probability.
   
   1.2 Separation of core model and extension model
   - Establish the core model and extended model system. The fields included in the core model support commonly used core services, and the fields included in the extended model support the needs of individualization or a small number of applications. Do not let the fields of the extended model invade the core model too much, so as not to damage the structure of the core model Simplicity and maintainability.