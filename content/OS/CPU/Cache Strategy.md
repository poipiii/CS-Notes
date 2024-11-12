---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - computer_organisation
Creation Date: 2024-11-06, 17:12
Last Date: 2024-11-06T17:38:44+08:00
References: 
draft: 
description: 
---

## Write-through Cache Strategy
---
![[write_through_cache.png|500]]

- Data is written to both [[Cache Server]]/[[CPU Cache]] and the [[Database]]/[[Main Memory]] at the same time

>[!important]
> This **ensures consistency** between the cache server and the database. However, it **increases write latency** because write operations are **limited by the speed of main memory**. This is a feasible solution **if write operations are infrequent**. Alternatively, a **write buffer** (as shown above) can **improve write performance**.

## Write-back Cache Strategy
---
- Data is written to [[Cache Server]]/[[CPU Cache]] first, and write to [[Database]]/[[Main Memory]] only when cache is replaced or [[Cache Eviction|evicted]]

>[!important]
> This approach offers **low write latency**. However, it risks **data loss in the event of system failures**, as the cache server stores data in **volatile main memory**.

>[!important] Boost efficiency
> To **reduce unnecessary write-backs**, each cache block can be assigned a **dirty bit**. This bit is flipped from `0` to `1` when the **data within the cache block is modified**. A write-back operation is **only performed if the dirty bit is set** when the cache block needs to be replaced.


## Write-around Cache Strategy
---
- Data bypasses [[Cache Server]]/[[CPU Cache]] and goes directly into the [[Database]]/[[Main Memory]]

>[!important]
> This **prevents cache flooding**.
> 
> However, this may **increases read latency** for new data.

## Read-through Cache Strategy
---
- After receiving a request, [[Host#Server]] first checks if the [[Cache Server]] has the available response
- If it has, it sends data back to the [[Host#Client]]
- If not, it queries the [[Database]], stores the response in cache server, and sends it back to the client



