![PuppyPlanner Logo](./resources/logo.png)  
# Software quality handbook

## Introduction  
PuppyPlanner has been imagined by puppy-lover's in order to help their master to organize their everyday life. The project is available on mobile devices as a mobile application and on customer’s favourite web browser as a web application.

Internally, there are 4 teams at PuppyPlanner: the mobile application team is made up of 8 people, the front-end and the back-end development teams, each made up of 3 people for the web application and the core team made up of 6 people that takes care of the API, the database and the business logic.

***

## Task estimation

### Smash your tasks into epics
Tasks are often substantial blocs of many smaller tasks that development team members discover as they carry out the aforesaid task. You should never estimate a task like this. Why not dividing it up instead ? First, you should separate the biggest tasks in themes. Then you might define those biggest tasks as epics and split them into smaller task called user stories. In this way, task estimation - or more accurately user stories estimation - is easier to perform and any mistake due to task estimation is easier to manage. By the way, the list of user stories constitute your product backlog.

### Uncertainty and confidence margins
As a team, you should not blame each other for bad time estimation because a user story estimation will never be perfect; that’s how it is. To keep the team chin up, you might use uncertainty and confidence margins within estimations. For each task evaluation, vote an uncertainty percentage and a confidence one and apply these percentages in the description. Be careful to ensure that the percentage does not exceed 50%. Otherwise, you probably made a bad estimation of the user-story.

![Task estimation diagram](./resources/figure1.png)  
_Figure 1: Define user stories from substantial tasks_

### Use a non-linear scale
Several companies are using user story points instead of time format (e.g. minute hour, week, …) nowadays. User story points rate the relative effort of work in a Fibonacci-like format : 0, 1, 2, 3, 5, 8, 13, 21, etc.
First, find the smallest defined user story of a previously selected epic and assign it a 1 as baseline. Then compare each other task to the baseline item and assign a value base on a comparison following those factors: size, difficulty, uncertainty and risk. Finally, assign user stories to each member of the development team equally by following those rates.


### Create your user stories

We have talked a lot about User Stories (US) but let me define this a bit more. When writing an US focus on providing clarity about your product features — the what, not the how. To write an user story you need to define who it concerns, what is the goal, and what it is for in the following format:
```gherkin
As a <role or person>
I can <goal/need>
So that <why>
```

Each US should be seen as a feature, that needs to be tested and documented.
***

## Coding standards

### Introduction to Gitflow
Gitflow is a strict branching model designed around the project release imagined by Vincent Driessen about 10 years ago. It probably remains the most popular Git workflow design nowadays. Gitflow simplicity might have made the tool's reputation. This is why PuppyPlanner developers must use this Git workflow.  

There are only 5 types of branch allowed in this model :  
- **Master** is unique and contains the official release history.  
- **Develop** is unique too and serves as an integration branch for features.  
- **Feature** branches are created when a new feature needs to be added to the project.  
- **Release** branches group features merged on develop before being pushed on master.  
- **Hotfix** branches are made for quick patch production releases.  

### Gitflow configuration and workflow
First of all, it is necessary to get the Git project on the machine. We recommend to install it on Windows since it is the most common Operating System at PuppyPlanner. You have to install [Git](https://git-scm.com/download/win) on the computer. Then, you will need to clone the project on the machine by entering the following command on the Git Bash prompt freshly installed :
```git
git clone git@github.com:<github-username>/sqa-infs3028.git
```
You now have a local version of the project on your computer. If you want to add a feature to the project, please enter the following command :
```git
git flow feature start feature_branch
```
It is worth noting that feature branch names must follow the [snake case](https://fr.wikipedia.org/wiki/Snake_case) convention. When you finished the feature development and you want to merge your work on the develop branch, please enter the following command :
```git
git flow feature finish feature_branch
```
Finally, when the develop branch contains all the predicted features of the next release, you can create a release branch by entering the following :
```git
git flow release start 1.0.1
```
Of course, feel free to replace the release number of this example by the actual release number. In addition to this release number, you have to fill the CHANGELOG.md file with your commits; you can find this file at the project root. This file has been written in Markdown and must be completed in accordance with the following template :
```Markdown
## [Next release number] - today’s date
### Added
- first commit made for added features
- second commit made for added features
- ...
### Updated
- first commit made for updated features
- second commit made for updated features
- ...
### Removed
- first commit made for removed features
- second commit made for removed features
- ...
```
If there is nothing in one of the parts, don't add it in the file CHANGELOG.md. Finally, if you are not comfortable with command line, feel free to use [GUI](https://www.computerhope.com/jargon/g/gui.htm) tools like [GitKraken](https://support.gitkraken.com/git-workflows-and-extensions/git-flow/) or [SourceTree](https://www.sourcetreeapp.com/) made by Atlassian.

### Insure JavaScript code quality
![ESLint Screenshot](./resources/eslint-screenshot.png)  
_Figure 2: Screenshot of the ESLint plugin for JetBrains_

The seventh version of ESLint has been released in February 2020; so less than two month before this handbook fulfillment. Shortly, ESLint is a pluggable linter for JavaScript that finds and fixes problems in the code. This tool not only standardize the code within a team but also in the whole company because all parts of PuppyPlanner have been thought to be based on Node.js. Briefly, about PuppyPlanner, the web part has been developed in [React](https://reactjs.org/), the mobile part has been developed with [React Native](https://reactnative.dev/) and the core is based on [Node.js](https://nodejs.org/). Needless to say, the installation will be quite tough because each member of the company who develops will have to do a code refactoring. This is why developers are strongly advised to use [WebStorm](https://www.jetbrains.com/webstorm/) - an IDE made by JetBrains - and download the dedicated [ESLint plugin](https://www.jetbrains.com/help/webstorm/eslint.html).

### Write consistent commit messages

PuppyPlanner beginnings turned quite chaotic because of liberties given to each teams; in particular, git commits are absolutely senseless. Thankfully, Git gives many possible configuration out of the box and the `commit.template` command is especially interesting regarding commits. Please enter the following command to set up the PuppyPlanner git message on your machine :
```git
git config --local commit.template “$HOME/<path-to-cloned-project>/.gitmessage”
```
This configuration will ensure you write proper commit messages. The commit command is now the following :
```git
git commit
```
That’s all folks ! Well, not exactly because this command will now open your default text editor and you will have to complete the commit message in accordance with the displayed template but you don’t need the `-m “<commit message>”` extension anymore. Then, all you need to do is enter the following and you are good :
```git 
git push origin <feature_branch>
```

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

### Testing

As mentioned in the code review part, tests are an essential part of a project’s life. All written code must have tests done and tested before committing. We will expect you to do the same. To briefly explain it, unit and functional testing is a proven technique for ensuring software quality for the following reasons:
- **Validation**: tests validate that each piece of your software not only works properly today but continues to work in the future.  
- **Defects**: test identify defects at an early stage of development, which reduce the cost to fix them in the later stages of the development.  
- **Safer to Refactor**: test can be quickly run repeatedly as we code to ensure the behaviour has not changed.  
- **Different perspective**: encourage the developer to take corner cases and error condition into account in their implementation.  
- **Code review**: testing helps understand how a specific part of code is supposed to run.  

To ensure a good development of test throughout the company, you will have to follow these points:
- **Tests must be trustworthy**: The test must fail the code is broken and only if the code is broken.  
- **Maintainable and readable**: As the code evolves, the test should too, therefore the test must be written following the company’s style and have proper naming convention.  
- **Single-use case**: One test only test one case!  
- **Isolation**: Test should be able to be run on **ANY** machine, in any order, without affecting each other.  

> The tests will be run automatically on every commit on Release, Develop and Master. You will be able to run the test at any time on your machine.

***

## Sources

### Task estimation
https://www.agilealliance.org/glossary/split  
https://www.atlassian.com/agile/project-management/estimation  
https://www.atlassian.com/agile/project-management/epics-stories-themes  
https://www.planisware.com/hub/blog/10-best-practices-project-estimation  
https://thedigitalbusinessanalyst.co.uk/how-to-estimate-agile-projects-93aeb16d3dd2  
https://thedigitalbusinessanalyst.co.uk/best-practices-for-agile-estimation-a3d4435a776a  
https://www.freecodecamp.org/news/how-and-why-to-write-great-user-stories-f5a110668246  

### Coding standards
https://chris.beams.io/posts/git-commit  
https://rubygarage.github.io/slides/git/gitflow#/15  
https://nvie.com/posts/a-successful-git-branching-model  
https://backlog.com/blog/git-commit-messages-bold-daring  
https://eslint.org/blog/2020/02/whats-coming-in-eslint-7.0.0  
https://daemotron.github.io/2017/05/02/Git-Flow-Groundhog-Day.html  
https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow  
https://thoughtbot.com/blog/better-commit-messages-with-a-gitmessage-template  

### Code reviews
https://www.youtube.com/watch?v=PJjmw9TRB7s  
https://stackify.com/unit-testing-basics-best-practices  
https://www.perforce.com/blog/qac/9-best-practices-for-code-review  
https://medium.com/palantir/code-review-best-practices-19e02780015f  
https://www.toptal.com/qa/how-to-write-testable-code-and-why-it-matters  
https://dzone.com/articles  unit-testing-best-practices-how-to-get-the-most-ou  
https://stackoverflow.blog/2019/09/30/how-to-make-good-code-reviews-better  

***