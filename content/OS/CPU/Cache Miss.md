---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - computer_organisation
Creation Date: 2024-11-06, 16:30
Last Date: 2024-11-06T17:42:43+08:00
References: 
draft: 
description: 
---
## Abstract
---
- When the [[CPU]] requests data that is not found in the [[CPU Cache]]
- It requires fetching the data from the slower [[Main Memory]], incurring a higher access time compared to a [[Cache Locality#Cache Hit]]

### Compulsory Miss
- Also known as **cold start miss** or **first reference miss**
- First time accessing the data

### Conflict Miss
- Also known as **collision miss** or **interference miss**
- When multiple data mapped to the same [[CPU Cache#Cache Line]]

### Capacity Miss
- When data is discarded from [[CPU Cache]] as the cpu cache is running out of space 

## Cache Write Miss
---
- The data isn't in the [[CPU Cache]] when we want to write data back

### Write Allocate
- We can load the entire [[CPU Cache#Cache Line]] into [[CPU Cache]] to write the data
- We can use [[Cache Strategy#Write-through Cache Strategy]] or [[Cache Strategy#Write-back Cache Strategy]] to write back the data to the [[Main Memory]]
- Or we can don't load the cache line to the cpu cache and use [[Cache Strategy#Write-around Cache Strategy]]