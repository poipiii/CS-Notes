---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - computer_organisation
Creation Date: 2024-10-29, 17:30
Last Date: 2024-10-29T21:02:51+08:00
References: 
draft: 
description: 
---
## Abstract
---
- Problems that prevent next instruction form immediately following previous instruction

### Pipeline Structural Hazard
- simultaneous use of a hardware resource which can be handle by [[Pipeline Stall]] or divide the stage into 2 parts, for example **register stage can be divided into write and read**. WB writes back first followed by ID reads 

### Pipeline Data Hazard
- A [[Pipeline Hazard]] occurs when an [[Instruction]] depends on the result of a previous instruction. This can be managed using [[Operand Forwarding]] and a [[Pipeline Stall]]
- One common example is [[Read-After-Write(RAW) Hazard]]


### Pipeline Control Hazard
- Change in program flow, and we need [[Pipeline Flush]] to handle this. It is hit to the performance. So we can reduce it by [[Branch Prediction]]

## References
---
- [1 3 4 Structural Hazards&Data Hazards - YouTube](https://youtu.be/8yxrT1isnpE?si=YbPeoM2PnfyXTbQz)
