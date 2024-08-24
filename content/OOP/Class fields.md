## Static Fields
- keyword in java to make a method,variable, subclass in a class have only 1 instance 
- hence no mater how many instances of a class you create they will all share the same static field  containing the same value 

>[!important]
>- you cannot use the `this` keyword on a static field because it is attached to the class not the particular instance 
>- java will thow the following error when you try to use this on a static field 
>```
>_.java:_: error: non-static variable this cannot be referenced from a static context
>      return this.id;
   >            ^
>```
