# Advanced CSS

Modern CSS is extremely powerful. Through its more advanced features, CSS makes otherwise static pages more dynamic. It can give users feedback when they are filling out forms, animate elements, and handle complex layouts.

## Specificity

```html
<button>Boring</button>
<button class="primary">Save</button>
```

```css
button {
  background-color: #EEEEEE;
  border: none;
  border-radius: 2px;
  font-size: 20px;
  padding: 5px 10px;
  text-transform: uppercase;
}

button.primary {
  background-color: rgba(46, 204, 113, .8);
  color: white;
}
```

The above example defines a simple button style intended to be used across a site, but can be a lot to digest.

The `button` rule defines what `<button>` elements should look like be default. They are gray, have slightly rounded corners, and contain a larger, uppercase font.

The `button.primary` rule defines what primary buttons should look like. Primary buttons should look like the default buttons, except they should be green with white text

This example introduces the important CSS concepts of __inheritance__ and __specificity__. When two (or more) rules can apply to an element, both get applied. When properties in those rules do not conflict, the more specific rule __inherits__ properties from the less specific rule. When properties in those rules conflict, the properties defined in the more __specific__ rule win out.

Looking at the save button, notice that the `button` rule says that the button should have `background-color: #EEEEEE` and `border-radius: 2px`. The more specific `button.primary` rule also applies to the save button. Since this rule is more specific, the save button gets `background-color: rgba(46, 204, 113, .8)`. Since `button.primary` doesn't define its own `border-radius`, it __inherits__ `border-radius: 2px` from the `button` rule.

## Advanced Selectors

| Selector                 | Example             | Example Description                                                           |
| ------------------------ | ------------------- | ----------------------------------------------------------------------------- |
| `element element`        | `div p`             | Selects all `<p>` elements inside `<div>` elements                            |
| `element > element`      | `div > p`           | Selects all `<p>` elements where the parent is a `<div>` element              |
| `element + element`      | `div + p`           | Selects all `<p>` elements that are placed immediately after `<div>` elements |
| `element ~ element`      | `p ~ ul`            | Selects all `<ul>` elements that are preceded by a `<p>` element              |
| `[attribute]`            | `[target]`          | Selects all elements with the `target` attribute                              |
| `[attribute = value]`    | `[target = _blank]` | Selects all elements with the `target` attribute having a value of `_blank`   |
| `::after` and `::before` | `p::after`          | Insert something after the content in each `<p>` element                      |
| `:disabled`              | `input:disabled`    | Selects every disabled `<input>` element                                      |
| `:hover`                 | `button:hover`      | Selects `<button>` elements that are being moused over                        |
| `:valid`  and `:invalid` | `input:invalid`     | Selects all `<input>` elements with an invalid value                          |

## Transitions

CSS transitions allow the values of different properties to change over some amount of time.

```html
<button>Boring</button>
<button class="primary">Save</button>
```

```css
button {
  background-color: #EEEEEE;
  border: none;
  border-radius: 2px;
  font-size: 20px;
  padding: 5px 10px;
  text-transform: uppercase;

  /**
   * Any time the background-color property changes on a <button>, animate that change over 0.3 seconds.
   */
  transition: background-color .3s;
}

button:hover {
  background-color: #DDDDDD;
}

button.primary {
  background-color: rgba(46, 204, 113, .8);
  color: white;
}

button.primary:hover {
  background-color: rgb(46, 204, 113);
}
```

This extends the previous example to make our buttons a little more exciting. When a mouse hovers over either of our buttons the more specific `:hover` rules get applied to each of our buttons and make their `background-color` a bit darker.

## Transforms

CSS transforms can modify the shape and position of elements without affecting the normal flow of the page.

```html
<img class="rotate" src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3d/CSS.3.svg/730px-CSS.3.svg.png" height="200">
<img class="skew" src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3d/CSS.3.svg/730px-CSS.3.svg.png" height="200">
<img class="scale" src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3d/CSS.3.svg/730px-CSS.3.svg.png" height="200">
```

```css
.rotate {
  transform: rotate(30deg);
}

.skew {
  transform: skewY(30deg);
}

.scale {
  transform: scaleX(1.5);
}
```

## At-Rules

### Font Faces

`@font-face` rules lets developers define custom font families by providing a font name and the associated font files. By providing multiple font formats and files, developers can ensure their font will work across multiple browsers.

```css
@font-face {
  font-family: 'Comedic Sans';
  src: url('comedic-sans.woff2') format('woff2'),
       url('comedic-sans.woff') format('woff');
}
```

### Keyframes

Keyframes are similar to transitions, but are better suited for certain types of animations. Unlike transitions, `@keyframes` rules grant the ability to animate an element at all times rather than when the element is active or being hovered over.

```html
<div class="advertisement">Hey! Look at me!</div>
```

```css
@keyframes annoying {
  0%, 100% {
    color: red;
    font-size: 20px;
  }

  33% {
    color: green;
    font-size: 30px;
  }

  66% {
    color: blue;
    font-size: 30px;
  }
}

.advertisement {
  animation: annoying 1s infinite;
  font-weight: bold;
}
```

### Media Queries

CSS media queries are useful for applying different styles depending on the device that's viewing a site. These allow us to specify media types like `screen` and `print` and conditionally apply some CSS rules based on the device's properties.

```css
button {
  font-size: 24px;
}

/* On screens that are 800px or narrower, make the button font smaller. */
@media screen and (max-width: 800px) {
  button {
    font-size: 16px;
  }
}
```

This example tells the browser to give all of our buttons `font-size: 24px;`. Our `@media` query describes a more specific rule that states, "If the device viewing our page has a screen and the window is less than 800px wide, give our buttons a font size of 16px."

## Flexbox

Flexbox is a relatively new CSS feature that is great for responsive designs. It makes scaling, ordering, and aligning web page components a breeze.

```html
<div class="flex-container">
  <div class="red">Short</div>
  <div class="green">Small</div>
  <div class="blue">
    But<br>
    I<br>
    am<br>
    extra<br>
    tall
  </div>
</div>
```

```css
.flex-container {
  display: flex;
}

.red {
  background-color: rgba(255, 0, 0, 0.3);
}

.green {
  background-color: rgba(0, 255, 0, 0.3);
}

.blue {
  background-color: rgba(0, 0, 255, 0.3);
}
```

Notice that each of the three child divs have equal height and that they are only as tall as the tallest of the three divs. Without flex, layouts like this can be tricky to achieve.

### Flex Direction

Although the example above doesn't specify this, our flex container has a default `flex-direction` of `row`. We can tell our flex container to order its contents in a different why by specifying a `flex-direction` of `column`, `row-reverse`, or `column-reverse`.

```css
.flex-container {
  display: flex;
  flex-direction: column;
}
```

### Flex Wrapping

In many grid-based designs seen in apps like Spotify or Netflix, there is a list of items that rearrange themselves as the screen grows and shrinks. This can be achieved with the `flex-wrap` property.

```css
.flex-container {
  display: flex;
  flex-wrap: wrap;
}
```

The `flex-flow` property can be used to define both `flex-direction` and `flex-wrap` in a single property.

```css
.flex-container {
  display: flex;
  flex-flow: row-reverse wrap;
}
```
