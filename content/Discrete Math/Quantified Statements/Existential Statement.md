---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - discrete_math
Creation Date: 2024-02-14, 10:22
Last Date: 2024-08-25T22:07:13+08:00
References: 
draft: 
description: 
---
## Existential Statement
---
$$
\exists x \in D, Q(x)
$$
- Made of [[Predicate#Predicate Symbol]], [[Predicate#Predicate Variable]] & [[Quantifier]]
- `true` iff `Q(x)` is `true for at least one x` in `D`
- `false` iff `Q(x)` is `false for all x` in `D` 
- For simple ones, usually existential comes with [[Propositional Logic#Logical Connectives]]

>[!important]
> $\exists x \in D, Q(x)$ is same as $Q(x_{1}) \lor Q(x_{2}) \lor \ldots \lor Q(x_{n})$.
### Negation of Existential
$$
\neg(\exists x \in D, Q(x)) \equiv \forall x \in D, \neg  Q(x)
$$
- Negation of existential is [[Propositional Logic#Logical Equivalence]] to [[Universal Statement]]
- `ALL ARE NOT`

### Unique Existence
$$
\exists ! x \in D, P(x)
$$
- There exists an unique (one and only one) $x$, such that $P(x)$ is true