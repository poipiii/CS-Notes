## Abstract 
- prevents the breaking of the abstraction barrier by preventing fields or methods to be accessed by the user

### Data hiding
- in java use can use `private` or `public` to restrict or allow fields or methods inside  or outside the class

| Accessed from     | `private` | `public` |
| ----------------- | :-------: | :------: |
| inside the class  |    ✔️     |    ✔️    |
| outside the class |    ✖️     |    ✔️    |

>[!important]
>### Inside the Class vs. Inside the Object
>Private fields and methods are accessible only within the same class. This means you can access private fields of another object if it’s from the same class.
>
>**Why is this okay?** The person who writes the class (the implementer) can access private fields of any object from that class. This is allowed because it's still within the same class, so the internal details stay hidden from the outside.
>```java 
> class Circle { 
>  private double x, y, r; 
>   public double getArea() { 
> return 3.141592653589793 * r * r; 
>  } 
> public boolean isLarger(Circle c) { 
> return this.r  > c.r; // This is allowed because both objects are from the Circle class 
>  } 
>   }
>    ```

when trying to access, update, or invoke fields or methods with `private` it  will give a compilation error by the compiler.


#### Constructors
- A **method** that initializes an object is called a _constructor_. It cannot be called directly but is invoked automatically when an object is instantiated
- in java it is instantiated with `new` and  _has the same name as the class_ and _has no return type_
#### example
```java
class Circle { 
private double x; 
private double y; 
private double r; 
// Constructor 
public Circle(double x, double y, double r) { 
this.x = x; 
this.y = y; 
this.r = r; 
} 
public double getArea() {
return 3.141592653589793 * this.r * this.r; 
}
}
```

>[!note] In Java
>If there is no constructor given, then a default constructor is added automatically. The default constructor takes no parameter and has no code written for the body. In the case of circle v0.1, the default constructor would be the following.
>```java
>Circle() {
}
>```
>Notice the condition "_if no constructor is given at all_". Therefore, if there is at least one constructor written, then the default constructor will not be added automatically.


### The `this` Keyword
- reference variable that refers back to the particular object instance 
- in the above example `this.x = x` means we want to set the field `x` of this object to the parameter `x`

>[!important]
>if you dont use the this keyword in a constructor and set the parameter `x = x` in the example it is the same as setting the parameter of `x` to `x` so nothing 
>```java
>// Constructor
public Circle(double x, double y, double r) {
  x = x;
  y = y;
  r = r;
}
>


### How does a Constructor work ?
1. Allocate sufficient memory location to store all the fields of the class and assign this reference to the keyword `this`.
2. Invoke the constructor function and passing the keyword `this` _implicitly_.
3. Once the constructor is done, return the reference pointed to by `this` back.




