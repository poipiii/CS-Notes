---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - computer_organisation
Creation Date: 2023-10-15T19:39:44
Last Date: 2024-10-24T08:52:44+08:00
References: 
description: Discusses the concept of asynchronous and synchronous sequential circuits, touching on level-sensitive and edge-triggered circuits, latches and flip-flops, Emphasising the benefits of synchronization in the design and analysis of circuits.
sr-due: 2024-03-13
sr-interval: 21
sr-ease: 236
aliases:
  - ../../Computer-Organisation/Circuits/Sequential-Circuits/Synchronous-Sequential-Circuit
---
## Abstract
---
- Present output = [[Combination Circuit]] + [[#Sequential Circuit State]]
- The digital circuit that is used to build [[Register]] and [[Main Memory]] etc

## Asynchronous Sequential Circuit
---
- [[Sequential Circuit]] that is [[#Level Sensitive]], thus the changes to state are not **syn·chro·nized** to a particular timing
- Usually operate based on **events** or **conditions**

>[!caution] Limited Control over State Changes
> ![[async_sequential_circuit_state_change_limitation.gif|500]]
> The above 4-bit [[Register]] is made of 4 [[Data Latch]]. When the **Store Input** is active, the above asynchronous circuit will keep updating the state. If we want a particular state, we need to turn the Store Input to inactive which is hard to achieve in a reliable way. Because everything happens in a fraction of a second.
> 
> If we want to have precise control over state changes in a reliable & predicable manner, we can use a [[Sequential Circuit#Synchronous Sequential Circuit]] which is synchronised with a [[Clock Oscillator]].

### Level Sensitive

![[level_sensititve.png|400]]

![[level_trigger.png|400]]


- Also known as **Pulse-triggered**
- Output is affected immediately by the input as long as the control signal is active
</br>

- **Active High** when it is considered to be **active** when **level is high**
- **Active Low** when it is considered to be **active** when **level is low**



## Synchronous Sequential Circuit
---
- [[Sequential Circuit]] that is [[#Edge-triggered]], aka the state only changes at **controlled time interval** achieved with [[Clock Oscillator]], not changing as many times as possible within a continuous period of time

>[!success] Benefit of Synchronisation
>![[sync_sequential_circuit.gif|500]]
> Ability to coordinate and manage the flow of information within the circuit in a reliable & predicable way. 
> 
> The flat parts are the **breathing room** to set things up like turning off the store signal if we want it to stop execution on the [[ALU]], making it easier to **design** and **analyze**.
### Edge-triggered

![[positive_edge_triggered.png|400]]

- Output only changes at a specific time, usually when [[Clock Oscillator#Clock Signal]] change from one edge to another
</br>

**2 types**
- **Positive edge triggering:** Transition from a low voltage (0) to a high voltage (1) on the clock signal
- **Negative edge triggering:** Transition from a high voltage (1) to a low voltage (0) on the clock signal



## Terminologies
---
### Sequential Circuit State
- Also known as feedback
- Past outputs


### Multivibrator
- A class of [[Sequential Circuit]]

>[!important] 3 types
> 1. Bistable (2 stable states), like [[Latch]]
> 2. Monostable or one-shot (1 stable state)
> 3. Astable (no stable state)




