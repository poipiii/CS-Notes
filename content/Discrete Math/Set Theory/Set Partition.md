---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - discrete_math
Creation Date: 2024-02-24, 15:33
Last Date: 2024-09-07T16:00:34+08:00
References: 
draft: 
description: 
---

## Abstract
---
![[union_of_mutually_disjoint_subsets.png|300]]

- A partition of [[Set]] $A$ is a finite or infinite collection of **NOT** [[Empty Set]], [[Mutually Disjoin Set]] that can be chained with [[OR]] to form $A$
</br>


$$
\forall x \in A, \exists ! S \in \zeta (x\in S)
$$

- $S$ is one of the mutually disjoin subset, also known as **component of the partition**
- $\zeta$ is the partition
- So basically each $S$ isn't empty, and its elements are not in other mutually disjoin subset

>[!caution]  Subset can contain duplicate elements
>Given a set $A =\{a,b,c,d,e,f\}$ , 
>
>$\{\{a\},\{b,f,b\},\{c,e,d,e\}\}$ is a valid partition, because it covers all the elements inside set $A$


## Relation from Partition
---
$$
\forall x,y \in A, xRy \leftrightarrow \exists \text{ a component of } S \text{ of } \zeta \text{ s.t. } x,y \in S
$$
- Theorem 8.3.1, [[Relation]] **induced** by [[Set Partition]]
- Two elements are related if and only if they belong to the [[Mutually Disjoin Set]] in the partition. This connection created by the partition is called the **relation induced by the partition**

>[!important]
> - Let $A$ be a [[Set]] with a Partition
> - Let $R$ be the relation induced by the partition
> - Then $R$ is [[Relation Property#Reflexive]], [[Relation Property#Symmetric]] and [[Relation Property#Transitive]]

>[!example]
> ![[relation_induced_by_parititon_example.png]]

>[!example]
> Imagine dividing students in a class into groups based on their favourite sport. The relation induced by this partition would tell us which students share the same sports preference.


