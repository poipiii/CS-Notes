---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - computer_organisation
Creation Date: 2023-10-07T16:30:00
Last Date: 2024-10-31T00:15:39+08:00
References: 
---
## Abstract
---
- **Increases** the **execution throughput of the machine** by processing multiple independent [[Instruction Stages]] simultaneously, supporting [[Instruction-Level Parallelism]].

>[!important]
> Pipelining **does not reduce the latency of a single instruction**, but it increases the throughput of the entire workload.

>[!important] 2 stages in one slot!
> Since the register file is very fast, the `ID stage` of the **second instruction** and the `WB stage` of the **first instruction** can be **executed concurrently**. This is possible because **writes to the register file always precede reads**.


### Pipeline Width
- The [[Instruction-Level Parallelism]] capabilities - how many [[Instruction]] can be run in parallel in the same time 


## References
---
- [CPU Pipelining - The cool way your CPU avoids idle time!](https://youtu.be/cZIPxra_apA)