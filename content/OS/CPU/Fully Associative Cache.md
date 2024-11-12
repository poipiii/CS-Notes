---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - computer_organisation
Creation Date: 2024-11-09, 16:54
Last Date: 2024-11-09T20:55:35+08:00
References: 
draft: 
description: 
---
## Abstract
---
![[fully_associative_cache_circuitry.png]]

- In a fully associative cache, a [[CPU Cache#Cache Line|cache line]] is not restricted by a cache index or cache set index and can be placed in any location. However, **memory access requires searching all cache lines**

>[!important]
> This approach is **beneficial for very small caches**, as it eliminates [[Cache Miss#Conflict Miss|conflict misses]] by allowing data to reside anywhere within the cache, but it takes a lot more resources to locate the cache.

>[!important] Just consists of 2 parts
> Since each cache line isn't restricted to a certain group of memory addresses, there is no cache set index or cache index. Therefore, the **block number is the same as the tag number for a fully associative cache**.