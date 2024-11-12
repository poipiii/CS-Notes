---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - computer_organisation
Creation Date: 2023-10-07T16:38:28+08:00
Last Date: 2024-10-24T08:39:33+08:00
References: 
sr-due: 2024-02-25
sr-interval: 13
sr-ease: 190
description: A latch that stores a single bit of computer data and allows for resetting the stored bit.
---
## Abstract
---
- [[Latch]] that has one **set input** to store a **single** [[Computer Data Representation#Bit]], and another **reset input** to **reset the stored bit**
</br>

- **Active Set:** turn on the output
- **Inactive Reset:** **locking** the **state of the set input** when **set** goes **inactive**
</br>

- **Active Reset:** turn off the output
- **Inactive Set:** **locking** the **state of the reset input** when the **reset** goes **inactive**

>[!caution] Invalid condition exists!
> When both S & R are 1, the output will be 0 which is invalid

### Circuit 1
![[sr_latch_basic_form.png|700]]
- As shown in the diagram above, we can build it with one [[OR]], one [[NOT]] and one [[AND]]
- Refer to footnote for a nice visualisation on how it works[^1]


### Active-high Latch
![[S-R_Latch_nor.png|700]]
- Can be built with two [[NOR]]
- Refer to footnote for a nice visualisation on how it works[^2]
</br>

>[!question] What is the output when the latch first turned on without any inputs?
> In an ideal case, the output would switch from **on to off in a very short interval**. To human eyes, it would appear to be constantly on.
> 
> However, in the real world, even two identical gates with the same wiring will have slightly different [[Logic Gates#Gate Delay|gate delays]]. Sometimes, one gate may have a shorter delay than the other.
> 
> As a result, the output **can be either `0` or `1`** when the latch is first turned on.
> 
> Refer to footnote for a nice visualisation of how it works[^3]

>[!important] Circuit diagram & truth table
> ![[S-R Latch.png|500]]
> 
> `Q` is the 1 bit storage. Below is a block diagram:
> 
> ![[S-R_Latch_diagram.png|200]]

## Gated S-R Latch
---
![[gated_sr_latch.png|500]]

- [[Set Reset Latch#Active-high Latch]] made with [[Latch#Steering Gate]] and active-low latch
- Only active when `EN` is high

[^1]: [[#Circuit 1]] (From `1:15` to `2:36`)
![How Do Computers Remember? - YouTube](https://youtu.be/I0-izyq6q5s?si=uCiyGmIsDyOfcte9)
[^2]: [[#Circuit 2]] (From `2:57` to `4:33`)
![How Do Computers Remember? - YouTube](https://youtu.be/I0-izyq6q5s?si=uCiyGmIsDyOfcte9)
[^3]: [[#Circuit 2]] Race Condition (From `5:56` to `7:35`)
![How Do Computers Remember? - YouTube](https://youtu.be/I0-izyq6q5s?si=uCiyGmIsDyOfcte9)