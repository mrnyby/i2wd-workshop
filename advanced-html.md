# Advanced HTML

![https://xkcd.com/9327/](https://imgs.xkcd.com/comics/exploits_of_a_mom.png "Her daughter is named Help I'm trapped in a driver's license factory.")

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
