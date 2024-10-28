---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - computer_organisation
Creation Date: 2024-10-25, 08:34
Last Date: 2024-10-28T07:58:51+08:00
References: 
draft: 
description: 
---
## Abstract
---
- We use a **state table** to analyse the behaviour of a [[Sequential Circuit|sequential circuit]]. The state table can be converted into a **state diagram** for better visualisation.

>[!question] How do you construct a state table?
> We need to determine the **state equations for the [[Flip-flop|flip-flop]] inputs**, as well as the **output functions for the circuit outputs**.
> 
> The state table will have $2^{m+n}$ rows if there are $m$ flip-flops and $n$ inputs.

>[!question] What is a state diagram?
> Each **combination of flip-flop values represents a state**, which is shown as a **circle**. 
> 
> Each **arrow** between two circles represents a transition in the sequential circuit, corresponding to **a row in the state table**. 
> 
> A label in the form $a/b$ is attached to each arrow, where $a$ denotes the input and $b$ denotes the output.


## Analyse Next State
---
- We are given the **input equations** for the [[Flip-flop|flip-flop inputs]] and the **current state**. Using the [[flip_flop_characteristic_table.png|characteristic table]], we can **determine the next state**

## Analyse the Input Equations
---
- We are given the the current state and next state of the flip flop. We need to determine inputs value to the flip flops using the excitation table, then obtain the input equation to each inputs of the flip flop using k-map
- We are provided with the **current and next states of the [[Flip-flop|flip-flop]]**. Our task is to **determine the input values** for the flip-flops using the **excitation table** and then **derive the input equations** for each flip-flop input using a [[Karnaugh Map]].