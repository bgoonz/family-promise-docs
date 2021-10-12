# Github Actions:



## Github Actions

### Objective

Provide an introduction to github actions, continuous integrations, and continuous delivery

### Technologies

* Github Actions

#### What are Github Actions

Github actions provide developers the ability to automate routine and necessary tasks. This will allow you to spend more time on this things you love (like code 👨‍💻).

When a user interacts with a Github repository an event triggers (eg. push request, pull request, merge requests). Developers can use these events to start an automated workflow — A git hub container with a set of instructions or actions. Rather than write actions from scratch, the most common actions have been provided by the Github community each on a repository capable of being forked and modified.

Common use cases for GitHub Actions include Continuous Integration, and Continuous Deployment

#### Setting up GitHub Actions

* For every repository on GitHub there is an actions tab, which provides a log of every action performed on the server
* In your repo .githib folder you will need to have a workflows folder, with each workflow as a .yml file. GitHub will automatically recognize all .yml files in this folder as workflows.
* For each workflow you will want to make a separate .yml folder ![Setting Up Workflow Folders](https://github.com/Lambda-School-Labs/gitbook-labs-guides/tree/1b9f095385cbf02520a451e3ea7ed75d8d417963/assets/images/github-actions/workflowFolder.png)

#### Parts of a YML File

A YML file, similar to a python script operates with indentation. Spacing determines what is nested beneath each operator.

Example .YML folder 

* On line 1, "name:" declares the name of the workflow
* On line 2, "on:" declares the events that trigger the workflow. In this example, the workflow will be triggered whenever the user makes a pull request, or pushes to the master branch
* On line 8, "jobs:" declares the actions that will occur when a triggering event occurs. The next level of indent declares the name.
* On line 11, "runs-on:" determines what operating system you wish to run on the GitHub virtual machine (Where the actions are being performed on GitHub)
* On line 13, "env:" establishes environmental configuration, often for establishing secrets, such as this case. PERSONAL_TOKEN is the name we gave our secret on the repository. A new secret can be added by going to settings on your repository-> Secrets -> New Secret(see image below).
* On line 14, "steps:" list the set of instructions for the action.
* In this example, first two actions (lines 15 and 18) are official actions that get our source code into the virtual machine (actions/checkout@v1) and setting up node (actions/setup-node@master). You will see these pretty often and most of your workflows will probably start with these.
* Lines 19-22, install and a linter that test Markdown
* The rest of the actions you see are custom scripts, or setting up the environment for this project and will vary from project to project. This is a simple continuos deployment example.
* In this example, we are installing markdownlint to test the formatting of our markdown files, we are setting up a python environment, and we then run a python program called mkdocs that builds simple website from our markdown files. If it was pushed, we then we set up continuous deployment to deploy to github pages.

#### Continuous Deployment

* The example above was an example of using GitHub Actions for continuous deployment.
* The purpose of continuous deployment is to push the code that we have written to our customers or a third party quickly and automatically. This allows features and bug fixes to be applied multiple times a day, once it passes our Quality Assurance checks.

#### Example: Continuous Integration

The purpose of continuous integration is to streamline the process to merge developer's code multiple times per day.

For continuous integration to work, every time a pull request is made, GitHub will run test script(s). It also will let you know how they went. If any tests fail or the build fails, the actions will have a red x letting you know that have a little more work to do. If all the tests pass you will get a little green checkmark ✔ and the reviewers will trust your changes. Yay! 😀

The code here uses the community action paanbati/codeclimate-action to integrate with the Lambda Labs code climate.

#### Links to external 3rd party tutorials and documentation

* [Github Actions Documentation](https://help.github.com/en/actions)
* [Fireship's GitHub Action's Tutorial](https://www.youtube.com/watch?v=eB0nUzAI7M8\&t)
