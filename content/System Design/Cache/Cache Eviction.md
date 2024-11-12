---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - system_design
  - computer_organisation
Creation Date: 2024-11-06, 17:17
Last Date: 2024-11-09T17:44:21+08:00
References: 
draft: 
description: 
---
## Abstract
---
- Once the [[Cache Server]] is full, any requests to add items to the cache server might cause existing items to be **removed**
- Can be handled gracefully with [[#Eviction Policy]]

>[!important] CPU Cache 
> In both [[Set Associative Cache|set-associative]] and [[Fully Associative Cache|fully associative caches]], an [[#Eviction Policy|eviction policy]] is necessary to determine which [[CPU Cache#Cache Line|cache line]] to replace when a new line needs to be loaded. This is because **multiple memory addresses can map to the same set of cache lines**. In contrast, a [[Direct Mapped Cache|direct-mapped cache]] has a **one-to-one mapping between memory addresses and cache lines**. Therefore, when a new line needs to be loaded, the existing line at that specific location is simply replaced.

### Eviction Policy
- Strategies to handle [[Cache Eviction]]
- One common strategy is [[LRU]] which takes advantage of [[Cache Locality#Temporal Locality]]

>[!important] Other common policies
> **First in first out (FIFO)**
> - Removes the oldest items first.
>   
> **Least frequently used (LFU)**
> - Removes the least often accessed items.