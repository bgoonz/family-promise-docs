# AWS-Networking

## AWS Networking

{% hint style="warning" %}
Please be sure to review, bookmark and follow all the AWS related standards in the [Labs Engineering Standards](https://docs.labs.lambdaschool.com/standards/infrastructure/aws).
{% endhint %}

{% hint style="info" %}
Only APLs will have permissions to modify AWS network settings for a product account.
{% endhint %}

### Overview

General network setup for an AWS Product Account requires:

* A product domain
* An AWS Hosted Zone to handle DNS requests for the domain
* An SSL Certificate to enable SSL protection

### The Product Domain

Each Product will have one and only one domain that will be used for all network traffic to all endpoints in all projects. Please refer to the [Labs Engineering Standards](https://docs.labs.lambdaschool.com/standards/) for naming details.

{% hint style="info" %}
The product Hosted Zone must be created _before_ you can register the product domain name. This is because the name servers in the hosted zone _must_ be listed in the domain registration.

If these don't match, DNS doesn't work.

However, domain registrations can always be updated by an engineering manager should they change for some reason.
{% endhint %}

### Product Hosted Zone

An [AWS Hosted Zone](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/hosted-zones-working-with.html) is a DNS resource for controlling name resolution for a domain. Each AWS Product Account will have a hosted zone setup to handle name requests for the product domain.

#### Setup Hosted Zone

1. Navigate to the Route 53 service in the product account
2. Click 'Hosted Zones' on the menu to see the list of hosted zones
3. You should see _one_ hosted zone with a domain name matching your product domain name
4. If not, you can click 'Create Hosted Zone'
   1. The domain name is your product domain name
   2. Public Hosted Zone
   3. No tags required
   4. Click create

{% hint style="info" %}
When you create a new Hosted Zone in Route 53, AWS will assign a set of 4 name servers. You'll need to provide these name servers to your Engineering Manager so they can configure them in the domain registration record via our domain registrar.
{% endhint %}

{% hint style="info" %}
You'll need to occasionally make modifications to your hosted zone records, you'll find those instructions embedded in these guides under specific services, such as Elastic Beanstalk.
{% endhint %}

### **Product SSL Certificate**

Every internet-facing product should be protected using an SSL certificate. You'll use the AWS Certificate Manager to create this certificate, which can then be used with various services.

1. Navigate to the Certificate Manager service
2. 'Request a Certificate'
3. 'Request a public certificate'
4. Ensure these 4 names are listed on the certificate:
   1. The root domain \(e.g. `ecosoap.dev`\)
   2. All first-level subdomains \(e.g. `*.ecosoap.dev`\)
   3. All subdomains under `api` \(e.g. `*.api.ecosoap.dev`\)
   4. All subdomains under `ds` \(e.g. `*.ds.ecosoap.dev`\)
5. Click Next
6. Choose 'DNS Validation'
7. No tags are required
8. Click 'Review' then 'Confirm and Request'
9. For each of the names on the certificate, click the triangle and then click the button to add the entry to the hosted zone.
10. After some time, around 10 minutes, the certificate should be fully validated and ready to use.

{% hint style="info" %}
You'll use this certificate as part of other services. You'll find those instructions embedded in these guides under specific services, such as Elastic Beanstalk.
{% endhint %}

