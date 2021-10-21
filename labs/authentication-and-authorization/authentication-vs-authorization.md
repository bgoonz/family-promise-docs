# Authentication VS Authorization

What's the difference between authentication and authorization? **Authentication** confirms that users are who they say they are. **Authorization** gives those users permission to access a resource.

While authentication and authorization might sound similar, they are distinct security processes in the world of identity and access management (IAM).

### What Is Authentication? <a href="what-is-authentication-0" id="what-is-authentication-0"></a>

Authentication is the act of validating that users are whom they claim to be. This is the first step in any security process.&#x20;

Complete an authentication process with:

* **Passwords. **Usernames and passwords** **are the most common [authentication factors](https://www.okta.com/products/adaptive-multi-factor-authentication/). If a user enters the correct data, the system assumes the identity is valid and grants access.
* [**One-time pins**](https://www.okta.com/blog/2020/06/what-is-a-one-time-password-otp/)**.** Grant access for only one session or transaction.
* **Authentication apps. **Generate security codes via an outside party that grants access.
* [**Biometrics**](https://www.okta.com/blog/2020/07/biometric-authentication/)**. **A user presents a fingerprint or eye scan to gain access to the system.&#x20;

In some instances, systems require the successful verification of more than one factor before granting access. This multi-factor authentication (MFA) requirement is often deployed to increase security beyond what passwords alone can provide.

### What Is Authorization? <a href="what-is-authorization-1" id="what-is-authorization-1"></a>

Authorization in system security is the process of giving the user permission to access a specific resource or function. This term is often used interchangeably with access control or client privilege.

Giving someone permission to download a particular file on a server or providing individual users with administrative access to an application are good examples of authorization.

In secure environments, authorization must always follow authentication. Users should first prove that their identities are genuine before an organization’s administrators grant them access to the requested resources.

![Authentication vs Authorization](https://www.okta.com/sites/default/files/styles/1640w\_scaled/public/media/image/2020-10/Authentication\_vs\_Authorization.png?itok=uBFRCfww)

&#x20;

### Authentication vs. Authorization <a href="authentication-vs-authorization-2" id="authentication-vs-authorization-2"></a>

Despite the similar-sounding terms, authentication and authorization are separate steps in the login process. Understanding the difference between the two is key to successfully implementing an IAM solution.

Let's use an analogy to outline the differences.

Consider a person walking up to a locked door to provide care to a pet while the family is away on vacation. That person needs:

* **Authentication**, in the form of a key. The lock on the door only grants access to someone with the correct key in much the same way that a system only grants access to users who have the correct credentials.
* **Authorization, **in the form of permissions. Once inside, the person has the authorization to access the kitchen and open the cupboard that holds the pet food. The person may not have permission to go into the bedroom for a quick nap.&#x20;

Authentication and authorization work together in this example. A pet sitter has the right to enter the house (authentication), and once there, they have access to certain areas (authorization).

|                                   |                                                       |                                               |
| --------------------------------- | ----------------------------------------------------- | --------------------------------------------- |
|                                   | **Authentication**                                    | **Authorization**                             |
| **What does it do?**              | Verifies credentials                                  | Grants or denies permissions                  |
| **How does it work?**             | Through passwords, biometrics, one-time pins, or apps | Through settings maintained by security teams |
| **Is it visible to the user?**    | Yes                                                   | No                                            |
| **It is changeable by the user?** | Partially                                             | No                                            |
| **How does data move?**           | Through ID tokens                                     | Through access tokens                         |

&#x20;

Systems implement these concepts in the same way, so it’s crucial that IAM administrators understand how to utilize both:

* **Authentication. **Let every staff member access your workplace systems if they provide the right credentials in response to your chosen authentication requirements.
* **Authorization. **Grant permission to department-specific files, and reserve access to confidential data, such as financial information, as needed. Ensure that employees have access to the files they need to do their jobs.&#x20;

Understand the difference between authentication and authorization, and implement IAM solutions that have strong support for both. You will protect your organization against data breaches and enable your workforce to be more productive.

### Granting Permissions with Okta <a href="granting-permissions-with-okta-3" id="granting-permissions-with-okta-3"></a>

Okta Lifecycle Management gives you an at-a-glance view of user permissions, meaning you can easily grant and revoke access to your systems and tools as needed. Meanwhile, Okta Adaptive MFA lets you safeguard your infrastructure behind your choice of authentication factors.&#x20;

For example, make production orders accessible only to certain users who may then have to authenticate using both their company credentials and voice recognition.&#x20;

The opportunities to streamline IAM in your organization are endless. Find out how Okta can keep you, your employees, and your enterprise safe.
