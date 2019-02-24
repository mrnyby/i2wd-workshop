# Advanced CSS

Modern CSS is extremely powerful. Through its more advanced features, CSS makes otherwise static pages more dynaic. It can give users feedback when they are filling out forms, animate elements, and handle complex layouts.

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

## Flexbox

## Transitions

## Transforms

## At-Rules

### Imports

### Font Faces

### Media Queries
