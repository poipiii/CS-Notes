---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - system_design
Creation Date: 2024-11-06, 17:17
Last Date: 2024-11-06T17:18:26+08:00
References: 
draft: 
description: 
---
## Abstract
---
- Once the [[Cache Server]] is full, any requests to add items to the cache server might cause existing items to be **removed**
- Can be handled gracefully with [[#Eviction Policy]]

### Eviction Policy
- Strategies to handle [[Cache Eviction]]
- One common strategy is [[LRU]]

>[!important] Other common policies
> **First in first out (FIFO)**
> - Removes the oldest items first.
>   
> **Least frequently used (LFU)**
> - Removes the least often accessed items.