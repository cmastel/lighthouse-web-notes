# jQuery General

## Event Listeners

```js
$("#btn").click(function() {
  console.log(this); //The this keyword is a reference to the button
});
```

Can be separated into the listener (typically in a client.js file):
```js
$("#btn").click(buttonPressFunction);
```
and then the handler function (typically in a handlers.js file):
```js
const buttonPressFunction = function() {
  console.log(this); //The this keyword is a reference to the button
};
```

## Change CSS

```js
 $("#someTag").css("color", "red");
 ```


 ## AJAX

 > Asynchronous JavaScript and XML

 Instead of an HTTP response replacing the web page in the browser, it is passed to a JavaScript function, and that function is responsible for determining what to do with it. Often the JavaScript will modify the DOM to reflect the response from the server.

 This allows for a page to be updated, without the page being reloaded. 

 ```js
 $.ajax({
     method: 'GET',
     url: '/tweets/',
     dataType: 'json',
     success: (data) => {
       const lastKey = Object.keys(data).reverse()[0];
       const tweet = data[lastKey];
       const $tweet = createTweetElement(tweet);
       $('.tweets-container').prepend($tweet);
     }
   })
```
The `.ajax` takes the place of the HTTP methods (POST, GET, etc). An action and method are required, and the `success:` details what happens after.

```js
  event.preventDefault();
```
Will prevent typical HTTP request calls in order to allow the AJAX function to run.

## Cross Site Scripting

When a user is able to input text into a form which gets sent to a server, there is the possibility of malicious code (`<script>BadCodeHere</script>`). To deal with this, the following will take that text string and render it safe:

```js
const escape =  function(str) {
  let div = document.createElement('div');
  div.appendChild(document.createTextNode(str));
  return div.innerHTML;
}

const safeHTML = `<p>${escape(textFromUser)}</p>`;
```

