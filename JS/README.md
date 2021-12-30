# Useful links
https://github.com/sudheerj/reactjs-interview-questions
https://alok722.github.io/namaste-javascript-notes/dist/lectures.html


- # Functions in JavaScript (ES5)

### What can in-browser JavaScript do?
Modern JavaScript is a “safe” programming language. It does not provide low-level access to memory or CPU, because it was initially created for browsers which do not require it.

JavaScript’s capabilities greatly depend on the environment it’s running in. For instance, Node.js supports functions that allow JavaScript to read/write arbitrary files, perform network requests, etc.

In-browser JavaScript can do everything related to webpage manipulation, interaction with the user, and the webserver.

For instance, in-browser JavaScript is able to:

Add new HTML to the page, change the existing content, modify styles.
React to user actions, run on mouse clicks, pointer movements, key presses.
Send requests over the network to remote servers, download and upload files (so-called AJAX and COMET technologies).
Get and set cookies, ask questions to the visitor, show messages.
Remember the data on the client-side (“local storage”).
What CAN’T in-browser JavaScript do?
JavaScript’s abilities in the browser are limited for the sake of a user’s safety. The aim is to prevent an evil webpage from accessing private information or harming the user’s data.

Examples of such restrictions include:

JavaScript on a webpage may not read/write arbitrary files on the hard disk, copy them or execute programs. It has no direct access to OS functions.

Modern browsers allow it to work with files, but the access is limited and only provided if the user does certain actions, like “dropping” a file into a browser window or selecting it via an < input > tag.

There are ways to interact with camera/microphone and other devices, but they require a user’s explicit permission. So a JavaScript-enabled page may not sneakily enable a web-camera, observe the surroundings and send the information to the NSA.

Different tabs/windows generally do not know about each other. Sometimes they do, for example when one window uses JavaScript to open the other one. But even in this case, JavaScript from one page may not access the other if they come from different sites (from a different domain, protocol or port).

This is called the “Same Origin Policy”. To work around that, both pages must agree for data exchange and contain a special JavaScript code that handles it. We’ll cover that in the tutorial.

This limitation is, again, for the user’s safety. A page from http://anysite.com which a user has opened must not be able to access another browser tab with the URL http://gmail.com and steal information from there.

JavaScript can easily communicate over the net to the server where the current page came from. But its ability to receive data from other sites/domains is crippled. Though possible, it requires explicit agreement (expressed in HTTP headers) from the remote side. Once again, that’s a safety limitation.



Such limits do not exist if JavaScript is used outside of the browser, for example on a server. Modern browsers also allow plugin/extensions which may ask for extended permissions.

### What makes JavaScript unique?
There are at least three great things about JavaScript:

Full integration with HTML/CSS.
Simple things are done simply.
Supported by all major browsers and enabled by default.
JavaScript is the only browser technology that combines these three things.

That’s what makes JavaScript unique. That’s why it’s the most widespread tool for creating browser interfaces.

That said, JavaScript also allows to create servers, mobile applications, etc.



- ## Topic covered

  1.Variable declaration in js


- ## Roles of functions

  - Functions

  - Methods

  - Constructor/object factories

  - [Factory Functions vs Constructor Functions vs Classes](https://medium.com/javascript-scene/javascript-factory-functions-vs-constructor-functions-vs-classes-2f22ceddf33e)

- ## Params vs Arguments

  The terms *parameter* and *argument* are often used interchangeably, because the context usually makes it clear what the intended meaning is. The following is a rule of thumb for distinguishing them.

  - *Parameters* are used to define a function. They are also called formal parameters and formal arguments. In the following example, `param1` and `param2` are parameters:

        function foo(param1, param2) {...}

  - *Arguments* are used to invoke a function. They are also called actual parameters and actual arguments. In the following example, `3` and `7` are arguments:

        foo(3, 7);

- ## Defining Functions

  All functions are objects, instances of `Function`:

      function id(x) { return x; }
      console.log(id instanceof Function); // true

  Therefore, functions get their methods from `Function.prototype`.

  - ### Function Expressions

    A function expression produces a value—a function object. For example:

        var add = function (x, y) { return x + y };
        console.log(add(2, 3)); // 5

    The preceding code assigned the result of a function expression to the variable `add` and called it via that variable. The value produced by a function expression can be assigned to a variable (as shown in the example), passed as an argument to another function, and more. Because normal function expressions don’t have a name, they are also called *anonymous function expressions*.

    #### Named function expressions

    You can give a function expression a name. *Named function expressions* allow a function expression to refer to itself, which is useful for self-recursion:

        var fac = function me(n) {
          if (n > 0) {
            return n * me(n-1);
          } else {
            return 1;
          }
        };
        console.log(fac(3)); // 6

    #### NOTE

    The name of a named function expression is only accessible inside the function expression:

        var repeat = function me(n, str) {
          return n > 0 ? str + me(n-1, str) : '';
        };
        console.log(repeat(3, 'Yeah')); // YeahYeahYeah
        console.log(me); // ReferenceError: me is not defined

  - ### Function Declarations

    The following is a function declaration:

        function add(x, y) {
          return x + y;
        }

    The preceding looks like a function expression, but it is a statement. It is roughly equivalent to the following code:

        var add = function (x, y) {
          return x + y;
        };

    In other words, a function declaration declares a new variable, creates a function object, and assigns it to the variable.

  - ### The Function Constructor

    The constructor `Function()` evaluates JavaScript code stored in strings. For example, the following code is equivalent to the previous example:

        var add = new Function('x', 'y', 'return x + y');

    However, this way of defining a function is slow and keeps code in strings (inaccessible to tools). Therefore, it is much better to use a function expression or a function declaration if possible.


 ## Assignment 1
   Create a function which take two parameter    

- ## [Hoisting](https://github.com/getify/You-Dont-Know-JS/blob/master/scope%20%26%20closures/ch4.md)

- ## More Control over Function Calls: call(), apply(), and bind()
  - [JavaScript’s this: how it works, where it can trip you up](http://2ality.com/2014/05/this.html)

  - [Javascript: call(), apply() and bind()](https://medium.com/@omergoldberg/javascript-call-apply-and-bind-e5c27301f7bb)

- ## [Arguments object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments)

- ## [`this` inside function](http://2ality.com/2014/05/this.html)

- ## The Scope of a Variable
  - [Variable scope](http://javascriptissexy.com/javascript-variable-scope-and-hoisting-explained/)

  - [YDNJS: Scope from a lower lever perspective](https://github.com/getify/You-Dont-Know-JS/blob/master/scope%20%26%20closures/ch1.md)

    - [Lexical Scope](https://github.com/getify/You-Dont-Know-JS/blob/master/scope%20%26%20closures/ch2.md)

- ## Closures

  - [What’s a JavaScript closure](https://medium.freecodecamp.org/whats-a-javascript-closure-in-plain-english-please-6a1fc1d2ff1c)

    - [An interactive tutorial for closure](https://jscomplete.com/labs/what-are-closures-in-javascript)

  - Why it's required in JS
    - [In-depth explanation of closure in YDKJS](https://github.com/getify/You-Dont-Know-JS/blob/master/scope%20%26%20closures/ch5.md)

  - [What are first class functions](https://hackernoon.com/javascript-and-functional-programming-pt-2-first-class-functions-4437a1aec217)



###Simple question to you should know
  - What is Prototypal Inheritance? How does it work?
  - Functional programming.
  - What is closure how does it work? Explain the application
  - Explain this in JS. 
  - Diff let var and const 
  - What is promise and write a polly fill for promise. Make sure you - have test case ready to test your code once completed
  - Map reduce and filter
  - Diff btw for each and normal for loop
  - CSS positioning , reset css, block vs inline , 
  - What is diff https and https2
  - What is eventloop 
  - How is CSR vs SSR and static sight diff
  - Understand all the fetch headers. And rest calls
  - Explain TCP 
  - Explain CDN and how is it better and how it helps to improve speed - give some examples of cdn you used
  - How to debug using chrome. Call stack debug
  - Explain async and await
  - Debounce,  throttle , bind polyfill
  - Explain react fiber , virtual dom comparison , how is it actually - implemented
  - What are the types of attack common what will you do to solve it
  - When to use local storage, session storage
  - Hardest library you have integrated explain
  - What all would you do to improve the performance of an application
  ( I divide into 3 stage, while architecting , while coding, deployment) 
    Architecting : webpack config, cdn , library to use etc different caching mechanism, reload , prefetch
  Coding: simple like from use let and const, use picture tag, use - memo ,
  - Deployment: capacity of server etc
  - Explain V8 engine of Chrome
  - Explain GC for Browser
  - Explain memory leak.
  - Make a facebook comment reply widget using JS
  - When to use redux ?
  - What is HOC tell some HOC which you have implemented in react and - also vanilla JS
  - New concepts you come across in FE development.
  - For performance improvement what all metric would you use if its up - to you and why.
  - Publish a npm module 
  - Tell 10 patterns use in JS
  - What is PWA make a small demo
  - Design a perfect Image component in react
  - Implement a single signon in react application
  - Integrate RazorPay in you application
  - What is a generator in JS how do you Implement it and when to use - it.
  - How do you ensure browser Compatibility for old bowser
  - How does redux work
  - All what you can do to improve you SEO.
  - How do you create customHooks? Give an example.
  - Explain how inheritance work in JS the memory location and what - happened when you create instance of it.
  - Advance question to you should know
  - ​​Create the HLD for NETFLIX/youtube , A BANKING APP,  FLIPKART, 
  - Write a LLD for once click sign up 
  - Write LLD for integration for integration of REDUX


### Some common coding you should know
Implement curry()
Composition 
Create a hook in ReactJS
Immutability helper in JS
Implement Promise
React Test case


We will try to answers for people who need coing skills impoved https://gist.github.com/ashwin-thinkify/77b64ed4680b38c3c795c3c81c42dffb

