# Environment Variables

## Environment Variables

Environment variables are used to configure your application to run in a specific environment. These environments are generally local development \(your laptop\), production \(a hosted server\), and other hosted servers related to non-production environments.

There should be a single set of environment variables for your application, with each environment simply defining different values for those variables.

![https://www.lucidchart.com/publicSegments/view/9df797cf-e1fb-4ff4-9d82-b2136344f405/image.png](https://www.lucidchart.com/publicSegments/view/9df797cf-e1fb-4ff4-9d82-b2136344f405/image.png)

One set of environment variables, different values for each environment.

{% hint style="success" %}
You'll need to set up your environment variables in order to run your applications and develop locally.
{% endhint %}

{% embed url="https://youtu.be/UsAH3dLkvu4" caption="" %}

For more information about security and protecting your secrets, [please see our entry in the Labs Guides.](https://docs.labs.lambdaschool.com/home/#please-read-this-carefully)

### Things not to do

{% hint style="danger" %}
**Checking in files like your .env or secrets file to git and GitHub is a major security flaw**, and there are some secrets and keys you'll use in Labs that will be flagged automatically by bots scanning for such incidents. If you check in secrets to version control during Labs, expect to have to work with your engineering manager to scrub them from your git history!
{% endhint %}

### Anti-pattern \#1

Having your application try to figure out which environment variables to use depending on the value of another environment variable.

```text
import axios from "axios";

axios.defaults.baseURL = (function() {
  switch (process.env.REACT_APP_ENV) {
    case "development":
      return process.env.REACT_APP_LOCAL_HOST;
    case "staging":
      return process.env.REACT_APP_STAGING_URL;
    case "production":
      return process.env.REACT_APP_PRODUCTION_URL;
    default:
      return process.env.REACT_APP_LOCAL_HOST;
  }
})();
```

There should only be one variable for the base URL, something like REACT\_APP\_AXIOS\_BASE\_URL. The value of this environment variable will be set to a value that depends on the environment where the app is running.

The environment variable REACT\_APP\_ENV probably shouldn't exist, as in general, the app doesn't need to know what environment it's running in, it just needs to know the values of the variables it requires to run.

{% hint style="warning" %}
Why? Because this makes your application confusing to deploy and manage. Having an extra layer of environment settings doubles the chances that something will go wrong. Keep it simple!

Plus, you almost never want your application to behave differently depending on which environment it's in. If it does, how will you be sure that it'll behave properly in production?
{% endhint %}

