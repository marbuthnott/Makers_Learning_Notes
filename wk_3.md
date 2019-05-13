## Week 2
## w/c 13th May 2019

## Mon 13th May 2019

### Weekly Goals

* Build a simple web app
    * (at least 2 pages + a form)
* Follow an effective debugging process for web applications
* Explain the basics of how the web works (e.g. request/response, HTTP, HTML, CSS)
* Explain the MVC pattern

**Daily Goals**

* Define an appropriate code review process.

### Code Review Workshop - Reviewing the airport_challenge

* W/ Sam Kitchen

**Structure for a code review**

* STEP 0 - Got to master repository and view pull requests to being reviewing code.
* STEP 1 - Structure and supporting files. Check gemfiles are correct. Review README.md
* 

### Feedback Workshop

* W/ Alice Lieutier

* How to come up with a coherent plan to start a project:
    * Use trial and error

* UML - Unified Modelling Language. Can be used but not critical. As long as a diagram is useful and applicable then it is appropriate.

**What is the web**

* Web is the visible outlet of the internet. i.e. web pages
* There is a lot of activity on the internet outside of the web. e.g. emails, VOIP, software update... etc

* Web created 1989
* Web opened to public 1991

* **Server** is a piece of software that takes incoming requests and sends messages to other sources. **The server is the software on a computer that stores information**.
* **Data Centers**. A group of servers.
* **DNS table**. Similar to a phone booth. Held locally.
* Request from laptop -> Local DNS table -> Main server (global).

* Browser (client) will send requests to the server
* The server will send responses to the browser

* **HTTP (Hyper Test Transfer Protocol)**. Revolutionized the way the internet was used. Previously the user would have to navigate to the server and use `grep` to search the directory, often the user would not have the right permissions. HTTP allowed users to access data with the use of a link which they could share.
* **HTML (Hypertext Markup Language)**. Standard programming language for creating web pages and web applications.

* **What can be sent?**
    * Images
    * HTML / CSS
    * Videos
    * Mp3
    * JavaScript -  this is the only language which executes on the browser. All the rest of it executes on the server.
    * PDFs

### Follow an effective debugging process for web apps

 * Debugging mantra **Get visibility. Tighten the loop**.

 * Updated portfolio directly with

 ### MVC - Model View Controller

 * [Medium - MVC](https://medium.freecodecamp.org/simplified-explanation-to-mvc-5d307796df30)

 * Three main componentsL:
    * Controller - handles the incoming requests from the User.
    * Models - What the users data look like on the back end.
    * View - The HTML template that is returned after your request is resolved.

* When interacting with a system you are usually able to Create, Retrieve, Update, and Delete objects (CRUD).

### Afternoon pairing

* W/ Chris Plant

* HTTP on the command line:
    * use `brew install httpie` to download. Then run url's after `http` to receive their code and their header.

* Use `http -v <URL>`. This will print the code for the request and the response. The `-v` stands for 'verbose'. Constitutes the *request*, the *response*, and the *body*.

* What is a URL:
    * A *Uniform Resource Locator*.
    * A simple URL would comprise of a minimum three parts. The protocol (`https://`), domain name (`domain name`), the path (`/blog/anatomy-of-a-url`)
    * Possible to pass arguments in the form of `GET` requests or `POST` requests. `POST` requests send data to a server to create / update a resource.

* A `POST` request can be used as follows `http -f POST https://getpostworkout.herokuapp.com/ name=Magnus`

```
[2019-05-13 15:08:32] INFO  WEBrick 1.4.2
[2019-05-13 15:08:32] INFO  ruby 2.5.0 (2017-12-25) [x86_64-darwin18]
== Sinatra (v2.0.5) has taken the stage on 4567 for development with backup from WEBrick
[2019-05-13 15:08:32] INFO  WEBrick::HTTPServer#start: pid=7053 port=4567
```
* `WEBrick 1.4.2` refers to the server
* `[x86_64-darwin18]` refers to the architecture and `darwin` the operating system
* `4567` is the port (endpoint of communication). The response from the server is sent through the port which is unique to types of data.
* `WEBrick::HTTPServer#start: pid=7053 port=4567` refers to the server starting up. pid (process identifier).

* Sinatra is a framework for creating web applications. Sinatra reading:
    * [Sinatra Main Intro Doc](http://www.sinatrarb.com/intro.html)
    * [Sinatra Up and Running](http://shop.oreilly.com/product/0636920019664.do)
    * [Jump Start Sinatra (Book)](http://www.sitepoint.com/store/jump-start-sinatra/)

* **Shotgun** automatic reloading system for web development. As opposed to stopping and restarting app it changes automatically.

* `shotgun app.rb -p 4567` this tells the system to run `app.rb` with `shotgun`. `-p` specifies which port to use; thereby keeping the same local address.

* **Separation of Concerns** - design principle for separating a computer program into distinct sections. I.e. separating each language to it's specific file. There will be an html file, a css file and a JS file.

* `erb` (embedded ruby) is a templating system. Embedded ruby means that the templates can combine plain text, such as HTML code, with executable Ruby code. Used to call the `index` file which contains the HTML code with `erb(:index)`.

* Using `<%= 2 + 2 %>` within an `erb` file will print `4`. While omitting the `=` will only evaluate it but not interpolate it into the string.

* `erb` reading [An introduction to ERB Templating](https://www.stuartellis.name/articles/erb/)

* As a rule of thumb logic should be pushed down the stack wherever possible. View (i.e. `irb`) files should be limited to light conditionals, such as `if` and `else`, and light iterators such as `each`. The view files should be able to call on these.

* Sinatra views syntax -> [Sinatra Views](http://sinatrarb.com/intro.html#Views%20/%20Templates)

* **Params**. In the context of HTTP requests, parameters provide a way for information to be passed from a user to your application. Params are used to allow interactivity on a website, for example by allowing form data to be sent.

More info at [Makers - Params pill](https://github.com/makersacademy/course/blob/master/pills/params.md)

`@username = params[:username]`
will be inputed in the query string like:
`?username=marbuthnott`
