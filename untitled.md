# Account Basics

{% hint style="warning" %}
[Please read this first!!](https://docs.labs.lambdaschool.com/guides/always-read-this-first)

Please be sure to review, bookmark and follow all the AWS related standards in the [Labs Engineering Standards](https://docs.labs.lambdaschool.com/standards/infrastructure/aws).

Most important! Please note that all infrastructure must be created in the `us-east-1` region in AWS. Any infrastructure found outside that region will need to be moved immediately or will be automatically de-provisioned. Thank you!
{% endhint %}

## Organizations

Labs manages a set of AWS accounts using the [AWS Organizations](https://aws.amazon.com/organizations/) service. This allows us to create a structure and better manage dozens of separate accounts.

* All student [AWS Product Accounts](../) are located in the `Students` Organizational Unit \(OU\).
* Only Engineering Managers can create new AWS Product Accounts.
* Labs projects must never use AWS Accounts not managed by Lambda School Labs.

You can see a list of accounts [here](https://airtable.com/shrQHnZkU56jOLZe1/tbliohq0z8d3PQj4g). Note, this list is not automatically updated, if you don't see your account, contact your engineering manager! Thanks.

## IAM Users

Each member of a student team will have an associated IAM User. This IAM User will be created and managed by the APL for the Product.

* Only APLs have the ability to provision and manage IAM Users
* IAM Users have the permissions required to [create AWS Access keys](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html#Using_CreateAccessKey) for their own use

## IAM Groups

Each account will have a group named `Students` that all student IAM Users will be assigned to. This group has only specific permissions required for their project, adhering to the [Principle of Least Privilege](https://en.wikipedia.org/wiki/Principle_of_least_privilege).

## Labs Bot

Labs APLs will have access to a Slack Bot that will allow them to manage user accounts for student teams.

### Adding Users

Labs Bot can create IAM users. These users should be created following the [naming format for IAM Users in the Engineering Standards](https://docs.labs.lambdaschool.com/standards/infrastructure/aws#aw-200-resource-naming).

{% hint style="info" %}
APLs can run `/labsbot` in Slack to work with the Labs Bot
{% endhint %}

* Example: jane.doe@lambdaschool.com - Jane Doe

