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
  <img width="800" height="600" src="https://github.com/marbuthnott/makers_learning_notes/blob/master/images/IMG_20190521_114336.jpg?raw=true/800/600">
</p>

* Specific use of many-to-many.

* Useful links. [Ruby Database Basics](https://www.learnhowtoprogram.com/ruby/ruby-database-basics/database-schema-and-relationship-types)