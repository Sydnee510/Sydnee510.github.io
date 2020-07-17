---
layout: post
title:      "Learning JavaScript"
date:       2020-07-17 23:23:18 +0000
permalink:  learning_javascript
---


My journey trying to learn JavaScript has been a very rocky road. I started out thinking every thing would be peaches and cream while I was learning about declaring variables and scope. I understood from day 1, the difference from using `let`, `const`,&  `var` when delclaring variables. In JavaScript it is more effecient to declare variables throughout your code with `let` & `const`. Variables declared with `let` CAN be reassigned throughout your code while variables declared with `const` CANNOT be reassigned. Both of these declarations are block scoped, which means they are only accessible within the block or curly braces in which they are defined. Variables declared with `var` are not block scoped, which means they are accessible all throughout your code and they also get hoisted to the top. When a variable gets hoisted, it means that no matter where you define this variable, rather at the bottom, the middle, or the top of your code, it can be used before it is declared and can be declared after it is used. For these reasons, the keyword `var` is not recommended to declare varibales in JavaScript. Some examples of declaring variables are here:
```
var x = 10;
// Here x is 10
{
  let x = 2;
  // Here x is 2
}
// Here x is 10

```

```
var x = 5;
// Here x is 5
{
  const x = 1;
  // Here x is 1
}
// Here x is 5

```
These examples above show that both the keywords `let` and `const` are indeed block scoped and can only be accessible from within their current block.

Below are examples of what is allowed and not allowed while trying to reassign variables

```
let x = 2;       // Allowed
{
  let x = 3;   // Allowed
	//Here x is 3
}
{
  let x = 4;   // Allowed
	//Here x is 4
}
//Here x is 2
```
This sample above is allowed because `let` is block scoped which means, variables declared with `let` can be reassigned as long as it's done in ANOTHER block!!

```
{
  const x = 2;   // Allowed
  const x = 3;   // Not allowed
  x = 3;         // Not allowed
  var x = 3;     // Not allowed
  let x = 3;     // Not allowed
}

```
This sample above is not allowed because since `const` is also block scoped, it can only be reassigned in separate blocks as well. 
The sample below is allowed beause the variables were all assigned in separate blocks.
```
const x = 2;       // Allowed
{
  const x = 3;   // Allowed
}
{
  const x = 4;   // Allowed
}

```
This sample below shows exactly why we don't use the keyword `var` while declaring variables. If we try to declare variables this way, by the end of the program, we will lose track of the actual value we really want our variable to be. Variables defined this way are able to be reassigned throughout the entire program, no matter the scope.
(BAD PRACTICE)
```
var x = 2;
// Now x is 2
var x = 3;
// Now x is 3

```
