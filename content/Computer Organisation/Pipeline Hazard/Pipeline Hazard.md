---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - computer_organisation
Creation Date: 2024-10-29, 17:30
Last Date: 2024-10-31T00:20:49+08:00
References: 
draft: 
description: 
---
## Abstract
---
- Problems that prevent next instruction form immediately following previous instruction

### Pipeline Structural Hazard
- Simultaneous use of a hardware resource which can be handle by [[Pipeline Stall]] or divide the stage into 2 parts, for example **register stage can be divided into write and read**. WB writes back first followed by ID reads 

### Pipeline Data Hazard
- A [[Pipeline Hazard]] occurs when an [[Instruction]] depends on the result of a previous instruction. This can be managed using [[Operand Forwarding]] and a [[Pipeline Stall]]
- One common example is [[Read-After-Write(RAW) Hazard]]


### Pipeline Control Hazard
- A situation that occurs in a pipeline when the flow of instructions is disrupted, usually due to a **branch instruction** (like jumps or conditional branches)

>[!caution] Performance hit!
> We need to perform a [[Pipeline Flush]], which results in losing the performance gains from [[Instruction-Level Parallelism]]. To minimise this, we can use [[Branch Prediction]].

>[!important] Solution 1: Early branch
> For [[MIPS]], a pipeline control hazard causes a **3-clock cycle delay** due to [[Pipeline Flush|pipeline flushing]]. A simple approach is to stall the pipeline for three clock cycles until the branch outcome is **determined**.
> 
> Early branching moves the branching decision from the `MEM` stage to the `ID` stage, resulting in only a **1-clock cycle delay** because the branch decision is made during the **second stage** (`ID`). 
> 
> However, if the **branch parameter** depends on an instruction like `add`, there will be a **2-clock cycle delay** since we **need to wait 1 clock cycle** for `add` to calculate the branch parameter in the `ALU` stage. A **3-clock cycle** delay occurs if it’s a `lw` instruction, as we must wait until the `MEM` stage.

>[!important] Solution 2: Delayed branch
> The idea is to move **non-control-dependent** [[Instruction|instructions]] into the $X$ cycles needed to **determine the branch outcome**. This reordering is handled by the [[Language Processors#Compiler|compiler]], allowing the program to continue as long as the **correctness of the program isn't violated**.

## References
---
- [1 3 4 Structural Hazards&Data Hazards - YouTube](https://youtu.be/8yxrT1isnpE?si=YbPeoM2PnfyXTbQz)
