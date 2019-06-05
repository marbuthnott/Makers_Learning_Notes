## Week 5
## w/c 28th May 2019

### Questions

* Get someone to explain how to use ActiveRecord.

### Week Goals

**I can test drive a simple front-end web app with Javascript**
Learning objectives:
* Build a working front end app.
* TDD using `Jasmin`.
* Ability to debug using JS.
* Understand JS syntax.

**I can follow an effective process for learning a new language**

## Tue 28th May 2019

### Code Review

WHAT WENT WELL:

* Modeling the code ahead of coding
* Using website design with CSS
* 25min planning increments.

WHAT COULD HAVE GONE BETTER:

* Use of travis.yml. Understanding what information to provide in the travis.yml and access error messages via github.

WHAT I FOUND OUT:

* DataMapper - An ORM (Object-Relational Mapping). Used in place of PG by managing databases. Significantly easier to use.

### Learning Java Script

* w/ Sophie Gill

JAVA basics:

* Asynchronous code. Focus on order things are happening
* Uses `Jasmin` to test drive
* Send screen recordings to coaches. Record in 'high quality' and 'quicktime'. No longer than 30mins.

### Afternoon pairing - Thermostat Challenge

* w/ Lisa

JavaScript definition - JavaScript (JS) is a lightweight interpreted or just-in-time compiled programming language with first-class functions. While it is most well-known as the scripting language for Web pages, many non-browser environments also use it, such as Node.js, Apache CouchDB and Adobe Acrobat. JavaScript is a prototype-based, multi-paradigm, dynamic language, supporting object-oriented, imperative, and declarative (e.g. functional programming) styles. Read more about JavaScript. [Link](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

LEARNING OBJECTIVES COVERED:

* Describe JavaScript as a scripting language built for the web
* Understand JavaScript's role in the browser ecosystem
* Use the Chrome console as a REPL
* Understand JavaScript language conventions

NEW SYNTAX:

* `console.log('Any string in here!!')`
* `var time = 2.0 * 2.5;` to set a variable
* use `===` unless good reason to use `==` [Link](https://dorey.github.io/JavaScript-Equality-Table/)
* creating an object:
```
var myObject = {} // you can make empty objects
var myOtherObject = {
                      some: 'stuff',
                      goes: 'in',
                      here: 123,
                      arrays: ['woah', 'check', 'it'],
                      nestedObject: {another: 'object'},
                      functionsToo: function(foo) { return foo }
                    }
```
* use `open -a "Google Chrome" index.html` to open a file in chrome.

* how to create a loop from 1 to 100 with method fBCalculator on object FizzBuzz
```
var printfb = new FizzBuzz();
for (var i = 1; i <= 100; i++) {
    console.log(printfb.fBCalculator(i));
}
```

NOTES

* Three Tier Web Architecture:
  - Web server
  - Application engine
  - Database

* (Intro to Javascript pill)[https://github.com/makersacademy/course/blob/master/pills/javascript&JasminePill.md]

**PAIRING REVIEW**

Feedback from pair programming
We looked at the Javascript basics,  how it differs from Ruby, using functions for classes and methods,
3 tier architecture

Understanding how to use chrome console as a recall.

Set up the Jasmine TDD environment
Wrote tests and code for fizzbuzz

What went well:
We completed the fizz buzz challenge and understood it.
We can set up a basic program and test in JS.


What didn’t go well:
Getting used to the syntax of a new language - using semicolons, curly brackets, camelCase,
Understanding how function is used.
Less descriptive error messages
The code we wrote was different from the walkthrough.
Using if instead of ? For boolean methods.

## Thursday 30th May 2019

**Daily Goals**

* Understanding JS syntax. Work through the Javascript pill and the Airport challenge.

### Javascript Syntax

`var Classname = function () {};` - 'class' creation of object factories. JS does not have classes in the same way as Ruby, however possible to see these as object factories for the time being.

Describe method in Javascript/Jasmine:
```
describe('', function() {
//method statements go here
});
```

`function() {}` declares the body of a method. Replaces ruby's `do` and `end`.

The full method now becomes:
```
methodName(function() {
// codeblock goes here
});
```

### Workshop - Encapsulation with the constructor and prototype pattern

* w/ Sophie

**LEARNING OBJECTIVES**

* Describe what a constructor function does. Describe what a constructor function's prototype does.
* Write a constructor function and prototype to encapsulate some behaviour.
* Explain the strengths and weaknesses of the constructor and prototype pattern as a way to encapsulate behaviour.

**NOTES**

`console.log()`:
* possible to console.log functions themselves

DEFINING FUNCTIONS:
```
function foo() {
  console.log("foo")
}
// foo
```

```
foobar("foo", function() {
  console.log("hi!")
})

function foobar(string, cb) {
  console.log(string)
  cb()
}
// cb for 'call back' calls the function from the previous statement
```

```
<!-- function Foo() {
  this._text = "hello, I'm foo";

  this.sayHi = function
} -->
```

**Farm Challenge**

An introduction to TDD with Javascript
```
As a shepherd
So my sheep can be safe
I want to have a pen they can go into

As a shepherd
So my sheep can be friends
I want them to be able to say their names

As a shepherd
So I can know all my sheep are home
I want to get a list of all the names of the sheep in the pen
```

Pen:
* holds sheep
* lists sheep by name

Sheep:
* says name

```js
function Pen() {
  this._sheep = [];
}

functin Sheep(name) {
  this._name = name
}

Pen.prototype.add = function(sheep) {
  this._sheep.push(sheep);
};

Pen.prototype.listSheep = function() {
  console.log('baaa!', this._name);
}

// alternative way of adding functions to a constructor
Pen.prototype = {
  add: function(sheep) {
    this._sheep.push(sheep);
  },
  listSheep: function() {
    console.log('baaa!, this._name);
  };
}

Sheep.protogype.sayName = function() {
  console.log(this._name);
}

var pen = new Pen();

var dolly = new Sheep("dolly");

pen.add(dolly);

dolly.sayName();
```

* If an instance of a class is created and the constructor then has a new function added to it, the instance class will still be able to call on that function.

* Using `SpyOn` in Javascript as a replica of stubbing in ruby.
```js
  it('blocks takeoff when weather is stormy', function(){
    plane.land(airport)
    spyOn(airport,'isStormy').and.returnValue(true);
    expect(function(){ plane.takeoff();}).toThrowError('cannot takeoff during storm');
    expect(airport.planes()).toContain(plane);
  });
  ```
Where the `spyOn` method ensures `true` is returned when `airport.isStormy` is called.

### Afternoon Pairing - Thermostat Challenge

* w/ Yemi

-[X] Thermostat starts at 20 degrees
-[X] You can increase the temperature with an up function
-[X] You can decrease the temperature with a down function
-[X] The minimum temperature is 10 degrees
-[X] If power saving mode is on, the maximum temperature is 25 degrees
-[X] If power saving mode is off, the maximum temperature is 32 degrees
-[X] Power saving mode is on by default
-[X] You can reset the temperature to 20 with a reset function
-[X] You can ask about the thermostat's current energy usage: < 18 is low-usage, < 25 is medium-usage, anything else is high-usage.
(In the challenges where we add an interface, low-usage will be indicated with green, medium-usage indicated with black, high-usage indicated with red.)

**Notes**

`counter++` will increase integer variable `counter` by 1incrementally
`'use strict';` at the top of the spec file. Ensures the file is executed in a certain way.

* Notes on [JavaScript constructors, prototypes, and the 'new' keyword](https://content.pivotal.io/blog/javascript-constructors-prototypes-and-the-new-keyword)

* Google Developer Philip Walton talking about [JavaScript Privacy](https://philipwalton.com/articles/implementing-private-and-protected-members-in-javascript/)

## Thursday 30th May 2019

* `Node.js` - Node.js is an open-source, cross-platform JavaScript run-time environment that executes JavaScript code outside of a browser. Node.js lets developers use JavaScript to write command line tools and for server-side scripting—running scripts server-side to produce dynamic web page content before the page is sent to the user's web browser. Consequently, Node.js represents a "JavaScript everywhere" paradigm,[7] unifying web application development around a single programming language, rather than different languages for server- and client-side scripts.

* `npm` - npm (originally short for Node Package Manager)[3] is a package manager for the JavaScript programming language. It is the default package manager for the JavaScript runtime environment Node.js.

* `Document Object Model (DOM)` - The Document Object Model (DOM) is an application programming interface (API) for HTML and XML documents. It defines the logical structure of documents and the way a document is accessed and manipulated.

* `jQuery` - jQuery is a JavaScript library designed to simplify HTML DOM tree traversal and manipulation, as well as event handling, CSS animation, and Ajax.[2] It is free, open-source software using the permissive MIT License.

* `jQuery` is written in Javascript but is designed to improve readability and ease of use. It consists of Javascript methods which are added to create dynamic behavior.

```js
$(document).ready(() => {
$('#nav-dropdown').hide();
});
```
Here the `ready` method waits until the HTML page's DOM is ready to manipulate. It ensures the web page is rendered before any jQuery code executes.

The `$` used before anything we target is an alias for `jQuery`. The two are interchangeable.

`let $name = $('#id');` - this is the basic syntax for storing a jQuery object in a variable.

Below  the `.on()` method adds the `click` event handler to the `#login` element. Inside the callback function we use the `.show()` method to show the jQuery object saved in the `$loginForm`variable.
```js
$('#login').on('click', () => {
  $loginForm.show();
})
```

The below `mouseleave` method will hide the `navDropdown` as soon as the mouse moves to a different area of the page.
```js
  $navDropdown.on('mouseleave', () => {
    $navDropdown.hide();
  })
```

* [JQuery Docs](http://api.jquery.com/)

## Saturday 1st June 2019

**Learning Objectives**

* Continue online tutorial on jQuery at [Link](https://www.youtube.com/watch?v=2OMzGhlIZpg&t=541s)


* Here we execute some basic code within the `.ready` method. When we click `button` we get an alert created using the text we input linked by the input `id`.
```html
  <body>
    <h1>jQuery Tutorial</h1>
    <p>By Magnus Arbuthnott</p>

    <input type="text" id="someText" value="">
    <button>Submit</button>
    
    <script>
      $(document).ready(function() {
        $("button").click(function(){
          alert("Value: " + $("#someText").val());
        });
      });
  
    </script>

  </body>
  ```

  * Below we use the `.addClass` method which calls the style and adds it to the `h1` tag.
  ```html
    <body>
    <h1>jQuery Tutorial</h1>
    <p>By Magnus Arbuthnott</p>
    
    <script>
      $(document).ready(function() {
        $("button:last").click(function(){
          $("h1").addClass("styleclass")
        });

        $("p").click(function(){
          $(this).hide();
        });
      });

    </script>

    <style>
      .styleclass {
        border: 5px solid tomato
      }
    </style>

    <button>Try add border</button>

  </body>
  ```
Is is also possible to use the `.removeClass()` and `.toggleClass()`. Additionally we've applied the `.hide()` method to the `<p>` toggle; this hides the text whenever we click on it.

`$(selector).on(event, function)` -> the `.on()` method takes an event and a function to execute when the event occurs.
`$(selector).keypress(function)` -> on the press of any character a function is executed:
```html
  <body>
    <h1>jQuery Tutorial</h1>
    <p>By Magnus Arbuthnott</p>
    <input type="text" id="someText" value="">

    <script>
      $(document).ready(function() {
        $("input").on("keypress", function() {
          $("p").hide();
        });
      });
    </script>
  </body>
```

* `$(selector).hide(speed, callback);`
* `$(selector).show(speed, callback);`
* `$(selector).toggle(speed, callback);`:
Here the toggle button toggles the `<p>` between hide and show.
```html
  <body>
    <h1>jQuery Tutorial</h1>
    <p>By Magnus Arbuthnott</p>
    <button class="button" id="toggle">Toggle</button>

    <script>
      $(document).ready(function() {
        $("#toggle").click(function() {
          $("p").toggle();
        });
      });
    </script>
  </body>
```
* `$(selector).fadeIn(speed, callback);`
* `$(selector).fadeOut(speed, callback);`
  * Possible to use `$(selector).fadeOut("slow")` to select the speed at which the image is hidden.
* `$(selector).slideUp(speed, callback);`
* `$(selector).slideDown(speed, callback);`
* `$(selector).dragable(speed, callback);`
  * Possible to drag and drop elements around the web page.
* `$(selector).datepicker();`
  * Can be placed directly into a `script` tag as opposed to using a `.ready()` function.

* CONSTRUCTOR -> The constructor method is a special method for creating and initializing an object created. Here is the Polygon class constructor method:
```js
class Polygon {
  constructor() {
    this.name = "Polygon";
  }
}

var poly1 = new Polygon();

console.log(poly1.name);
// expected output: "Polygon"
```

* Is there any youtube walkthroughs which would be useful for programming in JS???