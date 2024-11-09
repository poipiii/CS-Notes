---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - computer_organisation
Creation Date: 2024-11-06, 16:30
Last Date: 2024-11-09T17:22:00+08:00
References: 
draft: 
description: 
---
## Abstract
---
- When the [[CPU]] requests data that is not found in the [[CPU Cache]]
- It requires fetching the data from the slower [[Main Memory]], incurring a higher access time compared to a [[Cache Locality#Cache Hit]]

>[!important]
> The total miss is the sum of [[#Compulsory Miss]], [[#Conflict Miss]] and [[#Capacity Miss]].
> 
> Capacity miss is the **total miss excluding cold miss**, when **conflict miss is zero**. So capacity miss only happens on [[Fully Associative Cache]].

### Compulsory Miss
- Also known as **cold start miss** or **first reference miss**
- First time accessing the data

### Conflict Miss
- Also known as **collision miss** or **interference miss**
- When multiple data mapped to the same [[CPU Cache#Cache Line]]

>[!important]
> This can be reduced with [[Set Associative Cache]]. A [[Direct Mapped Cache]] of size $N$ has about the same miss rate as a [[Set Associative Cache|2-way set associative cache]] of size $N/2$.

>[!important]
> For the same cache size, **conflict miss goes down** with **increasing associativity**. Conflict miss is $0$ for [[Fully Associative Cache]].


### Capacity Miss
- When data is discarded from [[CPU Cache]] as the cpu cache is running out of space 

>[!important]
> For the **same cache size**, capacity miss **remains the same irrespective of associativity**. **Capacity miss decreases** with **increasing cache size**.

## Cache Write Miss
---
- The data isn't in the [[CPU Cache]] when we want to write data back

### Write Allocate
- We can load the entire [[CPU Cache#Cache Line]] into [[CPU Cache]] to write the data
- We can use [[Cache Strategy#Write-through Cache Strategy]] or [[Cache Strategy#Write-back Cache Strategy]] to write back the data to the [[Main Memory]]
- Or we can don't load the cache line to the cpu cache and use [[Cache Strategy#Write-around Cache Strategy]]