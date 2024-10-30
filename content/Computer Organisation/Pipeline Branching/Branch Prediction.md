---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - computer_organisation
Creation Date: 2023-08-27T14:44:00
Last Date: 2024-10-31T00:22:18+08:00
References: 
---
## Abstract
---
- Perform [[Instruction-Level Parallelism]] based on the prediction on if [[Pipeline Branching]] is going out of the loop or going back to the start of the loop
- There are many different [[Branch Prediction Strategies (Heuristics)]]. [[CPU]] usually uses multiple branch predication strategies 

>[!important] Next instruction is fetched immediately
> Branch prediction effectively **fetches the instruction following a conditional branch immediately** after the fetch stage of the branch instruction.

>[!example] Loop predication
> If we predict the loop is going out of the loop, then we will be wrong as many times as the number the loop iterates. We can only be wrong one time if we always predict the execution is going back to the start of the loop which is when the execution is going out of the loop.