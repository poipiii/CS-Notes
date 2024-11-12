---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - computer_organisation
Creation Date: 2024-10-24, 07:34
Last Date: 2024-10-24T09:25:08+08:00
References: 
draft: 
description: 
---
## Abstract
---
- A form of [[Sequential Circuit#Synchronous Sequential Circuit]]. The output changes are regulated by a [[Clock Oscillator]]

>[!important] Asynchronous inputs
> Asynchronous inputs affect the state of the flip-flop **independently of the clock**.
> 
> - When the **preset (PRE)**, also known as **direct set (SD)**, is `HIGH`, `Q` is immediately set to `HIGH`.
> - When the **clear (CLR)**, also known as **direct reset (RD)**, is `HIGH`, `Q` is immediately cleared to `LOW`.

## J-K Flip-flop
---
- `J` is basically `Set`, `K` is basically `Reset`. Active-high 

>[!important]
> The J-K flip-flop eliminates the invalid state when both `J` and `K` are active, causing the outputs to toggle.


### T Flip-flop
- When `T` is active, it will toggle the outputs of [[#J-K Flip-flop]]