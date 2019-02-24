# Advanced CSS

Modern CSS is extremely powerful. Through its more advanced features, CSS makes otherwise static pages more dynamic. It can give users feedback when they are filling out forms, animate elements, and handle complex layouts.

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
| `:disabled`              | `input:disabled`    | Selects every disabled `<input>` element`                                     |
| `:hover`                 | `button:hover`      | Selects `<button>` elements that are being moused over                        |
| `:valid`                 | `input:valid`       | Selects all `<input>` elements with a valid value                             |

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
   * Any time the background-color or box-shadow properties change on an element with class="button-primary", animate
   * that change over 0.2 seconds.
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

The example above defines a simple button style intended to be used across a site, but can be a lot to digest.

The `button` and `button:hover` rules define what `<button>` elements should look like be default. They are gray and turn to a darker gray when hovered over. They have slightly rounded corners and a larger, uppercase font.

The `button.primary` and `button.primary:hover` rules define what primary buttons should look like. Primary buttons should look like the default buttons, except they should be green with white text and turn to a darker green when hovered over.

### Specificity

This example introduces the important CSS concepts of __inheritance__ and __specificity__. When multiple rules can apply to an element, both get applied. When properties in those rules do not conflict, the more specific rule __inherits__ properties from the less specific rule. When properties in those rules conflict, the properties defined in the more specific rule win out.

Looking closer at our save button, we see that the `button` rules says that the button should have `background-color: #EEEEEE` and `border-radius: 2px`. However, the more specific `button.primary` rule also applies. Since it's more specific, the save button gets `background-color: rgba(46, 204, 113, .8)`. Since `button.primary` doesn't define its own `border-radius`, it __inherits__ `border-radius: 2px` from the `button` rule.

## Transforms

## Flexbox

## At-Rules

### Imports

### Font Faces

### Media Queries
