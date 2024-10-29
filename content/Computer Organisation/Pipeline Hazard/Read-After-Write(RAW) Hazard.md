---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - computer_organisation
Creation Date: 2023-08-18T20:46:00
Last Date: 2024-10-29T07:58:01+08:00
References: 
---
## Abstract
---
![[Read-After-Write(RAW) Hazard.png|500]]

* `x` is only available at `t=5`, as that's when the first [[Instruction|instruction]] (`x <- y + z`) completes. However, the second instruction (`w <- x`) requires `x` at `t=3`. If not handled properly, this discrepancy can lead to incorrect results.

>[!question] How to handle this?
> A RAW (Read After Write) hazard can be addressed with a [[Pipeline Stall]] which is a performance hit. Luckily, we can optimise this using [[Operand Forwarding]] and [[Out-of-Order Execution]].