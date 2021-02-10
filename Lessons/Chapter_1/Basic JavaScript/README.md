# Coding in JavaScript

## Lesson objectives

_After this lesson students will be able to:_
1. Basic JavaScript
1. Define and identify Values and Variables
1. Define Thread of Execution 
1. Define Execution Context
1. Define Global Memory and Local Memory
1. Define Paramater and Argument
1. Understand what Ecma International, ECMAScript, JavaScript and TC39 are
1. Start learning to talk about code.


## Basic JavaScript

> Inside the computer’s world, there is only data—that
which is not data does not exist. All this data is in
essence just sequences of bits and is thus fundamentally
alike. Bits are any kinds of two-valued things, usually
described as 0s and 1s. Inside the computer, they
take forms like a high or low electrical charge, a strong
or weak signal, or a shiny or dull spot on the surface of
a CD. _Eloquent JavaScript 2010 ed._


## Define and identify Values and Variables
- There are six basic types of values: **numbers**, **strings**, **Booleans**, **objects**, **functions**, and **undefined** values.
- To create a value, one must merely invoke its name. This is very convenient.
You don’t have to gather building material for your values or pay
for them; you just call for one, and woosh, you have it. They are not created
from thin air, of course. Every value has to be stored somewhere, and if you
want to use a gigantic amount of them at the same time you might run out
of computer memory. Fortunately, this is a problem only if you need them
all simultaneously. As soon as you no longer use a value, it will dissipate, leaving
behind only a few bits. These bits are recycled to make the next generation
of values.
	- Numbers
		- Values of the number type are, as you might have guessed, numeric values.
They are written as numbers usually are:


## How does this work? Aka (The Execution Context Interview Question Answer)

```javascript
let myNum = 2;

const square = (num) => {
	return num * num
}

```
So in our code we have now created a variable myNum on line 1  that is equal to 2 and then created
a variable called sqaure that is equal to the function we created.

JavaScript does 3 super awesome things that makes it a great very first programming language, and that makes
it elegant enough to be used by developers with decades of experience.

We will go over those things as we go through this course but what pertains to us is the awesome feature of the
JavaScript being single threaded and reading code line by line and executing code only when you ask it to.

So in JS when it comes to what's running in our code we are never too confused if we remember JS goes line by
line and 1 at a time.

And we keep track of this in what's called our Execution Context
![js engine 1](https://media.git.generalassemb.ly/user/15881/files/d4842a00-3df3-11ea-909c-33a0a198c451)

So when the JS Engine looks at our code it will start at the top and perform each operation line by line

![js engine 2](https://media.git.generalassemb.ly/user/15881/files/d77f1a80-3df3-11ea-90dd-edd3b3f119ef)

```javascript
let myNum = 2;

const square = (num) => {
	return num * num
}
const ans = square(myNum)

```

![js engine 3 updated](https://media.git.generalassemb.ly/user/15881/files/db12a180-3df3-11ea-8acb-33e15c196cf3)

So as you can see when we call a function we go ahead and add it to the stack of things that we want JS to
do. Once JS has finished that task it goes back to the main code on the next line and runs again.

So once square has completed running it will give us a value and assign it to ans


```javascript
let myNum = 2;

const square = (num) => {
	return num * num
}
const ans = square(myNum)
console.log("Hello World")

```
 what order will this happen


```javascript
let myNum = 2;

const square = (num) => {
	return num * num
}
console.log("Hello World")
const ans = square(myNum)

``` 
what about this?
