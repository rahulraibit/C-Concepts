***Definition*** : "Structural Design Patterns are Design Patterns that ease the design by identifying a simple way to realize relationships between entities"

From the above definition we can say that 

Structural patterns define how each component or entity should be structured so as to have very flexible interconnecting modules which can work together in a larger system.

A structural design pattern also describes how data moves through the pattern. 
Structural patterns describe how classes and objects can be combined to form larger structures.

These patterns describe how objects can be composed into larger structures using object composition, or the inclusion of objects within other objects.

***Gang of four has defined 7 Structural Design Patterns***

Adapter 
Bridge 
Composite 
Decorator 
Facade  
Flyweight 
Proxy

Let’s now look into the definition of these patterns

***Adapter*** : Match interfaces of different classes.

An adapter allows two incompatible interfaces to work together.
The Adapter design pattern allows incompatible classes to interact with each other by converting the interface of one class into an interface expected by the clients.
Leveraging on Adapter pattern Improves reusability of older functionality.

***Bridge*** : Separates an object’s interface from its implementation 

To Simplify this definition, The bridge pattern uses encapsulation, aggregation, and can use inheritance to separate responsibilities into different classes. 

It Decouples an abstraction from its implementation so that decoupling and abstraction can vary independently",  
The bridge pattern can also be thought of as two layers of abstraction. 

The Bridge pattern is use full when we want to avoid a permanent binding between an abstraction and its implementation
Bridge Patterns enables us to separate the interface from the implementation and Improves extensibility
Also, it hides implementation details from clients

***Composite*** : A tree structure of simple and composite objects 

In object-oriented programming, a composite is an object designed as a composition of one-or-more similar objects, all exhibiting similar functionality. 

The Composite pattern enables us to create hierarchical tree structures of varying complexity, while allowing every element in the structure to operate with a uniform interface.  
The composite pattern describes that a group of objects are to be treated in the same way as a single instance of an object. 

The intent of a composite is to "compose" objects into tree structures to represent part-whole hierarchies. Implementing the composite pattern lets clients treat individual objects and compositions uniformly. 

***Decorator*** : Add responsibilities to objects dynamically 

To simplify this, the Decorator pattern enables us to add or remove object functionality without changing the external appearance or function of the object.
The Decorator pattern attaches additional responsibilities to an object dynamically to provide a flexible alternative to changing object functionality without using static inheritance.

***Facade*** : A single class that represents an entire subsystem 

The Facade pattern provides a unified interface to a group of interfaces in a subsystem.

The Facade pattern defines a higher-level interface that makes the subsystem easier to use with only one single interface.

This unified interface enables an object to access the subsystem using the interface to communicate with the subsystem.

Reduces coupling between subsystems provided if every subsystem uses its own facade pattern and other parts of the system use the facade pattern to communicate with the subsystem.
Façade pattern Shields clients from subsystem components.

***Flyweight*** : A fine-grained instance used for efficient sharing 

The Flyweight pattern reduces the number of low-level, detailed objects within a system by sharing objects.

The Flyweight pattern defines a structure for sharing objects and focuses its capabilities for space efficiency.

Applications that use lots of objects must pay careful attention to the cost of each object. Substantial savings can be achieved by sharing objects instead of replicating them.

Leveraging on Flyweight pattern reduces in the number of objects to handle.

We need to use flyweight pattern when the application uses a large number of objects and the Storage costs are high because of the quantity of objects and when the application does not depend on object identity.

***Proxy*** : An object representing another object  

The Proxy pattern provides a surrogate or placeholder object to control access to the original object.
We should use the proxy pattern when we need a more versatile or sophisticated reference to an object than a simple pointer.
Remote proxy and Virtual proxy are some of the implementations of the Proxy design patterns with virtual proxy being the most common used implementation.