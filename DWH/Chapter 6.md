## ETL
### Extraction
#### 1.Data exploration system

#### 2.Change data capture
##### Based on query
###### Timestamp
- Absolute historical data table with timestamp and self-incrementing column:Directly insert based on timestamp or sequence value as marker position.
- With operation time:Maintain the update field to determine new data.
###### Snapshot
- Full comparison of featureless data tables:Based on unique constraints data comparison, if it does not exist, insert it. If it exists, compare whether the data in the key column is equal. If not, modify it.
##### Based on triggers
##### Based on log parsing

#### 3.Extraction system
- Load raw data all at once.
- Solution for task failure.

### Cleansing
#### Deduplication system
##### Handling stock duplicate data
- using rowid (may need to use window functions to generate), group by, distinct to deduplicate in SQL.
##### Handling incremental duplication issues
- Maintain the key column to the historical record table, and then compare the incremental data. Or use Merge to update historical data to prevent duplicates. Unique constraints can be used to ensure data is not duplicated.

### Data release

#### Fact table loading
| Features               | Transaction Facts             | Cycle Snapshot Facts    | Cumulative Snapshot Facts                         |
|------------------------|-------------------------------|-------------------------|---------------------------------------------------|
| **Time/Period**        | time                          | period                  | multiple points in time with short time spans     |
| **Granularity**        | one transaction fact per line | one time period per row | one business cycle per line                       |
| **Fact table loading** | add                           | add                     | add and modification                              |
| **Fact table update**  | not update                    | not update              | update when new events                            |
| **Time Dimension**     | business date                 | end of period           | multiple business process completion dates        |
| **Fact**               | trading activity              | performance over time   | limit performance across multiple business phases |


#### Slowly changing dimensions
- T1: Do not record historical data, new data overrides old data.
- T2: Set an effective FLAG value (can also use a zipper table, with the latest time).
- T3: Add historical fields, Current and Previous.
- T4: Build a micro dimension using intervals to store values.
- T5: Micro dimensions encapsulate fast changes, record historical data (encapsulate the changing part and query as needed).