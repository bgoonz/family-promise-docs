# Git Rebase:

## Git Rebase

### Rebasing a feature branch from main

On occassion you'll find that you've been working on a feature branch and you need to merge in changes from master. This could just be a final step before you push a series of commits to github before creating a PR.

These steps are similar to what the "Rebase and Merge" action does on github.

#### Objective

This guide will show you how to rebase \(rebuild\) a feature branch to begin at the current HEAD of the master branch. Think of it as if you are starting a new branch based on the current master and pasting all of your commits to the new branch.

![](https://github.com/bgoonz/family-promise-docs/tree/45cd78ca6494ce7c276cc2fa73667fb6cda1815c/docs/.gitbook/assets/git-rebase.svg)

{% hint style="danger" %}
Never rebase a branch that has already been pushed to a remote \(public, eg. the main branch\) repository, such as github; doing so will cause conflicts and confusion among your team.
{% endhint %}

**Technologies**

* git cli

**References**

* [The Pro Git book](https://git-scm.com/book/en/v2/Git-Branching-Rebasing)
* [bitbucket tutorials](https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase)

#### Getting Started

1. Make sure all changes are committed to your feature branch
2. You will need to update your local master branch
   * `> git checkout master`
   * `> git pull origin master`
3. Go back to your feature branch
   * `> git checkout feature-branch`
4. Now we can rebase the feature branch onto `master`

   > git rebase master First, rewinding head to replay your work on top of it... Applying: added staged command

5. Your commits will now show in the git log after the commits merged from master

