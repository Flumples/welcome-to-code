# Coding in JavaScript

## Lesson objectives

_After this lesson students will be able to:_
1. Define Thread of Execution 
1. Define Execution Context
1. Define Global Memory and Local Memory
1. Define Paramater and Argument
1. Understand what Ecma International, ECMAScript, JavaScript and TC39 are
1. Start learning to talk about code.


## How does this work? Aka (The Execution Context Interview Question Answer)

```javascript
let myNum = 2;

const square = (num) => {
	return num * num
}

```
so in our code we have now created a variable myNum on line 1  that is equal to 2 and then created
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
