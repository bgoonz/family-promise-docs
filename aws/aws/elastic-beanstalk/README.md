# Elastic Beanstalk

## Elastic Beanstalk

### Overview

[Elastic Beanstalk](https://aws.amazon.com/elasticbeanstalk/) is a [PaaS](https://en.wikipedia.org/wiki/Platform_as_a_service) service that is used in Labs to host Data Science related APIs.

### FAQ

**Why does my Elastic Beanstalk application fail with permission denied, mkdir?**

This is caused by the following:

* AWS Beanstalk servers are based on Amazon Linux, now you know
* The node-gyp module has native code, so needs to be compiled, no big deal
* There is no node-gyp binary distribution for Amazon Linux, it would be nice
* NPM tries to build the package on the Beanstalk server, which is normal
* Part of the build process runs as a non-root user and tries to write to /tmp which is owned by root, seems odd, but okay
* This mkdir call fails with permission denied and the build fails, which is the correct error

There are lots of different solutions on the world wide web, but only one seems to work consistently and is only mildly intrusive:

* Go to your Elastic Beanstalk environment
* Click 'Configuration' then click 'Software'
* At the bottom of this form, add this environment variable:
  * NPM\_CONFIG\_UNSAFE\_PERM=true

    ![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/497d8b5c-39f1-4a20-adfc-cc2b954b4b15/Untitled.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/497d8b5c-39f1-4a20-adfc-cc2b954b4b15/Untitled.png)

  * Click 'Apply'
  * This should trigger a rebuild, which should get you past the issue

**How do I resolve 413 Request Entity Too Large?**

TBD

**How do I deploy my Docker container to Beanstalk?**

TBD

### Glossary

#### Application

An Application in AWS Elastic Beanstalk is simply a collection of Elastic Beanstalk environments. It's simply a mechanism to organize Elastic Beanstalk environments.

In Labs, we use Elastic Beanstalk applications to group environments for a specific cohort. See the [Labs Engineering Standards](https://docs.labs.lambdaschool.com/standards/infrastructure/aws#aw-200-resource-naming) for instructions on how to name an Elastic Beanstalk Application.

#### Environment

An Environment in AWS Elastic Beanstalk is a collection of AWS resources that are managed by the Elastic Beanstalk service.

In Labs, a project team will each have a dedicated environment to host the resources they need for their API. See the [Labs Engineering Standards](https://docs.labs.lambdaschool.com/standards/infrastructure/aws#aw-200-resource-naming) for instructions on how to name an Elastic Beanstalk Environment.

