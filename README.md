# system-design

## 1. Introduction
<img src="https://user-images.githubusercontent.com/28957748/134184667-4269c336-204c-48a2-abbf-d015b0216413.png" height="300px" />

## 2. What Are Design Fundamentals?
- DFs are building blocks to solve Design Interview questions
- Just like you need to know Data Structure to solve Coding interview questions

## 3. Client—Server Model
- Flow when user enters url on browser and press enter:
  - A req is sent to DNS server, a resolved IP address corresonding to address is sent back to user
  - User uses that IP address as a unique identifier of one entity on the internet, send a message to server (including `src IP` and `dest IP`)
  - Server receives req from client, look at the req to determine what user needs before sending back the resource to `src IP`

## 4. Network Protocols
- HTTP (Hyper Text Transfer Protocol): 
- TCP (Transmission Control Protocol): top of IP, reliable (come in order + error checking), 3-way handshake before actual transmission
- IP (Internet Protocol): used for routing purposes, header contains `src IP` && `dest IP`, limited size, no order

## 5. Storage
- Database: stores data, supports 2 main operations: WRITE (Create, Update, Delete) && READ
- 2 types:
  - In-memory: Fast retrieval, not persist (after shutdown)
  - Disk: Slow, do persist

## 6. Latency And Throughput
- Latency: How long it takes for data to traverse between systems.
  - Specific systems may requires higher latency: online games
- Throughput: How much work can be handled at a time
  - Context :one: 1Gbps connection 
  - Context :two: Refers to amount of reqs that one server can handle at a time
- How to increase throughput:
  - Pay more $$$
  - Add more servers  

## 7. Availability
- What is availability? Resistant to failure or fault-tolerant (server shutdown || db shutdown || ...)
- Why is it important? You can lose customers if they can not access the service
- How to measure availability? Uptime / Total Time (1 Year) ~ 99.999%
- High Availability: More Nines
- SLA/SLO (Service Level Agreement/Objective): 
  - The Service Provider's promise about service's uptime.
  - They will take penalty if they fail to keep up with their words.
- Evaluating a system's availability, must consider all services, what is the core service.
- How to increase Availability? Redundancy
  - Add more servers to avoid single point of failure, having LB to coordinate traffic
  - Add more LBs
- 2 types of Redundancy:
  - Passive: having multiple machines working at the same time, when one goes down, others will take care
  - Active: having one machine working at one time, when it goes down, one machine from the pool takes over

## 8. Caching
- 🥅 Goal: Reduce latency
- Definition: Stores data in a place different from the original one. Only cache data to be read.
- Places to cache:
  - FE: static data, fetch once
  - BE: expensive computations, frequent calls to DB
  - DB: long-running queries that data does change frequently
- 2 types:
  - Write-through: Write to both cache and DB, takes time but high-consistent
  - Write-back: Write to cache only, db will be updated later (intervals), high risk of losing data before db able to sync data
- What types to choose: Depends on the resource and how important it is that resource is up-to-date
  - Comment on youtube: Requires high-accuracy
  - View Count: It's okay be stale for certain amount of time
- Stale data:
  - One that is out-of-date (in cache), that is not in sync with latest one in db
  - Solution: Invalidate
- Eviction policies: We don't want data to be in cache forever
  - LRU: Take the least recently used out
  - LFU: Take the least frequently used out
  - LIFO
  - FIFO

## 9. Proxies
## 10. Load Balancers
- Context: 1 server has limited throughput
- Scaling:
  - Vertical
  - Horizontal: Add more servers => need for a LB
- What is a LB:
  - Server or reverse proxy (acts on behalf of server)
  - Balance reqs between servers
- Types:
  - Hardware: Dedicated machine
  - Software (our focus)
- Server selection strategies:
  - Random: Naive, inconsistent, imbalance
  - Round-Robin: Select one by one alternately
  - Round-Robin Weighted: Put a weight on prioritized server (powerful one) so more traffic is directed for that one
  - Performance-based: Frequently do health check amongst servers, select one highly-performant
  - IP-based:  
    - Hash ip to get an unique number x
    - x % numOfServers => index of server
    - Pros: 1 ip / 1 server, reqs from 1 user comes back to same server, so never miss the cache
    - Cons: In case we add or remove servers, mapping will change
- Can use multiple selection strategies for one system.

## 11. Hashing
- Context: Server selection algorithm of LB (ip based)
- Problem with ordinary ip-based:
  - IP % numOfServers => index of server
  - As numberOfServers changes, the mapping between IP and Server will also change
#### :one: Consistent Hashing
<img height="200px" src="https://vitalflux.com/wp-content/uploads/2017/10/Screen-Shot-2017-10-10-at-9.01.36-AM.png" />

- As numberOfServers changes (add servers || existing one goes down) most of mappings will not change
- One server gets lot of load? Virtual servers

###### 🚀 My Impl: https://github.com/vnscriptkid/consistent-hashing

#### :two: Rendezvous Hashing

19. Relational Databases
20. Key-Value Stores
21. Specialized Storage Paradigms
22. Replication And Sharding
23. Leader Election
24. Peer-To-Peer Networks
25. Polling And Streaming
26. Configuration
27. Rate Limiting
28. Logging And Monitoring
29. Publish/Subscribe Pattern
30. MapReduce
31. Security And HTTPS
32. API Design
