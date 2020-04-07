<!-- TODO add resource picture -->
<!-- ![PuppyPlanner Logo](./resources/logo.png)   -->
# Software quality handbook

## Introduction  
PuppyPlanner has been imagined by puppy-lover's in order to help their master to organize their everyday life. The project is available on mobile devices as a mobile application and on customer’s favourite web browser as a web application.

Internally, there are 4 teams at PuppyPlanner: the mobile application team made up of 8 people, the front-end and the back-end development teams, each made up of 3 people for the web application and the core team made up of 6 people that takes care of the API, the database and the business logic.

***

## Task estimation

***

## Coding standards

***

## Code reviews

## How to review your code
PuppyPlanner is going through a crisis, as you might read above. Another problem is upon us, some developers are committing non-functional code, accidental errors or structural errors on the project branches. This needs to be fixed; therefore, we are going to implement code reviews.

> To put it simply, another developer in the company will review the code that you have committed, and you will review your co-worker’s commits.

![Code reviews job](./resources/code-reviews-diagram.png)  
_Figure 2: Code review must-complete tasks_

Your job as a reviewer will be to evaluate the following points:
- Purpose  
    - **Does this code accomplish the author’s purpose?** Every change should have a specific reason (new feature, refactor, bugfix, etc…).  
    - **Ask yourself questions.** Should this class or function exist? Is it useful to the overall objective?
- Implementation  
    - **Think about how you would have solved the problem.** Is it shorter/easier/cleaner/faster/safer yet functionally equivalent?
    - **Do you see potential for useful abstractions?** Any duplicated or useless code ?
    - **Think like an adversary.** Is there any input that could break the code? Did the developer take shortcuts that might create a security flaw?
    - **Does the changes follow the coding standards?** naming convention, comment convention, etc…
- Legibility and style  
    - **Think about your reading experience.** Was the flow sane and were variable and methods names easy to follow? Were you put off by inconsistent naming?
    - **Does this code have TODOs?** The proposed code change should not contain commented-out code.
- Maintainability  
    - **Read the tests.** Check the tests themselves: are they covering interesting cases? Are they readable?
    - **Does this change break backward compatibility?** Breaks can include database or schema changes, public API changes, user workflow changes, etc. Pay attention to this.
    - **Was the documentation updated?** Outdated documentation can be more confusing than none, and it will be more costly to fix it in the future than to update it now.

> If any of the above points is not compliant in the code that you review, then write a detailed comment and continue the review.

At the end of the review:  
- If the review is successful: the developer’s code will be pushed to the desired branch.  
- If the reviewer is unsatisfied: the code is sent back to the developer who applies the required changes based on the reviewer’s detailed comments.  

As you will see, reviewing is a tedious task, therefore, to ease your reviewer’s task we strongly recommend you to follow the following steps:
- **Scope and size**: Changes should have a narrow, well-defined, self-contained scope. To put it lightly, shorter changes are preferred over longer ones. For example: if you have made changes to more than 5 files or took longer than 1 or 2 days to write, consider splitting this into multiple commits, implying multiple code reviews. Keep in mind that your changes in each code review must be comprehensible, as so, split your changes smartly.  
- **Only submit complete, self-reviewed, and self-tested code.** Make sure your tests pass all builds as well as all tests and code quality checks.  
- **Refactoring changes.** Changes should not alter behavior; conversely, a behavior-changing changes should avoid refactoring and code formatting changes.  

> Remember that your co-workers will also follow these steps to make your job easier!

The two above lists must be taken into account in order to have a smooth and fulfilling experience at code reviewing and for your co-worker’s ease.

***

## Sources

### Code reviews
https://www.youtube.com/watch?v=PJjmw9TRB7s  
https://stackify.com/unit-testing-basics-best-practices  
https://www.perforce.com/blog/qac/9-best-practices-for-code-review  
https://medium.com/palantir/code-review-best-practices-19e02780015f  

***