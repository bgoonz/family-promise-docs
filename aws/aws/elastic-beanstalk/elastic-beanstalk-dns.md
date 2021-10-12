# Elastic Beanstalk DNS

## Elastic Beanstalk DNS

### Configuring your subdomain

When your application is deployed to Elastic Beanstalk, you'll get an automatically generated URL that you can use to connect to your API. This is handy for doing a quick test, but not very useful otherwise. You want to get a proper domain, like `c-ds.bridgestoprosperity.dev`

This name follows our naming standards and is easier to remember and to share.

First, open the AWS Route 53 console at [https://console.aws.amazon.com/route53/](https://console.aws.amazon.com/route53/). Route 53 is Amazon's [Domain Name System (DNS)](https://simple.wikipedia.org/wiki/Domain_Name_System) web service.

Then follow these instructions:

1. Click 'Create Record'
2. Use 'Simple Routing'
3. Click Next
4. Click 'Define Simple Record'
5. Your subdomain should follow the naming standards set in the [Labs Engineering Standards](https://en.wikipedia.org/wiki/List_of_TCP_and_UDP_port_numbers#Well-known_ports)
   * Example: `c-ds.bridgestoprosperity.dev`
6. Route traffic to 'Alias to Elastic Beanstalk environment'
7. Region: `us-east-1`
   * You _did_ create your environment in `us-east-1` right?
8. Record Type: [A](https://en.wikipedia.org/wiki/List_of_DNS_record_types)
9. Click 'Define Simple Record'
10. Click 'Create Records'

{% hint style="info" %}
Your A record will now have been created and you can start using it to access your API endpoint. For example: [http://c-ds.bridgestoprosperity.dev/](http://c-ds.bridgestoprosperity.dev)
{% endhint %}

### Configuring SSL Termination

The above subdomain configuration simply gives your API an easier to read name, but does _not_ enable SSL protection, which is essential for security.

The basic flow for hooking a proper domain name up to your environment is as follows:

1. Open your environment in the AWS console
2. Click 'Configuration'
3. Click 'Edit' in the 'Load Balancer' section
4. Click 'Add Listener' to add a new endpoint for your API
   1. Listener Port: 443
      * This is the [standard](https://en.wikipedia.org/wiki/List_of_TCP_and_UDP_port_numbers#Well-known_ports) port for HTTPS traffic
   2. Listener Protocol: HTTPS
      * This means the listener will encrypt traffic
   3. Instance Port: 80
      * This is the port your instances are listening on
   4. Instance Protocol: HTTP
      * The protocol your instances are using
   5. SSL Certificate
      * You should see a certificate with your domain in this list, if not, contact your APL
   6. Click 'Add'
   7. **Scroll to the bottom and click 'Apply'**
      * **Don't forget this step!!**

### How it works...

When a machine (or human) wants to connect to your API, they first need to find the IP address of the endpoint where your API is hosted.

This is step one, where the caller (aka client) asks the name servers in your hosted zone to translate your domain name (e.g. c-ds.ecosoap.dev) to a proper IP address.

Once the client has the IP address, it will connect to your API, which is hosted in your Elastic Beanstalk environment. We've made this connection secure by adding an SSL certificate to your load balancer and enabling HTTPS.

The client will then send encrypted traffic over the internet to your API. Then, the load balancer sends the traffic to your actual API instances, running on servers or in containers. Since your load balance and application instances are on the same private network (not on the internet) we don't need to keep the traffic encrypted, which adds cost and reduces performance.

The traffic is decrypted by the load-balancer and sent to your application as unencrypted HTTP traffic on port 80.
