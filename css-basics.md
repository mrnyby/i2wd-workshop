# CSS Basics

## CSS Files

CSS (Cascading Style Sheets) describes the __style__ of web pages through a set of rules. Each rule declares what elements it gets applied to with its __selector__ and describes the style of that element with its __properties__.

Web browsers only open HTML files, but we can add links to CSS files in our HTML document's head. When the browser opens our HTML file, the `<link>` element tells it to pull in whatever CSS files we specify.

```html
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="styles.css">
  <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Roboto"> 
</head>
</html>
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

In the above rule, `button` is the __selector__, everything between `{` and `}` is the __declaration__, `background` is a __property__, and `#444444` is the background property's __value__. This rule tells the browser how to style every `<button>` element. It gives the button a dark background, slightly rounded corners, white text, and a larger font.

## Selectors

### Element Selectors

`button` is an element selector. It tells the browser to apply whatever declaration we supply to all `<button>` elements. Element selectors are often used for high-level site themeing. Using them on small or specific components is risky because you can easily change the style of every occurrence of an element on the page or across the site!

### Class Selectors

Every HTML element supports an optional `class` attribute. Class selectors are similar to ID selectors, except you can use the same class more than once on a page. In many projects, class selectors are you'll work with most often.

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

Every HTML element also supports an optional `id` attribute which can be used to uniquely identify elements on a page. One reason you might use the `id` attribute is to ensure that only one element and nothing else gets a CSS rule applied to it.

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

If we want our CSS rule to apply to headings in addition to paragraphs, we could copy/paste our rule and change the selector to `h1`. But there's a better way! We can change our selector from `p` to `h1, p`. If we want to make all sizes of headings and paragraphs have green text:

```css
h1, h2, h3, h4, h5, h6, p {
  color: green;
}
```

## Common Properties

## Layout
