---
description: DS API - Family Promise 0.38.02
---

# Data Science API



{% embed url="https://github.com/Lambda-School-Labs/family-promise-service-tracker-ds-a" %}

{% embed url="http://family-promise-dev.us-east-1.elasticbeanstalk.com/" %}



### How to Use the DS API

Main URL: [http://family-promise-dev.us-east-1.elasticbeanstalk.com](http://family-promise-dev.us-east-1.elasticbeanstalk.com)

#### `/vizmap` endpoint

Perform SQL query of database according to filters implemented by user. Only pick out the following columns, and include those in a single JSON object that will be sent to DS API:

* `service_type_name` from `service_types` table.

Plus:

* address
* address\_line2
* city
* state
* zip
* country

from `locations` table.

\*zip codes are pulled from github repo link and added to a dataframe based on pulled zip

#### `/veteran_counts` endpoint

A JSON object containing:

* recipient\_id
* recipient\_veteran\_status

from `recipients` table.

#### `/age_metric` endpoint

A JSON object containing:

* recipient\_id
* recipient\_date\_of\_birth

from `recipients` table.

#### `/eligibility` endpoint

Accepts a string containing a household\_id from the households table.

Returns a JSON object containing:

* resident\_assistance\_eligibility: bool
* reduced\_bus\_fare\_eligiblity: bool

#### `/total_served` endpoint

Returns an integer representing the total number of recipients recorded in the database.

#### `/families_served` endpoint

Returns an integer representing the total number of families recorded in the database.

#### `/children_served` endpoint

Returns an integer representing the total number of children recorded in the database.

#### `/genders_served` endpoint

Returns an list displaying the total number of recipients of each gender in the database.

#### `/races_served` endpoint

Returns a list displaying the total number of recipients of each race in the database.

#### `/ethnicities_served` endpoint

Returns a list displaying the total number of recipients of each ethnicity in the database.

#### `/program_enrollment` endpoint

Returns a list displaying the total number of services done that fall under each program.

#### `/services_given` endpoint

Returns a list displaying the total number of each service done.

#### `/locations_of_service` endpoint

Returns a list displaying the total number of services given at each type of location in the database.

[Docs](https://docs.labs.lambdaschool.com/data-science/)

#### Running the DS application

* Create the .env file in the folder.
  * Add `DATABASE_URL = postgresql://docker:****@localhost:5400/api-dev` to the .env file.
    * That is only for spinning up the local instance for the DS API
  * Make sure the .env file matches the .env file that is in the non public documentation.
* run:`pipenv install --dev` to download all the dependencies.
* run:`pipenv shell` to start the pipenv environment.
* run:`uvicorn app.main:app --reload` to start running the fast api.

#### Running the DS application with Apple M1

* When you `pipenv install --dev` on the M1 you will most likely run into issues where the Pipfile will fail to lock due to issues with psycopg2. Psyocopg2 specifically has issues pip installing on the M1. After figuring out past issues with the M1, this is a work around until there is further bug fixing on compatibility.
* Install Homebrew.
  * [Homebrew](https://brew.sh/)
* Install miniforge for arm64\(Apple Silicone M1\).
  * [miniforge Github](https://github.com/conda-forge/miniforge).
  * This will not work with Anaconda.
* run: `conda create --name NAME python=3.8`: creates a conda environment.
* run: `conda activate NAME`: activates the conda environment.
  * The conda environment needs to running in order for the application to run.
* run: `conda install -c conda-forge -y psycopg2 numpy pandas`: install necessary dependencies.
* Create the .env file in the folder and continue following the instructions in the section above.

#### Updating the Elastic Beanstalk environment

1. Do a normal push to GitHub repo and wait for the changes to be approved and pushed to the main branch.
2. run:`git pull` to make sure code is perfect to deploy to Elastic Beanstalk.
3. run:`git add --all` to get all the changes to the api that has been made.
4. Change the version number in the `main.py` file. Example: `0.37.01`
   * run:`git commit -m 'Depoying version 0.XX.XX to AWS'` to get all the changes add.
   * When you start to deploy the new changes to Elastic Beanstalk it will take latest commit you made.
5. run: `eb init --region us-east-1 family-promise` to create the Elastic Beanstalk files in the application.
   * This step will only be required if you have not deployed to the Elastic Beanstalk environment.
6. run:`eb deploy --region us-east-1 family-promise-dev`.
   * Follow instruction that will given to you.
   * You may have to grab your security credentials from AWS.
7. Do a final push to add the final version number to the GitHub repo.

### Contributors

### **Data Science Team \(September, 2021\)**

| [Collin Jensen](https://github.com/collinjensen) | [Jeremiah Evangelista](https://github.com/mramputatoes) | [Paul Santora](https://github.com/santorap) |
| :---: | :---: | :---: |
| [![](https://avatars.githubusercontent.com/u/28957442?v=4)](https://github.com/collinjensen) | [![](https://avatars.githubusercontent.com/u/81700476?v=4)](https://github.com/mramputatoes) | [![](https://avatars.githubusercontent.com/u/77029484?v=4)](https://github.com/santorap) |
| [![](https://github.com/favicon.ico) ](https://github.com/collinjensen) | [![](https://github.com/favicon.ico) ](https://github.com/mramputatoes) | [![](https://github.com/favicon.ico) ](https://github.com/santorap) |
| [ ![](https://static.licdn.com/sc/h/al2o9zrvru7aqj8e1x2rzsrca) ](https://www.linkedin.com/in/collin-jensen-b29766146/) | [ ![](https://static.licdn.com/sc/h/al2o9zrvru7aqj8e1x2rzsrca) ](https://www.linkedin.com/in/jeremiah-evangelista-6ba928157/) | [ ![](https://static.licdn.com/sc/h/al2o9zrvru7aqj8e1x2rzsrca) ](https://www.linkedin.com/in/PaulSantora/) |

| [Sam Ebner](https://github.com/ebnersam) | [Samantha Temple](https://github.com/sntemple12) |
| :---: | :---: |
| [![](https://avatars.githubusercontent.com/u/84925046?v=4)](https://github.com/ebnersam) | [![](https://avatars.githubusercontent.com/u/79993685?v=4)](https://github.com/sntemple12) |
| [![](https://github.com/favicon.ico) ](https://github.com/ebnersam) | [![](https://github.com/favicon.ico) ](https://github.com/sntemple12) |
| [ ![](https://static.licdn.com/sc/h/al2o9zrvru7aqj8e1x2rzsrca) ](https://www.linkedin.com/in/sam-ebner/) | [ ![](https://static.licdn.com/sc/h/al2o9zrvru7aqj8e1x2rzsrca) ](https://www.linkedin.com/in/samantha-temple-487a3620a/) |















### DS API - Family Promise 0.38.02 OAS3

[/openapi.json](http://family-promise-dev.us-east-1.elasticbeanstalk.com/openapi.json)

To use these interactive docs:

* Click on an endpoint below
* Click the **Try it out** button
* Edit the Request body or any parameters
* Click the **Execute** button
* Scroll down to see the Server response Code & Details

#### [Database](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Database) <a id="operations-tag-Database"></a>

GET[​/info](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Database/get_url_info_get)Get Url

Verify we can connect to the database, and return the database URL in this format: dialect://user:password@host/dbname The password will be hidden with \*\*\*

**Parameters**

Cancel

No parametersExecute

**Responses**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Code</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Links</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">200</td>
      <td style="text-align:left">
        <p>Successful ResponseMedia typeapplication/jsonControls <code>Accept</code> header.</p>
        <ul>
          <li>Example Value</li>
          <li>Schema</li>
        </ul>
      </td>
      <td style="text-align:left">No links</td>
    </tr>
  </tbody>
</table>

#### [Visualizations](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Visualizations) <a id="operations-tag-Visualizations"></a>

POST[​/vizmap​/{query\_json}](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Visualizations/visual_vizmap__query_json__post)VisualPOST[​/veteran\_counts​/{query\_json}](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Visualizations/veteran_counts_veteran_counts__query_json__post)Veteran CountsPOST[​/age\_metric​/{query\_json}](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Visualizations/age_metric_age_metric__query_json__post)Age Metric

#### [Eligibility](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Eligibility) <a id="operations-tag-Eligibility"></a>

POST[​/eligibility​/{household\_id}](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Eligibility/check_eligibility_eligibility__household_id__post)Check Eligibility

#### [Metrics](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Metrics) <a id="operations-tag-Metrics"></a>

GET[​/total\_served](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Metrics/get_total_served_total_served_get)Get Total Served

Returns the total number of recipients TODO: Return recipients relavent to user

#### Returns

int total\_served

**Parameters**

Try it out

No parameters

**Responses**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Code</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Links</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">200</td>
      <td style="text-align:left">
        <p>Successful ResponseMedia typeapplication/jsonControls <code>Accept</code> header.</p>
        <ul>
          <li>Example Value</li>
          <li>Schema</li>
        </ul>
      </td>
      <td style="text-align:left">No links</td>
    </tr>
  </tbody>
</table>

GET[​/families\_served](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Metrics/get_families_served_families_served_get)Get Families Served

Returns the total number of families TODO: Return only those relavent to the user

#### Returns

int families\_served

**Parameters**

Try it out

No parameters

**Responses**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Code</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Links</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">200</td>
      <td style="text-align:left">
        <p>Successful ResponseMedia typeapplication/jsonControls <code>Accept</code> header.</p>
        <ul>
          <li>Example Value</li>
          <li>Schema</li>
        </ul>
      </td>
      <td style="text-align:left">No links</td>
    </tr>
  </tbody>
</table>

GET[​/children\_served](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Metrics/get_children_served_children_served_get)Get Children Served

Returns the number of recipients under 18, not inclusive.

#### Returns

int children\_served

**Parameters**

Try it out

No parameters

**Responses**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Code</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Links</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">200</td>
      <td style="text-align:left">
        <p>Successful ResponseMedia typeapplication/jsonControls <code>Accept</code> header.</p>
        <ul>
          <li>Example Value</li>
          <li>Schema</li>
        </ul>
      </td>
      <td style="text-align:left">No links</td>
    </tr>
  </tbody>
</table>

GET[​/genders\_served](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Metrics/get_genders_served_genders_served_get)Get Genders Served

Returns the count of each gender served.

#### Returns

list genders\_served

**Parameters**

Try it out

No parameters

**Responses**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Code</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Links</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">200</td>
      <td style="text-align:left">
        <p>Successful ResponseMedia typeapplication/jsonControls <code>Accept</code> header.</p>
        <ul>
          <li>Example Value</li>
          <li>Schema</li>
        </ul>
      </td>
      <td style="text-align:left">No links</td>
    </tr>
  </tbody>
</table>

GET[​/races\_served](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Metrics/get_races_served_races_served_get)Get Races Served

Returns the count of each race served.

#### Returns

list races\_served

**Parameters**

Try it out

No parameters

**Responses**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Code</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Links</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">200</td>
      <td style="text-align:left">
        <p>Successful ResponseMedia typeapplication/jsonControls <code>Accept</code> header.</p>
        <ul>
          <li>Example Value</li>
          <li>Schema</li>
        </ul>
      </td>
      <td style="text-align:left">No links</td>
    </tr>
  </tbody>
</table>

GET[​/ethnicities\_served](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Metrics/get_ethnicities_served_ethnicities_served_get)Get Ethnicities Served

Returns the count of each ethnicity served.

#### Returns

list ethnicities\_served

**Parameters**

Try it out

No parameters

**Responses**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Code</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Links</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">200</td>
      <td style="text-align:left">
        <p>Successful ResponseMedia typeapplication/jsonControls <code>Accept</code> header.</p>
        <ul>
          <li>Example Value</li>
          <li>Schema</li>
        </ul>
      </td>
      <td style="text-align:left">No links</td>
    </tr>
  </tbody>
</table>

GET[​/program\_enrollment](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Metrics/get_program_enrollment_program_enrollment_get)Get Program Enrollment

Returns the count of services done for each program.

#### Returns

list program\_enrollment

**Parameters**

Try it out

No parameters

**Responses**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Code</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Links</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">200</td>
      <td style="text-align:left">
        <p>Successful ResponseMedia typeapplication/jsonControls <code>Accept</code> header.</p>
        <ul>
          <li>Example Value</li>
          <li>Schema</li>
        </ul>
      </td>
      <td style="text-align:left">No links</td>
    </tr>
  </tbody>
</table>

GET[​/services\_given](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Metrics/get_services_given_services_given_get)Get Services Given

Returns the count of each service provided.

#### Returns

list services\_given

**Parameters**

Try it out

No parameters

**Responses**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Code</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Links</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">200</td>
      <td style="text-align:left">
        <p>Successful ResponseMedia typeapplication/jsonControls <code>Accept</code> header.</p>
        <ul>
          <li>Example Value</li>
          <li>Schema</li>
        </ul>
      </td>
      <td style="text-align:left">No links</td>
    </tr>
  </tbody>
</table>

GET[​/locations\_of\_service](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Metrics/get_locations_locations_of_service_get)Get Locations

Returns the count of services at each type of location.

#### Returns

list locations\_of\_service

**Parameters**

Try it out

No parameters

**Responses**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Code</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Links</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">200</td>
      <td style="text-align:left">
        <p>Successful ResponseMedia typeapplication/jsonControls <code>Accept</code> header.</p>
        <ul>
          <li>Example Value</li>
          <li>Schema</li>
        </ul>
      </td>
      <td style="text-align:left">No links</td>
    </tr>
  </tbody>
</table>

#### [Geocode](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Geocode) <a id="operations-tag-Geocode"></a>

POST[​/geocode​/](http://family-promise-dev.us-east-1.elasticbeanstalk.com/#/Geocode/get_latitude_longitude_geocode__post)Get Latitude Longitude

Please post an address as a JSON object with this exact format: { "address": "123 Gilman Dr W", "address\_line2": "", "city": "Seattle", "state": "WA", "zip": "98119", "country": "United States" }

All values should be a string if there is no address\_line2, the value should still be an empty string

The output will be a JSON object with the following format: {"latitude": , "longitude": }

**Parameters**

Try it out

No parameters

**Responses**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Code</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Links</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">200</td>
      <td style="text-align:left">
        <p>Successful ResponseMedia typeapplication/jsonControls <code>Accept</code> header.</p>
        <ul>
          <li>Example Value</li>
          <li>Schema</li>
        </ul>
      </td>
      <td style="text-align:left">No links</td>
    </tr>
  </tbody>
</table>

**Schemas**

HTTPValidationErrorValidationError

