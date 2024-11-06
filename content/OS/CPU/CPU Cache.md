---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - OS
Creation Date: 2023-07-14T20:41:40+08:00
Last Date: 2024-11-06T16:27:29+08:00
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

### CPU Cache and Cache Line Internals

```
+-----------------------------------------------------------+
|                        32-bit Address                     |
+-----------------------+------------+----------+-----------+
|         Cache         |   Cache    |   Word   |    Byte   |
|          Tag          |   Index    |  Offset  |   Offset  |
|        (18 bits)      | (10 bits)  | (2 bits) |  (2 bits) |
+-----------------------+------------+----------+-----------+
 ```

- In the above example, the [[CPU Cache]] has $2^{10}$ [[#Cache Line]], each contains $2^2$ words, each [[Computer Data Representation#Word|word]] is $2^2$ bytes 
- Each cache line is indexed with a **cache index**. This allows a CPU cache with limited storage to cover the entire main memory because **multiple physical addresses can map to the same cache line**. However, this mapping also means that multiple physical addresses share the same cache line. To **distinguish between these different addresses**, each cache line includes a **cache tag** that **identifies the specific physical address** currently stored in that line

>[!question] How is cache line updated?
> ![[cpu_cache_cache_line.png|600]]
> 
> 1. We first use the **cache index to locate the cache line**
> 2. We use the **valid bit** to check if the cache line contains data. If it does, and the **tag matches the given address**, we can select the word needed using the **word offset** with a help of a [[Multiplexer]]
> 3. Otherwise, there is a cache miss.






## References 
---
- [Ep 073: Introduction to Cache Memory - YouTube](https://youtu.be/Bz49xnKBH_0?si=KvO_9Bw3fUl1SnJr)
- [What is a cache line actually? - Quora](https://www.quora.com/What-is-a-cache-line-actually)