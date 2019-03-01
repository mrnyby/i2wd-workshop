# JavaScript Basics

Unlike HTML and CSS, JavaScript is a __programming language__. Like many other programming languages, JavaScript is __Turing complete__; JavaScript scripts or programs can do any possible computational task. JavaScript is one of the most prevalent programming languages in modern software development.

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

## Operators

After declaring variables, we can change the values stored in them using __operators__. We've already put `=` (the __assignment operator__) to use above.

### Mathematical Operators

```js
// +
var sum = 2 + 3;                   // 5
var sum = sum + 1                  // 6
var hello = 'Hello, ' + 'world.';  // 'Hello, world.'

// -
4 - 2                              // 2

// *, /
6 * 8                              // 48
16 / 2                             // 8

// ()
(2 + 3) * 10                       // 50

// %
8 % 3                              // 2
```

### Logical Operators

```js
// ===
1 === 1                       // true
2 + 2 === 5                   // false
'Hello' === 'Hello'           // true

// >, <
1 > 2                         // false
5 < 10                        // true
4 <= 4                        // true
2 >= 3                        // false

// && (AND), || (OR), ! (NOT)
true && true                  // true
true && false                 // false
true || false                 // true
false || false                // false
!true                         // false
!false                        // true
(2 + 3 > 4) || (3 + 3 === 6)  // true
```

### Type Conversion

Like most __dynamically typed__ languages, JavaScript will try to convert between variable types when it can. Sometimes this is helpful. Sometimes this results in nonsense.

```js
3 + 'b'                  // '3b'
1 + '2'                  // '12'
1 + 2 + '3'              // '33'
'Hello' - 'world'        // NaN (Not a number)
true === 'true'          // false
4 === '4'                // false
[1, 2, 3] === [1, 2, 3]  // false


4 == '4'                 // true
true == []               // true
true == ![]              // true... wait what?
```

Confused? The `===` operator checks for equal __value__ as well as equal __type__, so is often safer to use. `==` only checks for equal value __after converting types__.
