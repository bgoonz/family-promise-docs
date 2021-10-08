# Amplify Deployment

## Deploy Frontend React App

A walk through of one of the coolest new deployment platforms out there, Lab Standards compliant AWS Amplify.

### Objective

We will walk through the deployment of a front end react app on AWS Amplify, one of the approved services in the [Labs Standards](https://lambda-school-labs.github.io/labs-engineering-standards/). The deployment will have automatic deploys upon merge to `main`. In addition we will cover the steps to setup Previews that will be generated when a PR is created.

#### Technologies

* [AWS Management Console](https://console.aws.amazon.com)
* [github.com](https://github.com)

#### References

* [AWS Amplify](https://aws.amazon.com/amplify/)

#### Prerequsites

* You will need to have an [AWS account](https://console.aws.amazon.com)
* A [github.com](https://github.com) account

### Setup `main` deployment

* Create a base react app using create-react-app
* > `> npx create-react-app awesomeness-aws-app`
  >
  > `> cd awesomeness-aws-app`
* Initialize the Git repo and set origin to the new repo

  > `> git init`
  >
  > `> git remote add origin <new repo url>`

* Initialize the react project and confirm it works

  > `> npm; npm start; open http://localhost:3000`

* Push the repo to github

  > `> git push origin main`

* Open the AWS Amplify console and connect an app. Choose to connect existing code from github and enter your `main` branch ![Open AWS Amplify Console](https://github.com/Lambda-School-Labs/gitbook-labs-guides/tree/1b9f095385cbf02520a451e3ea7ed75d8d417963/aws/assets/images/aws-amplify/aws-console-amplify.png) ![connect an app](https://github.com/Lambda-School-Labs/gitbook-labs-guides/tree/1b9f095385cbf02520a451e3ea7ed75d8d417963/aws/assets/images/aws-amplify/amplify-connect-app.png)

!!! Info You will need to authorize WAS with github to gain access. This is similar to services like Netlify and Heroku.

```text
![Connect a repo](../assets/images/aws-amplify/amplify-connect-repo.png
"connect a repo")
```

* Save the default settings and watch the deploy ![Deploy app](https://github.com/Lambda-School-Labs/gitbook-labs-guides/tree/1b9f095385cbf02520a451e3ea7ed75d8d417963/aws/assets/images/aws-amplify/amplify-deploy.png)
* open your browser to the url amplify setup for you to confirm you have a Labs Standards compliant site running. 🎉

### Setup Previews

Similar to [Heroku Review apps](https://devcenter.heroku.com/articles/github-integration-review-apps) AWS Amplify can create resources to serve up your app based on a PR.

* Open Previews from the side bar
* Click to enable Previews

  !\[Enable previews\]\(../assets/images/aws-amplify/amplify-enable-previews.png

  "Enable previews"\)

{% hint style="info" %}
You will need to install a GitHub app to enable previews. Either your APL or Engineering Manager will need to do this for your repo.
{% endhint %}

```text
![Enable previews](../assets/images/aws-amplify/amplify-previews-github-app.png
```

```text
"Enable previews")
```

* After installing the github app open the preview for `main` branch and enable PR previews ![Manage previews](https://github.com/Lambda-School-Labs/gitbook-labs-guides/tree/1b9f095385cbf02520a451e3ea7ed75d8d417963/aws/assets/images/aws-amplify/amplify-manage-previews.png) ![Enable PR previews](https://github.com/Lambda-School-Labs/gitbook-labs-guides/tree/1b9f095385cbf02520a451e3ea7ed75d8d417963/aws/assets/images/aws-amplify/amplify-pr-previews.png)
* All set. Now go commit a change to your project and push to a new branch so you can create a PR.
* You should see a "github check" for `AWS Amplify Console Web Preview` in your PR Conversation view. ![PR preview](https://github.com/Lambda-School-Labs/gitbook-labs-guides/tree/1b9f095385cbf02520a451e3ea7ed75d8d417963/aws/assets/images/aws-amplify/amplify-pr-preview.png)
* It will take a few minutes to create your app in AWS but when it's done a link to the site will appear in the previews list. ![PR in previews list](https://github.com/Lambda-School-Labs/gitbook-labs-guides/tree/1b9f095385cbf02520a451e3ea7ed75d8d417963/aws/assets/images/aws-amplify/amplify-pr-previews-list.png)
* Open the PR url and see your changes live.
* When you merge your PR AWS Amplify will destroy the preview and automagically

  deploy main to the production resources. 🎉🎉

#### A video walk-through of this entire process

