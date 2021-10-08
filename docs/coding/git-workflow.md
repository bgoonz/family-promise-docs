# Git Workflow:

## Git Workflow

### Lambda Labs Git Workflow

We have some guidelines while you are working at Lambda Labs that will help reduce the friction of working in teams. Git is one of our most valued tools as developers. And as such we have put together the following guide regarding a workflow that will help keep you organized as well as save your butt from time to time.

#### Objective

We will walk through the basic steps of starting and finishing a feature or task in git and github.com.

**Technologies**

* git cli
* github.com Pull Requests

**References**

* [git-scm.com](https://git-scm.com/)
* [GitHub Pull Requests](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests)

#### Getting Started

So, you're ready to start work on a new Trello card, let's get started

{% hint style="info" %}
Obviously, you can't do anything with git until you’ve cloned the team repo. After that always make sure you start with a recent copy of the repo.
{% endhint %}

```text
    > git checkout main
    > git pull origin main
```

So, to get started on your first task let’s make a branch. Making sure you are on the `main` branch, start a new branch with a name that matches or correlates to the task you are about to begin. The trick here is to think beyond yourself when naming the branch, stay aligned with your Trello board so you **AND** others can easily make sense of it.

> git checkout -b \[new\_branch\_name\]

![](https://github.com/bgoonz/family-promise-docs/tree/45cd78ca6494ce7c276cc2fa73667fb6cda1815c/docs/.gitbook/assets/git-checkout-1.png)

#### Sharing Is Good

Now you have a branch to make all your awesome commits to. However, since you just had your team in mind while naming the branch, let’s take a minute or two to do something extra nice for them. Let's us the “Early Pull Strategy” to allow team members to follow along but not be nagged by our ongoing commits. This is done simply by pushing our new branch to the **origin** then create a draft **PR** in GitHub.

> git push -u origin ${git\_current\_branch}

or

> git push --set-upstream origin ${git\_current\_branch}

{% hint style="info" %}
The -u \(--set-upstream\) will save the tracking info for the remote branch to your git config. Yay. Now you can easily push your commits to the remote branch by git push. Easy.
{% endhint %}

![](https://github.com/bgoonz/family-promise-docs/tree/45cd78ca6494ce7c276cc2fa73667fb6cda1815c/docs/.gitbook/assets/git-push-1.png)

The next step is to create a draft PR _\(Pull Request\)_ **after you’ve created your first commit**. GitHub created this mode so that notifications will be turned off by default until you decide to turn off the draft and want to have the team give you a code review. Back when we traveled uphill both ways, we called this a WIP, putting these initials at the beginning of the title and we’d have to ignore notifications that had WIP in the title. 🤮 Now we have it good.

Making sure to use the template to provide a professional description \(seriously copy the description from the Trello card, right\) summarizing the actual work in the PR, let’s create a PR using the **main** branch as the **base**.

![](https://github.com/bgoonz/family-promise-docs/tree/45cd78ca6494ce7c276cc2fa73667fb6cda1815c/docs/.gitbook/assets/github-draft-pr.gif)

#### We have lift off

And just like that we’re ready to make some awesome software. Committing and pushing our code regularly are the habits worth having. Before we know it, we’ll be ready to take the PR out of draft mode.

{% hint style="success" %}
Do your best to be a great team member by making commit messages as succinct as possible. They don’t have to be elaborate, just to the point.
{% endhint %}

**One small step**

When you feel you’ve completed the task you’ve been working on it’s time to update the description, take the PR out of draft mode and make it **“ready for review”**.

![](https://github.com/bgoonz/family-promise-docs/tree/45cd78ca6494ce7c276cc2fa73667fb6cda1815c/docs/.gitbook/assets/github-ready-pr.png)

And just like that, the team will be notified of the PR and they can start a review and it can be merged.

{% hint style="info" %}
Follow the team policy regarding the number of reviewers required before merging
{% endhint %}

It’s really good practice to take the time to make comments in the code, even if they are positive notes on good work your teammate did.

#### QA changes on stage before merging to main

Since you branched off of main your PR should be tested on stage prior to approving and merging. If there are no issues found on stage and no conflicts to be resolved in the code choose “Rebase and merge” or "Squash and merge" from the merge button and let's get onto main.

![](https://github.com/bgoonz/family-promise-docs/tree/45cd78ca6494ce7c276cc2fa73667fb6cda1815c/docs/.gitbook/assets/github-merge.png)

If you find yourself with a merge conflict there are a number of ways to solve it. The GitHub tools are very handy or you can do it locally. When going down the local path there is a good set of instructions at [About pull request merges](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-request-merges)

And now your code changes are on the main branch, ready to wow users with your updates. Deploy your code \(if not automatically handled by GitHub events\) and be ready to support any issues that arise.

