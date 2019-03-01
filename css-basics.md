# CSS Basics

[__CSS__ (Cascading Style Sheets)](https://en.wikipedia.org/wiki/Cascading_Style_Sheets) describes the style of elements on the page.

## CSS Files

CSS (Cascading Style Sheets) describes the __style__ of web pages through a set of rules. Each rule declares what elements it gets applied to with its __selector__ and describes the style of that element with its __properties__.

Web browsers open HTML files, but we can add links to CSS files in our HTML document's head. When the browser opens our HTML file, the `<link>` element tells it to pull in whatever CSS files we specify.

```html
<head>
  <link rel="stylesheet" href="styles.css">
  <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Roboto"> 
</head>
```

## Rules

```css
button {
  background: #444444;
  border-radius: 3px;
  color: white;
  font-size: 20px;
}
```

In the above rule, `button` is the __selector__, everything between `{` and `}` is the __declaration__, `background` is a __property__, and `#444444` is the background property's __value__. This rule tells the browser how to style every `<button>` element. It gives buttons a dark background, slightly rounded corners, white text, and a larger font.

## Selectors

### Element Selectors

`button` is an element selector. It tells the browser to apply whatever declaration we supply to all `<button>` elements. Element selectors are often used for high-level site themeing. Using them on small or specific components is risky because you can easily change the style of every occurrence of an element on the page or across the site!

### Class Selectors

Every HTML element supports an optional `class` attribute. In many projects, class selectors are what you'll work with most often.

```html
<h2 class="joke">I got kicked out of a karaoke bar for singing "Danger Zone" five times.</h2>
<p class="punchline">I exceeded my number of Loggins attempts.</p>

<h2 class="joke">I just got back from a tour of the local pickle factory.</h2>
<p class="punchline">It was a jarring experience. I couldn't dill with it.</p>
```

```css
.joke {
  font-family: "Comic Sans";
}

.punchline {
  color: red;
}
```

### ID Selectors

Every HTML element also supports an optional `id` attribute which can be used to uniquely identify elements on a page. ID selectors are very similar to class selectors. Whereas a class can appear on a page countless times, there should only be one occurence of any one ID on the page at a time.

```html
<button id="big-red-button">LAUNCH MISSILES</button>
```

```css
#big-red-button {
  background: red;
  font-size: 50px;
}
```

### Selecting Multiple Elements

```css
p {
  color: green;
}
```

If we want the above CSS rule to apply to headings in addition to paragraphs, we could copy/paste our rule and change the selector to `h1`. But there's a better way! We can change our selector from `p` to `h1, p`. If we want to make all sizes of headings and paragraphs have green text.

```css
h1, h2, h3, h4, h5, h6, p {
  color: green;
}
```

## Layout

__Everything__ is a box. Right click on this text and click `Inspect Element`. In your dev tools, hover your mouse over the `<p>` element that contains this text and notice the box that appears around this paragraph. That highlighted box is this specific `<p>` element and all of the space that it occupies.

Hover over other elements. It's a box. Inspect the round GitHub logo at the top of the screen. Even _that_ is a box.

### Display

By default, page elements will be placed on the page in the order that they were declared. Depending on whether elements are __block__ or __inline__, they will appear __below__ or __to the right of__ the preceding element. __Block__ elements always start and end on a __new line__. __Inline__ are just the opposite; they don't have to start or end on a new line.

The `display` CSS property can change the default behavior of elements. For example, `<div>` elements default to `display: block`. A `<div>` element can be made inline by overwriting the default value in a CSS rule.

```css
.inline-div {
  display: inline;
}
```

### Float

The `float` property can be used to remove an element from the flow of the page. A simple use case for `float` is getting text to wrap around an image.

```html
<img class="float-right" src="http://www.pawmygosh.com/wp-content/uploads/2015/02/chubby4-570x596.jpg">
<p>
  Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's
  standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a
  type specimen book.
</p>
```

```css
.float-right {
  float: right;
}
```

### Position

`position` specifies how the element gets positioned on the page. Once declaring what type of positioning an element has, the `top`, `bottom`, `left`, and `right` properties can control where it ends up on the page.

```css
.indent {
  position: relative;
  left: 5px;
}
```

Using `position: relative` allows us to adjust the position that the element otherwise would have had. In the above example, an element with `class="indent"` will appear exactly where it would have before, but shifted slightly to the right.

```css
.bottom-right {
  position: absolute;
  bottom: 20px;
  right: 20px;
}
```

Using `position: absolute` let's us place an element on the page regardless of where it or any other elements might be. The above example would position an element exactly 20 pixels from the bottom right of the window.

### Borders, Margins, and Padding

* __Padding__ is the space around the __content__ of an element.
* __Margin__ is the space around the outside of the element.
* __Borders__ are the lines that sit just outside of the padding.

![Borders, margins, and padding](https://mdn.mozillademos.org/files/9443/box-model.png)

## Shorthand Properties

Many common CSS properties have shorthand versions. Both of the below rules give an element a `10px` top margin, a `20px` right margin, a `30px` bottom margin, and a `15px` left margin.

```css
.so-tedious {
  margin-top: 10px;
  margin-right: 20px;
  margin-bottom: 30px;
  margin-left: 15px;
}

.fancy {
  margin: 10px 20px 30px 15px;
}
```
