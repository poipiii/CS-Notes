---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - OS
  - computer_organisation
Creation Date: 2023-10-07T16:38:29+08:00
Last Date: 2024-10-28T08:05:46+08:00
References: 
---
## Abstract
---
- Also known as **RAM** (**Random-access Memory**)
- Made of [[#Memory Element]], which can be assessed using [[#Physical Address]] in a [[Memory Address#Random Access Addressing]] manner which is very efficient, and we use [[#Memory Frames]] for easier memory management 

>[!important]
> Data stored is lost when power is off!


### Memory Element
- A device which can remember value **indefinitely**
- Change value on command from its inputs
- A basic unit of storage element, able to store 1 [[Computer Data Representation#Bit]]
- 2 Types - [[Latch]] & [[Flip-flop]]

### Physical Address
- The address that points to a collection of [[#Memory Element]]
- Usually one physical address points to 8 memory elements to form one [[Computer Data Representation#Byte]]

### Memory Frames
- **Fixed-size blocks** that are obtained by dividing the [[Main Memory]]
- All frames share the same size 
- Size determined by the [[Kernel]] & [[Instruction Set Architecture (ISA)]]
- Represent actual Main Memory blocks that hold [[Data]] & [[Instruction]]


## SRAM
---
- Stands for **S**tatic **R**andom **A**ccess **M**emory
- A type of [[Main Memory]] characterised by its fast access speeds, but generally higher cost and lower density (stores less data per unit area)
- Commonly used to build [[CPU Cache]] and [[Register]] etc

>[!important]
> - SRAM will **hold** its **data permanently** in the **presence of power**
> - Faster than [[#DRAM]]

>[!question] How does it work?
> SRAM is typically built using [[Flip-flop|flip-flops]], with each flip-flop **holding one bit**. If each register is 32 bits, we **arrange 32 flip-flops in a row**. All flip-flops connect to a **common input and output data line**. A **control line**, connected to all flip-flops, specifies whether we want to read from or write to the flip-flops. The **address activates a particular row** of flip-flops.
## DRAM
---
- Stands for **D**ynamic **R**andom **A**ccess **M**emory
- The **'RAM'** that is commonly known to the consumers 

>[!important]
> DRAM **decays in seconds** and thus must be periodically [refreshed](https://en.wikipedia.org/wiki/Memory_refresh "Memory refresh"). Thus Slower than [[#SRAM]].

>[!important]
> [DDR SDRAM](https://en.wikipedia.org/wiki/DDR_SDRAM) is the DRAM that is commonly found in our machines, the common size is 8GB and 16GB.
> 
> [GDDR SDRAM](https://en.wikipedia.org/wiki/GDDR_SDRAM) is the DRAM that is commonly found in [[GPU]], supports **high volume** of **data transfer**.

## References
---
- [Static random-access memory - Wikipedia](https://en.wikipedia.org/wiki/Static_random-access_memory)
- [DDR SDRAM - Wikipedia](https://en.wikipedia.org/wiki/DDR_SDRAM)
- [GDDR SDRAM - Wikipedia](https://en.wikipedia.org/wiki/GDDR_SDRAM)