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



