# JavaScript-Book

One place JavaScript!

### Table of Contents

- [Callback/ Higher-order Function](#callback)
- [Promises](#promises)
- [Closures](#closures)
- [Splice vs Slice vs Split](#SDiff)

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

<a name=“closures”/>

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

