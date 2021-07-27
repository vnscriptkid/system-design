## Comparisons
#### SQL
- Structured in tables, with schemas
- Using JOINs to link tables
- ACID
  * Availability
  * Consistency: write values to table -> able to read exactly those values
  * Integerity
  * Durability
- When? Apps that have lot of transactional operations like banking

#### NonSQL
- 2 types: 
  * persistent (do persist on disk) mongodb 
  * non-persistent (memory db) like Memcache
- 2 types of storing:
  * key-value 
  * document based
- Unstructured, No schemas
- Good for: big data, distributed
- Pros:
  - Easy to scale
  - Quick development (no overhead of changing schema)
- Cons
  - Weak-consistency

## Questions to consider:
* Does app have a lot of transactional operations (high-consistency -> reliable)
* Will schema be changed often
* Will we do a lot of JOINs (analytics)
* How big do you want to scale it?
