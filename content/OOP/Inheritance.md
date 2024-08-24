---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - OOP
Creation Date: 2023-07-23T17:47:10+08:00
Last Date: 2024-08-20T00:56:51+08:00
References: 
---
## Abstract
---
- Extending from existing [[OOP#OOP Class]], the child classes take up all the properties and methods of their parent classes, building up on existing [[Software Engineering/Abstraction|abstraction]]

>[!important]
> Inheritance should be used only when a **clear [[#"Is-a" Relationship|hierarchical relationship]]** and **shared behaviours** exist between the **parent (or base) class** and the **child (or derived) class**. 
> 
> Otherwise, consider using [[OOP#OOP Interface|interfaces]] and [[Encapsulation#"Has-a" Relationship|composition]].

>[!important] Inheritance subtyping relationship
> If $S$ inherits from $T$, then $S :< T$. $S$ is a [[Subtyping|subtype]] of $T$.

## "Is-a" Relationship
---
- "A subclass **is a** superclass", we mean that the subclass [[Inheritance|inherits]] from the superclass. This implies that the **subclass can be used wherever the superclass is expected**, adhering to the "is-a" relationship

>[!important] A less abstracted explanation
> Consider a superclass `Animal` and a subclass `Dog`. In this scenario, a `Dog` **is an** `Animal`. This means `Dog` inherits all the characteristics (methods and fields) of `Animal`. During compilation, a `Dog` object can be assigned the `Animal` data type and utilise methods defined in `Animal`, potentially with modifications through **method overriding** in the `Dog` class.
> 
> This concept promotes [[Polymorphism|polymorphism]], allowing `Dog` objects to be treated as instances of their superclass `Animal`.



# composition
---
## Abstract
- works by passing around the instance of a class between classes 
-  allows us to create  new more complex class out of existing classes, without breaking the abstraction barrier of existing classes
- more flexible than inheritance as  you do not need to implement any abstract methods defined by the parent class you only need to consume it 
- preserves encapusaltion and is reusable
### "Has-A" Relationship
- Composition models a situation where one class contains or uses another class. For example, a `Car` class might have an `Engine` class as a member. This shows that a car "has an" engine.


### **super** in java
- When you create a constructor in a subclass and want to call a constructor of the superclass, the `super` call must be the **first line** of the constructor.
- If you don’t explicitly call `super()`, Java will automatically insert a call to the default no-argument constructor of the superclass.