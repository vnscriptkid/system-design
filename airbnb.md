# Design Airbnb
https://www.youtube.com/watch?v=YyOXt2MEkv4&t=206s

<img width="1234" alt="high-level" src="https://user-images.githubusercontent.com/28957748/159613344-293f878d-46ee-4ac3-8ff7-6b61f2a594cf.png">

## Notes:
- Elastic Search: fuzzy (take care of miss spell, typos)
- Cassandra: huge amount of reads and writes
- where to place Redis cluster: high-throughput point (searching for rooms)
