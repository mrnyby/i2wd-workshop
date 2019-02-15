# HTML Basics

## HTML Documents

```
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

## Lists

`<ol>` elements define ordered lists.

```
<ol>
  <li>Uno</li>
  <li>Dos</li>
  <li>Tres</li>
</ol>
```

`<ul>` elements define unordered lists.

```
<ul>
  <li>Disorder</li>
  <li>Choas</li>
  <li>Anarchy</li>
</ul>
```

In both of the above examples, the `<li>` __(list item)__ element is used to define elements in the list.

## Tables

```
<table>
  <tr>
    <th>
  </tr>
</table>
```
