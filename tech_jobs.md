# Tech Jobs 

## Contents

1. [Software Engineering](#software-engineering)
2. [CI/CD](#cicd)
3. [Front End vs Back End](#front-end-and-back-end)
4. [DevOps Engineer](#devops-engineer)
5. [Site Reliability Engineer](#site-reliability-engineer-sre)
6. [Testers](#testers)
7. [Tech Adjacent Jobs](#tech-adjacent-jobs)
8. [Technical Interview](#technical-interview)
9. [Lloyds Banking Group Seminar](#lloyds-banking-group-seminar)
99. [Agile Methodology](#agile-methodology)

## ***Software Engineering***

### How has it changed?

- Much more collaboration
- More accessible tools
- Wider range of technology
- Much bigger ecosystem

### Software Development Life Cycle (SDLC)

- Process that produces the highest quality and lowest cost software in the shortest time
- Needs a model for actual delivery - Agile, Waterfall, Iterative, Spiral
- All tech jobs are integrated into it

(look at Agile Methodolody section)

### CI/CD

- CI (continuous integration) - running tests continuously and automatically every time a developer makes changes to the source code. Catches bugs early and ensures new code doesn't break old code. **Tools include Jenkins, CircleCI, CodeShip, etc.** You get an email back if something breaks when you push code.
- CD (Continuous Delivery and Continuous Deployment) - delivery is the methodology of frequent shipping of code to different environments manually, like testing / staging (production stage of the code but not public to figure out last minute bugs) / production (final part). More akin to an approach than anything that relies on tools.
- Deployment is the automation of both delivery and integration to achieve constant and fluid release of code into production. Tools are mostly same as for integration. Building a pipeline that encompasses the entire process. Requires a lot of preparation and coding practices due to risky nature.

### CI/CD Pipeline Example

- Continuous Integration
    - Committing change to version control
    - Triggering and executing build (get notified)
    - Triggering and executing tests (get notified)
    - Notify on outcomes

* Continuous Delivery/Development
    * Deliver build to staging
    * Deliver and deploy build to production

## ***Various Roles***

- Technical Architect
- DevOps Engineer
- Tech Lead

... etc.

***Engineer vs. Developer*** - fundamentally the same thing! No major difference but within the role, there are some differences that are not due to the title.

- Levels
    - Junior / Graduate
    - Mid-level / "Medior"
    - Senior

### Front-End and Back-End

- Front End
    - Work on the user-facing parts of an application
    - Implement new features to improve user experience
    - You build and mostly not design
    - Accessibility standards are met
    - JS, CSS, HTML
    - Frameworks - React, Vue, Flask

* Back End
    * Work on the server-side parts of an application
    * Implement new features to support front-end functionality
    * Ensure the app runs efficiently
    * Java, Python, JS, Ruby ... etc.
    * SQL
    * Frameworks - Spring, Django

### Things They Don't Do (Much)

- Requirement gathering
- Building applications from scratch
- Publishing / deploying code (manually)

## ***DevOps Engineer***

(pinch of salt by Zsolt)

- Manages the deployment process
- Previously, its the developer to the sysadmin (hardware server guy) 
- Now is developer to DevOps, to help configure how to make sure the app being developed is configured correctly for the system
- Techy but there mostly to make sure all the developer and system is in sync
- Implements process to support the dev team
- Manage source codes (e.g. GitHub)
- Containerisation
- Automation of processes (CI/CD)

## ***Site Reliability Engineer (SRE)***

- Ensures the app stays up!
- Works with devops to manage demand
- Monitors and manage physical infrastructure
- The one who gets the midnight phone call

## ***Testers***

- Write tests to ensure the product meets the specification 
- These include stress tests, security tests, automated end-user tests... etc.
- Forms of testing:
    - Unit 
    - Integration
    - End-to-end
    - Acceptance
- Fully techy role

## ***"Tech Adjacent" Jobs***

- Product Owner - managing a project backlog
- Scrum Master - managing Scrum processes
- UI/UX Designer - designing and testing an app's front end
- Support Engineer - bug fixing
- Technical Writer 

## ***Skills Needed***

- Communication
- Knowledge of the other roles and how they relate to each other 
- Interest and enthusiasm for technology (fun, exciting, ever-changing)
- Understanding of the development process

## ***Technical Interview***

### Usual Process

1. **Chat** - often with HR or recruiter, find out whole process
2. **Cultures and Values** - competency interview
3. **Technical Interview** 

### Why?

- To avoid false positives
- Jeff Atwood - 'Coding Horror'
- 2007 blog, *Why Can't Programmers... Program?*

### Setup

- Handful of people (2 or 3)
    - HR/People
    - Technical Person
    - Product Owner or someone senior

### Tips

- They WILL look at your GitHub!
- Do not assume gender e.g. when you are in trouble, talk to my tech lead and see if they have advice
- Include all the other people

### Common Formats

- On the Spot Test
    - Choice of language and editor
    - 1-2 hours
    - Often paired programming exercise
    - Algorithmic type problem (think Parentheses Tracker)
    - Use pseudocode and planning
    - Read tests
    - Write tests if there are none!!
    - Use the technical person by asking

* Rest are ones you take back home 

## ***Lloyds Banking Group Seminar***

Debbie Marshall (17 years at LBG in Edinburgh) - 

- Mature student (21) with no A-levels, uni with computing and business modules
- Grew up on a farm
- Capability Lead for Everyday Banking Platform
    * attract, diversity and retain software engineers
    * provide outreach opportunities
    * talent engineering pipeline
- 26 million customers
- 58,000 employees
- Annual revenue £10 billion

What Debbie values -

- mindfulness
- curiosity (doesn't have to be loud and outspoken)
- willingness to learn and go in a direction
- honesty
- reinforcing value that she has seen by sending notes

Expectations of new intakes -

- whether they have some self sufficiency in terms of learning
- motivation to learn outside projects
- interest to help yourself through with guidance
- specific engineering paths to guide people through
- attitude and knowing what you want to do

Values - Boldness, People First, Inclusivity, Sustainable, Trust 

- Sustainability was introduced last year and the way to achieve it 
    * green coding?
    * hackathon with VISA that is sustainability themed
    * paperless, biking, recycling, lights

Everyday Banking Platform -

- savings, credits... etc
- strategy is to work effectively together and multiskilled teams
- enhance customer experience

Projects -

- technology 
- agile methodology
- ways to tackle fraud with more complex techniques
- investment mobile app
- AR mortgage journey

- innovation and learning hub (devised by first BNTA group), where business and engineers are working together on courses, budgeting mobile app, work with seniors just to experiment, sit down and do collaborative coding
- Edinburgh LBG is one of the first labs to build application updates to the cloud
- get a mentor or a sponsor

## ***Agile Methodology***

Project management methodology, not a framework. Agile has pillars and characteristics but does not give you a specific framework to work by. It is not a magic bullet as it is misused often.

Developed in response to some of the problems that arise from other project management processes.

### **Waterfall**

Comparison to **Waterfall** -

1. Gather requirements
2. Design
3. Build with unit and integration testing
4. Perform system testing
5. Perform user acceptance testing (UAT)
6. Fix any issues
7. Deliver the finished product

Drawbacks - 

- One round of gathering and documenting requirements, often difficult and the requirements can change over the time period of the design or testing
- Doesn't allow for changing requirements or deeper understandings
- Can lead to large losses in time
- Making changes can be difficult once the product is built
- Has been blamed for many a failed, expensive government projects

Agile tries to solve some of these problems.

### **Manifesto for Agile Software Development**

- Individuals and interactions over processes and tools
- Working software over comprehensive documentation
- Customer collaboration over contract negotiation
- Responding to change over following a plan

1. Analyse the problem
2. Planning
3. Increment/Deliverable [-> Design -> Build -> Test ->]
4. Deploy
5. Repeat steps 1. - 4.

Each iteration is a shorter period (2 - 4 weeks). In terms of Scrum, these iterations are sprints.

### **Time, Cost and Scope**

Every project is constrained by **Time**, **Cost** and **Scope**.

These constraints are usually fixed. Agile makes Scope flexible. Within these constraints we deliver what is most valuable.

### **Scrum**

***2 Pizza Rule*** *- should be able to feed each of your dev teams with 2 pizzas. Roughly 8 people maximum, 4 people minimum.*

Leading Agile framework where Scrum is taken from rugby, analogy used in HBP (Takeuchi & Nonaka) where everyone is in the scrum but the team members are valuable for their tasks.

**Scrums are high-performing and cross-functional.** This means each scrum is able to handle their part and is not separated into front end teams and back end teams. Instead it is a mixture of developers and project leads.

### **Scrum Team**

Minimum of three specific roles:

- ***The Product Owner*** ***(what needs to be done)***
    * Champions for their product
    * Focused on understanding business and market requirements
    * Prioritising the backlog
- ***Scrum Master*** ***(how the project is done, contact Zsolt for more info)*** 
    * Champions for scrum within their team
    * Coach and manage the workflow
    * Look for improvements in practice
- ***Dev Team***
    * Drives the plan for each sprint and decides how much to take on
    
### **Scrum Framework**

We have ceremonies and not meetings.

- The team must meet every day : **Stand Up** (usually 5-10 minutes for 8 people)
    * What are we doing today? Does anyone need to be caught up? What are the blockers?
- 2 - 4 week **Sprints**
- Dedicated team (no multi-tasking teams)
- 5 - 9 members
- Have a product vision from which you can extract **MVP**
- **Team Norms** (agreements on how to work together)
- Sprints finish with a **Retrospective**

### **Tools of the Trade**

- Kanban Board: Trello - trello.com
- Extreme Programming:
    * 5 values - Simplicity, Communication, Feedback, Courage, Respect
    * 12 principles - Planning Game, Customer Tests, Small Releases, Simple Design, Pair Programming, TDD, Refactoring, Collective Ownership, Continuous Integration, Sustainable Pace, Metaphor, Coding Standard
- Retrospectives:
    * Look back and evluate how a project or iteration went
    * Uses the traffic light or stop/start/continue points for topics
    * Emphasize success, not just the rough points

### **Other Approaches**

- **Rapid Application Development (RAD)** - [-> build -> check with client ->]
- **SAFe : Scaled Agile Framework** - scrum at large corporations (scrum of scrums, representative of each scrum team meet up to do their own scrums)
- **Spiral** - scope is rigid

