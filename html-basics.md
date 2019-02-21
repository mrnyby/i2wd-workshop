# HTML Basics

![https://xkcd.com/1144/](https://imgs.xkcd.com/comics/tags_2x.png "<A>: Like </a>this.&nbsp;")

## HTML Documents

```html
<!DOCTYPE html>
<html>
<head>
  <title>HTML Basics</title>
</head>
<body>
  <h1>I am a Big and Bold Heading</h1>
  <p>I am but a simple paragraph.</p>
</body>
</html>
```

HTML (Hypertext Markup Language) describes the __structure__ of web pages using a series of HTML elements (or tags). Different elements tell the browser to display different things. In the above example, the `<h1>` element tells the browser to render a heading.

HTML defines the general layout of a page and gives different pieces of a web page __semantic meaning__. It is not HTML's job to define more complex layouts or the nitty-gritty styling of elements; that's what CSS is for.

## Common Elements

| Element             | Meaning         | Description                                                          |
| ------------------- | --------------- | -------------------------------------------------------------------- |
| `<head>`            | Document head   | Contains the document's title, styles, scripts, and meta information |
| `<title>`           | Title           | Defines the document title (what you see up there in your tabs)      |
| `<body>`            | Document body   | Contains the document's contents, such as text, links, and images    |
| `<h1>`, ..., `<h6>` | Heading         | Defines a heading where smaller numbers means bigger text            |
| `<p>`               | Paragraph       | Defines a paragraph of text                                          |
| `<a>`               | Anchor          | Defines a hyperlink which links one page to another                  |
| `<div>`             | Division        | Defines a division or section in a document                          |
| `<em>`              | Emphasis        | Defines emphasized text (defaults to italics)                        |
| `<hr>`              | Horizontal rule | Defines a thematic break                                             |
| `<img>`             | Image           | Defines an image                                                     |
| `<span>`            | Span            | Groups inline elements                                               |
| `<strong>`          | Strong          | Defines strong text (defaults to bold)                               |
| `<button>`          | Button          | Defines a button                                                     |
| `<!--...-->`        | Comment         | Gets ignored by the browser and is used to comment code              |

## Attributes

Attributes are extra information that can be supplied to HTML elements that are always included in the starting tag of the element (`<p>`, __not__ `</p>`). Most of the time, attributes come in __name/value pairs__.

For example, `<a>` tags aren't very useful on their own. Without a page to redirect to, they might as well be plain text. We can use the `href` attributes on anchor elements to define where the link will take the user when it's clicked.

```html
<a href="https://www.warnerbros.com/archive/spacejam/movie/jam.htm">The pinnacle of web design.</a>
```

It's common for elements to have multiple attributes. If we wanted the browser to show an image but some text in case the image can't be loaded, we could use:

```html
<img src="puppy.jpg" alt="This is a really cute picture. Too bad it failed to load.">
```

## Lists

`<ol>` elements define ordered lists.

```html
<ol>
  <li>Uno</li>
  <li>Dos</li>
  <li>Tres</li>
</ol>
```

`<ul>` elements define unordered lists.

```html
<ul>
  <li>Disorder</li>
  <li>Choas</li>
  <li>Anarchy</li>
</ul>
```

In both of the above examples, the `<li>` __(list item)__ element is used to define elements in the list.

## Tables

```html
<table>
  <tr>
    <th>HTTP Status Code</th>
    <th>Meaning</th>
  </tr>
  <tr>
    <td>200</td>
    <td>OK</td>
  </tr>
  <tr>
    <td>404</td>
    <td>Not found</td>
  </tr>
  <tr>
    <td>418</td>
    <td>I'm a teapot</td>
  </tr>
  <tr>
    <td>500</td>
    <td>Internal server error>
  </tr>
</table>
```

| Element   | Meaning           |
| --------- | ----------------- |
| `<table>` | Table             |
| `<tr>`    | Table row         |
| `<th>`    | Table header cell |
| `<td>`    | Table data cell   |

HTML tables are great for displaying tabular data in web pages. Historically, tables have also been (ab)used to implement complex layouts where you want different components arranged in rows and columns. Complex layouts are __presentational__ information. Since HTML specializes in conveying __structural__ information, it's almost always better to implement layouts using CSS.
