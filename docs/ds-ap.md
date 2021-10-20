# DS AP

### DS API - Family Promise

#### [http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Geocode/get\_latitude\_longitude\_geocode\_\_post](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Geocode/get\_latitude\_longitude\_geocode\_\_post)

{% embed url="http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Geocode/get_latitude_longitude_geocode__post" %}





[/openapi.json](http://family-promise-dev.us-east-1.elasticbeanstalk.com/openapi.json)

#### [Database](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Database) <a href="operations-tag-database" id="operations-tag-database"></a>

GET[/info](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Database/get\_url\_info\_get)Get Url

Verify we can connect to the database, and return the database URL in this format: dialect://user:password@host/dbname The password will be hidden with \*\*\*

**Parameters**

Cancel

No parameters

ExecuteClear

**Responses**

**Curl**

```bash
curl -X 'GET' \
  'http://family-promise-dev.us-east-1.elasticbeanstalk.com/info' \
  -H 'accept: application/json'
```

**Request URL**

```
http://family-promise-dev.us-east-1.elasticbeanstalk.com/info
```

**Server response**

| Code | Details                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| ---- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 200  | <p><strong>Response body</strong></p><p>Download</p><pre class="language-json"><code class="lang-json">{
  "database_url": "postgresql://aztugzfejptrww:***@ec2-107-22-245-82.compute-1.amazonaws.com:5432/db9egku1e3j21v"
}</code></pre><p><strong>Response headers</strong></p><pre><code> connection: keep-alive  content-length: 112  content-type: application/json  date: Thu,14 Oct 2021 15:26:09 GMT  server: nginx/1.20.0 </code></pre> |

**Responses**

| Code | Description                                                                                                                                                                                                           | Links      |
| ---- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| 200  | <p>Successful Response</p><p>Media typeapplication/jsonControls <code>Accept</code> header.</p><ul><li>Example Value</li><li>Schema</li></ul><pre class="language-json"><code class="lang-json">"string"</code></pre> | _No links_ |

#### [Visualizations](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Visualizations) <a href="operations-tag-visualizations" id="operations-tag-visualizations"></a>

POST[/vizmap/{query\_json}](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Visualizations/visual\_vizmap\_\_query\_json\_\_post)Visual

Creates an interactive map with dots pertaining to location of service. The dots on the map are color coded by service. Because there is no latitude or longitude in BE database, we geocode in order to get latitude and longitude. With the acquired latitude and longitude, the map visualization can be created and sent to the BE in JSON form.

### Input:

query\_json : JSON object Sent to DS API from BE

### Output:

JSON object sent back to BE

**Parameters**

Cancel

| Name                 | Description |
| -------------------- | ----------- |
| query\_json \*(path) |             |

Execute

**Responses**

| Code | Description                                                                                                                                                                                                                                                                                    | Links      |
| ---- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| 200  | <p>Successful Response</p><p>Media typeapplication/jsonControls <code>Accept</code> header.</p><ul><li>Example Value</li><li>Schema</li></ul><pre class="language-json"><code class="lang-json">"string"</code></pre>                                                                          | _No links_ |
| 422  | <p>Validation Error</p><p>Media typeapplication/json</p><ul><li>Example Value</li><li>Schema</li></ul><pre class="language-json"><code class="lang-json">{
  "detail": [
    {
      "loc": [
        "string"
      ],
      "msg": "string",
      "type": "string"
    }
  ]
}</code></pre> | _No links_ |

POST[/veteran\_counts/{query\_json}](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Visualizations/veteran\_counts\_veteran\_counts\_\_query\_json\_\_post)Veteran Counts

This function will return a bar chart of the count of veterans being served by Family Promise, in JSON form.

**Parameters**

Cancel

| Name                 | Description |
| -------------------- | ----------- |
| query\_json \*(path) |             |

Execute

**Responses**

| Code | Description                                                                                                                                                                                                                                                                                    | Links      |
| ---- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| 200  | <p>Successful Response</p><p>Media typeapplication/jsonControls <code>Accept</code> header.</p><ul><li>Example Value</li><li>Schema</li></ul><pre class="language-json"><code class="lang-json">"string"</code></pre>                                                                          | _No links_ |
| 422  | <p>Validation Error</p><p>Media typeapplication/json</p><ul><li>Example Value</li><li>Schema</li></ul><pre class="language-json"><code class="lang-json">{
  "detail": [
    {
      "loc": [
        "string"
      ],
      "msg": "string",
      "type": "string"
    }
  ]
}</code></pre> | _No links_ |

POST[/age\_metric/{query\_json}](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Visualizations/age\_metric\_age\_metric\_\_query\_json\_\_post)Age Metric

This function will return a table visual of the count of recipients by age group being served by Family Promise, in JSON form.

**Parameters**

Cancel

| Name                 | Description |
| -------------------- | ----------- |
| query\_json \*(path) |             |

Execute

**Responses**

| Code | Description                                                                                                                                                                                                                                                                                    | Links      |
| ---- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| 200  | <p>Successful Response</p><p>Media typeapplication/jsonControls <code>Accept</code> header.</p><ul><li>Example Value</li><li>Schema</li></ul><pre class="language-json"><code class="lang-json">"string"</code></pre>                                                                          | _No links_ |
| 422  | <p>Validation Error</p><p>Media typeapplication/json</p><ul><li>Example Value</li><li>Schema</li></ul><pre class="language-json"><code class="lang-json">{
  "detail": [
    {
      "loc": [
        "string"
      ],
      "msg": "string",
      "type": "string"
    }
  ]
}</code></pre> | _No links_ |

#### [Eligibility](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Eligibility) <a href="operations-tag-eligibility" id="operations-tag-eligibility"></a>

POST[/eligibility/{household\_id}](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Eligibility/check\_eligibility\_eligibility\_\_household\_id\_\_post)Check Eligibility

Checks for eligibility for services based on service provider data.

#### Parameters

***

id A household\_id entry from the households table.

#### Returns

***

JSON "resident\_assistance\_eligibility": bool "reduced\_bus\_fare\_eligibility": bool

**Parameters**

Cancel

| Name                         | Description |
| ---------------------------- | ----------- |
| household\_id \*string(path) |             |

Execute

**Responses**

| Code | Description                                                                                                                                                                                                                                                                                    | Links      |
| ---- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| 200  | <p>Successful Response</p><p>Media typeapplication/jsonControls <code>Accept</code> header.</p><ul><li>Example Value</li><li>Schema</li></ul><pre class="language-json"><code class="lang-json">"string"</code></pre>                                                                          | _No links_ |
| 422  | <p>Validation Error</p><p>Media typeapplication/json</p><ul><li>Example Value</li><li>Schema</li></ul><pre class="language-json"><code class="lang-json">{
  "detail": [
    {
      "loc": [
        "string"
      ],
      "msg": "string",
      "type": "string"
    }
  ]
}</code></pre> | _No links_ |

#### [Metrics](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Metrics) <a href="operations-tag-metrics" id="operations-tag-metrics"></a>

GET[/total\_served](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Metrics/get\_total\_served\_total\_served\_get)Get Total Served

Returns the total number of recipients TODO: Return recipients relavent to user

#### Returns

***

int total\_served

**Parameters**

Cancel

No parameters

ExecuteClear

**Responses**

**Curl**

```bash
curl -X 'GET' \
  'http://family-promise-dev.us-east-1.elasticbeanstalk.com/total_served' \
  -H 'accept: application/json'
```

**Request URL**

```
http://family-promise-dev.us-east-1.elasticbeanstalk.com/total_served
```

**Server response**

| Code | Details                                                                                                                                                                                                                                                                                                                      |
| ---- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 200  | <p><strong>Response body</strong></p><p>Download</p><pre class="language-json"><code class="lang-json">115</code></pre><p><strong>Response headers</strong></p><pre><code> connection: keep-alive  content-length: 3  content-type: application/json  date: Thu,14 Oct 2021 15:26:36 GMT  server: nginx/1.20.0 </code></pre> |

**Responses**

| Code | Description                                                                                                                                                                                                           | Links      |
| ---- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| 200  | <p>Successful Response</p><p>Media typeapplication/jsonControls <code>Accept</code> header.</p><ul><li>Example Value</li><li>Schema</li></ul><pre class="language-json"><code class="lang-json">"string"</code></pre> | _No links_ |

GET[/families\_served](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Metrics/get\_families\_served\_families\_served\_get)Get Families Served

Returns the total number of families TODO: Return only those relavent to the user

#### Returns

***

int families\_served

**Parameters**

Cancel

No parameters

Execute

**Responses**

| Code | Description                                                                                                                                                                                                           | Links      |
| ---- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| 200  | <p>Successful Response</p><p>Media typeapplication/jsonControls <code>Accept</code> header.</p><ul><li>Example Value</li><li>Schema</li></ul><pre class="language-json"><code class="lang-json">"string"</code></pre> | _No links_ |

GET[/children\_served](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Metrics/get\_children\_served\_children\_served\_get)Get Children Served

Returns the number of recipients under 18, not inclusive.

#### Returns

***

int children\_served

**Parameters**

Cancel

No parameters

ExecuteClear

**Responses**

**Curl**

```bash
curl -X 'GET' \
  'http://family-promise-dev.us-east-1.elasticbeanstalk.com/children_served' \
  -H 'accept: application/json'
```

**Request URL**

```
http://family-promise-dev.us-east-1.elasticbeanstalk.com/children_served
```

**Server response**

| Code | Details                                                                                                                                                                                                                                                                                                                     |
| ---- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 200  | <p><strong>Response body</strong></p><p>Download</p><pre class="language-json"><code class="lang-json">71</code></pre><p><strong>Response headers</strong></p><pre><code> connection: keep-alive  content-length: 2  content-type: application/json  date: Thu,14 Oct 2021 15:27:14 GMT  server: nginx/1.20.0 </code></pre> |

**Responses**

| Code | Description                                                                                                                                                                                                           | Links      |
| ---- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| 200  | <p>Successful Response</p><p>Media typeapplication/jsonControls <code>Accept</code> header.</p><ul><li>Example Value</li><li>Schema</li></ul><pre class="language-json"><code class="lang-json">"string"</code></pre> | _No links_ |

GET[/genders\_served](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Metrics/get\_genders\_served\_genders\_served\_get)Get Genders Served

Returns the count of each gender served.

#### Returns

***

list genders\_served

**Parameters**

Cancel

No parameters

ExecuteClear

**Responses**

**Curl**

```bash
curl -X 'GET' \
  'http://family-promise-dev.us-east-1.elasticbeanstalk.com/genders_served' \
  -H 'accept: application/json'
```

**Request URL**

```
http://family-promise-dev.us-east-1.elasticbeanstalk.com/genders_served
```

**Server response**

| Code | Details                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| ---- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 200  | <p><strong>Response body</strong></p><p>Download</p><pre class="language-json"><code class="lang-json">[
  {
    "gender": "Female",
    "total": 5
  },
  {
    "gender": "Male",
    "total": 12
  },
  {
    "gender": "Transgender: M to F",
    "total": 4
  },
  {
    "gender": "Transgender: F to M",
    "total": 5
  },
  {
    "gender": "Gender fluid",
    "total": 6
  },
  {
    "gender": "Agender",
    "total": 5
  },
  {
    "gender": "Androgynous",
    "total": 8
  },
  {
    "gender": "Bi-gender",
    "total": 8
  },
  {
    "gender": "Non-binary",
    "total": 4
  },
  {
    "gender": "Demi-boy",
    "total": 3
  },
  {
    "gender": "Demi-girl",
    "total": 6
  },
  {
    "gender": "Genderqueer",
    "total": 7
  },
  {
    "gender": "Gender nonconforming",
    "total": 2
  },
  {
    "gender": "Tri-gender",
    "total": 6
  },
  {
    "gender": "All genders",
    "total": 6
  },
  {
    "gender": "In the middle of boy and girl",
    "total": 8
  },
  {
    "gender": "Intersex",
    "total": 10
  },
  {
    "gender": "Not sure",
    "total": 2
  },
  {
    "gender": "Prefer not to say",
    "total": 7
  },
  {
    "gender": "Other",
    "total": 0
  }
]</code></pre><p><strong>Response headers</strong></p><pre><code> connection: keep-alive  content-length: 716  content-type: application/json  date: Thu,14 Oct 2021 15:27:21 GMT  server: nginx/1.20.0 </code></pre> |

**Responses**

| Code | Description                                                                                                                                                                                                           | Links      |
| ---- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| 200  | <p>Successful Response</p><p>Media typeapplication/jsonControls <code>Accept</code> header.</p><ul><li>Example Value</li><li>Schema</li></ul><pre class="language-json"><code class="lang-json">"string"</code></pre> | _No links_ |

GET[/races\_served](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Metrics/get\_races\_served\_races\_served\_get)Get Races Served

Returns the count of each race served.

#### Returns

***

list races\_served

**Parameters**

Cancel

No parameters

Execute

**Responses**

| Code | Description                                                                                                                                                                                                           | Links      |
| ---- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| 200  | <p>Successful Response</p><p>Media typeapplication/jsonControls <code>Accept</code> header.</p><ul><li>Example Value</li><li>Schema</li></ul><pre class="language-json"><code class="lang-json">"string"</code></pre> | _No links_ |

GET[/ethnicities\_served](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Metrics/get\_ethnicities\_served\_ethnicities\_served\_get)Get Ethnicities Served

Returns the count of each ethnicity served.

#### Returns

***

list ethnicities\_served

**Parameters**

Cancel

No parameters

ExecuteClear

**Responses**

**Curl**

```bash
curl -X 'GET' \
  'http://family-promise-dev.us-east-1.elasticbeanstalk.com/ethnicities_served' \
  -H 'accept: application/json'
```

**Request URL**

```
http://family-promise-dev.us-east-1.elasticbeanstalk.com/ethnicities_served
```

**Server response**

| Code | Details                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ---- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 200  | <p><strong>Response body</strong></p><p>Download</p><pre class="language-json"><code class="lang-json">[
  {
    "ethnicity": "Hispanic/Latino",
    "total": 61
  },
  {
    "ethnicity": "Non-Hispanic/Non-Latino",
    "total": 51
  },
  {
    "ethnicity": "Prefer not to say",
    "total": 2
  }
]</code></pre><p><strong>Response headers</strong></p><pre><code> connection: keep-alive  content-length: 139  content-type: application/json  date: Thu,14 Oct 2021 15:27:29 GMT  server: nginx/1.20.0 </code></pre> |

**Responses**

| Code | Description                                                                                                                                                                                                           | Links      |
| ---- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| 200  | <p>Successful Response</p><p>Media typeapplication/jsonControls <code>Accept</code> header.</p><ul><li>Example Value</li><li>Schema</li></ul><pre class="language-json"><code class="lang-json">"string"</code></pre> | _No links_ |

GET[/program\_enrollment](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Metrics/get\_program\_enrollment\_program\_enrollment\_get)Get Program Enrollment

Returns the count of services done for each program.

#### Returns

***

list program\_enrollment

**Parameters**

Cancel

No parameters

ExecuteClear

**Responses**

**Curl**

```bash
curl -X 'GET' \
  'http://family-promise-dev.us-east-1.elasticbeanstalk.com/program_enrollment' \
  -H 'accept: application/json'
```

**Request URL**

```
http://family-promise-dev.us-east-1.elasticbeanstalk.com/program_enrollment
```

**Server response**

| Code | Details                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| ---- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 200  | <p><strong>Response body</strong></p><p>Download</p><pre class="language-json"><code class="lang-json">[
  {
    "program_name": "Shelter Support",
    "total": 174
  },
  {
    "program_name": "Prevention/Diversion",
    "total": 177
  },
  {
    "program_name": "Aftercare",
    "total": 151
  },
  {
    "program_name": "Test setup by Admin ",
    "total": 0
  }
]</code></pre><p><strong>Response headers</strong></p><pre><code> connection: keep-alive  content-length: 191  content-type: application/json  date: Thu,14 Oct 2021 15:27:34 GMT  server: nginx/1.20.0 </code></pre> |

**Responses**

| Code | Description                                                                                                                                                                                                           | Links      |
| ---- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| 200  | <p>Successful Response</p><p>Media typeapplication/jsonControls <code>Accept</code> header.</p><ul><li>Example Value</li><li>Schema</li></ul><pre class="language-json"><code class="lang-json">"string"</code></pre> | _No links_ |

GET[/services\_given](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Metrics/get\_services\_given\_services\_given\_get)Get Services Given

Returns the count of each service provided.

#### Returns

***

list services\_given

**Parameters**

Try it out

No parameters

**Responses**

| Code | Description                                                                                                                                                                                                           | Links      |
| ---- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| 200  | <p>Successful Response</p><p>Media typeapplication/jsonControls <code>Accept</code> header.</p><ul><li>Example Value</li><li>Schema</li></ul><pre class="language-json"><code class="lang-json">"string"</code></pre> | _No links_ |

GET[/locations\_of\_service](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Metrics/get\_locations\_locations\_of\_service\_get)Get Locations

Returns the count of services at each type of location.

#### Returns

***

list locations\_of\_service

**Parameters**

Cancel

No parameters

ExecuteClear

**Responses**

**Curl**

```bash
curl -X 'GET' \
  'http://family-promise-dev.us-east-1.elasticbeanstalk.com/locations_of_service' \
  -H 'accept: application/json'
```

**Request URL**

```
http://family-promise-dev.us-east-1.elasticbeanstalk.com/locations_of_service
```

**Server response**

| Code | Details                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| ---- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 200  | <p><strong>Response body</strong></p><p>Download</p><pre class="language-json"><code class="lang-json">[
  {
    "location_type": "Personal Home",
    "total": 146
  },
  {
    "location_type": "Halfway House",
    "total": 142
  },
  {
    "location_type": "Service Distribution Center",
    "total": 110
  },
  {
    "location_type": "Unaffiliated Service Distribution Location",
    "total": 104
  }
]</code></pre><p><strong>Response headers</strong></p><pre><code> connection: keep-alive  content-length: 228  content-type: application/json  date: Thu,14 Oct 2021 15:27:41 GMT  server: nginx/1.20.0 </code></pre> |

**Responses**

| Code | Description                                                                                                                                                                                                           | Links      |
| ---- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| 200  | <p>Successful Response</p><p>Media typeapplication/jsonControls <code>Accept</code> header.</p><ul><li>Example Value</li><li>Schema</li></ul><pre class="language-json"><code class="lang-json">"string"</code></pre> | _No links_ |

#### [Geocode](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Geocode) <a href="operations-tag-geocode" id="operations-tag-geocode"></a>

POST[/geocode/](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Geocode/get\_latitude\_longitude\_geocode\_\_post)Get Latitude Longitude

```
Please post an address as a JSON object with this format:
```

{"address": "123 Gilman Dr W", "address\_line2": "", "city": "Seattle", "state": "WA", "zip": "98119", "country": "United States"}

```
The output will be a JSON object with the following format:
```

{"latitude": 47.64971, "longitude": -117.39764}

**Parameters**

Cancel

No parameters

**Request body**

application/jsonExecuteClear

**Responses**

**Curl**

```bash
curl -X 'POST' \
  'http://family-promise-dev.us-east-1.elasticbeanstalk.com/geocode/' \
  -H 'accept: application/json' \
  -H 'Content-Type: application/json' \
  -d '{}'
```

**Request URL**

```
http://family-promise-dev.us-east-1.elasticbeanstalk.com/geocode/
```

**Server response**

| Code | Details                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ---- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 200  | <p><strong>Response body</strong></p><p>Download</p><pre class="language-json"><code class="lang-json">{
  "latitude": 47.64971,
  "longitude": -117.39764
}</code></pre><p><strong>Response headers</strong></p><pre><code> access-control-allow-credentials: true  access-control-allow-origin: *  connection: keep-alive  content-length: 44  content-type: application/json  date: Thu,14 Oct 2021 15:27:47 GMT  server: nginx/1.20.0 </code></pre> |

**Responses**

| Code | Description                                                                                                                                                                                                                                                                                    | Links      |
| ---- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| 200  | <p>Successful Response</p><p>Media typeapplication/jsonControls <code>Accept</code> header.</p><ul><li>Example Value</li><li>Schema</li></ul><pre class="language-json"><code class="lang-json">"string"</code></pre>                                                                          | _No links_ |
| 422  | <p>Validation Error</p><p>Media typeapplication/json</p><ul><li>Example Value</li><li>Schema</li></ul><pre class="language-json"><code class="lang-json">{
  "detail": [
    {
      "loc": [
        "string"
      ],
      "msg": "string",
      "type": "string"
    }
  ]
}</code></pre> | _No links_ |

**Schemas**

HTTPValidationError{

|        |              |
| ------ | ------------ |
| detail | Detail\[...] |
|        |              |

}ValidationError{

|        |                                    |
| ------ | ---------------------------------- |
| loc\*  | Location\[...]                     |
| msg\*  | <p>string<br>title: Message</p>    |
| type\* | <p>string<br>title: Error Type</p> |
|        |                                    |

}





![](<../.gitbook/assets/image (26) (1).png>)
