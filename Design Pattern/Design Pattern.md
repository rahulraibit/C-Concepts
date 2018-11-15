
# 3 Types of design pattern

Evolution from Gangs of 4 books

***Creational Design Pattern***

This deals with object creation and initilization of the object. This pattern give flexibility to the progrmmer to decide which object needs to be created in a given case.

eg. Singlaton, Factory, Abstract Factory, builder, prototype.

***Structural***

This deal with class and object composition. This pattern focus on decoupling interface and implementation of class and there objects.

Eg Adapter, Facad and Bridge.

***Behavioural***

This type deals with communication between class and object

Eg. Chain of Responsiblity, Command, Interprator etc.


***Builder Vs Factory and Abstract Factory***

Builder design pattern encapsulates complex creation into a single method. 

Builder design pattern focuses on construction of object in a step by step manner whereas Abstract factory pattern is used to solve problems related to the creation of families of products.

Builder design pattern returns the object after step by step construction of the complex object where as in Abstract factory or Factory pattern, we return the created product immediately.

To conclude, many application designs start out using Factory which is less complex and evolve towards Abstract Factory and Builder as the complexity increases with a demand of flexibility.