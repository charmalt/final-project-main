# RetroMail - Main repo
```
  _____________________  
 |\                   /|
 | \                 / |  A project
 |  \   RetroMail   /  |  that mimics
 |  /\_____________/\  |  how email
 | /        *        \ |  works.
 |/___________________\|

```

***
[Summary](#summary)<br/>
[The Project](#project): [Team process](#team-process) - [Original plan](#plan) - [Key learnings](#learnings) - [Potential enhancements](#enhancements)<br/>
[The Service](#service) - [Technical architecture](#architecture) - [Send email](#workflow-send) - [Receive email](#workflow-receive) - [Installation](#installation) [Contributors](#contributors)
***

## <a name="summary">Summary</a>
A project to mimic the basic functionality of how an email service works. This includes (nearly) all the basic elements you'd require for your own email service; a web client, API for the web client, Simple Mail Transfer Protocol (SMTP) server, Post Office Protocol (POP) server and database (that we're hosting on Amazon Web Services).


## <a name="project">The project</a>
This was build over 10 days (Monday to the following Wednesday) by a team of five. The team followed standard XP values in an agile framework.

### <a name="team-process">Team process</a>
[ waffle board here ]
We broke user stories down into individual tasks/issues/tickets which each add acceptance criteria.

We kept to a daily cycle of agile ceremonies of morning standup, post-lunch checkin, afternoon checkout. We were advised to work to two days sprints, so the morning of day one had a planning session and the afternoon of day two had a retro. Pairs were also rotated daily.

We planned extensively at the beginning of the project the steps that our systems would need to go through, you can see that below.


### <a name"plan">Original plan and Minimal Viable Product (MVP)</a>
[image here]
Our MVP was to complete the process of a message from the point a user clicks 'send' through to the message entering another user's inbox, essentially all the solid line boxes above.


### <a name="learnings">Key learnings and takeaways</a>
Email is both very complicated and very simple. SMTP and POP require a very strict set of rules, but on the other hand they are fundamentally going through a set of steps we were able to research and then implement simplified versions of in a short timeframe.


### <a name="enhancements">Potential future enhancements</a>
1. User creation/authentication. While the objects to create a user (including an encrypted password) and half the work to do the relevant username and password validations, it wasn't central to our MVP and thus prioritised other work during the final days of the project.

2. Error handling. [ Can someone else detail the work done on this please? ]

3. Proper design of the client. [ More here. ]

4. ???


## <a name="service">The Service</a>
As the point of the project was to understand and recreate the full email process, we deliberately built

## <a name="architecture">Technical architecture</a>
![Summary of our technical architecture](https://github.com/charmalt/final-project-main/blob/master/images/summary-architecture.png "Summary of our technical architecture")

[ Table of tech used here? ]

### <a name="workflow-send">Final send an email workflow</a>
![Send an email workflow](https://github.com/charmalt/final-project-main/blob/master/images/workflow-send.png "Send an email workflow")

Words here.

### <a name="workflow-receive">Final receive an email workflow</a>
![Receive an email workflow](https://github.com/charmalt/final-project-main/blob/master/images/workflow-receive.png "Receive an email workflow")

Words here.

### <a name="installation">Installation</a> (brace yourself)
Individual steps for each one can be found in there respective repos.

1. The client
```
git clone https://github.com/charmalt/final-project-client
```
2. SMTP
```
git clone https://github.com/charmalt/final-project-smtp
```
3. POP
```
git clone https://github.com/charmalt/final-project-pop
```
4. Postgres/whatever database you'd live
```
brew install postgresql
```


### <a name="contributors">Contributors</a> (The team)

* **Charlene Chetcuti** - [@charmalt](https://github.com/charmalt)
* **Ben Furber** - [@benfurber](https://github.com/benfurber)
* **John Newman** - [@JohnNewman1](https://github.com/JohnNewman1)
* **George Sykes** - [@georgesykes86](https://github.com/georgesykes86)
* **Igor Ryabchuk** - [@nixlim](https://github.com/nixlim)
