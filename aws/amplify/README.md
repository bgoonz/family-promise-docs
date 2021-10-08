# Amplify

{% hint style="warning" %}
Please be sure to review, bookmark and follow all the AWS related standards in the [Labs Engineering Standards](https://docs.labs.lambdaschool.com/standards/infrastructure/aws).
{% endhint %}

[AWS Amplify](https://aws.amazon.com/amplify/) is a [PaaS](https://en.wikipedia.org/wiki/Platform_as_a_service) service that is used to host static websites.

## Glossary

### Amplify Application

An Application in AWS Amplify represents a group of deployments from a specific repository. As such, each project team will work inside a separate AWS Amplify Application. See the [Labs Engineering Standards](https://docs.labs.lambdaschool.com/standards/infrastructure/aws#aw-200-resource-naming) for instructions on how to name the Application.

## FAQ

### How do I request a new AWS account or access to an existing account to use Amplify?

Your APL will provide your team with access to a Lambda School managed AWS account.

### How do I configure the Amplify build process?

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

### Why is my build working locally, but not in Amplify?

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

### Why is my OIDC callback route not working?

**tl;dr**

Add this rule: [https://docs.aws.amazon.com/amplify/latest/userguide/redirects.html\#redirects-for-single-page-web-apps-spa](https://docs.aws.amazon.com/amplify/latest/userguide/redirects.html#redirects-for-single-page-web-apps-spa)

**What's really happening?**

The redirect URL \(usually something like `[<https://myapp.com/implicit/callback>](<https://myapp.com/implicit/callback>)`\) that your OIDC identity provider sends the user back to leads to a route in your React app. Usually, there is a code passed back to your app using query parameters, like this: `[<https://myapp.com/implicit/callback?code=asdlakjdoiajsdoiqwodiqmwxo>](<https://myapp.com/implicit/callback?code=asdlakjdoiajsdoiqwodiqmwxo>)`. This code is used by the OIDC client in your app to retrieve tokens for the current user.

The issue seems to be that AWS Cloudfront \(which serves your static SPA from an S3 bucket\) considers the `/implicit/callback` path to be a directory. This automatically triggers a 301 redirect to the equivalent path _with_ a trailing slash appended. Apparently this is a function of many CDNs in order to normalize paths to maximize cache hits. This also seems to cause lots of problems with various static websites and SPAs.

For some reason, which is not clear to me, by default Cloudfront not only does a 301 redirect, but _also_ strips off query parameters... which breaks our callback. Cloudfront _does_ [support](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/QueryStringParameters.html) 301 forwarding while preserving query parameters, but that option is not able to be configured using Amplify. Though, this feature does appear to be on their backlog: [https://github.com/aws-amplify/amplify-console/issues/97](https://github.com/aws-amplify/amplify-console/issues/97)

For now though, you can add a rewrite rule that's specified here, which will resolve the [issue](https://docs.aws.amazon.com/amplify/latest/userguide/redirects.html#redirects-for-single-page-web-apps-spa)... though why it does is not clear.

If deploying an SPA to Amplify that does client-side authentication using OIDC w/PKCE, you'll need to following the directions here to add a rewrite rule that will allow your callback route to work properly: [https://docs.aws.amazon.com/amplify/latest/userguide/redirects.html\#redirects-for-single-page-web-apps-spa](https://docs.aws.amazon.com/amplify/latest/userguide/redirects.html#redirects-for-single-page-web-apps-spa)

## Resources

[What Happens When I Register a Domain? - Namecheap Blog](https://www.namecheap.com/blog/registering-domain-names/)

