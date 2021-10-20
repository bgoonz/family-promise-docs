# GitHub

## GitHub

### What's GitHub?

[**GitHub (Links to an external site.)**](https://github.com) is an online repository hosting service and is the most commonly used of its kind in the software industry. While git is a command line tool, GitHub provides us with an online graphical user interface (GUI) to use for storing and working with our repositories.

Understanding the basic commands to work with git and subsequently publish your work to a remote repository is of the utmost importance for you as you enter the job force.

For more information on our GitHub setup in Labs, see our entry in [the Labs Guides (Links to an external site.)](https://docs.labs.lambdaschool.com/guides/github/github-basics).



## Branching

This is something you already know how to do. Using `git checkout -b <your-branch-name>` is how we create new branches to work off of.

In Labs, **we require that all branches be broken off of the `main` branch in your repositories.** This will allow for a clean development flow.

There are two types of branches you'll create during your time in Lambda School Labs, and we ask that you follow a specific naming convention for each flow:

1. **Feature** branches: `feature/description-description-of-the-feature`
   * _Example_: If I needed to implement a login form for my app, my branch name would be `feature/login-form`
2. **Bug** branches: `bug/description-of-bug`
   * _Example_: If I was fixing the login form button, my branch name would be `bug/login-submit-handler`

The reason for segmenting everything into these two simple branching flows is so that you don't have a messy **git history**—the chronological log of changes that were made to your project's code over time.

In the real world, you might see more complex and/or specific strategies, depending on how your team operates. Knowing this flow will help you be prepared for any strategy a team deems necessary to deploy.





## Creating Pull Requests and Draft Pull Requests

### Forking vs. Cloning

In order to submit your code for review and eventually merge your code into the main branch of your project's repository, you'll need to open a pull request.

This step is one you're familiar with at this point in your Lambda School journey. The main difference between what you've been doing in core instruction versus what we do here in Labs is that **you won't fork your project's repositories**—instead, you'll **clone** them, working within the same GitHub organization.

Forking is a natural choice for open source contributions to product repositories in GitHub organizations that you don't belong to. Here in Labs, you'll be part of the Lambda School Labs GitHub organization. You've been granted write access to the repos with which you'll be working.

Thus, in Labs, **you'll never need to fork a repository**—except perhaps at the very end of your project, when you can decide to fork your project repos to keep a copy of your work in that state after you leave Labs (note that **if you don't do this, you'll lose access to the project code!**).

### Draft Pull Requests

A [**draft pull request (Links to an external site.)**](https://github.blog/2019-02-14-introducing-draft-pull-requests/) is a feature introduced by GitHub in early 2019 that lets you easily share and track a **work in progress**. As you go through the process of opening a pull request, you can designate it as a draft, which comes with many benefits.

Draft pull requests can't be merged, so you won't accidentally merge in changes that aren't ready. When you submit draft pull requests, you also won't spam any "code owners" (in Labs, your Release Manager!) with spurious notifications.

But opening a draft pull request _will_ let you easily show your work and consolidate a conversation around it as it progresses. We **highly recommend** using draft pull requests in Labs to maximize visibility into your work and facilitate the number one factor in the success of a project: **communication**.

### Further Reading

* **GitHub:** [About pull requests: Draft pull requests](https://docs.github.com/en/github/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests#draft-pull-requests)



## Rebasing

Throughout your career, you'll encounter a variety of merging strategies. We require you use a [Git Rebase (Links to an external site.)](https://docs.labs.lambdaschool.com/guides/coding/git-rebase) strategy for your team's workflow in Labs.

How teams merge code is a _hotly_ debated topic in the industry, but here in Lambda School Labs, we ask that you use a `rebase` strategy to keep your git commit history clean. Although there are other strategies for merging code across development teams, rebase is the dominantly accepted practice in the industry today.

### **Why Rebase?**

On occasion, you'll find that you've been working on a feature branch and you need to merge in changes from the main branch. This could just be a final step before you push a series of commits to GitHub in order to create a pull request (PR). Or, maybe it's to update your branch from `main` after a day or so of work.

With rebasing, you approach this situation by finding the "common ancestor" of the main and feature branch, and then "replaying" the commits made since then to create a new base commit.

![A rebase workflow showing the new combined HEAD](https://lambdaschool.instructure.com/courses/1552/files/388782/preview)

Sound complicated? Here's how it works:

### **How to Rebase**

These steps are similar to what the "Rebase and Merge" action does on GitHub. **(You should always use this if "Squash and Merge" isn't available.)**

1. Make sure all changes are committed to your feature branch.
2. Update your local master branch:
   * `> git checkout master`
   * `> git pull origin master`
3. Go back to your feature branch:
   * `> git checkout feature-branch`
4. Now we can rebase the feature branch onto `master`:
   * `> git rebase master`
   * Result: `First, rewinding head to replay your work on top of it...` `Applying: added staged command`
5. Your commits will now show in the git log after the commits merged from master.

&#x20;

For more information, see our entry on Git Rebase in [the Labs Guides (Links to an external site.)](https://docs.labs.lambdaschool.com/guides/coding/git-rebase).

### Further Reading

* **git**: [Rebasing (Links to an external site.)](https://git-scm.com/book/en/v2/Git-Branching-Rebasing)
* **Atlassian**: [git-rebase](https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase)



## Merge Conflicts

### What are Merge Conflicts?

**Merge conflicts** occur within a development team's workflow when two developers try and update the same line of code in the same file. When this happens, git will inform you that you have a merge conflict.

You need to resolve merge conflicts before pushing to your branch and rebasing your code into `main`.

When a merge conflict occurs, git will write some text directly into the file where the conflict exists. You'll need to:

1. Go into that file and remove that inserted text
2. Specify which lines of code you want to live in your branch

&#x20;

💡  Pro tip: VSCode (and other IDEs) have great merge conflict tools built in. We **highly** recommend you resolve any merge conflicts that arise with another developer present—preferably the developer whose code you're conflicting with!

### Dealing With Merge Conflicts

Here's how to deal with merge conflicts in practice:

### Further Reading

* **GitHub**: [All About Merge Conflicts (Links to an external site.)](https://docs.github.com/en/github/collaborating-with-pull-requests/addressing-merge-conflicts/about-merge-conflicts)
* **GitHub:** [How to Resolve Merge Conflicts (Links to an external site.)](https://docs.github.com/en/github/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-using-the-command-line)





## Reviewing Pull Requests

Here in Lambda School Labs, we firmly believe that **clean code lives and dies by authoring and reviewing high-quality pull requests**.

In Labs, the pull request is the final step between your development lifecycle and deployment. Since it's your final step to get your code pushed to production, it's of the utmost importance that you try your hardest to ensure that the quality of the code you'll be submitting is held to the highest standard possible.

### Pull Request Requirements in Labs

We require that each pull request:

* contains a **brief, 2–5 minute** video walkthrough presenting your work
* is well documented and provides links to any supporting documents—like Trello cards, design artifacts, or further documentation to ensure everyone knows **why** the pull request was necessary.
* has commits that are relevant to what has changed.
* contains work relevant to the pull request description.
* has been adequately **reviewed by at least 2 peers and your release manager**. Your release manager has final approval, and your code will not be merged into `main` unless your release manager has approved it.
* contains maintainable code that has been formatted to your product specifications.
* follows industry best practices.

Not only do pull requests highlight the code you write—**they're the best mechanism for a hiring manager get a glimpse into how you work as an effective member of a dev team.** Treat them as professionally as you'd like to be treated in the industry.

#### The Pull Request Rubric

Follow our rubric to help you practice authoring and reviewing proper pull requests. Throughout Labs, we'll hold regular Pull Request Critique sessions, where your engineering manager will breakdown the work you've done and how you've worked to make it clear to reviewers.

[**Pull Request Rubric**](https://www.notion.so/lambdaschool/1fc04e4fedeb429ba873b7c68d281707?v=74054da7991341c0bf970f39410c43da)



## Pull Request Rubric

|                                                                                                                                                               |                                                                                                                                                                                                                    |                                                                                                                                                                                        |                                                                                                                                                  |                                                                                                                                                                                                                |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Objective                                                                                                                                                     | Description                                                                                                                                                                                                        | 1-3 (Not Passing)                                                                                                                                                                      | 4 (Passing)                                                                                                                                      | 5-7 (Exceptional)                                                                                                                                                                                              |
| [Clearly documents the motivation and what changed](https://www.notion.so/Clearly-documents-the-motivation-and-what-changed-7bde9cc88e8241ee8d802b5d6ff146fa) | Is it clear why the pull request exists? Does it link to supporting documentation (user story, product roadmap, design) to give broader context? Is the code itself appropriately commented?                       | The PR description is either blank or only contains the boilerplate PR template or unchecked checklist items. Code comments aren't used, even when they would be helpful.              | The PR description outlines the motivation for the feature and/or links to a user story or other document describing the purpose of the feature. | The PR description includes a clear rationale for the feature, or a screenshot showing either the intended state or completed state of the feature, and gives additional context about changes made in the PR. |
| [Atomic, well-named commits](https://www.notion.so/Atomic-well-named-commits-cb361314bff941fbaa6bbf8f325bfea7)                                                | Does the pull request consist of small commits with clear titles? Do all commits have relevant and sensible messages of what was changed?                                                                          | Commits are not named appropriately. Commits have sensible messages. Example. "Updated", "Fixed a bug"                                                                                 | Commits are well named. Commits have descriptive messages relevant to what changed. Some commits are not atomic.                                 | Commits are well named. Commits have descriptive messages. Each commit introduces atomic changes.                                                                                                              |
| [Appropriately Scoped](https://www.notion.so/Appropriately-Scoped-d04fd9f628494c8da1025a40c9b352c5)                                                           | Is the pull request small enough to review easily? Is it focused on solving a single cohesive problem?                                                                                                             | Pull request introduces multiple features or solves multiple problems. PR is unreasonably big with many changed files. Some code changes that are not related to the purpose of the PR | PR is relatively small. PR has some minor changes not related to the feature or primary change being introduced.                                 | PR is focused on a single problem. PR is small enough and easy to review.                                                                                                                                      |
| [Adequately reviewed](https://www.notion.so/Adequately-reviewed-e390e4309863446da82907cdd6d76c18)                                                             | Has the pull request been reviewed by at least two team members? Your release manager will be the final reviewer of the pull request. Did they leave any comments or suggestions? Were those suggestions acted on? | PR was merged by the same developer who requested it. The reviewer rejected PR with no comments. PR was initiated again and suggested changes were not addressed.                      | At least two team members reviewed PRs. Appropriate comments were left in the PR. Suggestions were acted upon.                                   | PRs were reviewed by more than one team member. PR requests were sent to multiple reviewers. Active high-quality discussions are evident in PRs.                                                               |
| [Code is clear and maintainable](https://www.notion.so/Code-is-clear-and-maintainable-ff6dbd609cf84aabb825fdd854758986)                                       | Is the code formatted appropriately? Is there dead code? _**logs and print statements have no place in your main branches!**_ Are there instances of duplicate code? Does code have TODOs committed to main?       | Code has inconsistent formatting. Significant amount of dead code across the codebase. Multiple instances on TODOs in main. Significant amount of duplicated code.                     | Code is consistently formatted. Functions are relatively small. Few instances of duplicate code. Few instances of dead code.                     | Code is consistently formatted. Has config files to enforce linting and formatting. No instance on duplicate code.                                                                                             |
| [Code is idiomatic](https://www.notion.so/Code-is-idiomatic-3ba62709ad784917973adcc74cfc3248)                                                                 | Does the code follow industry standards for the language, framework, and libraries used?                                                                                                                           | Code consistently does not adhere to best practices for the language, framework or libraries used.                                                                                     | Code has apparent minor deviations from industry standards.                                                                                      | Code follows best practices of language, framework and libraries use. Effort has been made to improve on those practices.                                                                                      |

