## Week 3
## w/c 20th May 2019

### Weekly Questions

* config.ru vs running ruby app.rb with `run! if app_file == $0` at the bottom.

* How does the following code work? Does it set `order` and `sms` with default values?:
```
  def initialize(menu:, order: nil, sms: nil)
    @menu = menu
    @order = order || Order.new(menu)
    @sms = sms || SMS.new
  end
```

* ENVIRONMENTAL variables??

* Step 11 on bookmark challenge. When adding a `url`. Tests passing yet throwing error when feature testing it through `rackup`. Also walkthrough suggests it should be failing.

## Mon 20th May 2019

### Code Review

* w/ Ben Reynolds-Carr

**Q/A session run by ???**

* Focus on HTML/CSS -> should not be concerned with learning language. Focus should be on test driving / use of sinatra.

* `self.` -> replaces an instance of an object, a method is instead called on the the object directly. More research needed!!

* One to many relationships

**Weekly Learning Objectives**
* To build a web app that uses a database.

**Personal weekly goals**

* I can understand the Class Responsibility Collaborator cards within domain modelling.
* Explain how basic databases work (e.g. tables, SQL, basic relationships).
* Follow an effective debugging process for database applications
* Generate user stories from requirements - weekly bookmark challenge
* Entity Relationship Diagrams
* Improve in HTML
* Fundamentals of PosgreSQL

**Main Focuses**
* Agile and TDD
* Engineering and 'Dev Recipes'
* Databases
* Tooling

**Databases**
* Postgres. A way of structuring our database.
* In order to interact with Postgres we use `PSQL`.
* Use `real database` and `test database`. The `test database` is used to test the behavior of the database, while the `real database` is not affected by the test. E.g. testing if a database accepts and input; this would happen in the `test database`.
* **RESTful** routes when defining routes into the controller.

### Afternoon pairing - Bookmark challenge

* W/ Ben Reynolds-Carr

* Set up a web page. [Github pill](https://github.com/makersacademy/course/blob/master/pills/ruby_web_project_setup_list.md)

* `run! if app_file == $0` entered at the base of the app.rb file. It starts the server if ruby file executed directly.

* Rails has a set of conventions for what URLs to use when dealing with directories. These are on top of the basic `create`, `read`, `update`, and `delete`:
```
Verb    URI Pattern            Controller#action
------  ---------------------  ------------------
GET     /restaurants           restaurants#index
POST    /restaurants           restaurants#create
GET     /restaurants/new       restaurants#new
GET     /restaurants/:id/edit  restaurants#edit
GET     /restaurants/:id       restaurants#show
PATCH   /restaurants/:id       restaurants#update
PUT     /restaurants/:id       restaurants#update
DELETE  /restaurants/:id       restaurants#destroy
```

* REST - Representational State Transfer. In RESTful apps the URLs aren't just vague strings we make up on the spot, instead they map to a resource. The commands above indicate what the route does.

* `self` can be applied when each iteration of a class contains the same thing. 

## Tue 21st May 2019

### SQL Familiarisation

* Updated code cheatsheet -> Found in my docs.

### Workshop - Databases 2

[Link](https://github.com/makersacademy/skills-workshops/tree/master/week-4/databases_2)

* w/ Carolina

**Learning Objectives**

* CLASS RESPONSIBILITY COLLABORATOR CARDS (CRC)

* Explain how to use CRC cards to model a domain
* Model a simple domain using CRC cards
* Infer database structure from domain structure

**CRC Layout**

Checklist
* Class name table
* Hand-drawn CRC cards

**User Stories**
```
As a coach
So I can get to know all students
I want to see a list of students' names
```
* 'T' shaped graph with responsibilities on the left and collaborations (i.e. other objects) on the right.

One to many relationships:

  * `primary key` - The PRIMARY KEY constraint uniquely identifies each record in a table.
  * `foreign key` - A FOREIGN KEY is a key used to link two tables together.

* Worked in group w/ Laurence, Edina, and Lisa through receiving user stories and converting into a 'T' shaped graph and then translated into a table.

<p align="center">
  <img width="800" height="800" src="https://github.com/marbuthnott/makers_learning_notes/blob/master/images/IMG_20190521_114336.jpg?raw=true/800/800">
</p>

* Specific use of many-to-many.

* Useful links. [Ruby Database Basics](https://www.learnhowtoprogram.com/ruby/ruby-database-basics/database-schema-and-relationship-types)

## Afternoon Pairing - bookmark_challenge

* w/ Nick Barnes

### Learning Objectives

* Attach a database to a web application
* Setting up a testing environment for web application with a database

### Pairing notes

* Why is a database the best solution here? -> It can be manipulated by the program and accessed via PostgreSQL. Immediately available.

* [Postgres cheatsheet](http://www.postgresqltutorial.com/postgresql-cheat-sheet/)
* [PostgreSQL Command Line Cheat Sheet 2](https://blog.jasonmeridth.com/posts/postgresql-command-line-cheat-sheet/)

**SETTING UP A DATABASE**
* Install PostgreSQL - used `brew install postgresql`
* Started PostgreSQL via `brew services start postgresql`
* Enter postgres through `psql postgres`
* Create a database `CREATE DATABASE bookmark_manager`
* Show databases `\l`
* Connect to a database `\c bookmarks`
* Create a new table. Where `id` is the primary key and `url` has a varchar of 60:
```
CREATE TABLE bookmarks(id SERIAL PRIMARY KEY, url VARCHAR(60));
```
* Show table `\dt`
* Delete a table `DROP TABLE bookmarks;`

* Commands beginning with a \ are psql-specific commands (e.g. connecting to databases using \c).
* Everything else is part of SQL (e.g. SELECT * FROM ...), so can be used with any SQL-based Relational Database.

* Introduction to CRUD (**c**reate, **r**ead(query), **u**pdate, and **d**elete)

**USEFUL SYNTAX**
* to display details of a table `\d`.
* Insert multiple rows:
```
INSERT INTO bookmarks VALUES(1, 'http://www.makersacademy.com'), (2, 'http://www.askjeeves.com'),...;
```
* Alternatively it can assume the id if you are adding the data iteratively:
```
INSERT INTO bookmarks (url) VALUES ('http://www.askjeeves.com'), ('http://www.twitter.com')...;
```
* Use `SELECT * FROM bookmarks;` to view all records in `bookmarks` table.
* Limit the number of records viewed to the top two using `SELECT * FROM bookmarks LIMIT 2;`.
* Or scoping specific data using `SELECT * FROM bookmarks WHERE url = 'http://www.makersacademy.com';`.
* To delete a record we use `DELETE FROM bookmarks WHERE url = 'http://www.twitter.com';`.
* To update / replace a record we can use `UPDATE bookmarks SET url = 'http://www.destroyallsoftware.com' WHERE url = 'http://www.askjeeves.com';`

**ATTACHING A DATABASE TO A WEB APPLICATION**

* install the `pg` gem. This is the Ruby interface to the PostgreSQL.

* Ruby code to draw data from a database. First of all run `require 'pg'` at the top of the file. Followed by this code in the class file:
```
# this assigns the 'bookmark_manager' database to 'conn'
conn = PG.connect(dbname: 'bookmark_manager')
# this extracts the table from 'bookmark_manager' and assigns it to 'result'
result = conn.exec("SELECT * FROM bookmarks;")
# this extracts the 'url' column and pushes to an array
result.map { |bookmark| bookmark['url'] }
```

**INSTALLING AND CONNECTING TABLE PLUS**

* `PostgreSQL` server is running 'backgrounded' on the local machine, by default on `Port 5432`.

* Installed TablePlus:
  * Where it is -> localhost (i.e. your PostgreSQL server is running 'backgrounded' on your local machine, on Port 5432).
  * What login details are required -> Your computer's name as a username (or, you can find this out by listing databases in psql), and no password. (i.e. `student`)
  * What database should it start with -> The bookmark_manager database.
 
**SETTING UP A TESTING ENVIRONMENT**

* `psql`, `pg` and `TablePlus` are interfaces to the `PostgreSQL` server.

* Multiple environments in applications:
* A **development** environment that runs locally on your computer, so you can click around it and work on it.
* A **production** environment that runs remotely on someone else's computer, so other people on the internet can click around it.
* A **test** environment that runs locally on your computer whenever you run your tests. It comes into being especially for your tests, and disappears straight after your tests finish.
```
Additionally a staging environment, where your application runs remotely on someone else's computer, at a secret link so you can click  around it to check it's all working before it's moved to production.
```

PROCESS FOR SETTING UP A TESTING ENVIRONMENT:
* Set up a database for our test environment.
* Set up an Environmental Variable to tell the application to start in the test environment.
* Write a script that sets up the testing environment before our tests run.
* Integrate the script with our test runner `rspec` so we don't have to think about it anymore.

## Mon 20th May 2019

**Daily Goals**
* Entity Relationship Diagrams
* Review youtube of takeaway challenge

### Entity Relationship Diagrams (ERD)

* [Hackmd example from Makers](https://hackmd.io/SQFve009TPah8w97EDfPew?both)

* Useful example created as a flow chart in draw.io:

![Flow chart created in draw.io](https://github.com/marbuthnott/makers_learning_notes/blob/master/images/Untitled%20Diagram-ERD%20Data%20Structure%20-%20Habit%20Tracker%20App.jpg?raw=true)

* `draw.io` has specific ERD tab.

**Definition**
An Entity Relationship Diagram shows the relationships of entity sets stored in a database. An entity in this context is an object. An entity set is a collection of similar entities.

ERDs are used to sketch out the design of a database.

**Diagram Symbols**

* Entity represented by a **rectangle** is an object or concept about which you want to store information.
* Actions are represented by **diamond** shapes. They show how two entities share information in the database.
* **Ovals** are attributes. A key attribute is the unique distinguishing characteristic of the entity. An employees social security number might be the employee's key attribute.

## Continued review of Takeaway Challenge on youtube

Questioned the use of the following code to instantiate with default values:
```
  def initialize(menu:, order: nil, sms: nil)
    @menu = menu
    @order = order || Order.new(menu)
    @sms = sms || SMS.new
  end
  ```
## Afternoon pairing

* w/ Cosmin

### Cont. SETTING UP A TEST ENVIRONMENT

* Created a `bookmarks_manager_test`. In psql run:
```
CREATE DATABASE "bookmark_manager_test";
```
* Create an identical table in `bookmarks_manager_test` that we have in `bookmark_manager`:
```
CREATE TABLE bookmarks(id SERIAL PRIMARY KEY, url VARCHAR(60));
```

* Introduced environmental variables using `p ENV` in `app.rb`.

* Added `ENV['ENVIRONMENT'] = 'test'` to the top of our `spec_helper.rb`. This instantiates a test environment whenever we run `rspec`.

* Updated `bookmarks.rb` with the following:
```
  def self.all
    if ENV['ENVIRONMENT'] == 'test'
      conn = PG.connect(dbname: 'bookmark_manager_test')
    else
      conn = PG.connect(dbname: 'bookmark_manager')
    end
    
    result = conn.exec("SELECT * FROM bookmarks;")
    result.map { |bookmark| bookmark['url'] }
  end
  ```
  Here we added an `if` statement to the method. It calls the `test` environment when we run rspec.

* Every time rspec is run new entries are made to the `test` database and respective table. Therefore after each test we must remove these entries. Create `setup_test_database.rb` and insert the following:
```
require 'pg'

p "Setting up test database..."

conn = PG.connect(dbname: 'bookmark_manager_test')

# Clear the bookmarks table
conn.exec("TRUNCATE bookmarks;")
```
`TRUNCATE` removes the contents of the `bookmarks` table. Now every time we execute `rspec` in the command line is clear the contents of the table. Ideally we would have this executing at the beginning of each test. This can be achieved with the following at the top of our `spec_helper`:
```
RSpec.configure do |config|
  config.before(:each) do
    setup_test_database
  end
end
```

**PAIRING REVIEW**

What went well:
* Good switching scheme. Adhered to the timer but completed each task before switching.
* Thorough understanding of concept before moving to next step.

What we did (summary):
* Created testing environment for database
* Altered the database by being able to enter new rows via the app.rb and #add within the bookmarks.rb file.
* Refactored.
* Added new columns.
* Started step 11.

Cosmin suggested a learning resource, `Jesus Costello` who has a youtube account focused on ruby fundamentals.

## Mon 20th May 2019

**Daily Goals**

* Continue with takeaway challenge youtube walkthrough:
  * Improve understanding of Twilio.
* 1hr on process workshop - improve understanding of working in multiple environments.
* Focus on web apps with databases - complete the [Daily Diary](https://github.com/toddpla/daily-diary) project on github.

**Goals Completed**

*

### Cont. Takeaway challenge youtube walkthrough

SETTING UP TWILIO FOR OUTBOUND CALLS
* `gem ruby-twilio` in the Gemfile
* create `make_call.rb` or `send_text.rb`. In the file include:
  * `require("bundler")`
  * `Bundler.require`
  * Declare our account variables. Look something like the below. They are stored in environment variables for safe keeping but could be called directly with `account_sid = "ACxxxxxxxx"` and `auth_token = "fjiewofjdsklaf"`:
    * `account_sid = ENV["TWILIO_ACCOUNT_SID"]`
    * `auth_token = ENV["TWILIO_AUTH_TOKEN"]`
  * Variables used to create twilio rest client:
    * `@client = Twilio::REST::Client.new(account_sid, auth_token)`
  * Use the rest client to create a phone call:
    * Again phone number is stored as an environment variable for safe keeping).
    * `from` number is the number you purchased from the twilio numbers console.
    * `url` is the website that twilio uses to find instructions on what to say - this one's just a demo. It essentially it runs some HTTP code.
  ```  
  @client.calls.create(
    to: ENV["MY_PHONE_NUMBER], 
    from: "+12152341751",
    url: "http://demo.twilio.com/docs/voice.xml"
  )
  ```
* back to terminal and run `bundle exec ruby make_call.rb`

SETTING UP TWILIO FOR INBOUND CALLS
* `gem sinatra` in Gemfile
* `bundle` to install
* create `app.rb` file to include:
  * `require "bundler"` - using Bundler to pull in the Twilio bundler helper library and sinatra web framework
  * `Bundler.require()`
  * Create a `post` route called `/voice` where twilio will request some TwiLM when a call comes in. This uses text to speech to say "Hello from your pals at Twilio":
```
post "/voice" do
  Twilio::TwiML::VoiceResponse.new do |r|
    r.say("Hello from your pals at Twilio")
  end.to_s
end
```
Here `end.to_s` will return the string representation out of this route

* back to terminal and run `bundle exec ruby app.rb` - this will start a server on a given port within localhost (it will print the port you are using).
* create an ngrok tunnel to get twilio to reach our local host code, by typing - `ngrok http 4567` where `4567` is the specific port.
  * the ngrok will give a publicly accessible url which can be copied (it's the `Forwarding`, `https` url). Then posted into the twilio app to link to when calls come in, paste under the `A CALL COMES IN` with `Webhook` and `HTTP POST` selections.

### Daily Diary Web App - Workshop

* [Daily Diary - github](https://github.com/toddpla/daily-diary)
* [Daily Diary - Diode](https://diode.makersacademy.com/students/soph-g/projects/2074)

* Project to diagram the Entity relationships. Draw.io file stored in ./workshops/practicals/daily-diary

![Daily Diary Workshop (https://github.com/marbuthnott/makers_learning_notes/blob/master/images/Untitled%20Diagram.jpg)]