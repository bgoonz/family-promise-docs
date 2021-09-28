# DNS

### \(DNS-100\) Product Domain <a id="dns-100-product-domain"></a>

Each product will have a single registered domain that will be used for all endpoints in all services and for all projects.

* Domain name registration for products will be handled by Labs Engineering Managers
* Nameservers will be provided by an AWS Route 53 Hosted Zone
* Naming Standard
  * Alphanumeric characters only
  * Use the `dev` TLD only
  * Examples:
    * `bridgestoprosperity.dev`
    * `ecosoap.dev`

Rationale:

* DNS is the root of many network operations and having a consistent naming convention across our products will help manage the complexity.

Alternatives:

* None

Exceptions:

* None

### \(DNS-200\) Product Subdomains <a id="dns-200-product-subdomains"></a>

Subdomains should be used for various endpoints of a product: e.g. DS API, Web Front-end, etc.

* Naming
  * All lowercase
  * Alphanumeric characters only
  * Web Frontend
    * Use the format: `<team letter>.<product domain>`
      * `c.bridgestoprosperity.dev`
      * `a.ecosoap.dev`
  * Web API
    * Use the format: `<team letter>-api.<product domain>`
      * Examples:
        * `c-api.bridgestoprosperity.dev`
        * `a-api.ecosoap.dev`
  * Data Science API:
    * Use the format: `<team letter>-ds.<product domain>`
      * `c-ds.bridgestoprosperity.dev`
      * `a-ds.ecosoap.dev`

Rationale:

* DNS is the root of many network operations and having a consistent naming convention across our products will help manage the complexity.

Alternatives:

* None

Exceptions:

* None

[  
](https://docs.labs.lambdaschool.com/standards/platforms-and-services/data-persistence)

