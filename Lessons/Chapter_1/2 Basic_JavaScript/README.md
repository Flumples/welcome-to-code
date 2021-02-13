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
a CD. _(Eloquent JavaScript 2010 ed.)_


## Define and identify Values and Variables
- There are six basic types of values: **numbers**, **strings**, **Booleans**, **objects**, **functions**, and **undefined** values.
- To create a value, one must merely invoke its name. You don’t have to gather building material for your values or pay for them; you just call for one, and *woosh*, you have it. They are not created from thin air, of course. Every value has to be stored somewhere, and if you want to use a gigantic amount of them at the same time you might run out of computer memory. Fortunately, this is a problem only if you need them all simultaneously. As soon as you no longer use a value, it will dissipate, leaving behind only a few bits. These bits are recycled to make the next generation of values.


	- **Numbers**
		- Values of the number type are, as you might have guessed, numeric values.They are written as numbers usually are:

```
100
```

- Put that into a program, and it will cause the number 144 to come into existence inside the computer. This is what 144 might look like in bits:

```
0100000001100010000000000000000000000000000000000000000000000000
```

- If you were expecting something like 10010000 here (which is the integer or binary representation of 144) ...good call. It might actually be represented like that in some situations. But the standard describes JavaScript numbers as 64-bit floating-point values. This means they can also contain fractions and exponents.
- But we won’t go too deeply into binary representations here. The interesting thing, to us, is the practical repercussions they have for our numbers. For one thing, the fact that numbers are represented by a limited amount of bits means they have a limited precision. A set of 64 with values 1 or 0, can represent only 264 different numbers. This is a lot, though, more than 1019 (a 1 with 19 zeroes).
- Fractional numbers are written by using a dot:

```
9.81
```

- For very big or very small numbers, one can also use “scientific” notation
by adding an e, followed by the exponent of the number:

```
2.998e8
```

- That is 2.998 x 10^8 = 299800000.
- Calculations with whole numbers (also called integers) that fit in 52 bits are guaranteed to always be precise. Unfortunately, calculations with fractional numbers are generally not. Like  (pi) cannot be precisely expressed by a finite amount of decimal digits, many numbers lose some precision when only 64 bits are available to store them. This is a shame, but it causes practical problems only in very specific situations. The important thing is to be aware of it and treat fractional digital numbers as approximations, not as precise values.


	- **Arithmetic**
		- Arithmetic operations such as addition or multiplication take two number values and produce a new number from them. Here is what they look like in JavaScript:

```
100 + 4 * 11
```
- The + and * symbols are called *operators*. The first stands for addition, and the second stands for multiplication. Putting an operator between two values will apply it to those values and produce a new value.
- Does the example mean “add 4 and 100, and multiply the result by 11,” or is the multiplication done before the adding? As you might have guessed, the multiplication happens first. But, as in mathematics, this can be changed by wrapping the addition in parentheses:

```
(100 + 4) * 11
```

- For subtraction, there is the - operator, and division can be done with /. When operators appear together without parentheses, the order in which they are applied is determined by the precedence of the operators. The example show that multiplication comes before addition. / has the same precedence as *, and likewise for + and -. When multiple operators with the same precedence appear next to each other (as in 1 - 2 + 1), they are applied left to right.
- These rules of precedence are not something you should worry about.
- When in doubt, just add parentheses. There is one more arithmetic operator, which is possibly less familiar to you. The % symbol is used to represent the *modulo* operation. X modulo Y is the remainder of dividing X by Y. For example, 314 % 100 is 14, 10 % 3 is 1, and 144 % 12 is 0. Modulo’s precedence is the same as that of multiplication and division.


	- **Strings**
		- The next data type is the string. Its use is not as evident from its name as with numbers, but it also fulfills a very basic role. Strings are used to represent text. (The name supposedly derives from the fact that it strings together a bunch of characters.) Strings are written by enclosing their content in quotes:

```
"Patch my boat with chewing gum."
'You ain't never seen a donkey fly!'
```

- Both single and double quotes can be used to mark strings—as long as the quotes at the start and the end of the string match.
- Almost anything can be put between quotes, and JavaScript will make a string value out of it. But a few characters are tricky. You can imagine how putting quotes between quotes might be hard. Newlines, the things you get when you press ENTER, can also not be put between quotes—the string has to stay on a single line.
- To be able to have such characters in a string, the following trick is used: Whenever a backslash (\) is found inside quoted text, it indicates that the character after it has a special meaning. A quote that is preceded by a backslash will not end the string, but be part of it. When an n character occurs after a backslash, it is interpreted as a newline. Similarly, a t after a backslash means a tab character. Take the following string:

```
"This is the first line\nAnd this is the second"
```

The actual text contained is this:

```
This is the first line
And this is the second
```

- There are, of course, situations where you want a backslash in a string to
be just a backslash, not a special code. If two backslashes follow each other,
they will collapse right into each other, and only one will be left in the resulting
string value. This is how the string A newline character is written like
"\n" can be written:

```
"A newline character is written like \"\\n\"."
```

- Strings cannot be divided, multiplied, or subtracted. The + operator can
be used on them. It does not add, but it concatenates; it glues two strings
together. The following line will produce the string "concatenate":

```
"con" + "cat" + "e" + "nate"
```

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
