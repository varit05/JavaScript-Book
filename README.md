# JavaScript-Book

One place JavaScript!

### Table of Contents

- [Callback/ Higher-order Function](#callback)
- [Promises](#promises)

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

