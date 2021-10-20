# Planning as an Engineer

## Planning as an Engineer

### Introduction

Part of your journey as a tech professional will be figuring out how to navigate all of the tasks that aren't necessarily related to coding. Writing code isn't all that developers do—and in fact, it may end up being something you do a lot less often than you might expect, depending on where you work, what you're working on, and which part of the release cycle your team is currently working in.

As a tech professional, you'll be involved at least in some way in the planning process—_how_ your software gets built. Our hope is to break down the process of developing a working architectural plan, so that when the time comes for you to get into the codebase and start writing code, you'll be ready. **This will be something you do often in your career.** In Labs, we're "throwing you into the deep end"—but you've got floaties and lifeguards!

Understanding how all the pieces of your system fit together is vitally important. **It will provide you with a valuable visual way to present the work you've done when asked in an interview setting**. Our goal is to ensure you feel prepared to talk about your system with confidence.

### Documenting Architecture

A large part of every engineering team's process is to document their application's architecture.

* We'll use a tool called [Whimsical (Links to an external site.)](https://whimsical.com) to to walk you through the process of diagramming out your system requirements. **Navigate over to Whimsical now and open a free account.**
* Work together as a team to take everything you know about your product and diagram out all the pieces of your system that will combine to build your application.
* Identify and diagram out each individual app (frontend, backend, data science) and how each piece fits together.

Ensuring that you have an understanding of your application's architecture and a strong visualization to work from is a great way to align all development teams.

**Your architecture diagram needs to be a document that can updated as time goes on.** If you're inheriting a diagram, you'll need to focus in on the features you'll be developing while you're in Labs.



## Technical Research

Beyond laying out your system's architecture, it's important that you do a good chunk of discovery around the technical components of your application. When designing a feature or crafting an algorithm, it's critical to consider all of the tools you might need before you start implementing anything.

It's also important to find a good balance between spending time researching packages/libraries you might integrate into your project and actually moving forward with a selected package. **We urge you to practice discipline and extreme caution—do a little research on packages you'll use in your product.**

### How to Research Resources

When deciding whether a package or API is suitable for your project and the feature you're attempting to build, follow these steps:

* Discover if it's already something found in our [standards documentation. (Links to an external site.)](https://docs.labs.lambdaschool.com/standards/)
* Discover the size of the package on `npm`.
* Comb through the documentation of the API or package. Does it make sense? At a first glance, does it seem easy enough to work with? Will you need an account to generate an API key?
* Find out if the package/API is still being maintained. When was the last publishing? How many open pull requests are there? How many issues are filled out in the issue tracker?
* Another useful thing to look for (but not completely necessary) is how often that package is being used by others in the community (weekly downloads). Popular projects are more likely to be well maintained.

Ultimately, though, **there is no one single way to do technical research.** The important thing is to ensure that you do these things as a team. You should never just `npm install` willy-nilly. Always include another team member, your Technical Project Manager(s), your release manager, or your engineering manager in the process of researching APIs.

\


* [Home](https://lambdaschool.instructure.com/courses/1552)
* [Modules](https://lambdaschool.instructure.com/courses/1552/modules)
* [Grades](https://lambdaschool.instructure.com/courses/1552/grades)

## Schema Design

You've learned a little bit about designing the schema for an application, so now we're going to take that foundational knowledge to the next level. Ensuring that you have an understanding of your schema and a strong visualization to work from is a great way to align frontend and backend development teams.

**You should update the documents you work through on a regular basis as things change.** No one thing that you develop will ever be permanent, so getting in the habit of going back and updating your documentation and diagrams will be a big part of your job in Labs—especially if you're picking up a project that has been previously worked on.

Refer to the following diagram as an example of the level of detail we're looking for here. Every DBDesigner diagram of a Labs project should look something like this.

&#x20;

![ScreenShot2021-08-23at11.39.32AM.png](https://lambdaschool.instructure.com/courses/1552/files/388783/preview)

&#x20;

> Shoutout to all the teams who've worked on Family Promise Service Tracker for this amazing schema design document—and specifically to the Labs 37 learners who took it to the next level!

&#x20;Environment Variables

### What are Environment Variables?

**Environment variables** are secrets and tokens that we keep to ourselves and never share across the internet. Environment variables are variables that are set in the environment in which your application runs.

* If you're running your application locally off of development servers on your machine, the environment would be a `.env` file (or similar) found at the root of your application's directory tree.
* If the environment that is running your application is deployed to a hosting service like AWS or Heroku, then you'll need to set the appropriate variables there to allow your application to run.

&#x20;

🔑  **You'll need to set up your environment variables in order to run your applications and develop locally.**

**Checking in files like your `.env` or `secrets` file to git and GitHub is a major security flaw**, and there are some secrets and keys you'll use in Labs that will be flagged automatically by bots scanning for such incidents. If you check in secrets to version control during Labs, expect to have to work with your engineering manager to scrub them from your git history!

&#x20;

For more information about security and protecting your secrets, [please see our entry in the Labs Guides.](https://docs.labs.lambdaschool.com/home/#please-read-this-carefully)
