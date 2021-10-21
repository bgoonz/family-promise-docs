# Rest Architecture

###

## Introduction

API Browser Quick Guide

**It can make your life easier** if you use some kind of **API browser application** to **explore the API** when diving into this documentation.

* We recommend to use the free [Postman](http://www.getpostman.com) browser plugin.
* For easy onboarding take a look at **our** [Explore the API using Postman](https://plonerestapi.readthedocs.io/en/latest/exploring.html#exploring-api-postman-onboarding) **Quick-Guide**.

A hypermedia API provides an entry point to the API, which contains hyperlinks the clients can follow. Just like a human user of a regular website, who knows the initial URL of a website and then follows hyperlinks to navigate through the site. This has the advantage that the client only needs to understand how to detect and follow links. The URLs (apart from the inital entry point) and other details of the API can change without breaking the client.

The entry point to the Plone RESTful API is the portal root. The client can ask for a [REST](https://plonerestapi.readthedocs.io/en/latest/glossary.html#term-rest) API response by setting the `'Accept'` HTTP header to `'application/json'`:

http

curl

httpie

python-requests

```
GET /plone HTTP/1.1
Accept: application/json
Authorization: Basic YWRtaW46c2VjcmV0
```

This uses so-called ‘content negotiation’

> * [More on Content Negotiation](https://plonerestapi.readthedocs.io/en/latest/content-negotiation.html)

The server will then respond with the portal root in the JSON format:

```
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@components": {
        "actions": {
            "@id": "http://localhost:55001/plone/@actions"
        },
        "breadcrumbs": {
            "@id": "http://localhost:55001/plone/@breadcrumbs"
        },
        "contextnavigation": {
            "@id": "http://localhost:55001/plone/@contextnavigation"
        },
        "navigation": {
            "@id": "http://localhost:55001/plone/@navigation"
        }
    },
    "@id": "http://localhost:55001/plone",
    "@type": "Plone Site",
    "blocks": {},
    "blocks_layout": {},
    "description": "",
    "id": "plone",
    "is_folderish": true,
    "items": [
        {
            "@id": "http://localhost:55001/plone/front-page",
            "@type": "Document",
            "description": "Congratulations! You have successfully installed Plone.",
            "review_state": "private",
            "title": "Welcome to Plone"
        }
    ],
    "items_total": 1,
    "parent": {},
    "title": "Plone site"
}
```

`@id` is a unique identifier for resources (IRIs). The `@id` property can be used to navigate through the web API by following the links.

`@type` sets the data type of a node or typed value

`items` is a list that contains all objects within that resource.

A client application can “follow” the links (by calling the @id property) to other resources. This allows to build a losely coupled client that does not break if some of the URLs change, only the entry point of the entire API (in our case the portal root) needs to be known in advance.

Another example, this time showing a request and response for a document. Click on the buttons below to show the different syntaxes for the request.

http

curl

httpie

python-requests

```
GET /plone/front-page HTTP/1.1
Accept: application/json
Authorization: Basic YWRtaW46c2VjcmV0
```

```
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@components": {
        "actions": {
            "@id": "http://localhost:55001/plone/front-page/@actions"
        },
        "breadcrumbs": {
            "@id": "http://localhost:55001/plone/front-page/@breadcrumbs"
        },
        "contextnavigation": {
            "@id": "http://localhost:55001/plone/front-page/@contextnavigation"
        },
        "navigation": {
            "@id": "http://localhost:55001/plone/front-page/@navigation"
        },
        "types": {
            "@id": "http://localhost:55001/plone/front-page/@types"
        },
        "workflow": {
            "@id": "http://localhost:55001/plone/front-page/@workflow"
        }
    },
    "@id": "http://localhost:55001/plone/front-page",
    "@type": "Document",
    "UID": "SomeUUID000000000000000000000001",
    "allow_discussion": false,
    "changeNote": "",
    "contributors": [],
    "created": "1995-07-31T13:45:00",
    "creators": [
        "test_user_1_"
    ],
    "description": "Congratulations! You have successfully installed Plone.",
    "effective": null,
    "exclude_from_nav": false,
    "expires": null,
    "id": "front-page",
    "is_folderish": false,
    "language": "",
    "layout": "document_view",
    "lock": {
        "locked": false,
        "stealable": true
    },
    "modified": "1995-07-31T17:30:00",
    "next_item": {},
    "parent": {
        "@id": "http://localhost:55001/plone",
        "@type": "Plone Site",
        "description": "",
        "title": "Plone site"
    },
    "previous_item": {},
    "relatedItems": [],
    "review_state": "private",
    "rights": "",
    "subjects": [],
    "table_of_contents": null,
    "text": {
        "content-type": "text/plain",
        "data": "<p>If you&#x27;re seeing this instead of the web site you were expecting, the owner of this web site has just installed Plone. Do not contact the Plone Team or the Plone mailing lists about this.</p>",
        "encoding": "utf-8"
    },
    "title": "Welcome to Plone",
    "version": "current",
    "versioning_enabled": true,
    "working_copy": null,
    "working_copy_of": null
}
```

And so on, see

> * [Representation of all standard Plone contenttypes](https://plonerestapi.readthedocs.io/en/latest/plone-content.html)



## Explore the API using Postman

To discover the API interactively, using [Postman](http://www.getpostman.com) is recommended.

Note

The Chrome-Extension version of Postman is deprecated and it is recommended to use the native app available instead.

### Configuration

To easily follow links returned by request based on the API,

* go to the menu under the  wrench icon on the top right
* choose Settings
* activate the option Retain headers on clicking on links by selecting ON:

![postman-retain-headers](https://plonerestapi.readthedocs.io/en/latest/\_images/postman\_retain\_headers.png)

This option makes sure, once a [HTTP-Header](https://plonerestapi.readthedocs.io/en/latest/glossary.html#term-http-header) is configured, it will be reused during following [requests](https://plonerestapi.readthedocs.io/en/latest/glossary.html#term-requests) , if these are initiated by clicking on links resulting from the initial [request](https://plonerestapi.readthedocs.io/en/latest/glossary.html#term-request). This way navigating the structure using the API becomes a snap.

The option Send anonymous usage data to Postman should be deactivated by setting to OFF.

### Usage

Choose the suitable [HTTP Verb](https://plonerestapi.readthedocs.io/en/latest/glossary.html#term-13) to be used for your request. This can be selected using the [Postman](http://www.getpostman.com) HTTP Verb -> GET drop-down menu.

Enter the [Object URL](https://plonerestapi.readthedocs.io/en/latest/glossary.html#term-object-url) of the object that should be the target of a request into the URL field right to the [HTTP Verb](https://plonerestapi.readthedocs.io/en/latest/glossary.html#term-13):

![postman-request](https://plonerestapi.readthedocs.io/en/latest/\_images/postman\_request.png)

Now set the appropriate HTTP headers.

* The [Authorization Header](https://plonerestapi.readthedocs.io/en/latest/glossary.html#term-authorization-header) for the authentication related to the right user
* The [Accept Header](https://plonerestapi.readthedocs.io/en/latest/glossary.html#term-accept-header) to initiate the right behaviour by the API related to this [Request](https://plonerestapi.readthedocs.io/en/latest/glossary.html#term-request).

***

To set the [Authorization Header](https://plonerestapi.readthedocs.io/en/latest/glossary.html#term-authorization-header), there is a reserved tab, that is responsible to generate the final [Header](https://plonerestapi.readthedocs.io/en/latest/glossary.html#term-header) based on the [authentication method](https://plonerestapi.readthedocs.io/en/latest/glossary.html#term-authentication-method) and username + password.

You have to select

* in the drop-down menu Basic Auth -> the term [Basic Auth](https://plonerestapi.readthedocs.io/en/latest/glossary.html#term-basic-auth) as the authentication method
* A valid existing user with appropriate permissions

After providing these parameters you can create the resulting [Authorization Header](https://plonerestapi.readthedocs.io/en/latest/glossary.html#term-authorization-header) and insert it into the prepared request by clicking on Preview Request.

![postman-basic-auth](https://plonerestapi.readthedocs.io/en/latest/\_images/postman\_basic\_auth.png)

***

Under the Headers tab you now need to insert in the [Accept Header](https://plonerestapi.readthedocs.io/en/latest/glossary.html#term-accept-header) application/json\` header as well:

![postman-headers](https://plonerestapi.readthedocs.io/en/latest/\_images/postman\_headers.png)

The request is now ready and can be send by clicking on Send button.

The [Response](https://plonerestapi.readthedocs.io/en/latest/glossary.html#term-response) of the server is now displayed below the [Request](https://plonerestapi.readthedocs.io/en/latest/glossary.html#term-request). You can easily follow the links on the `@id` attributes by clicking on them. For every link [Postman](http://www.getpostman.com) has prepared another request sharing the same headers that can be send again by licking on the Send button.

![postman-response](https://plonerestapi.readthedocs.io/en/latest/\_images/postman\_response.png)

Conclusion

You can now explore the whole stucture of your application easily via the API using _GET_ requests.





## Content Manipulation

plone.restapi does not only expose content objects via a RESTful API. The API consumer can create, read, update, and delete a content object. Those operations can be mapped to the HTTP verbs POST (Create), GET (Read), PUT (Update) and DELETE (Delete).

Manipulating resources across the network by using HTTP as an application protocol is one of core principles of the REST architectural pattern. This allows us to interact with a specific resource in a standardized way:

| Verb   | URL                   | Action                                    |
| ------ | --------------------- | ----------------------------------------- |
| POST   | /folder               | Creates a new document within the folder  |
| GET    | /folder/{document-id} | Request the current state of the document |
| PATCH  | /folder/{document-id} | Update the document details               |
| DELETE | /folder/{document-id} | Remove the document                       |

### Creating a Resource with POST

To create a new resource, we send a POST request to the resource container. If we want to create a new document within an existing folder, we send a POST request to that folder:

http

curl

httpie

python-requests

```
POST /plone/folder HTTP/1.1
Accept: application/json
Authorization: Basic YWRtaW46c2VjcmV0
Content-Type: application/json

{
    "@type": "Document",
    "title": "My Document"
}
```

By setting the ‘Accept’ header, we tell the server that we would like to receive the response in the ‘application/json’ representation format.

The ‘Content-Type’ header indicates that the body uses the ‘application/json’ format.

The request body contains the minimal necessary information needed to create a document (the type and the title). You could set other properties, like “description” here as well.

A special property during content creation is “UID”, as it requires the user to have the _Manage Portal_ permission to set it. Without the permission, the request will fail as Unauthorized.

#### Successful Response (201 Created)

If a resource has been created, the server responds with the [201 Created](https://plonerestapi.readthedocs.io/en/latest/http-status-codes.html#term-201-created) status code. The ‘Location’ header contains the URL of the newly created resource and the resource representation in the payload:

```
HTTP/1.1 201 Created
Content-Type: application/json
Location: http://localhost:55001/plone/folder/my-document

{
    "@components": {
        "actions": {
            "@id": "http://localhost:55001/plone/folder/my-document/@actions"
        },
        "breadcrumbs": {
            "@id": "http://localhost:55001/plone/folder/my-document/@breadcrumbs"
        },
        "contextnavigation": {
            "@id": "http://localhost:55001/plone/folder/my-document/@contextnavigation"
        },
        "navigation": {
            "@id": "http://localhost:55001/plone/folder/my-document/@navigation"
        },
        "types": {
            "@id": "http://localhost:55001/plone/folder/my-document/@types"
        },
        "workflow": {
            "@id": "http://localhost:55001/plone/folder/my-document/@workflow"
        }
    },
    "@id": "http://localhost:55001/plone/folder/my-document",
    "@type": "Document",
    "UID": "SomeUUID000000000000000000000005",
    "allow_discussion": false,
    "changeNote": "",
    "contributors": [],
    "created": "1995-07-31T13:45:00",
    "creators": [
        "admin"
    ],
    "description": "",
    "effective": null,
    "exclude_from_nav": false,
    "expires": null,
    "id": "my-document",
    "is_folderish": false,
    "language": "",
    "layout": "document_view",
    "lock": {
        "locked": false,
        "stealable": true
    },
    "modified": "1995-07-31T17:30:00",
    "next_item": {},
    "parent": {
        "@id": "http://localhost:55001/plone/folder",
        "@type": "Folder",
        "description": "This is a folder with two documents",
        "review_state": "private",
        "title": "My Folder"
    },
    "previous_item": {
        "@id": "http://localhost:55001/plone/folder/doc2",
        "@type": "Document",
        "description": "",
        "title": "A document within a folder"
    },
    "relatedItems": [],
    "review_state": "private",
    "rights": "",
    "subjects": [],
    "table_of_contents": null,
    "text": null,
    "title": "My Document",
    "version": "current",
    "versioning_enabled": true,
    "working_copy": null,
    "working_copy_of": null
}
```

#### Unsuccessful Response (400 Bad Request)

If the resource could not be created, for instance because the title was missing in the request, the server responds with [400 Bad Request](https://plonerestapi.readthedocs.io/en/latest/http-status-codes.html#term-400-bad-request):

```
HTTP/1.1 400 Bad Request
Content-Type: application/json

{
  'message': 'Required title field is missing'
}
```

The response body can contain information about why the request failed.

#### Unsuccessful Response (500 Internal Server Error)

If the server can not properly process a request, it responds with [500 Internal Server Error](https://plonerestapi.readthedocs.io/en/latest/http-status-codes.html#term-500-internal-server-error):

```
HTTP/1.1 500 Internal Server Error
Content-Type: application/json

{
  'message': 'Internal Server Error'
}
```

The response body can contain further information such as an error trace or a link to the documentation.

#### Possible POST Responses

Possible server reponses for a POST request are:

* [201 Created](https://plonerestapi.readthedocs.io/en/latest/http-status-codes.html#term-201-created) (Resource has been created successfully)
* [400 Bad Request](https://plonerestapi.readthedocs.io/en/latest/http-status-codes.html#term-400-bad-request) (malformed request to the service)
* [500 Internal Server Error](https://plonerestapi.readthedocs.io/en/latest/http-status-codes.html#term-500-internal-server-error) (server fault, can not recover internally)

#### POST Implementation

A pseudo-code example of the POST implementation on the server:

```
try:
    order = createOrder()
    if order == None:
        # Bad Request
        response.setStatus(400)
    else:
        # Created
        response.setStatus(201)
except:
    # Internal Server Error
    response.setStatus(500)
```

TODO: Link to the real implementation… \[

### Reading a Resource with GET

After a successful POST, we can access the resource by sending a GET request to the resource URL:

http

curl

httpie

python-requests

```
GET /plone/folder/my-document HTTP/1.1
Accept: application/json
Authorization: Basic YWRtaW46c2VjcmV0
```

#### Successful Response (200 OK)

If a resource has been retrieved successfully, the server responds with [200 OK](https://plonerestapi.readthedocs.io/en/latest/http-status-codes.html#term-200-ok):

```
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@components": {
        "actions": {
            "@id": "http://localhost:55001/plone/folder/my-document/@actions"
        },
        "breadcrumbs": {
            "@id": "http://localhost:55001/plone/folder/my-document/@breadcrumbs"
        },
        "contextnavigation": {
            "@id": "http://localhost:55001/plone/folder/my-document/@contextnavigation"
        },
        "navigation": {
            "@id": "http://localhost:55001/plone/folder/my-document/@navigation"
        },
        "types": {
            "@id": "http://localhost:55001/plone/folder/my-document/@types"
        },
        "workflow": {
            "@id": "http://localhost:55001/plone/folder/my-document/@workflow"
        }
    },
    "@id": "http://localhost:55001/plone/folder/my-document",
    "@type": "Document",
    "UID": "SomeUUID000000000000000000000005",
    "allow_discussion": false,
    "changeNote": "",
    "contributors": [],
    "created": "1995-07-31T13:45:00",
    "creators": [
        "admin"
    ],
    "description": "",
    "effective": null,
    "exclude_from_nav": false,
    "expires": null,
    "id": "my-document",
    "is_folderish": false,
    "language": "",
    "layout": "document_view",
    "lock": {
        "locked": false,
        "stealable": true
    },
    "modified": "1995-07-31T17:30:00",
    "next_item": {},
    "parent": {
        "@id": "http://localhost:55001/plone/folder",
        "@type": "Folder",
        "description": "This is a folder with two documents",
        "review_state": "private",
        "title": "My Folder"
    },
    "previous_item": {
        "@id": "http://localhost:55001/plone/folder/doc2",
        "@type": "Document",
        "description": "",
        "title": "A document within a folder"
    },
    "relatedItems": [],
    "review_state": "private",
    "rights": "",
    "subjects": [],
    "table_of_contents": null,
    "text": null,
    "title": "My Document",
    "version": "current",
    "versioning_enabled": true,
    "working_copy": null,
    "working_copy_of": null
}
```

For folderish types, their childrens are automatically included in the response as `items`. To disable the inclusion, add the GET parameter `include_items=false` to the URL.

By default only basic metadata is included. To include additional metadata, you can specify the names of the properties with the `metadata_fields` parameter. See also [Retrieving additional metadata](https://plonerestapi.readthedocs.io/en/latest/searching.html#retrieving-additional-metadata).

The following example additionaly retrieves the UID and Creator:

http

curl

httpie

python-requests

```
GET /plone/folder?metadata_fields=UID&metadata_fields=Creator HTTP/1.1
Accept: application/json
Authorization: Basic YWRtaW46c2VjcmV0
```

```
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@components": {
        "actions": {
            "@id": "http://localhost:55001/plone/folder/@actions"
        },
        "breadcrumbs": {
            "@id": "http://localhost:55001/plone/folder/@breadcrumbs"
        },
        "contextnavigation": {
            "@id": "http://localhost:55001/plone/folder/@contextnavigation"
        },
        "navigation": {
            "@id": "http://localhost:55001/plone/folder/@navigation"
        },
        "types": {
            "@id": "http://localhost:55001/plone/folder/@types"
        },
        "workflow": {
            "@id": "http://localhost:55001/plone/folder/@workflow"
        }
    },
    "@id": "http://localhost:55001/plone/folder",
    "@type": "Folder",
    "UID": "SomeUUID000000000000000000000002",
    "allow_discussion": false,
    "contributors": [],
    "created": "1995-07-31T13:45:00",
    "creators": [
        "test_user_1_"
    ],
    "description": "This is a folder with two documents",
    "effective": null,
    "exclude_from_nav": false,
    "expires": null,
    "id": "folder",
    "is_folderish": true,
    "items": [
        {
            "@id": "http://localhost:55001/plone/folder/doc1",
            "@type": "Document",
            "Creator": "test_user_1_",
            "UID": "SomeUUID000000000000000000000003",
            "description": "",
            "review_state": "private",
            "title": "A document within a folder"
        },
        {
            "@id": "http://localhost:55001/plone/folder/doc2",
            "@type": "Document",
            "Creator": "test_user_1_",
            "UID": "SomeUUID000000000000000000000004",
            "description": "",
            "review_state": "private",
            "title": "A document within a folder"
        },
        {
            "@id": "http://localhost:55001/plone/folder/my-document",
            "@type": "Document",
            "Creator": "admin",
            "UID": "SomeUUID000000000000000000000005",
            "description": "",
            "review_state": "private",
            "title": "My Document"
        }
    ],
    "items_total": 3,
    "language": "",
    "layout": "listing_view",
    "lock": {},
    "modified": "1995-07-31T17:30:00",
    "nextPreviousEnabled": false,
    "next_item": {},
    "parent": {
        "@id": "http://localhost:55001/plone",
        "@type": "Plone Site",
        "description": "",
        "title": "Plone site"
    },
    "previous_item": {
        "@id": "http://localhost:55001/plone/front-page",
        "@type": "Document",
        "description": "Congratulations! You have successfully installed Plone.",
        "title": "Welcome to Plone"
    },
    "relatedItems": [],
    "review_state": "private",
    "rights": "",
    "subjects": [],
    "title": "My Folder",
    "version": "current",
    "working_copy": null,
    "working_copy_of": null
}
```

Note

For folderish types, collections or search results, the results will be **batched** if the size of the resultset exceeds the batch size. See [Batching](https://plonerestapi.readthedocs.io/en/latest/batching.html) for more details on how to work with batched results.

#### Unsuccessful response (404 Not Found)

If a resource could not be found, the server will respond with [404 Not Found](https://plonerestapi.readthedocs.io/en/latest/http-status-codes.html#term-404-not-found):

```
HTTP/1.1 404 Not Found
Content-Type: application/json

{
  'error': 'NotFound'
}
```

#### GET Implementation

A pseudo-code example of the GET implementation on the server:

```
try:
    order = getOrder()
    if order == None:
        # Not Found
        response.setStatus(404)
    else:
        # OK
        response.setStatus(200)
except:
    # Internal Server Error
    response.setStatus(500)
```

You can find implementation details in the [plone.restapi.services.content.add.FolderPost class](https://github.com/plone/plone.restapi/blob/dde57b88e0f1b5f5e9f04e6a21865bc0dde55b1c/src/plone/restapi/services/content/add.py#L35-L61)

#### GET Responses

Possible server reponses for a GET request are:

* [200 OK](https://plonerestapi.readthedocs.io/en/latest/http-status-codes.html#term-200-ok)
* [404 Not Found](https://plonerestapi.readthedocs.io/en/latest/http-status-codes.html#term-404-not-found)
* [500 Internal Server Error](https://plonerestapi.readthedocs.io/en/latest/http-status-codes.html#term-500-internal-server-error)

### Updating a Resource with PATCH

To update an existing resource we send a PATCH request to the server. PATCH allows to provide just a subset of the resource (the values you actually want to change).

If you send the value `null` for a field, the field’s content will be deleted and the `missing_value` defined for the field in the schema will be set. Note that this is not possible if the field is `required`, and it only works for Dexterity types, not Archetypes:

http

curl

httpie

python-requests

```
PATCH /plone/folder/my-document HTTP/1.1
Accept: application/json
Authorization: Basic YWRtaW46c2VjcmV0
Content-Type: application/json

{
    "title": "My New Document Title"
}
```

#### Successful Response (204 No Content)

A successful response to a PATCH request will be indicated by a [204 No Content](https://plonerestapi.readthedocs.io/en/latest/http-status-codes.html#term-204-no-content) response by default:

```
HTTP/1.1 204 No Content
```

#### Successful Response (200 OK)

You can get the object representation by adding a _Prefer_ header with a value of _return=representation_ to the PATCH request. In this case, the response will be a [200 OK](https://plonerestapi.readthedocs.io/en/latest/http-status-codes.html#term-200-ok):

http

curl

httpie

python-requests

```
PATCH /plone/folder/my-document HTTP/1.1
Accept: application/json
Authorization: Basic YWRtaW46c2VjcmV0
Prefer: return=representation
Content-Type: application/json

{
    "title": "My New Document Title"
}
```

```
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@components": {
        "actions": {
            "@id": "http://localhost:55001/plone/folder/my-document/@actions"
        },
        "breadcrumbs": {
            "@id": "http://localhost:55001/plone/folder/my-document/@breadcrumbs"
        },
        "contextnavigation": {
            "@id": "http://localhost:55001/plone/folder/my-document/@contextnavigation"
        },
        "navigation": {
            "@id": "http://localhost:55001/plone/folder/my-document/@navigation"
        },
        "types": {
            "@id": "http://localhost:55001/plone/folder/my-document/@types"
        },
        "workflow": {
            "@id": "http://localhost:55001/plone/folder/my-document/@workflow"
        }
    },
    "@id": "http://localhost:55001/plone/folder/my-document",
    "@type": "Document",
    "UID": "SomeUUID000000000000000000000005",
    "allow_discussion": false,
    "changeNote": "",
    "contributors": [],
    "created": "1995-07-31T13:45:00",
    "creators": [
        "admin"
    ],
    "description": "",
    "effective": null,
    "exclude_from_nav": false,
    "expires": null,
    "id": "my-document",
    "is_folderish": false,
    "language": "",
    "layout": "document_view",
    "lock": {
        "locked": false,
        "stealable": true
    },
    "modified": "1995-07-31T17:30:00",
    "next_item": {},
    "parent": {
        "@id": "http://localhost:55001/plone/folder",
        "@type": "Folder",
        "description": "This is a folder with two documents",
        "review_state": "private",
        "title": "My Folder"
    },
    "previous_item": {
        "@id": "http://localhost:55001/plone/folder/doc2",
        "@type": "Document",
        "description": "",
        "title": "A document within a folder"
    },
    "relatedItems": [],
    "review_state": "private",
    "rights": "",
    "subjects": [],
    "table_of_contents": null,
    "text": null,
    "title": "My New Document Title",
    "version": "current",
    "versioning_enabled": true,
    "working_copy": null,
    "working_copy_of": null
}
```

See for full specs the [RFC 5789: PATCH Method for HTTP](http://tools.ietf.org/html/rfc5789)

### Replacing a Resource with PUT

Note

PUT is not implemented yet.

To replace an existing resource we send a PUT request to the server:

TODO: Add example.

In accordance with the HTTP specification, a successful PUT will not create a new resource or produce a new URL.

PUT expects the entire resource representation to be supplied to the server, rather than just changes to the resource state. This is usually not a problem since the consumer application requested the resource representation before a PUT anyways.

When the PUT request is accepted and processed by the service, the consumer will receive a [204 No Content](https://plonerestapi.readthedocs.io/en/latest/http-status-codes.html#term-204-no-content) response ([200 OK](https://plonerestapi.readthedocs.io/en/latest/http-status-codes.html#term-200-ok) would be a valid alternative).

#### Successful Update (204 No Content)

When a resource has been updated successfully, the server sends a [204 No Content](https://plonerestapi.readthedocs.io/en/latest/http-status-codes.html#term-204-no-content) response:

TODO: Add example.

#### Unsuccessful Update (409 Conflict)

Sometimes requests fail due to incompatible changes. The response body includes additional information about the problem.

TODO: Add example.

#### PUT Implementation

A pseudo-code example of the PUT implementation on the server:

```
try:
    order = getOrder()
    if order:
        try:
            saveOrder()
        except conflict:
            response.setStatus(409)
        # OK
        response.setStatus(200)
    else:
        # Not Found
        response.setStatus(404)
except:
    # Internal Server Error
    response.setStatus(500)
```

TODO: Link to the real implementation…

#### PUT Responses

Possible server reponses for a PUT request are:

* [200 OK](https://plonerestapi.readthedocs.io/en/latest/http-status-codes.html#term-200-ok)
* [404 Not Found](https://plonerestapi.readthedocs.io/en/latest/http-status-codes.html#term-404-not-found)
* [409 Conflict](https://plonerestapi.readthedocs.io/en/latest/http-status-codes.html#term-409-conflict)
* [500 Internal Server Error](https://plonerestapi.readthedocs.io/en/latest/http-status-codes.html#term-500-internal-server-error)

#### POST vs. PUT

Difference between POST and PUT:

> * Use POST to create a resource identified by a service-generated URI
> * Use POST to append a resource to a collection identified by a service-generated URI
> * Use PUT to overwrite a resource

This follows [RFC 7231: HTTP 1.1: PUT Method](https://tools.ietf.org/html/rfc7231#section-4.3.4).

### Removing a Resource with DELETE

We can delete an existing resource by sending a DELETE request:

http

curl

httpie

python-requests

```
DELETE /plone/folder/my-document HTTP/1.1
Accept: application/json
Authorization: Basic YWRtaW46c2VjcmV0
```

A successful response will be indicated by a [204 No Content](https://plonerestapi.readthedocs.io/en/latest/http-status-codes.html#term-204-no-content) response:

```
HTTP/1.1 204 No Content
```

#### DELETE Implementation

A pseudo-code example of the DELETE implementation on the server:

```
try:
    order = getOrder()
    if order:
        if can_delete(order):
            # No Content
            response.setStatus(204)
        else:
            # Not Allowed
            response.setStatus(405)
    else:
        # Not Found
        response.setStatus(404)
except:
    # Internal Server Error
    response.setStatus(500)
```

TODO: Link to the real implementation…

#### DELETE Responses

Possible responses to a delete request are:

> * [204 No Content](https://plonerestapi.readthedocs.io/en/latest/http-status-codes.html#term-204-no-content)
> * [404 Not Found](https://plonerestapi.readthedocs.io/en/latest/http-status-codes.html#term-404-not-found) (if the resource does not exist)
> * [405 Method Not Allowed](https://plonerestapi.readthedocs.io/en/latest/http-status-codes.html#term-405-method-not-allowed) (if deleting the resource is not allowed)
> * [500 Internal Server Error](https://plonerestapi.readthedocs.io/en/latest/http-status-codes.html#term-500-internal-server-error)

### Reordering sub resources

The resources contained within a resource can be reordered using the _ordering_ key using a PATCH request on the container.

Use the _obj\_id_ subkey to specify which resource to reorder. The subkey _delta_ can be ‘top’, ‘bottom’, or a negative or positive integer for moving up or down.

Reordering resources within a subset of resources can be done using the _subset\_ids_ subkey.

A response 400 BadRequest with a message ‘Client/server ordering mismatch’ will be returned if the value is not in the same order as serverside.

A response 400 BadRequest with a message ‘Content ordering is not supported by this resource’ will be returned if the container does not support ordering.

http

curl

httpie

python-requests

```
PATCH /plone/folder/my-document HTTP/1.1
Accept: application/json
Authorization: Basic YWRtaW46c2VjcmV0
Content-Type: application/json

{
    "ordering": {"obj_id": "item_3", "delta": "top", "subset_ids": ["item_1", "item_3", "item5"]}
}
```

To rearrange all items in a folderish context use the _sort_ key.

The _on_ subkey defines the catalog index to be sorted on. The _order_ subkey indicates ‘ascending’ or ‘descending’ order of items.

A response 400 BadRequest with a message ‘Content ordering is not supported by this resource’ will be returned if the container does not support ordering.

http

curl

httpie

python-requests

```
PATCH /plone/folder HTTP/1.1
Accept: application/json
Authorization: Basic YWRtaW46c2VjcmV0
Content-Type: application/json

{
    "sort": {"on": "modified", "order": "descending"}
}
```



















































## Conventions

### Naming Convention for REST API Resources/Endpoints

#### Nouns vs Verbs

Rule: Use nouns to represent resources.

Do:

```
/my-folder
/@registry
/@types
```

Don’t:

```
/createFolder
/deleteDocument
/updateEvent
```

Reason:

RESTful URI should refer to a resource that is a thing (noun) instead of referring to an action (verb) because nouns have properties as verbs do not. The REST architectural principle uses HTTP verbs to interact with resources.

Though, there is an exception to that rule, verbs can be used for specific actions or calculations, .e.g.:

```
/login
/logout
/move-to
/reset-password
```

#### Singluar vs Plural

Rule: Use plural resources.

Do:

```
/users
/users/21
```

Don’t:

```
/user
/user/21
```

Reason:

If you use singular for a collection like resource (e.g. “/user” to retrieve a list of all users) it feels wrong. Mixing singular and plural is confusing (e.g. user “/users” for retrieving users and “/user/21” to retrieve a single user).

#### Upper vs. Lowercase

Rule: Use lowercase letters in URIs.

Do:

```
http://example.com/my-folder/my-document
```

Don’t:

```
http://example.com/My-Folder/My-Document
```

Reason: RFC 3986 defines URIs as case-sensitive except for the scheme and host components. e.g.

Those two URIs are equivalent:

```
http://example.org/my-folder/my-document
HTTP://EXAMPLE.ORG/my-folder/my-document
```

While this one is not equivalent to the two URIs above:

```
http://example.org/My-Folder/my-document
```

To avoid confusion we always use lowercase letters in URIs.

### Naming Convention for attribute names in URIs

Rule: Use hyphens (spinal case) to improve readability of URIs.

Do:

```
/users/noam/reset-password
```

Don’t:

```
/users/noam/resetPassword
/users/noam/ResetPassword
/users/noam/reset_password
```

Reason:

Spinal case is better to read and safer to use than camelCase (URLs are case sensitive (RFC3986)). Plone uses spinal case for URL creation (title “My page” becomes “my-page”) and mixed naming conventions in URLs would be confusing (e.g. “[/my-folder/@send\_url\_to\_user](mailto:/my-folder/%40send\_url\_to\_user)”). Google recommends spinal-case in URLs for better SEO ([https://support.google.com/webmasters/answer/76329](https://support.google.com/webmasters/answer/76329)).

Discussion:

[https://github.com/plone/plone.restapi/issues/194](https://github.com/plone/plone.restapi/issues/194)

### Naming Convention for attribute names in response body

Rule: Use snake\_case to reflect Python best practices.

Do:

```
{
  translation_of: ...
}
```

Don’t:

```
{
  translationOf: ...,
  TranslationOf: ...,
}
```

Reason:

We map over Python attributes 1:1 no matter if they are snake case (modern Python/Plone, Dexterity) of lowerCamelCase (Zope 2, Archetypes).

### Versioning

Versioning APIs does make a lot of sense for public API services. Especially if an API provider needs to ship different versions of the API at the same time. Though, Plone already has a way to version packages and it currently does not make sense for us to expose that information via the API. We will always just ship one version of the API at a time and we are usually in full control over the backend and the frontend.
