---
Author:
  - Xinyang YU
Author Profile:
  - https://linkedin.com/in/xinyang-yu
tags:
  - programming
  - rust
  - java
  - c
  - js
Creation Date: 2023-08-18T20:47:17+08:00
Last Date: 2024-09-01T02:38:18+08:00
References: 
---
## Abstract
---
- Datatype is a **classification of information** and it **decides** the **computation** that can be performed on a variable

>[!success] Benefits of explicit datatype
> 1. Save [[Main Memory]]
> 2. **Generally speeds up** program, refer to this [video](https://www.youtube.com/watch?v=hwyRnHA54lI) for more details. However, use it with caution, refer to the 'Premature optimisation is the root of all evil' below for more information 
> 

>[!bigbrain]- Premature optimisation is the root of all evil
> Something to note is that the size of your data can affect performance as well as memory usage. CPUs are specifically designed to handle 32 bit and 64 bit values very fast, and sometimes, counterintuitively, an 8 bit value may take longer to process. So, as with everything, **premature optimisation** is the **root of all evil**. 
> 
> Keep the integer as a 32 bit integer for now, if you have 10 million of them and have identified it as a problem that it uses too much memory then go down to a u8 or use **bit-packing methods**.
>
 > It's actually even more nuanced than that, because of [[CPU Cache#Cache Locality]], so actually smaller data can be faster and slower depending on the circumstance. But that's very complex and should be left to experimentation **if the need arises**.


### Primitive Datatype
- Also known as **Built-in Datatype**
* Great performance since there isn't much abstraction like [[#Custom Datatype]]
- In [[Java]], primitive datatypes are [[Immutability|immutable]]

### Custom Datatype
- In [[Java]], custom datatypes **aren't** [[Immutability|immutable]]
- Examples are [[OOP#OOP Class]] and [[#Struct]]

>[!caution] Value comparison of custom datatype in Java
> We can't use `==` to compare [[OOP#OOP Object]], because `==` compares the value holding by the variable. However, variables are only holding the [[Memory Address]] to the OOP Object. So if we want to compare the value of OOP Object, we need to use the `equals()` method.



### Complex Type
- Data structures that are built upon simpler types. [[Array]] are a primary example of a complex type in this context




## Rust Datatype
---
### Rust Scalar Type
- Basically [[#Primitive Datatype]], rust supports 
	1. [[Integer Encoding (数字编码)#2's Complement (补码)]] for [[Integer Encoding (数字编码)]] (For [[Integer Encoding (数字编码)#Integer Overflow]], panic in debug mode and go back to the biggest or smallest value in release mode)
	2. [[Floating-Point Encoding (浮点数编码)|Floating Point]]
	3. Boolean
	4. Character
- Refer to [Rust Scalar Data Types](https://rust-book.cs.brown.edu/ch03-02-data-types.html#scalar-types) for more details
### Rust Compound Type
- Basically [[#Custom Datatype]] rust supports **natively**
	1. Array, basically [[Array]]
	2. Tuple, basically array that contains elements of different [[Datatype]]
- Refer to [Rust Compound Data Types](https://rust-book.cs.brown.edu/ch03-02-data-types.html#compound-types) for more details