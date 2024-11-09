---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - computer_organisation
Creation Date: 2024-11-09, 10:49
Last Date: 2024-11-09T20:56:18+08:00
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
|                 Block              |        Offset        |
|                 Number             |                      |
|               (28 bits)            |       (4 bits)       |
+-----------------------+------------+----------+-----------+
|         Cache         |   Cache    |   Word   |    Byte   |
|          Tag          |   Index    |  Offset  |   Offset  |
|        (18 bits)      | (10 bits)  | (2 bits) |  (2 bits) |
+-----------------------+------------+----------+-----------+
 ```

- In the above example, the [[CPU Cache]] has $2^{10}$ [[#Cache Line]], each contains $2^2$ words, each [[Computer Data Representation#Word|word]] is $2^2$ bytes 
- Each cache line is indexed with a **cache index**. This allows a CPU cache with limited storage to cover the entire main memory because **multiple physical addresses can map to the same cache line**. However, this mapping also means that multiple physical addresses share the same cache line. To **distinguish between these different addresses**, each cache line includes a **cache tag** that **identifies the specific physical address** currently stored in that line

>[!question] How is data read?
> ![[cpu_cache_cache_line.png|600]]
> 
> 1. We first use the **cache index to locate the cache line**
> 2. We use the **valid bit** to check if the cache line contains data. If it does, and the **tag matches the given address**, we can select the word needed using the **word offset** with a help of a [[Multiplexer]]
> 3. Otherwise, there is a cache miss.
