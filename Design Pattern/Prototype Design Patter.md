
Prototype Design Pattern Specify the kind of objects to create using a prototypical instance, and create new objects by copying this prototype"

To simplify, instead of creating object from scratch every time, you can make copies of an original instance and modify it as required. 

Prototype is unique among the other creational patterns as it doesn't require a class but only an end object. 

***We need to choose Prototype Design Pattern when***

Creating an object is an expensive operation and it would be more efficient to copy an object.
System should be independent of how its products are created, composed, and represented.
Objects are required that are similar to existing objects.
We need to hide the complexity of creating new instance from the client.

***Shallow and Deep Copy*** : The idea of using copy is to create a new object of the same type without knowing the exact type of the object we are invoking. 

***Shallow Copy*** : copies an object's value type fields into the target object and the object's reference types are copied as references into the target object.