# Amplify-DNS

## Amplify DNS

### Configuring your subdomain

When your application is deployed to Amplify, you'll get an automatically generated URL that you can use to open the site in your browser. This is handy for doing a quick test, but not very useful otherwise. You want to get a proper domain, like `https://c.bridgestoprosperity.dev`

The basic flow for hooking a proper domain name up to your application is as follows:

1. Click 'Domain Management'
2. Click 'Add Domain'
3. You should see your product domain in the dropdown when you search for domain.
   * If not, please contact your APL.
4. Choose your product domain
5. Add the front-end subdomain per the Labs Engineering Standards
   * For example `c.bridgestoprosperity.dev`
6. Click 'Configure Domain'
7. Press 'Remove' next to the `www` subdomain line
8. Uncheck the 'Setup redirect from...\` option
9. Save

{% hint style="info" %}
Monitor the progress and speak with your APL if domain activation fails
{% endhint %}

### How it works

Behind the scenes, AWS Amplify orchestrates several different AWS services to build, deploy and manage your application.

![](https://app.lucidchart.com/publicSegments/view/85a071bc-1af9-4cd4-aafc-535a73d90c4d/image.png)

