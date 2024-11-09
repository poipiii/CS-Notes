---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - computer_organisation
Creation Date: 2024-11-09, 10:52
Last Date: 2024-11-09T15:55:20+08:00
References: 
draft: 
description: 
---
## Abstract
---
```
+-----------------------------------------------------------+
|                        32-bit Address                     |
+-----------------------+------------+----------+-----------+
|         Cache         |    Set     |   Word   |    Byte   |
|          Tag          |   Index    |  Offset  |   Offset  |
|        (28 bits)      |  (1 bits)  | (1 bits) |  (2 bits) |
+-----------------------+------------+----------+-----------+
 ```

- One way to design a [[CPU Cache|CPU cache]] is to have it consist of a number of sets, each containing $n$ [[CPU Cache#Cache Line|cache lines]]. Within a set, a memory block can be placed in any of the $n$ cache lines.
- In the above example, we have a 2-way set associative cache. The [[CPU Cache]] has $2^{1}$ sets, each containing $2$ cache lines. Each contains $2^{1}$ words, and each [[Computer Data Representation#Word|word]] is $2^2$ bytes 

>[!question] What is the benefit?
> ![[2-way_set_associative_cache.png]]
> 
> Set associative caches reduce the likelihood of [[Cache Miss#Conflict Miss|conflict misses]] compared to [[Direct Mapped Cache|direct-mapped caches]]. In a direct-mapped cache, if two **frequently accessed memory locations map to the same cache index, they will constantly evict each other,** causing repeated conflict misses. A set associative cache provides multiple cache lines within each set, allowing these memory locations to **coexist in the cache simultaneously**, minimising conflict misses and improving performance.


>[!question] How is data read?
> ![[set_associative_cache_read_circuit.png|600]]
> 
> 1. We first use the **set index to locate the set**
> 2. We simultaneously "search" on all **valid bit** and **tags** of the set to check if one of the cache line contains data. If it does, and the **tag matches the given address**, we can select the word needed using with a help of a [[Multiplexer]]
> 3. Otherwise, there is a cache miss.