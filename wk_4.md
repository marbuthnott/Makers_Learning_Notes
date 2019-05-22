## Week 3
## w/c 20th May 2019

### Weekly Questions

* config.ru vs running ruby app.rb with `run! if app_file == $0` at the bottom.

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

**Definition**
An Entity Relationship Diagram shows the relationships of entity sets stored in a database. An entity in this context is an object. An entity set is a collection of similar entities.

ERDs are used to sketch out the design of a database.

**Diagram Symbols**

* Entity represented by a **rectangle** is an object or concept about which you want to store information.
* Actions are represented by **diamond** shapes. They show how two entities share information in the database.
* **Ovals** are attributes. A key attribute is the unique distinguishing characteristic of the entity. An employees social security number might be the employee's key attribute.