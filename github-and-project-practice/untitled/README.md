# GitHub

Think of commits on GitHub as elements of a linked list.

{% embed url="https://lambdaschool.enterprise.slack.com/files/U02CA71AVQV/F02GB1KFAE8/git_and_trello_walkthrough.mp4" %}

Steps for Pull Request\


1. Git Status - to see what files were updated
2. Git Add (by filename) - to add the files that are relevant to the push
3. Git commit 'insert message here'
4. Git push origin \<branch name> - name branch after the funtion being created
5. Open the PR in github
6. Invite and Get 2 reviewers to approve the code
7. Ash will then watch your loom video and merge the request – He's the “Release Manager”

As an alternative to merging, you can rebase the feature branch onto main branch using the following commands:git checkout feature\
git rebase mainThis moves the entire feature branch to begin on the tip of the main branch, effectively incorporating all of the new commits in main. But, instead of using a merge commit, rebasing re-writes the project history by creating brand new commits for each commit in the original branch.**Fill out In PR**### Description\*\*Invited Collaborator(s) to Review\
\- Added person to review relating to feature/bug\
\- If not available, ask another reviewer on team\*\*What work was done?\*\*\
\- Describe in detail what's been modified/created\*\*Why was this work done?\*\*\
\- What is the purpose of the feature?\*\*What feature / user story is it for?\*\*\
(Link if possible)\
\*\*Any relevant links or images / screenshots\*\*### Type of change\
Please delete options that are not relevant.\
\- New feature (non-breaking change which adds functionality)Testing\
\- Has this feature been tested before conflict?\
\- Has this feature been tested after conflict?Change Status\
\- Completed, ready to review and merge### Checklist\
\- My code follows the style guidelines of this project\
\- I have performed a self-review of my own code\
\- My code has been reviewed by at least one peer\
\- I have commented my code, particularly in hard-to-understand areas\
\- I have made corresponding changes to the documentation\
\- My changes generate no new warnings\
\- There are no merge conflicts



{% file src="../../.gitbook/assets/image (2).png" %}

{% embed url="https://familypromise.org/" %}

## NEW GITFLOW:

* [ ] Git Status - to see what files were updated
* [ ] Git Add (by filename) - to add the files that are relevant to the push
* [ ] Git commit 'insert message here'
* [ ] Git push origin
* [ ] Open the PR in github
* [ ] Get 2 reviews
* [ ] I will then watch your loom video and merge

## Pull Request Rubric

| Objective                                                                                                                                                     | Description                                                                                                                                                                                                        | 1-3 (Not Passing)                                                                                                                                                                      | 4 (Passing)                                                                                                                                      | 5-7 (Exceptional)                                                                                                                                                                                              |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Clearly documents the motivation and what changed](https://www.notion.so/Clearly-documents-the-motivation-and-what-changed-0c7f5d04d7f9401e8e861ce93312d503) | Is it clear why the pull request exists? Does it link to supporting documentation (user story, product roadmap, design) to give broader context? Is the code itself appropriately commented?                       | The PR description is either blank or only contains the boilerplate PR template or unchecked checklist items. Code comments aren't used, even when they would be helpful.              | The PR description outlines the motivation for the feature and/or links to a user story or other document describing the purpose of the feature. | The PR description includes a clear rationale for the feature, or a screenshot showing either the intended state or completed state of the feature, and gives additional context about changes made in the PR. |
| [Atomic, well-named commits](https://www.notion.so/Atomic-well-named-commits-67085273f3b945beb14af73e51c61522)                                                | Does the pull request consist of small commits with clear titles? Do all commits have relevant and sensible messages of what was changed?                                                                          | Commits are not named appropriately. Commits have sensible messages. Example. "Updated", "Fixed a bug"                                                                                 | Commits are well named. Commits have descriptive messages relevant to what changed. Some commits are not atomic.                                 | Commits are well named. Commits have descriptive messages. Each commit introduces atomic changes.                                                                                                              |
| [Appropriately Scoped](https://www.notion.so/Appropriately-Scoped-3b6f396ee76d4075b0b66c702624f05e)                                                           | Is the pull request small enough to review easily? Is it focused on solving a single cohesive problem?                                                                                                             | Pull request introduces multiple features or solves multiple problems. PR is unreasonably big with many changed files. Some code changes that are not related to the purpose of the PR | PR is relatively small. PR has some minor changes not related to the feature or primary change being introduced.                                 | PR is focused on a single problem. PR is small enough and easy to review.                                                                                                                                      |
| [Adequately reviewed](https://www.notion.so/Adequately-reviewed-44cf640022d94c35a23589263a943d76)                                                             | Has the pull request been reviewed by at least two team members? Your release manager will be the final reviewer of the pull request. Did they leave any comments or suggestions? Were those suggestions acted on? | PR was merged by the same developer who requested it. The reviewer rejected PR with no comments. PR was initiated again and suggested changes were not addressed.                      | At least two team members reviewed PRs. Appropriate comments were left in the PR. Suggestions were acted upon.                                   | PRs were reviewed by more than one team member. PR requests were sent to multiple reviewers. Active high-quality discussions are evident in PRs.                                                               |
| [Code is clear and maintainable](https://www.notion.so/Code-is-clear-and-maintainable-de9ef74e969b47f5bab234f5a346c407)                                       | Is the code formatted appropriately? Is there dead code? _**logs and print statements have no place in your main branches!**_ Are there instances of duplicate code? Does code have TODOs committed to main?       | Code has inconsistent formatting. Significant amount of dead code across the codebase. Multiple instances on TODOs in main. Significant amount of duplicated code.                     | Code is consistently formatted. Functions are relatively small. Few instances of duplicate code. Few instances of dead code.                     | Code is consistently formatted. Has config files to enforce linting and formatting. No instance on duplicate code.                                                                                             |
| [Code is idiomatic](https://www.notion.so/Code-is-idiomatic-c8d7786458b9430d9b6bad50cd904c9c)                                                                 | Does the code follow industry standards for the language, framework, and libraries used?                                                                                                                           | Code consistently does not adhere to best practices for the language, framework or libraries used.                                                                                     | Code has apparent minor deviations from industry standards.                                                                                      | Code follows best practices of language, framework and libraries use. Effort has been made to improve on those practices.                                                                                      |

![](https://i.imgur.com/GkA8KdP.png)

## Pull Request Template

#### Description

\*\*Invited Collaborator(s) to Review

* Added person to review relating to feature/bug
* If not available, ask another reviewer on team

**What work was done?**

* Describe in detail what's been modified/created

**Why was this work done?**

* What is the purpose of the feature?

**What feature / user story is it for?** (Link if possible) **Any relevant links or images / screenshots**

#### Type of change

Please delete options that are not relevant.

* New feature (non-breaking change which adds functionality)

Testing

* Has this feature been tested before conflict?
* Has this feature been tested after conflict?

Change Status

* Completed, ready to review and merge

#### Checklist

* My code follows the style guidelines of this project
* I have performed a self-review of my own code
* My code has been reviewed by at least one peer
* I have commented my code, particularly in hard-to-understand areas
* I have made corresponding changes to the documentation
* My changes generate no new warnings
* There are no merge conflicts

## GitHub Basics

### The Labs GitHub Org

Lambda Labs maintains a GitHub organization ([https://github.com/Lambda-School-Labs](https://github.com/Lambda-School-Labs)) which houses all of the Labs projects (with few exceptions) that are built by student teams during Labs.

#### The Basics

* All repositories are [publicly accessible](https://help.github.com/en/github/administering-a-repository/setting-repository-visibility) and licensed under [The MIT License](https://opensource.org/licenses/MIT)
  * This effectively means that the code in the repositories belongs to the world; Lambda School simply maintains the organization to keep the code accessible and organized.
* Only Lambda School Engineering Managers will have the role of Owner in the organization, everyone else will have the role of Member
  * The Member role has very limited permissions and will only be able to access repositories that are specifically assigned to the user, directly or through Teams. Work with an Engineering Manager for any administrative tasks

#### GitHub Teams

Member permissions for teams are generally granted using [Teams](https://help.github.com/en/github/setting-up-and-managing-organizations-and-teams/organizing-members-into-teams). This allows individual member permissions to be more easily maintained and made consistent. A GitHub team will be created for each Labs team with a specific naming convention to identify the team: `<Cohort>-<Team Letter>-<Product Name>` (e.g. `Labs 26 - A - Apollo`).

* There will be one team per project, per cohort.
* The APL, TPL and all students that are part of the project will be members of this team.
* Teams will be deleted shortly after the Labs cohort ends.
  * This means Team members will lose direct access to the code in the Labs org... but don't worry! The code is public and MIT licensed, so you can fork away to continue working on the code!

To be a member of a Team, you must be a member of the Organization that the Team is part of. If this is your first time on a Labs team, Labby will invite you to be a member of the Labs GitHub Organization. This invite _should_ arrive in the email that is associated with your GitHub account. If it doesn't, check your spam filter folder. If it's not there, you _should_ be able to see the invite in your GitHub notifications tab: [https://github.com/notifications](https://github.com/notifications)

If you think you should have an invite, but can't find it, please talk to a Section Lead or Tech Lead.

### FAQ

#### Why am I being automatically subscribed to new repositories?

Automatic subscriptions are controlled via your personal settings: [https://github.com/settings/notifications](https://github.com/settings/notifications)
