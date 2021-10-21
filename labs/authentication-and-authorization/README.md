# Authentication and Authorization

## Authentication and Authorization

### Authentication vs. Authorization

**Authentication** is when we provide our user credentials to a login form. Typically in modern auth flows, you give a username and password, and your API will verify that you are who you say you are based on your credentials provided. This step verifies users in your system.

**Authorization** is when you grant access/permissions to portions of your website to individuals who've previously been authenticated. This usually requires some form of user management.

In this module, we'll go over how we approach both authentication and authorization in Labs using Okta.







## Okta

### **What is Okta?**

[Okta (Links to an external site.)](https://www.okta.com) is an identity management service that's used in Labs to provide centralized authentication for Labs applications.

We use a centralized identity management service because it's typically the way applications are authenticated in the industry. This gives you practice using centralized identity management technologies like [OAuth (Links to an external site.)](https://developer.okta.com/blog/2017/06/21/what-the-heck-is-oauth) and [OIDC (Links to an external site.)](https://openid.net/connect/faq/).

We use Okta specifically because it's an [industry leader (Links to an external site.)](https://www.okta.com/resources/access-management-leader-gartner-magic-quadrant) and has high-quality support and documentation.

### Okta's Place in Your Architecture

In Labs, we'll use Okta as our **identity provider** (IDP), leveraging its existing user management system to store and manage identities. Watch this overview to understand how Okta works at a high level for authentication and authorization:

&#x20;

&#x20;

We end up with the following high-level architecture diagram:

&#x20;

![ScreenShot2021-08-24at2.47.44PM.png](https://lambdaschool.instructure.com/courses/1552/files/388784/preview)

&#x20;

### Using Okta in Your Project

Here's an overview of how Okta works and how to use it in your Labs project:

&#x20;

&#x20;

In order to work with Okta within our Frontend and Backend applications, you'll need two environment variables:

* The client ID for your product (provided by your Release Manager)
* The issuer URI ([`https://auth.lambdalabs.dev/oauth2/default` (Links to an external site.)](https://auth.lambdalabs.dev/oauth2/default))

For more on using Okta in Labs, consult [this entry in the Labs Guides (Links to an external site.)](https://docs.labs.lambdaschool.com/guides/okta/okta-basics).

### Further Reading

* **Okta:** [Authentication vs. Authorization (Links to an external site.)](https://www.okta.com/identity-101/authentication-vs-authorization/)

Okta BasicsCurrently only Labs Managers have admin access to Okta administration. If you have Okta issues, please reach out to your Engineering Manager.​[Okta](https://www.okta.com) is an identity management service that's used in Labs to provide centralized authentication for Labs applications.We use a centralized identity management service because it is typically the way applications are authenticated in the industry. This gives our students practice using centralized identity management technologies like [OAuth](https://developer.okta.com/blog/2017/06/21/what-the-heck-is-oauth) and [OIDC](https://openid.net/connect/faq/).We use Okta specifically because it is an [industry leader](https://www.okta.com/resources/access-management-leader-gartner-magic-quadrant) and has high-quality support and documentation.Here is a quick walk thru of okta and how it is used in our Labs projects.

## The Okta Account <a href="the-okta-account" id="the-okta-account"></a>

Okta provides centralized identity management. This means that you can have a single set of identities that can be used across many different applications. If you use Google services, you can see this in action as you log in to Google once but can move between Google apps (Mail, Calendar, Sheets, etc.) without having to log in each time.We use Okta the same way. There is a single Labs Okta account that has a set of identities that can access all Labs applications. These identities are test users that can be used by teams for testing their applications without having to constantly create new identities.Since Labs applications are always under development, it's very handy to have a set of test identities readily available to test various aspects of your application.Labs applications should always authenticate using the alias (auth.lambdalabs.dev), though, for reference, the Labs Organization URL is: [https://dev-625244.okta.com](https://dev-625244.okta.comdashboard)​

### Logging In <a href="logging-in" id="logging-in"></a>

As an APL, you'll have access to log in to the Labs Okta account to perform various tasks. Before Labs, you'll receive your login credentials and can use the following link to log in:​[Labs - Sign In](https://auth.lambdalabs.dev)​If you can't login, please contact your engineering manager.

#### Test Users <a href="test-users" id="test-users"></a>

A set of test users has been created that teams can use for authentication. These users follow a simple naming convention to make it easy for projects to authenticated.There are 8 test users, each one using a 3-digit sequence for username and password:UsernamePasswordMailboxllama001@maildrop.ccTest001Test​[https://maildrop.cc/inbox/llama001](https://maildrop.cc/inbox/llama001)​llama002@maildrop.ccTest002Test​[https://maildrop.cc/inbox/llama002](https://maildrop.cc/inbox/llama002)​llama003@maildrop.ccTest003Test​[https://maildrop.cc/inbox/llama003](https://maildrop.cc/inbox/llama003)​llama004@maildrop.ccTest004Test​[https://maildrop.cc/inbox/llama004](https://maildrop.cc/inbox/llama004)​llama005@maildrop.ccTest005Test​[https://maildrop.cc/inbox/llama005](https://maildrop.cc/inbox/llama005)​llama006@maildrop.ccTest006Test​[https://maildrop.cc/inbox/llama006](https://maildrop.cc/inbox/llama005)​llama007@maildrop.ccTest007Test​[https://maildrop.cc/inbox/llama007](https://maildrop.cc/inbox/llama005)​llama008@maildrop.ccTest008Test​[https://maildrop.cc/inbox/llama008](https://maildrop.cc/inbox/llama005)​Since the test users are using [maildrop.cc](https://maildrop.cc) for email, you can easily check their inbox if they are meant to receive email notifications from applications.Please take care never to modify these users in any way! These users are shared across Labs projects, so editing a user can affect other projects.

## Administrative Tasks <a href="administrative-tasks" id="administrative-tasks"></a>

The following are administrative tasks that you'll need to perform in Okta to support Labs teams.

### Retrieve Product Client ID <a href="retrieve-product-client-id" id="retrieve-product-client-id"></a>

There is a single Client ID for each product that must be supplied to Labs project teams in order for them to enable authentication. Each product will be set up as an Okta Application. The Client ID can be found using the Admin interface, by clicking on the Applications Tab.Products have one client id that is shared among all active projects working on that product. Client IDs should not be shared across products.

![](https://files.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-MFfkpZnSSKK09iKBtrP%2F-MGESC8nTVOTY4CwdraH%2F-MGEVPGS7FUaHy9HAoeR%2Fimage.png?alt=media\&token=a6dc3d4f-174a-49f7-9510-4308b7a92c10)

### Issuer URI <a href="issuer-uri" id="issuer-uri"></a>

The Issuer URI is also required for Labs projects to correctly configure authentication. For Labs projects, this value will always be: [https://auth.lambdalabs.dev/oauth2/default](https://auth.lambdalabs.dev/oauth2/default)​

