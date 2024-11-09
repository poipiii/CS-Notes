---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - OS
Creation Date: 2023-07-14T20:41:40+08:00
Last Date: 2024-11-09T10:50:16+08:00
References: 
---
## Abstract
---
- A **small-sized** type of volatile computer memory that provides **high-speed data access** to a [[CPU]]. **10-100 times faster** than accessing accessing data from [[Main Memory]]. Built with [[Main Memory#SRAM]]

>[!question] Differences between L1, L2, and L3 CPU Cache?
> **L1 Cache** is known as **primary cache**, runs at the **same speed** as the **CPU**.
> 
> **L2 Cache**, also called the **secondary cache**, is accessed if the CPU cannot find the data in L1 Cache. It can be up to [[Latency Number|10 times slower]] than L1 cache.
> 
> **L3 Cache** is known as **shared cache**, because it is shared between all the [[CPU#CPU Core|cores]] of the CPU. Accessed if data isn't found in L2 cache. L3 Cache is still twice as fast as [[Main Memory#DRAM]].

### Cache Line
- **Unit of transfer** between [[Main Memory|memory]] and [[CPU Cache]]

>[!important] Spatial locality
> A cache line typically contains one or more [[Computer Data Representation#Word|words]]. When the CPU fetches data from memory, it retrieves an entire cache line, not just the specific bytes needed immediately. This takes advantage of [[Cache Locality#Spacial Locality|spatial locality]].

>[!question] How big should a cache line be?
> ![[cache_line_size.png]]
> 
> The **larger the cache line**, the better we can **take advantage of spatial localit**y, since we have more surrounding data cached in the cpu cache.
> 
> However, this brings a **larger miss penalty**, as it **takes longer to transfer** one cache line to the CPU cache.
> 
> Furthermore, CPU cache has a **very limited size**. The larger the cache line, the **fewer cache lines** can be loaded into the CPU cache. Consequently, the cached data tends to be more concentrated, and the **miss rate will increase**.
> 
> Therefore, we need to find a **sweet spot in the cache line size** to **maximise spatial locality** and **reduce the miss penalty and miss rate**.





## References 
---
- [Ep 073: Introduction to Cache Memory - YouTube](https://youtu.be/Bz49xnKBH_0?si=KvO_9Bw3fUl1SnJr)
- [What is a cache line actually? - Quora](https://www.quora.com/What-is-a-cache-line-actually)