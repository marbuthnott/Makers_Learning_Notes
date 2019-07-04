## Week 6
## w/c 17th June 2019

### Questions

### Week Goals

* Learn high quality processes to build a project in teams.
* Get a video recording from a process workshop.

## Monday 17th June 2019

### Engineering Project Kickoff

* w/ Alice Lieutier

* Reviewed Agile methodology, compared with its predecessor Waterfall.

**Agile**

* Project Management methodology.
* It is iterative.
* An iteration can take up to two weeks, i.e. 1 sprint.

* Tools:
  - Scrum
  - Sprint
  - Backlog
  - Standups
  - Retros

* Pairing/mobbing/code reviews:
  - Keeps everyone involved
  - Code quality

* Agile planning:
  - Modelling
  - Breakdown user stories
  - Estimating. Time estimate to complete work.

* Linters. These are automated programs to tidy up the code.
  - Rubocop
  - Other automated code quality tool.

* Testing + coverage. Good code quality tool to make sure test pass and there is good code coverage.

* CICD - Continuous Implementation, Continued Deployment. As soon as code passes it can immediately be hosted on heroku.

**Requirements**

* 2 day sprints
* Meeting schedule to Alice
* Friday - team alignment and retro
* Presentation at the end of the project

# ACEBOOK CHALLENGE

## INTRODUCTION

This blog is for team D-Railed (named in a moment of inspiration by Ollie) and will give you an idea of our approach when tackling the Makers Academy challenge... Acebook.

The challenge itself stems from the eighth week of the Makers Academy software engineering bootcamp and introduces all us students to Ruby on Rails, and testing the water with the Agile development methodology.

### Monday 17th June 2019

Day 1!!

First things first we set up a Trello account, luckily for us the coaches had set it up with a complete list of user stories and a small nudge in the right direction to get us started. Having not used Trello before we approached it with a bit of trepidation but soon realised that it is brilliant!! Allowing us to set goals, keep track and delegate tasks with total ease.

With most of the day spent in the project brief and immersing ourselves in the project requirements we decided to try our hand at setting up the environment; this would need a link to host the project on Heroku, and setting up Continuous Integration and Deployment via Travis. Only having a couple of hours left in the day we thought we'd have it nailed before evening yoga... little did we know.

We decided to split ourselves into two teams of three, we wouldn't necessarily do this again, however, as we were all new to rails we thought it would speed up our approach having more heads focussing on a single problem. Ollie, Vlad and Cosmin would look at hosting our project on Heroku while Magnus, Edina and Lucy would work on achieving Continuous Integration and Deployment ([CICD](https://medium.com/@nirespire/what-is-cicd-concepts-in-continuous-integration-and-deployment-4fe3f6625007)) through Travis. GET TO WORK!!

Needless to say when yoga time came about all we had done was research the setup procedure and have a (marginally) better understanding of Rails. We hoped setting ourselves up for a strong Tuesday!

### Tuesday 18th June 2019

Starting out again on Tuesday we were all feeling slightly more confident on rails. Many of the group had managed to complete the walkthrough of rails from their official [getting started guide](https://guides.rubyonrails.org/getting_started.html).

We had our 10am morning standup where we looked again at the specifications and came up with a feature model (see below); this took a fair amount of time but hope it stuck to the old analogy 'time spent in recce is seldom wasted' and would pay dividends when it came to writing the code. To complete our standup we came up with a plan for the day which was to (hopefully) setup the environment by mid morning and start coding in the afternoon.

Starting out on the setup our error was to have two separate groups doing something that is inherently very similar; the work in travis was directly incorporated in heroku and visa versa. With both teams being new to this we struggled on for most of the morning, trying all the while to work on the CICD across two computers and encountering plenty of problems with our sync. Fortunately, our lunchtime standup would highlight this issue and make us re organise our setup, for the afternoon we would have three continue their research on rails while the setup continued on a single computer. TESTS GREEN AND AUTO DEPLOYMENT ON HEROKU!! SUCCESS!!

Now to starting our carefully coordinated plan to start on the code and nail the sign up page by the end of the day. Again, as Rails was new territory, we adopted mobbing as our development process where all of us crowded around a single computer to complete the first feature. This worked well as it allowed us to learn the code and bring everyone onto the same page, however, be wary of having too many on one computer... six is about the limit.

By the end of day 2 we were 90% of the way there with the sign up feature, and after night of rest and rails research were confident of an 'ell ova good Wednesday. Full steam ahead!!

## Wednesday 19th June 2019

## Thursday 20th June 2019

### CV Workshop

* w/ Becks

**STRUCTURE**

**Profile**
Passion:
* What you bring
* What you love about tech (going to hackathons)

Set your career in stone - "I am a full stack developer"

**Projects**

3 - 5 projects on each CV

Brexit means Breadsticks - search Nikhil

Hackathons (Hackathons.com/.co.uk)

**Skills**

**Education**

**Hobbies**

**What you don't include**

**Vlad**

* Discovered programming;
  - While in construction as a manager. Engaged with it so started attempting projects outside.
  - Stated with HTML/CSS and looking to JavaScript in the future.
  - Python course in Romania via codecademy.
  - Struggled with motivation in construction led to a change to tech.
  - Found a new interest in technology, plenty of crossovers with construction. Building an application, project management vs product management.

* Love for tech:
  - Building something that is tangibly useful. The industry is can have an affect on society. The social impact of tech, exciting place to be.
  - Had issues within the construction industry where tech would have significantly streamlined it.

* Where will you be in 5 years:
  - has an interest in Blockchain
  - project management
  - in 5 years would like to work as a blockchain engineer.

* Proudest achievement:
  - making the move from Romania to the UK, pushing career and making senior management.

* Can you think of a time when you used technology to solve a problem:
  - bluebeam software for building design.

## Friday 21th June 2019

**QUESTIONS**

* What is a request response cycle in rails.
* Should commits have a single line followed by a description?
* Unit tests for ruby on rails

### Review Acebook

* w/ Alice

* Commits having a single descriptive line followed by a full description.
* Instructions on how to test, deploy the app, how to contribute