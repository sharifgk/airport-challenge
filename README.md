Airport Challenge
=================

```
         ______
        __\____\___
=  = ==(____DFA____)
           \_____\__________________,-~~~~~~~`-.._
          /     o o o o o o o o o o o o o o o o  |\_
          `~-.__       __..----..__                  )
                `---~~\___________/------------`````
                =  ===(_________)

```

## Domain Model

| Objects | Properties                | Messages          | Outputs |
| ------- | ------------------------- | ----------------- | ------- |
| Airport |landedPlanes @Array[@Plane]| landPlane(@Plane  | @Void   |
|         |capacity@int               | flyPlane(@Plane)  | @Void   |
|         |                           |isFull()           | @boolean|
|         |                           |                   |         |
| Plane   | id @String                | getId()           | @String |
| Weather | weatherStatus@int ?       | generateWeather() | @String |


## Installation Procedure 

1. Fork this repo, and clone to your local machine
2. `npm install` to install project dependencies
3. Enter the project directory by using the CD command in the terminal
4. Use "node specRunner.js" to run the runner file and output the test results in the terminal.

## Approach taken

* To begin with, on pen and paper I wrote down the user story I was tackling, tried to convert the user story into a domain model of objects, their properties and functions.

* When happy with my domain models I then wrote down test ideas, as specifically as I could in plane english to help me better convert these into code.

* I first took on the Acceptance criteria to try and meet the minimum requirements as best I could in hoping to pass the challenge, before moving onto the extended requirements and implementing a weather behaviour for the program.

## Some thoughts.

* I believe my functions are way to long and not adhering to being 5 lines or less (or close to this size). When trying to refactor I often brick my code trying different techniques that I research online. This is probably due to my inexperience and lack of knowledge of what is actually happening in the code. This I hope is something I can improve upon with practice and more experience.

* My code is not loosely coupled , once again this is something I would rather leave as is on this assignment as to not break my code. However, this will definitely be essential on the Bank challenge and i hope to get a better understanding of it while working on that challenge.

* I will mention that I am most happy with my Weather class. I think that using the RNG and boundaries within the expected pool of numbers was an elegant way of implementing this behaviour, compared to the rest of my code.
For some reason this solution came to me quite naturally, more so than for the rest of the challenge problems.









Instructions
---------

* Feel free to use google, your notes, books, etc. but work on your own.
* Keep it SIMPLE - it's not nearly as complicated as it first may look.
* You must [submit your challenge](https://airtable.com/shrUGm2T8TYCFAmjN) by the deadline, wherever you get to.
* Use your own test framework and evidence your test-driven development by committing on passing tests.
* Please write your own README detailing how to install your project, how to run the tests, how you approached the problem and provide screenshots of interacting with your program.
* If you refer to the solution of another coach or student, please put a link to that in your README.
* Please create separate files for every class, module, and spec.

Steps
-------

1. Fork this repo, and clone to your local machine
2. `npm install` to install project dependencies
3. Convert stories into a representative domain model and test-drive your work.
4. Run your tests using `npm test` or `node specRunner.js`
5. OPTIONAL: [Lint](https://eslint.org/docs/user-guide/getting-started) your source code using `npx eslint src`.

Task
-----

We have a request from a client to write the software to control the flow of planes at an airport. The planes can land and take off provided that the weather is sunny. Occasionally it may be stormy, in which case no planes can land or take off.  Here are the user stories that we worked out in collaboration with the client:

#### Acceptance Criteria
```
As an air traffic controller
So I can get passengers to a destination
I want to instruct the airport to land a plane

As the system designer
So that the software can be used for many different airports
I would like a default airport capacity that can be overridden as appropriate

As an air traffic controller
To ensure safety
I want to prevent landing when the airport is full

As an air traffic controller
So I can get passengers on the way to their destination
I want to instruct the airport to let a plane take off and confirm that it is no longer in the airport

As an air traffic controller
To avoid confusion
I want to prevent asking the airport to let planes take-off which are not at the airport, or land a plane that's already landed
```

#### Extended Acceptance Criteria
```
As an air traffic controller
To ensure safety
I want to prevent takeoff when weather is stormy

As an air traffic controller
To ensure safety
I want to prevent landing when weather is stormy

As an air traffic controller
To count planes easily
Planes that have landed must be at an airport
```

Your task is to test drive the creation of a set of classes/objects to satisfy all the above user stories. You will need to use a random number generator to set the weather (it is normally sunny but on rare occasions it may be stormy). In your tests, you'll need to stub random behaviour to ensure consistent test behaviour.

Your code should defend against [edge cases](http://programmers.stackexchange.com/questions/125587/what-are-the-difference-between-an-edge-case-a-corner-case-a-base-case-and-a-b) such as inconsistent states of the system ensuring that planes can only take off from airports they are in; planes that are already flying cannot take off and/or be in an airport; planes that are landed cannot land again and must be in an airport, etc.
