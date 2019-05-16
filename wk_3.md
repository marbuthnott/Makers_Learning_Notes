## Week 2
## w/c 13th May 2019

## Mon 13th May 2019

### Qs over the course of the week

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

* Use the URL `http://localhost:4567/` to access

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

## Tues 14th May 2019

### takeaway_challenge cont.

* `rsepc mocks` on github provide comprehensive list of syntax

* Use of **instance doubles** where it is possible to test the method against the class it is being called against, even if that is not the correct spec file.

`let(:menu) { instance_double("Menu") }`

### Modelling the HTTP request/response cycle

* Alice Lieutier

* Wk 3 workshop - [Process modelling, applied to HTTP request/response cycle](https://github.com/makersacademy/skills-workshops/tree/master/week-3/process_modelling)

* Use `inspect` from the right click menu to see the HTML code.

* `network` tab shows all activity on the web page's network.
    * `Headers` sub tab shows `status codes` (i.e. whether the site is working. numbers range from 100-500)
    * 1xx, 2xx: all ok, 3xx: redirect, 4xx: client error, 5xx: server error.

* **Request Headers** within `inspect`, `network` and `headers`:

Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8
Accept-Encoding: gzip, deflate
Accept-Language: en-GB,en-US;q=0.9,en;q=0.8
Cache-Control: max-age=0
Connection: keep-alive
Host: makers-cats.herokuapp.com
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_3) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/73.0.3683.86 Safari/537.36

* **Response Headers** within `inspect`, `network` and `headers`:

Connection: keep-alive
Content-Length: 219
Content-Type: text/html;charset=utf-8 ***direct reply to the client***
Date: Tue, 14 May 2019 09:07:04 GMT
Server: WEBrick/1.3.1 (Ruby/2.3.4/2017-03-30)
Via: 1.1 vegur
X-Content-Type-Options: nosniff
X-Frame-Options: SAMEORIGIN
X-Xss-Protection: 1; mode=block

* Link to cheatsheet by myself and Remi.

* Great link!! [HTTP and Websockets: Understanding the capabilities of today’s web communication technologies](https://medium.com/platform-engineer/web-api-design-35df8167460)

    * HTTP the underlying comms protocol of WWW. Request-response protocol in the client-server computing model.

### Afternoon pairing - HTTP

* W/ Frankie

**Starting from Step: Sinatra Views**

**Gemfiles**

* When opening a project, create a Gemfile with the requirements and `source "https://rubygems.org"`.

* **Tags in HTML** - here we create an h1 (header1) tag `<h1>This is heading 1</h1>`.

* Use `p params` to execute it in the terminal:
```
get '/named-cat' do
  p params
  @name = params[:name]
  @age = params[:age]
  erb(:index)
end
``` 
In the Ruby file. And the following in the `index.erb`:
```
<div
style='border: 3px dashed red'>
<img src='http://bit.ly/1eze8aE'>
</div>

<h1>Hi there, Visitor! <%= @name %>. Who is <%= @age %> years old! </h1>
```
Now if you type this in as a URL `http://localhost:4567/named-cat?name=Magnus&age=60`. - this part of the URL `name=Magnus&age=60` is the query string.

* Using form to get input from the user on the web page as opposed to having it written into the URL:
```
<form action="/named-cat">
  First name: <input type="text" name="name">
  Age: <input type="text" name="age">
  <input type="submit" value="Submit">
</form>
```
* Using an `if` statement within HTML:
```
<% if !@name.empty? %>
<h1>My name is <%= @name%>. And i am <%= @age %> years old!!</h1>
<% end %>
```

* Example of an incoming request from our server logs:
[image](https://github.com/makersacademy/course/blob/master/intro_to_the_web/images/sinatra_get_request.png)
[image](https://github.com/makersacademy/course/blob/master/intro_to_the_web/images/sinatra_get_request_annotated.jpg)

* Set of common methods for HTTP:
    * [Link](https://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html) to method definitions.
    * **GET**: retrieve information
    * **POST**: modify a resource
    * **OPTIONS**: a request for information about the communication options available on the request/response chain.
    * **HEAD**: identical to GET except the server MUST NOT return a message-body.
    * **PUT**: requests that the enclosed entity be stored under the supplied Request-URI (an already existing resource).
    * **DELETE**: origin server delete the resources identified by the Request-URI.
    * **CONNECT**: for use with a proxy that can dynamically switch to being a tunnel.

## Wed 15th May 2019

### Daily Goals

* [Domain Modeling Workshop](https://github.com/makersacademy/skills-workshops/tree/master/week-2/domain_model_diagramming)
* Start Birthday Greeter App - [Link to Makers workshop](https://github.com/makersacademy/course/blob/master/intro_to_the_web/post_challenges/birthday_app.md)

### Empathy Workshop

* Dana

**Effects of empathy**

* Empathy is critical in building trust. If an individual makes the effort to demonstrate an understanding of someone else's emotions, that process helps to build trust.

* 3 types of empathy:
  * Affective empathy
  * Empathic concern
  * Cognitive empathy

**Effective tools**

* 'Just like me' concept. Relate to other people and draw out similarities
* Metta Bhavana - simply wanting to please others/ make them happy
* Empathetic Listening - giving an individual full attention as opposed to waiting for the next opportunity to speak

### Birthday Greeter App

* Using capybara with RSpec.
* Capybara is a web-based test automation software that simulates scenarios for user stories and automates web application testing for behavior-driven software development. Written specifically for Ruby.

* Using the sinatra MVC (Models, Views, and Controllers).
    * creates `models`, `views`, and `controllers` folder.
    * optional `helpers` and `lib` folders.

### Afternoon pairing

* Vijay

* Within RSpec to test private methods use `.send` methods.

* Use of private methods

* `brew cask install firefox` installs Firefox browser

* Capybara default to use firefox app

* Manipulate capybara from the `pry` repl:
    * `click_button 'Click me!'` - will select specified button
    * `check('first')` - will check first box. `second` for second box.
    * [Capybara workout](http://capybaraworkout.herokuapp.com/workout)

???
```
require 'sinatra/base'

class Battle < Sinatra::Base
    get '/' do
        'Hello Battle'
    end

    run! if app_file == $0

end
```
* Almost every Capybara feature test involves this process:

    *  What does the user have to do?
    *  What does the user expect to see?

**Pairing Review**

* Discussed daily goals:
    * Test driving private methods via `.send`.
    * Discussed use of `context` within RSpec
* Initialised the battle web app
* Sorted Gemfile
* Set up config.ru
* Familiarised with capybara
* Initialised server through `rackup`
* Created web app to receive names, store as `session` instance variables, created POST-redirect loop to avoid rendering a view from a POST request, and returned to `view` via `get '/play'`.

* **Worked well**
    * Working through daily goals at start of pairing session
    * Being thorough

## Thu 16th May 2019

### Daily goals

* Web debugging workshop w/ Alice Lieutier
* Servers practical. [Link](https://github.com/makersacademy/skills-workshops/blob/master/practicals/servers_and_clients/servers.md)

### Servers practical