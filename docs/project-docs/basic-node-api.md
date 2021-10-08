# Basic Node API

## Basic Node API

Welcome to your `Basic Node API Repository`. Use this to start your own Greenfield Project using nodejs, express and common industry standards.

This repository assumes a handful of industry practices and standards. We strive to keep you up to date in the industry and as a result, we have made some opinions for you so that you don't have to; you're welcome.

The following working examples can be found in this project template.

* CRUD [routes](https://docs.labs.lambdaschool.com/api/examples/routes) for a single resource
* A Knex [model](https://docs.labs.lambdaschool.com/api/examples/models) providing CRUD methods for DB operations
* Okta authentication verification middleware
* eslint setup and prettier formating.
* Jest tests for routes with mocking of database calls
* Inline [Swagger](https://docs.labs.lambdaschool.com/api/examples/swagger-docs) docs with a live route at `/api-docs`
* Github workflow config setup to run linting, tests and upload coverage to code climate
* docker-compose file for spinning up postgresql db. \(Win10 Home requires WSL\)

## API doc <a id="api-doc"></a>

The documentation can be viewed in the `/api-docs` route of your deploy \(or [locally](https://localhost:8000/api-docs)\). [See example](https://api.labsscaffolding.dev/api-docs/)​

Read more about the setup of [config/jsdoc.md](https://docs.labs.lambdaschool.com/api/examples/swagger-docs)​

## Requirements <a id="requirements"></a>

Labs teams must follow all [Labs Engineering Standards](https://labs.lambdaschool.com/topics/node-js/).

## Getting Started <a id="getting-started"></a>

Here is a brief walk thru of setting up the node api application.

### Enviornment Variables <a id="enviornment-variables"></a>

The following enviornment variables are required. the dotenv library is installed which will allow you to use a `.env` file.

* `PORT` - API port \(optional, but helpful with FE running as well\)
  * The following ports are whitelisted for use with okta
    * 3000
    * 8000
    * 8080
* `DS_API_URL` - URL to a data science api. \(eg. [https://ds-bw-test.herokuapp.com/](https://ds-bw-test.herokuapp.com/)\)
* `DS_API_TOKEN` - authorization header token for data science api \(eg. SUPERSECRET\)
* `DATABASE_URL` - connection string for postgres database
* `OKTA_URL_ISSUER` - The complete issuer URL for verifying okta access tokens. `https://example.okta.com/oauth2/default`
* `OKTA_CLIENT_ID` - the okta client ID.

See .env.sample for example values.

### Setup postgres <a id="setup-postgres"></a>

There are 3 options to get postgresql installed locally \[Choose one\]:

1. Use docker. [Install](https://docs.docker.com/get-docker/) for your platform
   * run: `docker-compose up -d` to start up the postgresql database and pgadmin.
   * Open a browser to [pgadmin](http://localhost:5050/) and you should see the Dev server already defined.
   * If you need to start over you will need to delete the folder `$ rm -rf ./data/pg` as this is where all of the server data is stored.
     * if the database `api-dev` was not created then start over.
2. Download and install postgresql directly from the [main site](https://www.postgresql.org/download/)​
   * make note of the port, username and password you use to setup the database.
   * Connect your client to the server manually using the values previously mentioned
   * You will need to create a database manually using a client.
   * Make sure to update the DATABASE\_URL connection string with the values for username/password, databasename and server port \(if not 5432\).
3. Setup a free account at [ElephantSQL](https://www.elephantsql.com/plans.html)​
   * Sign up for a free `Tiney Turtle` plan
   * copy the URL to the DATABASE\_URL .env variable
   * make sure to add `?ssl=true` to the end of this url

### Setup the application <a id="setup-the-application"></a>

From your project locally run the following commands:

* run: `npm install` to download all dependencies.
* run: `cp .env.sample .env` and update the enviornment variables to match your local setup.
* run: `npm run knex migrate:latest` to create the starting schema.
* run: `npm run knex seed:run` to populate your db with some data.
* run: `npm run tests` to confirm all is setup and tests pass.
* run: `npm run watch:dev` to start nodemon in local dev enviornment.

Make sure to update the details of the app name, description and version in the `package.json` and `config/jsdoc.js` files.

## Contributing <a id="contributing"></a>

See the [contributing doc](https://docs.labs.lambdaschool.com/api/contributing) for more info.

