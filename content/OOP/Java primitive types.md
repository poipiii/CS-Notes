
## abstract
in java Primitive types are types that hold numeric values (integers, floating-point numbers) as well as boolean values (`true` _and_ `false`).

>[!important]
>Unlike reference types, primitive type variables never share their value with each other, i.e., if we have:
>>`i` and `j` each store a copy of the value `1000` after Line 2. Changing `i` on Line 3 does not change the content of `j`
>
>```
>int i = 1000;
int j = i;
i = i + 1 


### primitive types
| **Kinds**          | **Types** | **Sizes** |
| ------------------ | --------- | --------- |
| **Boolean**        | boolean   | 1-bit     |
| **Character**      | char      | 16-bit    |
| **Integral**       | byte      | 8-bit     |
|                    | short     | 16-bit    |
|                    | int       | 32-bit    |
|                    | long      | 64-bit    |
| **Floating-Point** | float     | 32-bit    |
|                    | double    | 64-bit    |


### references
[2.variable and types ](https://nus-cs2030s.github.io/2324-s2/02-type.html)
