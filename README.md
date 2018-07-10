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
**[Summary](#summary)**<br/>
**[The Project](#project)**: [Team process](#team-process) - [Original plan](#plan) - [Key learnings](#learnings) - [Potential enhancements](#enhancements)<br/>
**[The Service](#service)**: [Technical architecture](#architecture) - [Send email](#workflow-send) - [Receive email](#workflow-receive) - [Installation](#installation) [Contributors](#contributors)
***

## <a name="summary">Summary</a>
A project to mimic the basic functionality of how an email service works. This includes (nearly) all the basic elements you'd require for your own email service; a [web client](https://github.com/charmalt/final-project-client), API for the web client, [Simple Mail Transfer Protocol (SMTP) server](https://github.com/charmalt/final-project-smtp), [Post Office Protocol (POP) server](https://github.com/charmalt/final-project-pop) and database (that we're hosting on Amazon Web Services).


## <a name="project">The project</a>
This was build over 10 days (Monday to the following Wednesday) by a team of five. The team followed standard XP values in an agile framework.

### <a name="team-process">Team process</a>
We broke user stories down into individual tasks/issues/tickets each of which we then added acceptance criteria to.

We kept to a daily cycle of agile ceremonies of morning standup, post-lunch checkin, afternoon checkout. We were advised to work to two days sprints, so the morning of day one had a planning session and the afternoon of day two had a retro. Pairs were also rotated daily.

We planned extensively at the beginning of the project the steps that our systems would need to go through, you can see that below.

### <a name="plan">Original plan and MVP Minimal Viable Product (MVP)</a>
![MVP workflow](https://github.com/charmalt/final-project-main/blob/master/images/mvp-as-agreed.png "MVP workflow")

Our MVP was to complete the process of a message from the point a user clicks 'send' through to the message entering another user's inbox, essentially all the solid line boxes above.

One important goal for the project was to have code that was understandable, well encapsulated and easy to extend. We took an Object Oriented Programming (OOP) approach and, although there are still plenty of areas we would like to improve if given the time, we tried to keep to Single Responsibility Principle.

### <a name="learnings">Key learnings and takeaways</a>
Email is both very complicated and very simple. SMTP and POP require a very strict set of rules, but on the other hand they are fundamentally going through a set of steps we were able to research and then implement simplified versions of in a short timeframe.


### <a name="enhancements">Potential future enhancements</a>
1. **User creation/authentication**. While the objects to create a user (including an encrypted password) into a database and half the work to do the relevant username and password validations were written, it wasn't central to our MVP and thus other work was prioritised during the final days of the project.

2. **Error handling**. Currently our servers have minimal error handling and error checking functionality. Future work would look to handle unexpected server events as well as implementing more robust checks for the handshake between server and clients.

3. **Proper design of the client**. Our mail client currently has a basic user interface will minimal functionality. New features might include pagination of emails, filtering, folders and the ability to search.

4. **Full deployment**. We deployed our database and extra time was spent attempting to deploy the SMTP server on AWS. While the environment was successfully recreated and our scripts started, we didn't have the time to configure the firewall correctly to allow our custom TCP server script to listen on the correct port.

## <a name="service">The Service</a>
As the point of the project was to understand and recreate the full email process, we deliberately built our own server scripts to run our mimic SMTP and POP servers.



### <a name="architecture">Technical architecture</a>
![Summary of our technical architecture](https://github.com/charmalt/final-project-main/blob/master/images/summary-architecture.png "Summary of our technical architecture")

Table of tech used here?


### <a name="workflow-send">Final send an email workflow</a>

![Send an email workflow](https://github.com/charmalt/final-project-main/blob/master/images/workflow-send.png "Send an email workflow")

Words here.

### <a name="workflow-receive">Final receive an email workflow</a>

![Receive an email workflow](https://github.com/charmalt/final-project-main/blob/master/images/workflow-receive.png "Receive an email workflow")

Words here.

### <a name="installation">Installation</a> (brace yourself)
Individual steps for each of the components can be found in there respective repos.

1. [The client](https://github.com/charmalt/final-project-client)
```
git clone https://github.com/charmalt/final-project-client
```
2. [SMTP](https://github.com/charmalt/final-project-smtp)
```
git clone https://github.com/charmalt/final-project-smtp
```
3. [POP](https://github.com/charmalt/final-project-pop)
```
git clone https://github.com/charmalt/final-project-pop
```
4. Postgres/whatever database you'd like
```
brew install postgresql
```

## Testing

### Testing Approach

We took a test-driven development (TDD) approach to this project with extensive unit testing to ensure our code was behaving as we intended. We isolated our test objects using Jest's in-build mocking capabilities. We made sure to mock out any imported libraries as these should have been tested by the library developers. We also used Jest with Enzyme to help test React components.

Certain key interfaces such as database connection and connecting to clients were tested using feature tests. One area for improvement would be to have more feature tests as this would have helped identify some issues with functionality at an earlier stage.

### Code Style

We used ESLint with Standard.js as the style guide to ensure we worked with a consistent coding style.

## Deployment

We investigated hosting each of the individual services on AWS however there were a number of technical challenges that let to a decision to de-prioritise deployment as it was not critical to MVP.

The main technical challenges were:
* The servers required a static IP and port to allow clients to access them
* The hosting service required configuring to enable a TCP connection

In the end we hosted a production PostgerSQL database on an Amazon EC2 instance that our servers could talk to.

### <a name="contributors">Contributors</a> (The team)

* **Charlene Chetcuti** - [@charmalt](https://github.com/charmalt)
* **Ben Furber** - [@benfurber](https://github.com/benfurber)
* **John Newman** - [@JohnNewman1](https://github.com/JohnNewman1)
* **George Sykes** - [@georgesykes86](https://github.com/georgesykes86)
* **Igor Ryabchuk** - [@nixlim](https://github.com/nixlim)
