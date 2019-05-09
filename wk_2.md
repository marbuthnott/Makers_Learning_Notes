## Week 2
## w/c 6th May 2019

## Tues 7th May 2019

### Code Review Workshop - Reviewing the airport_challenge

### Coach Advice

* Alice Lieutier

**Code Reviews**

* Use code [Review Rubric](https://github.com/makersacademy/airport_challenge/blob/master/docs/review.md)
* Use of comments and following the rubrics guidelines.
* Format: 30mins code review, 30mins feedback/implementing feedback.

**Weekly Goals**

* Use all of week 1's skills (don't underestimate the importance of this)
* Break one class into two classes that work together, while maintaining test coverage
* Unit test classes in isolation using mocking
* Explain some basic OO principles and tie them to high level concerns (e.g. ease of change)
* Review another person's code and give them meaningful feedback

**Learning Objectives**

* Write code that is easy to chahnge
* Test-drive code
* Breaking classes into smaller objects (how to use encapsulation and delegation in design)

Updated [Magnus_Portfolio](https://docs.google.com/document/d/19A4I_orxfbWUq_ab6fx7-5aP-z2NTb3cyctfCWauUc8/edit#)

**Intro Sophie Gill**

* Working towards the refactoring_challenge. Should be aiming for step 14
* Single workshop on Thursday morning
* Friday with Eddie Andress to work through weekly review

### Reviewing airport_challenge

* Using [Review Rubric](https://github.com/makersacademy/airport_challenge/blob/master/docs/review.md) as a handrail through process.
* Link to model [README.md](https://github.com/nkhil/takeaway-challenge). And another [Clothing_retail_react_app](https://github.com/nkhil/clothing-retail-react-app).
* Useful to design appropriate domain modelling diagram through [miro](https://github.com/nkhil/takeaway-challenge) software.

### Weekly challenge

* Oystercard Challenge
* Pair partner - Carlton

Focus goals for this project:

***I write code that is easy to change***
Writing easy to change software is highly prized amongst developers and employers. By developers because most of a developer's time is spent changing software. By employers because their teams can deliver value to customers faster.

***I can test-drive my code***
Tested software is easier to change because you can tell when it's broken just by running a command, even the tricky edge cases.

***I can build with objects***
Most code in the world is structured in small pieces called objects. This is done because it is easier to change than having everything in one place.

## Wed 8th May 2019

### Encapsulation and cohesion workshop

* classes should have one purpose or job, sometimes referred to as its responsibility
* group methods together by how related they seem. If a single method appears separate from the others then create a single class.

### Reflective Learning Session

* Alice Lieutier

**What I learnt yesterday**

* Use feature test via `irb` ahead of writing test cases.
* What a Gemfile is / using `bundle install`
* Include detail on how to set up the program in a README.md:
  * General tip - Include anything that can be communicated to a human.
* RVM (Ruby Version Manager).

**Daily goals**

* Review the airport_challenge on [Youtube](https://www.youtube.com/watch?v=Vg0cFVLH_EM&t=64s), note down the following:
  * What I could have done better
  * What I did well
* Mocking workshops from Wk1 and Wk2. Log completion on portfolio.

### Feedback workshop

* Dana

**Why is feedback difficult**

* Difficulty in providing constructive criticism.
* Feedback is fear driven. People find it difficult as they feel they need to protect themselves.

**Becoming a skillful feedback receiver**

* Shift your prospective
  * Feedback is designed to be kind

* Empowered receiver
  * As a receiver FB helps us understand ourselves.
  * Helps practice assertiveness, boundaries, cultivate authentic and equal relationships.
  * Improve work life, and overall quality.

* Know thyself
  * Truth triggers - seems wrong or off target
  * Relationship triggers - something about the relationship with the person
  * Identity triggers - undermines how we see ourselves
  * Do not wrong spot!!
  * Be conscious of how others perceive you.

* Understand feedback
  * Appreciation - To acknowledge, connect, motivate, reassure, thank!
  * Evaluation - To rate or rank against a set of standards, align expectations, inform, decision-making.
  * Coaching - To help receiver knowledge, sharpen skill, improve capability.

* Use a framework
  * Actionable
  * Specific
  * Kind

  * Possible to use the 'Four-Part Nonviolent communication process'. Focus on empathy and expressive communication and using the stages, Observation, Feeling, Need, and Request.

**How to build resilience**

* Those with more of a positive outlook can recover / sustain for longer periods

### Daily goal - Digest airport_challenge Youtube

* Understanding the first user story

```
As an air traffic controller
So I can get passengers to a destination
I want to instruct a plane to land at an airport
```
* Gemfile.lock is a statement of which precise packages are already installed in project.

* Start by using `irb` to feature test. Expect there is an airport and plane objects, and a #land with one argument for airport class.

* Create a ./spec/features/user_stories_spec file. This holds tests directly applicable to the user stories. E.g:

```
descirbes User_Stories do
  #As an air traffic controller
  #So I can get passengers to a destination
  #I want to instruct a plane to land at an airport
  it 'so planes land at airports, instruct a plane to land' do
    airport = Airport.new
    plane = Plane.new
    expect { airport.land(plane) }.not_to raise_error
  end
end
```
Essentially printing our feature test from `irb` into a feature test within a file.

* update .rspec file and update with flags. `Colour` and `--format documentation`

* Now add airport_spec.rb file and continue unit test to check for airport and plane objects.

* When using `subject` in rspec files, explicitly state what it is immediately below the describe method to avoid confusion.

`subject(:airport) { described_class.new }`

* use `git commit` less `-m "<message>"` to add detailed commit. When test passed on user story, input `User Story 1` and print the full user story.

* [Error Message Guidelines, Nielsen Norman Group](https://www.nngroup.com/articles/error-message-guidelines/). Originated from Jakob Nielsen (Danish web usability consultant).

* When constructing error messages, Nielsen states that the message should include; what the error is, why the error occurred, and what you can do to solve it. E.g. `Cannot land plane: airport full. Take off a plane first`.

* Continued Thurs 9th May 2019...

### Pairing w/ Ollie on oystercard_challenge

**Worked well**
* Swapping every 25mins
* Committing after every User Story complete and passed.
* Extremely thorough with each challenge. Not moving on until the other fully understood the process.
* Kept each other up to speed.

**Work on**
* Work on the README.md template
* Attempted RSpec feature testing; however neither had complete grasp of the process. WORK ON!!/ ask for guidance.

## Thurs 9th May 2019

### Cont. Daily Goal - Digest Airport Challenge Youtube

* **Use of `private`**. Use private for methods that you don't need to call out side of a class. Such as:

```
class Airport do
  def land(plane)
    raise 'Cannot land plane: airport full' if full?
  end

  private

  def full?
    @planes.length >= @capacity
  end
end
```

### Reflective Learning

* Alice Lieutier

**Reflective Learning framework**

Use the following when logging lessons learnt:
* Concretes - This is written code that you can now understand.
* Concept - Understanding broad concepts. E.g. Gemfiles, Encapsulation... etc.
* Processes/skills - TDD, Refactoring, Writting good code, Debugging
* Behaviour/Mindset - Being open, collaboration

Over one concept there should be multiple concretes at least one process/skill. These can be used within the personal portfolios when searching for evidence.

**Learnt this week**
* Feature testing. Applying user_stories_spec file to input user stories and then analyse them.

**Daily Goals**
* Expand knowledge and process behind feature testing. Make full use of the feature_spec directory. Run feature test ahead of unit testing.
* Start planning TDD process for weekend challenge (Takeaway Challenge). Make use of ma_approach.md file.
* Understand Inheritance
* Understand Delegation

### OOP Delegation workshop

* Sophie Gill

**Learning Objectives**

* Describe "delegation" as "one class telling another class to do something and the other class encapsulating how to do it."
* Explain what is meant by the advice "delegate, delegate, delegate".
* Implement OOP delegation.

**Overview**

* Example of delegation within airport_challenge. Airport class delegates to class Weather to decide weather_state.

* If within the following example the CEO class is delegating to the COO class and sending it the message `find_company_savings`:
```
class Ceo
  def initialize(coo = Coo.new)
    @coo = coo
  end

  def make_company_efficient
    @coo.find_company_savings
  end
end

class Coo
  def initialize(hr_manager)
    @entertainment_budget = 1000
    @hr_manager = hr_manager
  end

  def find_company_savings
    reduce_entertainment_budget
    @hr_manager.reduce_payroll
  end

  private

  def reduce_entertainment_budget
    @entertainment_budget -= 200
  end
end
```

* This relies heavily on **dependency injection**.

* Delegation still operates within blocks:

For the below the `employee` is set within the `@employees` array. Within the block `employee` is sent the `.performance` message.

```
class HrManager
  def initialize(employees)
    @employees = employees
  end

  def reduce_payroll
    @employees
      .select { |employee| employee.performance < 7 }
      .each(&:fire)
  end
end

class Employee
  def fire
    @fired = true
  end

  def performance
    rand(1..10)
  end
end
```
* In order to understand create 'sequence diagram' and 'class diagram'.

**Attempted `./skills_workshops/week-2/oop_3`**

* **Step 1** - to examine both feature_spec files. Find out what it should do.
* **Step 2** - examine the unit tests. Look for repetition of noun which hints towards creating a separate class.
* The double syntax within the great `todo_list_spec`:
```
let(:todo) { double(:todo) }
let(:todo_class) { double(:todo_class, new: todo) }
```
Here a `todo` double is created. `todo_class` is created and it is set to call `new` on it and return a `todo` double.

* Start on feature test. Try to mimic error messages on user test.