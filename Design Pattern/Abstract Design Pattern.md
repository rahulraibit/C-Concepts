# What is Abstract Factory Design Pattern

http://csharp-video-tutorials.blogspot.com/2017/08/abstract-factory-design-pattern.html

The Abstract factory pattern provides a way to encapsulate a group of individual factories that have a common theme without specifying their concrete classes

The Abstract Factory Pattern provides an interface for creating families of related or dependent objects without specifying their concrete classes

Abstract Factory pattern belongs to creational patterns and is one of the most used design patterns in real world applications

Abstract factory is a super factory that creates other factories

***We need to Choose Abstract Factory Pattern when***

1. The application need to create multiple families of objects or products
2. We need to use only one of the subset of families of objects at a given point of time
3. We want to hide the implementations of the families of products by decoupling the implementation of each of these operations

***Abstract Factory and Factory Method***

1. Abstract factory pattern adds a layer of abstraction to the factory method pattern
2. Abstract factory pattern implementation can have multiple factory methods
3. Similar products of a factory implementation are grouped in Abstract factory
4. Abstract Factory uses object composition to decouple applications form specific implementations
5. Factory Method uses inheritance to decouple applications form specific implementations