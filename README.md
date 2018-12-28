# JavaScript-Book

One place JavaScript!

### Table of Contents

- [Design Pattern](#pattern)
- [Callback/ Higher-order Function](#callback)
- [Promises](#promises)
- [Closures](#closures)
- [Pure functions](#pure)
- [Splice vs Slice vs Split](#diffs)
- [Data Types](#datatypes)
- [DOM](#dom)
- [Equality comparisons](#eqality)

<a name=“pattern”/>

#### Design Pattern

- [Singleton Pattern](#singleton)


<a name=“singleton”/>

##### Singleton Pattern: 
The singleton design pattern restricts the instantiation of a function/class to one variable/object.

Uses: 
1. When exactly one variable/object is needed to coordinate actions across the system.
2. Reduce the need of global variables.
3. The getInstance method demonstates another design pattern called Lazy Load.

``` javascript
var Singleton = (function () {
    var instance;
 
    function createInstance() {
        var object = new Object("I am the instance");
        return object;
    }
 
    return {
        getInstance: function () {
            if (!instance) {
                instance = createInstance();
            }
            return instance;
        }
    };
})();
 
function run() {
 
    var instance1 = Singleton.getInstance();
    var instance2 = Singleton.getInstance();
 
    alert("Same instance? " + (instance1 === instance2));  //Output: Same instance? true
}
```

Ref:

https://blog.mgechev.com/2014/04/16/singleton-in-javascript/

https://www.dofactory.com/javascript/singleton-design-pattern

<a name=“callback”/>

#### Callback/ Higher-order Function

A callback function is a function passed into another function as an argument, 
which is then invoked inside the outer function to complete some kind of action.
It is also known as Higher-order Function.

Callback functions are derived from a programming paradigm known as **functional programming.**
Basically, functional programming specifies the use of functions as arguments.

When we pass a callback function as an argument to another function, we are only passing the function definition.
We are not executing the function in the parameter. In other words, we aren’t passing the function with the trailing
pair of executing parenthesis () like we do when we are executing a function.

Callback functions Are **Closures.** Callback function is executed inside the containing function’s body just as if
the callback were defined in the containing function. Hence callback function has access to the function variables as
well as global variables. 

[JsFiddle Example](http://jsfiddle.net/varit05/o3vu14kd/)

<a name=“promises”/>

#### Promises

The promise constructor takes one argument, a callback with two parameters, resolve and reject. 
Do something within the callback, perhaps async, then call resolve if everything worked, otherwise call reject.

A Promise can be:
1. fulfilled - The action relating to the promise succeeded
2. rejected - The action relating to the promise failed
3. pending - Hasn't fulfilled or rejected yet
4. settled - Has fulfilled or rejected

<a name=“closures”/>

#### Closures

Closures are related to function scope. Every function in JS is closure.
Whenever you create a function within another function, you have created a closure. The inner function is the closure.
This closure is usually returned so you can use the outer function's variables at a later time.

```javascript
function outerFunction () {
     const outer = "I see the outer variable!"

  return function innerFunction() {
    console.log(outer)
  }
}

outerFunction()() // I see the outer variable!
```


<a name=“pure”/>

#### Pure functions

A Pure functions doesn't depend on and doesn't modify the states of the variable out of its scope. 
Technically, that means a pure function always returns same results given same parameters.
Its execution doesn't depends on the state of the system.
Pure functions are the piller of the Functional Programming 


<a name=“sdiff”/>

#### Splice vs Slice vs Split

## Splice:
The splice() method adds or removes items to or from an array, and returns the removed item(s).

NOTE: The original array will be changed by this Method.
```javascript
Syntax: array.splice(start[, deleteCount[, item1[, item2[, ...]]]])

let car = ["Audi", "BMW", "Bajaj", "Aston Martin"];
car.splice(1, 0, "Chevrolet", "Chrysler");

car;
(6) ["Audi", "Chevrolet", "Chrysler", "BMW", "Bajaj", "Aston Martin"] // Added Chevrolet to car array at index of 1 and followed by Chrysler. Since Second argument is 0, none of the item is removed from an array.
let result = car.splice(1, 1);  ["Chevrolet"] // Returns the removed item 
car
(5) ["Audi", "Chrysler", "BMW", "Bajaj", "Aston Martin"]
```

## Slice:
The slice() method returns the selected elements in an array, as a new array object.
It selects the elements starting at the given start argument, and ends at, but does not include, the given end argument.

NOTE: The original array will not be changed. It can be used with String as well.
```javascript
Syntax: arr.slice([begin[, end]])

let fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
let citrus = fruits.slice(1, 3);

fruits
(5) ["Banana", "Orange", "Lemon", "Apple", "Mango"]
citrus
(2) ["Orange", "Lemon"] // Doesn't included the end element- Apple in an result array.
```

## Split:
The split() method is used to split a string into an array of substrings, and returns the new array.

Note: The split() method does not change the original string.

USE: Reverse String, Substring
```javascript
Syntax: str.split([separator[, limit]])

let str = "How are you doing today?";
let res = str.split(" ");

res
(5) ["How", "are", "you", "doing", "today?"]
```

<a name=“datatypes”/>

#### Data Types

## Dynamic typing

JavaScript is Dynamic/ loosly typed language. Variables are not associate with any *types* in js.

```javascript
var a = "github";
typeof(a); // a is type of string 
a = 5;
typeof(a); // a is type of number
a = true;
typeof(a); // a is type of "boolean" 
    
```

With Latest ECMA, JS has 7 data types

Six primitive data types:

     1. Boolean
     2. String
     3. Number
     4. Null 
     5. Undefined
     6. Symbol (Introduced in ES6)
     
     7. Object // This is not primitive data type.

<a name=“dom”/>

#### DOM - Document Object Model

DOM(Document Object Model) is a crucial part for making any Web apps and Mobile apps interactive. 
The DOM model represents a document with a logical tree. Each branch of the tree ends in a node, and each node contains objects.
Accessing DOM element, we can change the document structure, style and content.


```HTML
<h2 class="hello"> Hello Github! </h2>
```

```javascript
let h2 = document.getElementsByTagName('h2')[0]; // Since getElementsByTagName returns an array, to access it need to add [0]
console.log(h2.innerText); // Hello Github!
console.log(h2.className); // Hello
```
Such this, there are many other interface listed below in MDN.
[List of DOM Interface](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model#DOM_interfaces)

<a name=“equality”/>

#### Equality Comparison

JavaScript provides three different value-comparison operations:
1. Strictly equality (===)

triple equals (===) will do the same comparison (including the special handling for NaN, -0, and +0) but without type conversion, by simply always returning false if the types different.

```HTML
Values are not implicitly converted to the some other value. If the values have different types, values are considered differnt. 
```
2. Abstract Equality (==)

double equals (==) will perform a type conversion when comparing two things, and will handle NaN, -0, and +0 specially to conform to IEEE 754 (so NaN != NaN, and -0 == +0);

3. Object.is

Object.is does not do type conversion and no special handling for NaN, -0, and +0 (it has the same behavior as === except on those special numeric values).

``` javascript
var a = 0;
var b = new String('0');
var c = '0';

console.log(a === a); // true
console.log(b === b); // true
console.log(c === c); // true

console.log(a === b); // false
console.log(a === c); // false
console.log(b === c); // false

console.log(null === undefined); // false
console.log(obj === null); // false
console.log(obj === undefined); // false
```
