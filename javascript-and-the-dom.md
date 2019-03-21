# JavaScript and the DOM

The [Document Object Model](https://en.wikipedia.org/wiki/Document_Object_Model) is the __tree structure__ representing an HTML document.

```html
<!DOCTYPE html>
<html>

  <head>
    <title>DOM Trees</title>
    <meta charset="UTF-8">
  </head>

  <body>
    <h1>Save the Trees!</h1>
    <p>How do all trees die? They dialogue.</p>
  </body>

</html>

<!--
              <html>
               /  \
              /    \
             /      \
        <head>      <body>
        /\              /\
       /  \            /  \
      /    \          /    \
<title>    <meta>  <h1>    <p>
-->
```

## Querying and Modifying the DOM

We can select elements from the DOM using the `document` object. `document` is a global variable made available to JavaScript code by the web browser. This object has [many properties and methods](https://developer.mozilla.org/en-US/docs/Web/API/Document). The `querySelector()` method can be used to get JavaScript variables representing the elements on your web page. These variables can be modified, in turn changing the page after it has loaded.

```html
<span id="timestamp"></span>
```

```js
/**
 * window.onload gets executed as soon as the page is finished loading
 */
window.onload = function() {
  var timestampElement = document.querySelector('#timestamp');
  timestampElement.textContent = 'This site loaded on ' + getTimestamp();
}

var months = [
  'January',
  'February',
  'March',
  'April',
  'May',
  'June',
  'July',
  'August',
  'September',
  'October',
  'November',
  'December',
]

/**
 * Gets the current month, day, and year as a string
 *
 * EXAMPLE:
 * 'January 1, 1970'
 */
function getTimestamp() {
  var now = new Date();
  var month = months[now.getMonth()];
  var day = now.getDate();
  var year = now.getFullYear();

  return month + ' ' + day + ', ' + year;
}
```

## Events
