# Positioning and Layout

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
.top-right {
  position: absolute;
  top: 20px
  right: 20px;
}
```

Using `position: absolute` let's us place an element anywhere within it's parent element. If we applied this class to an element directly under the `<body>` element, it would appear exactly 20 pixels from the top right of the page.

### Borders, Margins, and Padding

* __Padding__ is the space around the __content__ of an element.
* __Margin__ is the space around the outside of the element.
* __Borders__ are the lines that sit just outside of the padding.

![Borders, margins, and padding](https://mdn.mozillademos.org/files/9443/box-model.png)

## Flexbox

[Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/flex) is a relatively new CSS feature that is great for responsive designs. It makes scaling, ordering, and aligning web page components a breeze.

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

Although the example above doesn't specify this, our flex container has a default `flex-direction` of `row`. We can tell our flex container to order its contents in a different way by specifying a `flex-direction` of `column`, `row-reverse`, or `column-reverse`.

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

## Grid

[CSS grids](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout) are an even newer CSS feature than flex. Although flex is perfectly capable of creating responsive grid layouts, using CSS grids is often more straightforward and easier to read.

```css
.grid {
  display: grid;
  grid-gap: 8px;
  grid-template-columns: repeat(4, 1fr);
}
```

```html
<div class="grid>
  <div>One</div>
  <div>Two</div>
  <div>Three</div>
  ...
  <div>Forty-two</div>
</div>
```

This example creates an auto-growing grid layout with four equally-sized columns.
