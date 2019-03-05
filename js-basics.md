# JavaScript Basics

```html
<head>
  <script src="script.js"></script>
  <script>
    var x = 4;
    console.log(x);
  </script>
</head>
```

Just like we did with CSS files, we can bring include JavaScript files on our web page by adding a link to our HTML document's header.

Unlike HTML and CSS, JavaScript is a __programming language__. Like many other programming languages, JavaScript is __Turing complete__; JavaScript scripts or programs can do any possible computational task. JavaScript is one of the most prevalent programming languages in modern software development.

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
  return 'More on functions in just a bit!';
};
```

### Arrays

Arrays store __collections__ or __lists__ of data and are __numerically indexed__. In other words, array elements are each assigned some number, starting from 0.

```js
var superheroes = ['Spiderman', 'Iron Man', 'Thor', 'Captain Marvel'];
var mostHandsome = superheroes[2];  // 'Thor'
```

Each array has a `length` __property__ as well as __methods__ or __functions__.

```js
var superheroes = ['Spiderman', 'Iron Man', 'Thor', 'Captain Marvel'];
superheroes.length;              // 4
superheroes.reverse();           // Reverses the order of elements in the array
var firstHero = superheroes[0];  // 'Captain Marvel'
```

### Objects

Objects are variables that store __key-value pairs__. They are extremely versatile and used to group related data, and there are similar data structures in most other languages.

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

## Control Flow

### If and Else

```js
var animal = 'dog';
var sound;

if (animal === 'cat') {
  sound = 'meow';
} else if (animal === 'dog') {
  sound = 'woof';
} else {
  sound = 'moo?';
}
```

### While Loops

While loops run some block of code repeatedly until the given __condition__ evaluates to false.

```js
while (true) {
  // Turn computer into a space heater
}
```

```js
var i = 0;
while (i < 10) {
  console.log(i);
  i++;
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
  console.log(browsers[i];
  i++;
}
```

## Functions

Functions are used to break your programs into digestible chunks. Most functions take some set of variables as input and return another variable. Like in any language, functions are used to __abstract__ away complex code. For example, the `reverse()` function that called on an array let us reverse the order or an array without needing to understand how that really works.

```js
function add(x, y) {
  return x + y;
}

var sum = add(2, 3);  // 5
```

Above, we declare a new function named `add`. It takes in two __arguments__ or __parameters__ which we've named `x`, and `y`, then returns the sum of `x` and `y` to whatever code __calls__ or __executes__ the `add` function. We call our new `add` function by typing its name followed by the list of __parameters__ that we want the `add` function to use which are surrounded by parens.
