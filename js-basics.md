# JavaScript Basics

Unlike HTML and CSS, JavaScript is a __programming language__. Like many other programming languages, JavaScript programs can theoretically do any possible computational task. JavaScript is one of the most prevalent languages in modern software development.

```html
<head>
  <script src="script.js"></script>
  <script>
    var x = 4;
    console.log(x);
  </script>
</head>
```

Just like we did with CSS files, we can include JavaScript files on our web page by adding to our HTML document's header. To bring in CSS, we used the `<link>` element. To bring in JS files, we use the `<script>` element.

## Variables and Types

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
  return 'More on functions in a bit!';
};
```

### Arrays

Arrays store __collections__ or __lists__ of data and are __numerically indexed__. In other words, array elements are each assigned some number, starting from 0.

```js
var computerScientists = ['Alan Turing', 'Grace Hopper', 'Tim Berners-Lee'];
```

Each array has a `length` __property__ as well as several __methods__.

```js
var avengers = ['Spiderman', 'Iron Man', 'Thor', 'Captain America'];
avengers.length;                 // 4
avengers.reverse();              // Reverse the order of elements in the array
var firstAvenger = avengers[0];  // 'Captain America'
```

### Objects

Objects are variables that store __key-value pairs__. They are extremely versatile and used to group related data. You can think of objects like arrays, but instead of being __numerically indexed__ objects are __indexed by strings__ (or __keys__). We can access keys in an object using `[]` just like we did with arrays or we can use the `.` operator.

```js
var book = {
  title: 'The Fellowship of the Ring',
  author: 'J. R. R. Tolkien',
  publicationYear: 1954,
};

var bookTitle = book.title;
var bookAuthor = book['author'];

var key = 'publicationYear';
var bookPublicationYear = book[key];
```

## Operators

After declaring variables, we can change their values and evaluate expressions using __operators__. We've already put `=` ( __assignment operator__), `[]` (__array access operator__), and `.` (__property access operator__) to use above.

### Mathematical Operators

```js
// +
var sum = 2 + 3;                   // 5
var sum = sum + 1;                 // 6
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

// Shorthand
var i;
i++;                               // i = i + 1;
i--;                               // i = i - 1;
i += 2;                            // i = i + 2;
i *= 4;                            // i = i * 4;
```

### Logical Operators

```js
// ===
1 === 1                       // true
2 + 2 !== 4                   // false
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
[1, 2, 3] + [4, 5, 6]    // '1,2,34,5,6'
true === 'true'          // false
4 === '4'                // false
[1, 2, 3] === [1, 2, 3]  // false


4 == '4'                 // true
true == []               // true
[] == ![]                // true
```

Confused? The `===` operator checks for equal __value__ as well as equal __type__, so is often safer to use. `==` only checks for equal value __after converting types__.

## Functions

Functions are used to break your programs into digestible chunks. Most functions take some set of variables as input and return another variable. Like in any language, functions are used to __abstract__ away complex code. For example, the `reverse()` function on any array lets us reverse the order of an array without needing to understand the code the algorithm used to accomplish the reversal.

```js
function add(x, y) {
  return x + y;
}

var sum = add(2, 3);  // 5
```

Above, we declare a new function named `add`. It takes in two __parameters__ which we've named `x`, and `y`, then returns the sum of `x` and `y` to whatever code __executes__ the `add` function. We call our new `add` function by typing its name followed by the list of __arguments__ that we want the `add` function to use which are surrounded by parens.

## Control Flow

### If and Else

```js
/**
 * Returns the sound that the given animal makes
 */
function makeSound(animal) {
  if (animal === 'cat') {
    return 'meow';
  } else if (animal === 'dog') {
    return 'woof';
  } else {
    return 'moo?';
  }
}
```

### While Loops

While loops run some block of code repeatedly until the given __condition__ evaluates to false.

```js
while (true) {  // Always true, so this will run until the tab is closed
  // Turn computer into a space heater
}
```

```js
/**
 * Counts to the given number
 */
function count(n) {
  var i = 1;
  while (i <= n) {
    console.log(i);
    i++;
  }
}
```

### For Loops

For loops are just as powerful as while loops, but can be nicer to read in situations that you want to __iterate__ over something. Both of the below loops do exactly the same thing.

```js
var browsers = ['Chrome', 'Firefox', 'Edge', 'Safari'];
for (var i = 0; i < browsers.length; i++) {
  console.log(browsers[i]);
}
```

```js
var i = 0;
while (i < browsers.length) {
  console.log(browsers[i]);
  i++;
}
```
