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

13. Availability
14. Caching
15. Proxies
16. Load Balancers
17. Hashing
18. Relational Databases
19. Key-Value Stores
20. Specialized Storage Paradigms
21. Replication And Sharding
22. Leader Election
23. Peer-To-Peer Networks
24. Polling And Streaming
25. Configuration
26. Rate Limiting
27. Logging And Monitoring
28. Publish/Subscribe Pattern
29. MapReduce
30. Security And HTTPS
31. API Design
