# Amplify:

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



## Amplify

{% hint style="warning" %}
Please be sure to review, bookmark and follow all the AWS related standards in the [Labs Engineering Standards](https://docs.labs.lambdaschool.com/standards/infrastructure/aws).
{% endhint %}

[AWS Amplify](https://aws.amazon.com/amplify/) is a [PaaS](https://en.wikipedia.org/wiki/Platform_as_a_service) service that is used to host static websites.

### Glossary

#### Amplify Application

An Application in AWS Amplify represents a group of deployments from a specific repository. As such, each project team will work inside a separate AWS Amplify Application. See the [Labs Engineering Standards](https://docs.labs.lambdaschool.com/standards/infrastructure/aws#aw-200-resource-naming) for instructions on how to name the Application.

### FAQ

#### How do I request a new AWS account or access to an existing account to use Amplify?

Your APL will provide your team with access to a Lambda School managed AWS account.

#### How do I configure the Amplify build process?

Configuration is done using a file named `amplify.yml` that resides in the root folder of your project. This file controls the [build settings](https://docs.aws.amazon.com/amplify/latest/userguide/build-settings.html) for your application.

When you first begin using Amplify, this file is automatically created, but not stored in your repository. Instead, the file can be edited in the console, by clicking the "Build Settings" link in the menu.

{% hint style="success" %}
Pro Tip: Don't edit the `amplify.yml` file in the AWS console! You should download it, put it in your project root directory and commit it to Git to keep it version controlled.
{% endhint %}

Always make absolutely sure that you are not storing any secrets in this file!

* Why is Amplify showing me some ugly XML that says `AccessDenied` when I try to hit my app?

  If you see something like this in your browser...

  ```text
  <Error>
      <Code>AccessDenied</Code>
      <Message>Access Denied</Message>
      <RequestId>10B47523D97FE645</RequestId>
      <HostId>NGnyQXQ4VPYlEEqW6VHifVA=</HostId>
  </Error>
  ```

  Your build is probably not working correctly and you're not giving Amplify any static HTML to display. Double-check your `amplify.yml` file and your build output to be sure that the `baseDirectory` in the `artifacts` section is correctly pointing to your generated HTML.

#### Why is my build working locally, but not in Amplify?

If you are building a project using Node.js, your dependencies will be downloaded and stored by NPM in a `node_modules` folder. Dependency management is hard and sometimes NPM store dependencies that break your build. When this happens, you can delete your `node_modules` folder and reinstall your dependencies. When Amplify builds a project, by default, it caches your `node_modules` folder to speed up the build process. Unfortunately, sometimes this means that a bad dependency will be "stuck" in the `node_modules` folder that is being cached by Amplify. You can force Amplify to delete your `node_modules` folder and rebuild your project by temporarily adding a step to your build process defined by your `amplify.yml` file:

```text
version: 0.1
frontend:
  phases:
    preBuild:
      commands:
        # Temporarily delete node_modules before building
        - rm -rf node_modules
        - npm install
    build:
      commands:
        - npm build
  artifacts:
    baseDirectory: build
    files:
      - '**/*'
  cache:
    paths:
      - node_modules/**/*
```

Be sure to remove this line after the build is fixed, as rebuilding node\_modules from scratch will significantly increase your build times.

#### Why is my OIDC callback route not working?

**tl;dr**

Add this rule: [https://docs.aws.amazon.com/amplify/latest/userguide/redirects.html\#redirects-for-single-page-web-apps-spa](https://docs.aws.amazon.com/amplify/latest/userguide/redirects.html#redirects-for-single-page-web-apps-spa)

**What's really happening?**

The redirect URL \(usually something like `[<https://myapp.com/implicit/callback>](<https://myapp.com/implicit/callback>)`\) that your OIDC identity provider sends the user back to leads to a route in your React app. Usually, there is a code passed back to your app using query parameters, like this: `[<https://myapp.com/implicit/callback?code=asdlakjdoiajsdoiqwodiqmwxo>](<https://myapp.com/implicit/callback?code=asdlakjdoiajsdoiqwodiqmwxo>)`. This code is used by the OIDC client in your app to retrieve tokens for the current user.

The issue seems to be that AWS Cloudfront \(which serves your static SPA from an S3 bucket\) considers the `/implicit/callback` path to be a directory. This automatically triggers a 301 redirect to the equivalent path _with_ a trailing slash appended. Apparently this is a function of many CDNs in order to normalize paths to maximize cache hits. This also seems to cause lots of problems with various static websites and SPAs.

For some reason, which is not clear to me, by default Cloudfront not only does a 301 redirect, but _also_ strips off query parameters... which breaks our callback. Cloudfront _does_ [support](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/QueryStringParameters.html) 301 forwarding while preserving query parameters, but that option is not able to be configured using Amplify. Though, this feature does appear to be on their backlog: [https://github.com/aws-amplify/amplify-console/issues/97](https://github.com/aws-amplify/amplify-console/issues/97)

For now though, you can add a rewrite rule that's specified here, which will resolve the [issue](https://docs.aws.amazon.com/amplify/latest/userguide/redirects.html#redirects-for-single-page-web-apps-spa)... though why it does is not clear.

If deploying an SPA to Amplify that does client-side authentication using OIDC w/PKCE, you'll need to following the directions here to add a rewrite rule that will allow your callback route to work properly: [https://docs.aws.amazon.com/amplify/latest/userguide/redirects.html\#redirects-for-single-page-web-apps-spa](https://docs.aws.amazon.com/amplify/latest/userguide/redirects.html#redirects-for-single-page-web-apps-spa)

### Resources

[What Happens When I Register a Domain? - Namecheap Blog](https://www.namecheap.com/blog/registering-domain-names/)

