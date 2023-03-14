## Design Process
![](https://github.com/NorthShip/Data-Engineer-Learning/blob/main/img/dwh%201.png)

### Business Research
Researching business processes, exploring data situations, and analyzing requirements.

###### Example table

| Example Company | Trade | Logistics | Marketing |
|-----------------|-------|-----------|-----------|
| Target          |       |           |           |
| Needs           |       |           |           |
| Data            |       |           |           |
| Application     |       |           |           |

### Division of Data Domain

###### Example table

| Data Domain     | Business Process |
|-----------------|------------------|
| Business data   |                  |
| Log data        |                  |
| Management data |                  |

### Defining Bus Matrix 
Data Domain, Business Process, Data Granularity, Dimension, Atomic Indicator
###### Example table

![](https://github.com/NorthShip/Data-Engineer-Learning/blob/main/img/dwh%202.png)

### Clarifying Statistical Indicators
- Data domain: A collection that abstracts business processes or dimensions for business analysis. Business processes can be summarized as indivisible behavioral events, and indicators can be defined under business processes. A dimension refers to the environment in which a measurement is taken, such as a buyer placing an order, with the buyer being the dimension. To ensure the vitality of the entire system, data domains need to be abstracted and refined, and maintained and updated in the long term, but not changed lightly. When dividing data domains, they should not only cover all current business needs, but also include new business without affecting existing data domains and expanding new data domains.
- Business process: Refers to the business activity events of an enterprise, such as ordering, payment, and refund. A business process is an indivisible behavioral event. In simple terms, a business process is an event in an enterprise's activities.
- Time period: Used to clarify the time range or time point of data statistics, such as the last 30 days, natural week, end of the day, etc.
- Modifier: Refers to the business scenario that limits the abstraction of indicators other than the statistical dimensions. Modifiers belong to a type of modification, such as PC-side, wireless-side, etc. under the access terminal type in the log domain.
- Measurement/Atomic indicator: The atomic indicator has the same meaning as the measurement. It is a measure based on a certain business event behavior, and is an indicator that cannot be further divided in the business definition. It is a noun with a clear business meaning, such as payment amount.
- Dimension: A dimension is the environment of measurement used to reflect a class of business attributes. The collection of such attributes constitutes a dimension, which can also be called an entity object.
- Dimension attribute: A dimension attribute belongs to a dimension. For example, the country name, country ID, and province name in the geographical dimension are all dimension attributes.
- Derived indicator: Derived indicator = Atomic indicator + Business Limitation + Time Period + Granularity Selection
- Total mobile phone category orders by province in the last day = Total order amount + Mobile phone category + Last day + Provincial level
- Derived ratio: Various statistical ratios and proportions.