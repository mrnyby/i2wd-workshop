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

## Embedded Content
