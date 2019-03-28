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

Try opening the below HTML file in your browser, open the JavaScript console in your browser's development tools, and use `document.querySelector()` to select elements on the page. Try selecting the following:

* The document's title
* The first header on the page
* A list of all headers on the page (hint: use `document.querySelectorAll()`)
* The button on the page

```html
<!DOCTYPE html>
<html>

  <head>
    <title>Select Me!</title>
    <meta charset="UTF-8">
  </head>

  <body>
    <h1 class="header">You can select anything.</h1>
    <h1>Like seriously anything.</h1>
    <button id="big-button">All of it.</button>
  </body>

</html>
```

`document.querySelector()` returns the __first__ element matching the given CSS selector. `document.querySelectorAll()` returns an __array__ of __all elements__ that match the given CSS selector.

## Events

There are a huge variety of __events__ that take place as a user interacts with a web page, and JavaScript lets us listen for these events and execute some code in response to them taking place. For example, different events fire when:

* The page finishes loading
* The value of an input changes
* An element is clicked

We can register __event listeners__ on both the __window__ or on __individual elements__. These are functions that get executed whenever an event occurs.

```html
<button id="button">Click to Count!</button>
<p>
  You've clicked that button <span id="counter">0</span> times.
</p>
```

```js
window.addEventListener('load', function() {
  // Log an event as soon as the page is loaded
  console.log('The page is loaded!');

  var nTimesClicked = 0;
  // If we try to find the button before the page has loaded, it might not be on the page yet
  document.querySelector('#button').addEventListener('click', function() {
    console.log('Clicked!');

    nTimesClicked++;
    document.querySelector('#counter').textContent = nTimesClicked;
  });
});
```
