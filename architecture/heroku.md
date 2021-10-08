# Heroku

## Heroku

### \(HE-100\) Naming Standards <a id="he-100-naming-standards"></a>

The following naming standards apply to all apps in Heroku:

* The name of the Heroku App must match the repository name

Rationale:

* Naming conventions are crucial for managing the large number of different applications we support

Alternatives:

* None

Exceptions:

* None

[  
](https://docs.labs.lambdaschool.com/standards/infrastructure/aws)Heroku Basics

​[Please read this first!!](https://docs.labs.lambdaschool.com/guides/always-read-this-first)​

## SSL <a id="ssl"></a>

Enabling SSL is as easy as switching it on in the settings tab.

1. Click Configure SSL
2. Choose Automatic Certificate Management \(ACM\)
3. Done

## FAQ <a id="faq"></a>

### How do we get a new or existing Heroku account? <a id="how-do-we-get-a-new-or-existing-heroku-account"></a>

Your APL will provide your team access to a Heroku application as needed in a Lambda School managed Heroku account

## Heroku Node Deployment

Heroku

![](https://gblobscdn.gitbook.com/assets%2F-MFfkpZnSSKK09iKBtrP%2Fsync%2Fb9db5d8a348e9131be46c653a1a61b2f407fac21.png?alt=media)

As `Associate Product Lead` and `Technical Project Leads` you'll be responsible for provisioning Heroku accounts for your students, configuring the applications to use a `Postgres` addon, and granting access to the provisioned app to the students who need it \(should be WEB students primarily\).

Currently only APLs will have full admin access to apps.

There are some settings any team member can perform, eg. `Environment Variables`

## Steps to setting up and provisioning Heroku apps - APLs <a id="steps-to-setting-up-and-provisioning-heroku-apps-apls"></a>

If you haven't gotten admin access to Heroku yet please ask you engineering manager to set that up using your `Lambda School Student Email` \(@lambdastudents.com\)

1. Log into the Heroku console using your Lambda issued student email.

   _You should have received access to the console from your engineering manager._

2. Click on the `New` button in the top right corner
3. Name the app using our Labs naming convention: `productname-team-api` i.e.

   `ecosoap-a-api`

![](https://gblobscdn.gitbook.com/assets%2F-MFfkpZnSSKK09iKBtrP%2F-MJ4repw6VEnN11x8bTF%2F-MJ4sN9tNJs6qpGlg2-W%2Fheroku-app-deploy-1.png?alt=media&token=f08bfcb4-7e6c-47d1-b7c7-f184ccee4744)

### Configuring the `PostgresQL` add-on - APLs <a id="configuring-the-postgresql-add-on-apls"></a>

1. Select the app and click on `Overview`
2. Select `Configure Add-ons`
3. Search for `Postgres` and `Heroku Postgres` should appear in the list of options
4. Select `Heroku Postgres` and select -&gt; `Hobby Basic - $9.00`
5. Select `Provision`

### Adding Members to the provisioned app - APLs <a id="adding-members-to-the-provisioned-app-apls"></a>

1. Once the app is created click on the app and select the `access` tab
2. Click `Add Member` and add your students \(please use their lambda issued emails\) and TPL to the app as making sure that `View`, `Deploy`, `Operate` boxes are all selected. Click `Save Changes`
3. Your students should receive an email granting them access to their console; follow up and make sure they are able to get in

_Note: For build-ons, you'll be adding students to an existing Heroku app._

### Environment Variables - Any team member with access <a id="environment-variables-any-team-member-with-access"></a>

1. From the application tab navigation select `Settings`
2. Select `Reveal Config Vars`
3. \*\*You should already see a `DATABASE_URL` assigned to the postgres add-on you

   set up\*\*

4. Add all the proper environment variables

### Deployment - APLs <a id="deployment-apls"></a>

#### Setup <a id="setup"></a>

Connect github

![](https://gblobscdn.gitbook.com/assets%2F-MFfkpZnSSKK09iKBtrP%2F-MJ4repw6VEnN11x8bTF%2F-MJ4sgX5bhECjfTJm0ZA%2Fheroku-app-deploy-github.png?alt=media&token=11817507-3af6-4e8c-91c3-979e1868090d)

1. From the application tab navigation select `Deploy`
2. Select the `GitHub` "Deployment Method"
3. Find the `Connect to GitHub` section and select `Lambda-School-Labs`
4. Find your app and select `Connect`
5. Deploy from the `main` branch
6. Select `Wait for CI to pass before deploy`
7. `Enable Automatic Deploys` so that anytime a branch is merged into main

connect repo

![](https://gblobscdn.gitbook.com/assets%2F-MFfkpZnSSKK09iKBtrP%2Fsync%2F38e94b355c612085c6cc12c927819876a0b797a8.png?alt=media)

#### First Deploy <a id="first-deploy"></a>

There are 2 conditions where Heroku will likely not automatically deploy the app right after setup:

1. The events `push` for the main branch and `ci_complete` haven't triggered
2. There is no code in the repo yet 😬😂

When your repo is ready follow these steps to complete the deploy.

1. run a manual deploy by hitting the `Deploy Branch` button at the bottom of

   the page

2. Click `Open app`; you will see the `"api":"up"` message if all is well.
3. Using the heroku console run the following commands \(Alternatively you

   can use the heroku cli app\)

   1. `bash` then you can run the following commands from the shell
   2. `npm run knex migrate:latest`
   3. `npm run knex seed:run` this is optional if the team wants to start with

      5 profiles.

| ​ | ​ |
| :--- | :--- |
| ​​ | ​​ |

![run console](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-MFfkpZnSSKK09iKBtrP%2Fsync%2F7f5a1f23850486ea860661a25b409d5299f03d6f.png?generation=1602119567515531&alt=media)

![console bash](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-MFfkpZnSSKK09iKBtrP%2Fsync%2F30f3b8bfd575390a51b13adafce932191edd2019.png?generation=1602119568513943&alt=media)

**Your team is now set up! Now when someone has a PR merged into** **`main`** **your team's app will update across the world wide web**

### Next Steps <a id="next-steps"></a>

Checkout how to [setup Review Apps](https://github.com/Lambda-School-Labs/gitbook-labs-guides/tree/f514baf6b1b0c2764cc2bce1739043d8ef763b96/heroku/heroku/review-apps/README.md) to have Heroku automatically deploy your app for each github PR that you create.

Optionally, See the [setting up a Custom Domain Guide](https://github.com/Lambda-School-Labs/gitbook-labs-guides/tree/f514baf6b1b0c2764cc2bce1739043d8ef763b96/heroku/heroku/heroku-custom-domain/README.md) to make sure that your API doesn't have the ugly `herokuapp` in it's URL.



## Heroku Networking

By default, Heroku creates an endpoint for your application like this:

* `https://bridges-a-api.herokuapp.com/`

This is okay, but if you want to use your custom product domain \(e.g. `a-api.bridgestoprosperity.dev`\) for your API, you can do this using Route 53.

1. In your Heroku application settings, click Add Domain
2. Your domain name will be a subdomain of your product domain, following the [naming standards](https://docs.labs.lambdaschool.com/standards/infrastructure/dns#dns-200-product-subdomains). For example, if your product domain is `bridgestoprosperity.dev` and your team letter is 'a', your API domain will be `a-api.bridgestoprosperity.dev`
3. Heroku will now issue you a specially generated domain to link traffic to your API subdomain
4. Open Route 53 in your AWS account
5. Open the hosted zone for your product
6. Click Create Record
7. Simple Routing
8. Define simple record
   * Record name: Your API domain \(e.g. `a-api)`
   * Route traffic to: IP address or another value
   * Value: The generated name from Heroku \(e.g. `concentric-turtle-7byvtq3pnb7n316b8zeu6peq.herokudns.com`\)
   * Record type: CNAME
9. Define simple record
10. Create records
11. Now you may need to wait a while for the internet DNS system to catch up
12. But once it does, you can now hit your Heroku app using `a-api.bridgestoprosperity.dev`
13. Done!

## What's Next <a id="whats-next"></a>

If you haven't already setup Review Apps then head over to the [guide](https://github.com/Lambda-School-Labs/gitbook-labs-guides/tree/f514baf6b1b0c2764cc2bce1739043d8ef763b96/heroku/heroku/review-apps/README.md) for more info



## Heroku Pipelines

Heroku is an amazing hosting platform for any project. Today, I spun up an app to show you how easy it is to set up a Heroku pipeline connected to a GitHub repository and have your project, front or back end, deployed in minutes with a wonderful staging environment set up.

Having a good staging environment set up can save you from accidentally running production. Trust me, I've been there. Thankfully you don't have to be a tech wizard to set up your project the right way. Setting up a pipeline for your project is as easy as hosting it. So, without further ado, let's dig in.

## Technologies Discussed <a id="technologies-discussed"></a>

* ​[Heroku Pipeline](https://devcenter.heroku.com/articles/pipelines)​
* ​[GitHub](https://www.github.com/)​

## References <a id="references"></a>

In addition to the links above, you can watch a [full video walk through here.](https://youtu.be/nlBBAdkUEO4).

**Step 1**

Heroku uses `npm start` to deploy your JavaScript projects. You can change and edit your Heroku dynos \(the thing that runs `npm start` on your project\) if you want... for money!for money

![](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fmedia.giphy.com%2Fmedia%2FFWfURU6rf4hAk%2Fgiphy.gif&f=1&nofb=1)

React projects are usually good to go out of the box. For back end projects you want to be passing your port number as an env variable so heroku can serve it on it's own port.

```text
app.listen(process.env.PORT || "4000", () => {  console.log("Running on ${process.env.PORT || "4000"}!`)}
```

One last tip for making sure you have a successful hosting experience is to make sure you have either a package-lock.json or a yarn.lock, but never both. When you npm install packages it creates a package-lock.json and when you yarn install you get a yarn.lock. If you have both files then heroku won't know what to do and freak out.freaking out

![](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fs18670.pcdn.co%2Fwp-content%2Fuploads%2Fbreathing-in-and-out.gif&f=1&nofb=1)

One solution that can be particularly useful when working in a group project is adding the one your not going to be using to your .gitignore. So if you are using yarn, add `package-lock.json` to your .gitignore and if you're using npm, add `yarn.lock`. Once all of those things and good to go, your ready to make the magic happen!magic

![](https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2F25.media.tumblr.com%2Ftumblr_m3gzxnu8XZ1r4xouyo1_250.gif&f=1&nofb=1)

**Step 2**

We are going to go to our heroku dashboard, where we can see all of our projects and click on new &gt; create new pipeline.create new pipeline

![](https://dev-to-uploads.s3.amazonaws.com/i/6usjrmhwn2h7r7yctfto.png)

Then we can give our pipeline a name and connect it to our repository. In my case, I'm going to choose the repository I created named `next-app`. Once you have done that, we can click on `Create pipeline`.set up pipeline

![](https://dev-to-uploads.s3.amazonaws.com/i/7a89ce5qj6a4duspkn8m.png)

Once you have created your pipeline, you will see a page with three sections: review apps, staging, production.pipeline

![](https://dev-to-uploads.s3.amazonaws.com/i/e74f3a54zx7mpy8vpoey.png)

In the staging section, click `Add app` then `Create new app...`.create staging app

![](https://dev-to-uploads.s3.amazonaws.com/i/d8nnlxmuqcl1al3gqrig.png)

Name you staging app. I named mine `next-app-stage`. You're going to have multiple URLs in your staging to production set up, so it's good to reflect that in how you name them. Once you have your app named and have the appropriate region selected \(I live in USA, so I keep it default\), click on `Create app` at the bottom. Now we can see our `next-app-stage` app hanging out in the stage tab. Let's click on that app. Once we are viewing that app we just created, we can click on the deploy tag and see that Heroku has already taken the liberty of connecting our repository to the app.deploy tab

![](https://dev-to-uploads.s3.amazonaws.com/i/lbfomqxuhbutpy47uvqe.png)

**Step 3**

Now if our project has any env variables we want to set those fist. Click on `settings` &gt; `Reveal config vars` to do so. My project does not have any env variables to add, so I'm just going to scroll down and click `Enable Automatic Deploys` then on `Deploy Branch`. Mine is set up to master branch, which is perfect.deployed app

![](https://dev-to-uploads.s3.amazonaws.com/i/83lechbrsd0e5vtdvui3.png)

My app was successfully deployed on the first go, I can click on the `view` button and see that my next app is up and running! 🎉next staging app

![](https://dev-to-uploads.s3.amazonaws.com/i/vzvw5bo3ysqffyg1tmvx.png)

Sweet! So far, so good. Now, since everything looks great, we can create our production app and push our changes to production. Woo hoo!

We can go back to our pipeline, click `Add app` and then `Create new app...` on the production tab. This time I'm going to name my app `next-app-prod` \(only because `next-app` wasn't available, go figure\) and then `Create App`.production pipeline added

![](https://dev-to-uploads.s3.amazonaws.com/i/x6rz1snnlzcnsqu3mo7z.png)

Since everything looked good on our staging app, we are going to go ahead and click the `Promote to production` button and then `Promote`. Changes should be promoted very quickly and then we can click on `Open app` on our production app we just created and see our site.production website

![](https://dev-to-uploads.s3.amazonaws.com/i/5fh7rpe0tvpqdnirpf24.png)

## Conclusion <a id="conclusion"></a>

We did it! Notice the URL here. This is our production URL now. If you bought a custom domain, you want to go into the settings tab in your production app and you can manage your domain name from there. If you have bought a secure domain with SLL \(which you totally should\) you will have to upgrade you subscript from free to hobby \($7 bucks a month\) for heroku to manage your SLL cert for you. Which is totally worth it in my opinion. Another amazing feature the pipeline has is that it's already set up so that if you make any pull requests to the master branch it will create a preview for that pull request that you will be able to see in the `Review Apps` section of your pipeline, so you can check every branch before it gets merged to master. Once it gets pushed to master, it will build and redeploy your staging app. If everything still looks and works the way it should, all you have to do is promote it to production and you are ready to rock and roll!rock and roll

![](https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fmemecrunch.com%2Fmeme%2FAWGN%2Frock-and-roll%2Fimage.jpg&f=1&nofb=1)



## Heroku Review Apps

## Objective <a id="objective"></a>

The Review Apps Heroku Pipeline would allow one not to have to use the Heroku remote to push to the staging server on Heroku. Overall, this should allow one to increase workload capacity since the Review Apps Pipeline could cut out the learning curve of deploying to Heroku via the Heroku remote through the CLI.

Heroku deploys the HEAD commit of the branch that the associated Pull Request is created on. When the branch is updated Heroku redeploys to the connected repo on the Review Apps Pipeline with your latest commit.

In summary, this guide will help you have a better understanding of what Review Apps on Heroku does and how to set it up for your GitHub repo.

### Technologies Discussed <a id="technologies-discussed"></a>

* Heroku
* Review Apps Pipeline

### Setting Up Review Apps Steps <a id="setting-up-review-apps-steps"></a>

1.Create a Pipeline by going to your Heroku dashboard, going to `new`, clicking the dropdown, and clicking on `create new Pipeline`create new pipeline

![](https://tk-assets.lambdaschool.com/fbc62d5d-ea11-4976-bd98-c8294305f2fe_ScreenShot2020-05-07at3.43.16PM.png)

2.Make sure to add the repo you want to connect the Review Apps Pipeline toconnect repo to pipeline

![](https://tk-assets.lambdaschool.com/a6312cb5-6b39-42db-be84-724d05881acc_ScreenShot2020-05-07at3.48.55PM.png)

3.Once on the Pipeline Dashboard click `Enable Review Apps`enable review apps

![](https://tk-assets.lambdaschool.com/e148df1f-653b-4f43-a3ac-0317e233997a_ScreenShot2020-05-07at3.53.22PM.png)

4.Then config Reviews Apps with your preferred settings

* `Automatically create review apps for new PRs`
* `Destroy stale review apps automatically` - set to preferred time frame

config pipeline

![](https://tk-assets.lambdaschool.com/0f2e4a39-c47d-4a07-baaf-c19d12e68ff5_ScreenShot2020-05-07at3.57.09PM.png)

### References <a id="references"></a>

For more information about setting up Review Apps on Heroku click [here](https://devcenter.heroku.com/articles/github-integration-review-apps#configuration)

