---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - computer_organisation
Creation Date: 2023-07-20T18:20:00
Last Date: 2024-10-30T07:44:08+08:00
References: 
---
## Abstract
---
![[operand_forwarding.png|600]]

- A **tunnel** connects one [[Instruction Stages|Pipeline Stage]] of an [[Instruction]] to a different pipeline stage of another instruction. 
- As shown in the diagram above, we can avoid idle time caused by the [[Instruction Stages#Write Back]] stage of the first instruction

>[!important] Results can't be forwarded
> ![[load_use_data_hazard.png|500]]
> 
> If an instruction that **directly follows a load instruction** uses the data loaded by it, a [[Pipeline Stall|pipeline stall]] is necessary. This stall occurs **because loading data from memory takes one extra CPU cycle**. In this case, we must apply a pipeline stall.

## References
---
- [1 3 4 Structural Hazards&Data Hazards - YouTube](https://youtu.be/8yxrT1isnpE?si=J3GieelUBMxsG9I_)
- [1 3 5 Load use Data Hazard - YouTube](https://youtu.be/V8YFDHft8XA?si=61Ip-5S1LC2ueKGy)