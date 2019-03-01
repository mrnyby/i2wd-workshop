# JavaScript Basics

Unlike HTML and CSS, JavaScript is a true __programming language__. Like many other programming languages, JavaScript is __Turing complete__; JavaScript scripts or programs can do any possible computational task. JavaScript is one of, if not the, most prevalent programming languages in modern software development.

## Types

Like any programming language, JavaScript has a set of __types__ used to describe all of the __variables__ or data flowing through your program. Unlike statically typed languages like C or Java, developers don't need to explicitly tell JavaScript the type of a variable. To put it in technical terms, JavaScript is __dynamically typed__ rather than __statically typed__.

Below is a list of __variable declarations__ demonstrating JavaScript's basic variable types. To the left of the `=` is the variable __name__, to the right is the variable __value__.

```js
// Booleans
var yes = true;
var no = false;

// Numbers
var whole = 4;
var decimal = 3.5;

// Strings
var hello = 'Hello, world.';
var hola = "Hola Mundo.";
var character = 'x';

// Arrays
var emptyArray = [];
var numbers = [1, 2, 3, 4];
var fruits = ['apple', 'banana', 'orange'];

// Objects
var emptyObject = {};
var user = { firstName: 'Ghee', lastName: 'Buttersnaps', age: 32 };

// Functions
var fun = function () {
  return 'More on functions in just a bit!';
};
```
