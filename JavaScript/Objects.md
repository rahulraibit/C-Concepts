## Note

JavaScript has one complex data type, the Object data type, and it has five simple data types: Number, String, Boolean, Undefined, and Null. Note that these simple (primitive) data types are immutable (cannot be changed), while objects are mutable (can be changed)

## Object Data Properties Have Attributes

Each data property (object property that store data) has not only the name-value pair, but also 3 attributes (the three attributes are set to true by default):
— Configurable Attribute: Specifies whether the property can be deleted or changed.
— Enumerable: Specifies whether the property can be returned in a for/in loop.
— Writable: Specifies whether the property can be changed.

## Creating Objects
These are the two common ways to create objects

1. Object Literals
The most common and, indeed, the easiest way to create objects is with the object literal described here

```
var mango = {
color: "yellow",
shape: "round",
sweetness: 8,

howSweetAmI: function () {
console.log("Hmm Hmm Good");
}

```

2. Object Constructor
The second most common way to create objects is with Object constructor. A constructor is a function used for initializing new objects, and you use the new keyword to call the constructor.

Prototype Pattern for Creating Objects

function Fruit () {

}

`Fruit.prototype.color = "Yellow";
Fruit.prototype.sweetness = 7;
Fruit.prototype.fruitName = "Generic Fruit";
Fruit.prototype.nativeToLand = "USA";

Fruit.prototype.showName = function () {
console.log("This is a " + this.fruitName);
}

Fruit.prototype.nativeTo = function () {
            console.log("Grown in:" + this.nativeToLand);
}`

Note

Property names can be a string or a number, but if the property name is a number, it has to be accessed with the bracket notation

`var ageGroup = {30: "Children", 100:"Very Old"};
console.log(ageGroup.30) // This will throw an error
// This is how you will access the value of the property 30, to get value "Children"
console.log(ageGroup["30"]); // Children

//It is best to avoid using numbers as property names.`

