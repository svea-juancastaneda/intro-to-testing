## Workshop on testing
### A very opinionated one
---
## Expectations
* What is a test?
* Why to test?
* How does a test look like?
* Should I care?
* Why am I here?
* Can/should I learn something?
* Why should I listen to you?
* Testing sucks, Can it be good?
* What is in it for me?
---
## Why Testing?
- Coming from XP 
 - Feedback from the system (Report system changes or not expected behavior)
 - Feedback from the customer/client (Report progress)
- Refactoring
- Uncle Bob's double-entry bookkeeping
 - Different view of the same problem
 - End result is a balance
- Release often, safe and build confidence on code base
---
## Kinds of testing
- Automated
 - TDD
 - BDD
 - Acceptance
 - Integration
 - Regression
 - Security
- Manual
 - Exploratory ;)
---
## Testing that matters
- Units
  - What is a unit?
  - What is worth testing?
  - How to test a unit?
- QA
- Tests just verify what it is documented on the test. The rest is unknown behavior
- Tests NEED to be maintained - not just to be shut
---
## Testing that matters 2
- Tests NEED to be run - an invalid run is an invalid check-in and a NO deploy
- Tests should be fast
- Tests cost in time and mental power
 - Make them count by not testing if frameworks work (e.g. Moq)
---
### How can you refactor with unit testing
* Decouple the test for the implementation (what vs how)
* The test should have as high quality as the production code
* The test is just an append only file
---
## Anatomy of a unit test
* Arrange -> Act  -> Assert
* Given   -> When -> Then
---
## How it is implemented
* NUnit/XUnit/MSTest/
 * With Attributes (setup/teardown/test,etc)
* Use your own class (independent of the framework)
 * Steps
 * Fixture
---
## Organizing the test
* The test method describes the test
 * Svea.StorePay.Gateway.Test/IdentityServer/RequestAuthenticationTests.cs
 * ClientStructure.Core.Tests/Handlers/NodePropertiesHandlerTests.cs
* Test only one thing of the unit
* Avoid repeting the testing the same thing on other test methods
---
## Tools
* Think before acting. Coding is the easy part. Abstraction and deduction process is better paid.
* Good development practices:
 * Software patterns
 * Code reviews
 * Be lazy so reause code. Can copy but not PASTE! except...
 * Allow you to copy/paste once, but twice requires a refactor/reuse
---
## Tools 2
 * Delay decisions as much as possible. Do you really need a database? a cache? optimize? what is the value on those? can they be tested apart?
 * Isolate requests to external apis. Business logic should not depend on a service call. The result of a call can be used as an input to the business object and simulated on the test setup.
* Have FUN :|
---
## Tools 3
* SOLID
 * S: Single responsability: Things that change together, stick together. High cohesion and low coupling
 * O: Open for extension: Closed for change. GoF: Decorator, Composite, etc
 * L: Lizkov substitution: Any subtype can be used instead of the general type
---
## Tools 4
* SOLID * I: Interface segregation: Program against interfaces with small surface and narrow scope. No God object/interface.
 * D: Dependency injection: Business and domain classes depend on interfaces that are implemented by things like serialization and determined by a setup. Do not make business code dependent on a IoC Container
---
## The exercise!
* Pair programming
* 1.5 hrs to implement and compete!
* 2 runs.
* Tests will be shown and commented for the winner team. We all need to learn from the best!
 * But it is not for shaming and comments should be good critics. We are all learning!
* Nice price at the end for the winner
* Write tests that are readable
---
## The exercise 2
* Along with the code there is an example and the boilerplate code
* Your code is not yours and you will maintain somebody else
* You will not purposely know who write what. Just to know how it feels to maintain other people's fantastic code/tests :smiling_imp:
* The lazy PO is not sure and may introduce changes under development