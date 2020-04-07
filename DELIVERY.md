<!-- TODO add resource picture -->
<!-- ![PuppyPlanner Logo](./resources/logo.png)   -->
# Software quality handbook

## Introduction  
PuppyPlanner has been imagined by puppy-lover's in order to help their master to organize their everyday life. The project is available on mobile devices as a mobile application and on customer’s favourite web browser as a web application.

Internally, there are 4 teams at PuppyPlanner: the mobile application team made up of 8 people, the front-end and the back-end development teams, each made up of 3 people for the web application and the core team made up of 6 people that takes care of the API, the database and the business logic.

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

We have talked a lot about User Stories (US) and let me define this a bit more. When writing an US focus on providing clarity about your product features — the what, not the how. To write an user story you need to define who it concerns, what is the goal, and what it is for in the following format:
```gherkin
As a <role or person>
I can <goal/need>
So that <why>
```

Each US should be seen as a feature, that needs to be tested and documented.
***

## Coding standards

***

## Code reviews
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

***