---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - OS
  - computer_organisation
Creation Date: 2024-11-04, 22:53
Last Date: 2024-11-06T16:33:11+08:00
References: 
draft: 
description: 
---
## Abstract
---
![[cache_locality.gif]]
- Also known as **Locality of Reference**
- When we obtain an [[Instruction]] or [[Data]] from [[Main Memory|main memory]], a [[CPU Cache#Cache Line]] is transferred into the [[CPU Cache]]. If we are retrieving the **same data** or **surrounding data**, the [[CPU]] can obtain it directly from the CPU Cache, which is much faster (**10-100 times faster**) than accessing main memory


>[!important] Principle of Locality
> A [[Process (进程)]] accesses only a **small portion** of its [[Memory Address|memory address space]] **within a small time interval**. Thus, a **small** amount of very fast cache memory can provide a **great performance boost**.


### Temporal Locality
- Once an **[[Instruction]] executed** or a piece of **data is accessed**, the element **will be used again** soon

### Spacial Locality
- Once an **[[Instruction]] executed** or a piece of **data is accessed**, its **neighbours will also be accessed** soon

>[!important]
> Spacial Locality has a special **sub-category** called **sequential locality**, which **shines** in cases like executing a **for loop**.

## Average Memory Access Time
---
- **Average memory access time** = [[#Cache Hit|hit rate]] $\times$ hit time $+$ [[Cache Miss|miss rate]] $\times$ miss penalty(time to replace [[CPU Cache#Cache Line]] + hit time)
- Miss rate is basically $1 -$ hit rate

>[!example]
> If the CPU cache hit time is `0.8 ns` and the [[Main Memory#DRAM|DRAM memory]] access time is `10 ns`, the **miss penalty** is $10 + 0.8$ = `10.8 ns`. To achieve an average memory access time of `1 ns`, we need a hit rate of $98\%$.
> 
> Here's how we calculate that:
> 
> Let $h$ be the hit rate. The formula for average memory access time (AMAT) is:
> 
> AMAT = (Hit Rate $\times$ Hit Time) $+$ (Miss Rate $\times$ Miss Penalty)
> 
> We want AMAT to be `1 ns`. Substituting the known values:
> 
> `1 ns` = ($h \times$ `0.8 ns`) $+ ((1 - h) \times$ `10.8 ns`) 
> 
> Solving for $h$:
> 
> - $1 = 0.8h + 10.8 - 10.8h$
> - $9.8 = 10h$
> - $h = 0.98$
> 
> Therefore, the required hit rate is $0.98$ or $98\%$.


### Cache Hit
- When [[CPU Cache]] needed is in [[CPU Cache]]
- Takes about 2 [[Latency Number |clock cycles]]
