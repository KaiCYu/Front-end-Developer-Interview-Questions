JS Questions:

Explain event delegation
Explain how this works in JavaScript
Explain how prototypal inheritance works
What do you think of AMD vs CommonJS?
Explain why the following doesn't work as an IIFE: function foo(){ }();.
What needs to be changed to properly make it an IIFE?
What's the difference between a variable that is: null, undefined or undeclared?
How would you go about checking for any of these states?
What is a closure, and how/why would you use one?
What's a typical use case for anonymous functions?
How do you organize your code? (module pattern, classical inheritance?)
What's the difference between host objects and native objects?
Difference between: function Person(){}, var person = Person(), and var person = new Person()?
What's the difference between .call and .apply?
Explain Function.prototype.bind.
When would you use document.write()?
What's the difference between feature detection, feature inference, and using the UA string?
Explain AJAX in as much detail as possible.
Explain how JSONP works (and how it's not really AJAX).
Have you ever used JavaScript templating?
If so, what libraries have you used?
Explain "hoisting".
Describe event bubbling.
What's the difference between an "attribute" and a "property"?
Why is extending built-in JavaScript objects not a good idea?
Difference between document load event and document ready event?
What is the difference between == and ===?
Explain the same-origin policy with regards to JavaScript.
Make this work:
duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]
Why is it called a Ternary expression, what does the word "Ternary" indicate?
What is "use strict";? what are the advantages and disadvantages to using it?
Create a for loop that iterates up to 100 while outputting "fizz" at multiples of 3, "buzz" at multiples of 5 and "fizzbuzz" at multiples of 3 and 5
Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?
Why would you use something like the load event? Does this event have disadvantages? Do you know any alternatives, and why would you use those?
Explain what a single page app is and how to make one SEO-friendly.
What is the extent of your experience with Promises and/or their polyfills?
What are the pros and cons of using Promises instead of callbacks?
What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?
Testing Questions:

What are some advantages/disadvantages to testing your code?
What tools would you use to test your code's functionality?
What is the difference between a unit test and a functional/integration test?
What is the purpose of a code style linting tool?
Performance Questions:

What tools would you use to find a performance bug in your code?
What are some ways you may improve your website's scrolling performance?
Explain the difference between layout, painting and compositing.
Network Questions:

Traditionally, why has it been better to serve site assets from multiple domains?
Do your best to describe the process from the time you type in a website's URL to it finishing loading on your screen.
What are the differences between Long-Polling, Websockets and Server-Sent Events?
Explain the following request and response headers:
Diff. between Expires, Date, Age and If-Modified-...
Do Not Track
Cache-Control
Transfer-Encoding
ETag
X-Frame-Options
What are HTTP actions? List all HTTP actions that you know, and explain them.
Coding Questions:

Question: What is the value of foo?

var foo = 10 + '20';
Question: How would you make this work?

add(2, 5); // 7
add(2)(5); // 7
Question: What value is returned from the following statement?

"i'm a lasagna hog".split("").reverse().join("");
Question: What is the value of window.foo?

( window.foo || ( window.foo = "bar" ) );
Question: What is the outcome of the two alerts below?

var foo = "Hello";
(function() {
  var bar = " World";
  alert(foo + bar);
})();
alert(foo + bar);
Question: What is the value of foo.length?

var foo = [];
foo.push(1);
foo.push(2);
Question: What is the value of foo.x?

var foo = {n: 1};
var bar = foo;
foo.x = foo = {n: 2};