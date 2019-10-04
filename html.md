# HTML Basics

![https://xkcd.com/1144/](https://imgs.xkcd.com/comics/tags_2x.png "<A>: Like </a>this.&nbsp;")

[__HTML__ (Hypertext Markup Language)](https://en.wikipedia.org/wiki/HTML) describes the structure of a webpage.

## HTML Documents

```html
<!DOCTYPE html>
<html>

<head>
  <title>HTML Basics</title>
  <meta charset="UTF-8">
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
| `<span>`            | Span            | Groups inline elements                                               |
| `<strong>`          | Strong          | Defines strong text (defaults to bold)                               |
| `<em>`              | Emphasis        | Defines emphasized text (defaults to italics)                        |
| `<hr>`              | Horizontal rule | Defines a thematic break                                             |
| `<img>`             | Image           | Defines an image                                                     |
| `<button>`          | Button          | Defines a button                                                     |
| `<input>`           | Input           | Defines an input element (text boxes, checkboxes, etc.)              |
| `<!--...-->`        | Comment         | Gets ignored by the browser and is used to comment code              |

## Attributes

Attributes are extra information that can be supplied to HTML elements that are always included in the starting tag of the element (`<p>`, __not__ `</p>`). Most of the time, attributes come in __name/value pairs__.

For example, `<a>` tags aren't very useful on their own. Without a page to redirect to, they might as well be plain text. We can use the `href` attributes on anchor elements to define where the link will take the user when it's clicked.

```html
<a href="https://www.warnerbros.com/archive/spacejam/movie/jam.htm">The pinnacle of web design.</a>
```

It's common for elements to have multiple attributes. If we wanted the browser to show an image but some text in case the image can't be loaded, we could use:

```html
<img src="http://mosthdwallpapers.com/wp-content/uploads/2016/05/Cute-Dog-Wallpapers-Free.jpg" alt="This is a really cute picture. Too bad it failed to load.">
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

## Inputs

```html
<input type="text">
<input type="number" min="-10" max="10">
<input type="range">
```

We use the `<input>` element use to collect some kind of input from users. After filling out an input with data, users typically see something in the page change or have a chance to submit information to a server. Oftentimes, `<input>` elements look like text boxes, but this element can handle more complex input as well. Understanding all of the valid values for its `type` attribute can save you tons of work creating custom inputs.

* Checkbox
* Color
* Date
* Email
* File upload
* Number
* Password
* Range
* Radio
* URLs

## Forms

```html
<form action="https://www.oh.no/add-user" method="POST">
  <input name="email" placeholder="Email" type="email">
  <input name="password" placeholder="Password" type="password">
  <input type="submit" value="Register">
</form>
```

Above is a new user registration form. The `<form>` element has two attributes: `action` and `method`. The `action` attribute tells the browser what URL to send information to when the usert clicks the "Register" button. The `method` attribute indicates which __HTTP method__ to use when sending the form's information.

Using `POST` as our method will place the email and password in the HTTP request's __body__. Alternatively, we could use `GET` which would tell the browser to send the information through URL __query parameters__: `https://www.oh.no/add-user?email=anyone@anymail.com&password=blueberry1`. For a form like this, using `POST` is a better idea because then the user's password won't ever be visible in their browser's address bar or history.

The `name` attribute of the email and password `<input>` elements tells the browser what to call each bit of data. `name="email"` tells the browser to call whatever gets typed into that input box "email."

### Form Validation

```html
<form action="https://www.oh.no/add-user" method="POST">
  <input name="email" placeholder="Email" required type="email">
  <input name="password" placeholder="Password" required type="password">
  <input type="submit" value="Register">
</form>
```

HTML 5 has powerful validation built in to its forms. For example, the `required` attribute on any `<input>` element tells the browser that an input needs to be filled out for a form to be valid. Just using `type="email"` on an input will flag our input and the entire form as being invalid if a user doesn't enter a valid email address.

As we'll learn later, CSS can style forms differently when they're in an error state. JavaScript can add more complex validation, disable submission buttons when a form is invalid, and more.

Other helpful form validation attributes include `minlength`, `maxlength`, and `pattern`.

## Embedded Content

```html
<video src="fluffy-kitty.mp4" controls></video>
```

```html
<audio src="never-gonna-give-you-up.mp3" autoplay loop>What is this, IE8?</audio>
```

```html
<canvas id="draw-on-me" height="400" width="600"></canvas>
```

Embedding multimedia in a web page is easier than ever with HTML 5. Similar to the `<img>` element, HTML has elements for video, audio, and canvases. Canvases can be drawn to by JavaScript to dynamic images like animated charts or game sprites. All of these elements allow developers to define fall-back content between tags that will be displayed to any users running old browsers.

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
