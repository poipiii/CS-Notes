---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - computer_organisation
Creation Date: 2024-10-24, 07:34
Last Date: 2024-10-24T08:53:53+08:00
References: 
draft: 
description: 
---
## Abstract
---
- [[#Asynchronous Sequential Circuit]] that is able to remember a [[Computer Data Representation#Bit]] when the **input power turns to inactive**

>[!example]
>- [[Set Reset Latch]]
>- [[Data Latch]]


### Steering Gate
- Introduces a **control input** that determines whether the [[Latch]] is in a **transparent**(allows data to pass through) or **opaque** state(holds its current state, blocking any changes from the input)
- When the steering gate is active (usually set to a certain logic level), the latch becomes transparent

>[!important]
> Often used in digital circuits for **synchronization** and **control purposes**.