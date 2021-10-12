# Frontend:

{% embed url="https://github.com/Lambda-School-Labs/family-promise-service-tracker-be-a" %}



## Family Promise Service Tracker

[Family Promise](https://familypromise.org) helps local communities coordinate their compassion to address the root causes of family homelessness. They tap existing local resources to empower families towards economic stability. Families come to them in crisis; they help them rebuild their lives with new skills and ongoing support. They address the issue holistically, providing prevention services before families reach crisis, shelter and case management when they become homeless, and stabilization programs once they have secured housing to ensure they remain independent.

Family Promise needs a way to track and visualize the services they provide external to the shelter to gain actionable insights.

Our goal is to build a generalizable monitoring and evaluation (M\&E) platform that meets Family Promise's needs, with an eye toward additional potential use cases that would be useful for many other organizations.

### Schema

[ DB Designer Schema Link](https://dbdesigner.page.link/VWjy5xWKghDumgmV8)

### Status

Deployed here: [https://fp-service-tracker.herokuapp.com/](https://fp-service-tracker.herokuapp.com)

_**Needs Updating**_ Current Roadmap in [Notion](https://www.notion.so/Roadmap-Family-Promise-Service-Tracker-2ca00c11c8e14dec93c861ac7aae49c0), all activity tracked in [Trello](https://trello.com/b/U8UUCBeb/family-promise-service-tracker).

### Requirements

Details on the Labs Node Scaffolding here: [https://docs.labs.lambdaschool.com/labs-api-strarter/](https://docs.labs.lambdaschool.com/labs-api-strarter/)

Labs teams must follow all [Labs Engineering Standards](https://docs.labs.lambdaschool.com/standards/).

### Documentation

* The documentation for how to work with the JSONB column used for Service Entry data and type models, check out **/docs/API-README-SERVICE-ENTRIES.md**
* The current API documentation is found in **/docs/API-README.md**
* List of known issues is found in **/docs/known-defects.md**
* Pull Request Template found in **/docs/pull_request_template.md**

### Getting Started

Please reference the step by step instructions to setup development environment in **/docs/dev-setup.md**

#### Enviornment Variables

* `PORT` - API port (optional, but helpful with FE running as well)
  * The following ports are whitelisted for use with okta
    * 3000
    * 8000
    * 8080
* `DS_API_URL` - URL to a data science api. (eg. [https://ds-bw-test.herokuapp.com/](https://ds-bw-test.herokuapp.com))
* `DS_API_TOKEN` - authorization header token for data science api (eg. SUPERSECRET)
* `DEV_DATABASE_URL` - connection string for local postgres database
* `OKTA_URL_ISSUER` - The complete issuer URL for verifying okta access tokens. `https://example.okta.com/oauth2/default`
* `OKTA_CLIENT_ID` - the okta client ID.
* `OKTA_ORG_URL` - The base url for the Okta org
* `OKTA_API_TOKEN` - Okta API token

See .env.sample for example values

#### Setup postgres

There are 3 options to get postgresql installed locally \[Choose one]:

1. Use docker. [Install](https://docs.docker.com/get-docker/) for your platform
   * run: `docker-compose up -d` to start up the postgresql database and pgadmin.
   * Open a browser to [pgadmin](http://localhost:5050) and you should see the Dev and Test server already defined.
   * If you need to start over you will need to delete the folder `$ rm -rf ./data/pg` as this is where all of the server data is stored (_ONLY IF YOU NEED TO START OVER_)
   * Upon logging into postgres admin on localhost (2nd dash above), you'll see the API-DEV server, but you will need to check if there is a "api-dev" database within that server, if not or if the databases `api-dev` and `api-test` were not created then you'll need to create them by right clicking databases, clicking create database, and adding a database for "api-dev" and then start over at step 1. You may need to grant system execution access to the .sh file in docker/pg/pg-init-scripts:
   * Run following from within root: `chmod +x ./docker/pg/pg-init-scripts/create-multiple-postgresql-databases.sh`
2. Download and install postgresql directly from the [main site](https://www.postgresql.org/download/)
   * make note of the port, username and password you use to setup the database.
   * Connect your client to the server manually using the values previously mentioned
   * You will need to create a database manually using a client.
   * Make sure to update the DATABASE_URL connection string with the values for username/password, databasename and server port (if not 5432).
3. Setup a free account at [ElephantSQL](https://www.elephantsql.com/plans.html)
   * _**Downside**_: JSONB column displays as `[object Object]`, so not good when testing/creating JSON queries
   * Sign up for a free `Tiney Turtle` plan
   * copy the URL to the DATABASE_URL .env variable
   * make sure to add `?ssl=true` to the end of this url

#### Setup the application

* create your project repo by forking or using this as a template.
* run: `npm install` to download all dependencies.
* run: `cp .env.sample .env` and update the enviornment variables to match your local setup.
* run: `npm run knex migrate:latest` to create the starting schema.
* run: `npm run knex seed:run` to populate your db with some data.
* run: `npm run tests` to confirm all is setup and tests pass.
* run: `npm run watch:dev` to start nodemon in local dev enviornment.





Readme:



## Family Promise Service Tracker

Family Promise helps local communities coordinate their compassion to address the root causes of family homelessness. They tap existing local resources to empower families towards economic stability. Families come to them in crisis; they help them rebuild their lives with new skills and ongoing support. They address the issue holistically, providing prevention services before families reach crisis, shelter and case management when they become homeless, and stabilization programs once they have secured housing to ensure they remain independent.

Family Promise needs a way to track and visualize the services they provide external to the shelter to gain actionable insights.

Our goal is to build a generalizable monitoring and evaluation (M\&E) platform that meets Family Promise's needs, with an eye toward additional potential use cases that would be useful for many other organizations.

You can find the deployed project at a.familypromiseservicetracker.dev/.

\
\


![https://mit-license.org](https://img.shields.io/packagist/l/doctrine/orm.svg) ![https://reactjs.org](https://img.shields.io/badge/react-v16.13.1-blue) ![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg?style=flat-square)

* DO NOT fork the repo. Clone directly!
* run: `npm install` to download all dependencies.
* run: `npm start` to start your local development server.

> When using Okta for authentication, the app will need to run locally on port 3000.

#### Key Features

* Admin users can add / edit / delete employees, add / edit / delete programs, add / edit / delete services types & add / edit / delete services.
* Program Managers can add / edit / delete programs, add / edit / delete services types & add / edit / delete services.
* Service Managers can view and add / edit / delete services.
* All users can update their profile image and names.

**Front end deployed to AWS Amplify.**

[**Back end**](https://github.com/Lambda-School-Labs/family-promise-service-tracker-be-a)** built using:**

**Node.js with Postgres**

* point one
* point two
* point three

## Installation Instructions

create your project repo by forking or using this as a template. run: `npm install` to download all dependencies. run: `npm start` to start the live server. Note: must be running on localhost:3000 g

## Map setup

Setting up map for dashboard:

Must have a token setup in a .env.local file (must create file on fresh clone) with the following format for map to render `REACT_APP_MAPBOX_TOKEN = "Token string"`

## Contributing

When contributing to this repository, please first discuss the change you wish to make via issue, email, or any other method with the owners of this repository before making a change.

Please note we have a code of conduct. Please follow it in all your interactions with the project.

### Issue/Bug Request

**If you are having an issue with the existing project code, please submit a bug report under the following guidelines:**

* Check first to see if your issue has already been reported.
* Check to see if the issue has recently been fixed by attempting to reproduce the issue using the latest master branch in the repository.
* Create a live example of the problem.
* Submit a detailed bug report including your environment & browser, steps to reproduce the issue, actual and expected outcomes, where you believe the issue is originating from, and any potential solutions you have considered.

#### Feature Requests

We would love to hear from you about new features which would improve this app and further the aims of our project. Please provide as much detail and information as possible to show us why you think your new feature should be implemented.

#### Pull Requests

If you have developed a patch, bug fix, or new feature that would improve this app, please submit a pull request. It is best to communicate your ideas with the developers first before investing a great deal of time into a pull request to ensure that it will mesh smoothly with the project.

Remember that this project is licensed under the MIT license, and by submitting a pull request, you agree that your work will be, too.

**Pull Request Guidelines**

* Update the README.md with details of changes to the interface, including new plist variables, exposed ports, useful file locations and container parameters.
* Ensure that your code conforms to our existing code conventions and test coverage.
* Include the relevant issue number, if applicable.
* You may merge the Pull Request in once you have the sign-off of two other developers, or if you do not have permission to do that, you may request the second reviewer to merge it for you.

### Documentation

See [Backend Documentation](https://github.com/Lambda-School-Labs/family-promise-service-tracker-be-a) for details on the backend of our project.

### Contributors

#### **Front-End Team (Labs 35)**

|                                                                                                         |                                                                                                             |                                                                                                                          |
| :-----------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------: | :----------------------------------------------------------------------------------------------------------------------: |
|                                [Adam Purdy](https://github.com/PurdyRad)                                |                              [Jason Corchado](https://github.com/JasonCorchado)                             |                                   [Jonathan Calderon](https://github.com/Jonathan1600)                                   |
|         [![](https://avatars.githubusercontent.com/u/76630666?v=4)](https://github.com/PurdyRad)        |        [![](https://avatars.githubusercontent.com/u/77353218?v=4)](https://github.com/JasonCorchado)        |              [![](https://avatars.githubusercontent.com/u/70250506?s=400)](https://github.com/Jonathan1600)              |
|                    [![](https://github.com/favicon.ico)](https://github.com/PurdyRad)                   |                   [![](https://github.com/favicon.ico)](https://github.com/JasonCorchado)                   |                          [![](https://github.com/favicon.ico)](https://github.com/Jonathan1600)                          |
| [![](https://static.licdn.com/sc/h/al2o9zrvru7aqj8e1x2rzsrca)](https://www.linkedin.com/in/adam-purdy/) | [![](https://static.licdn.com/sc/h/al2o9zrvru7aqj8e1x2rzsrca)](https://www.linkedin.com/in/jason-corchado/) | [![](https://static.licdn.com/sc/h/al2o9zrvru7aqj8e1x2rzsrca)](https://www.linkedin.com/in/jonathan-calderon-silberman/) |

|                                                                                                       |                                                                                                             |
| :---------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------: |
|                            [Monica Zwissler](https://github.com/Monicascz)                            |                               [Robert Allen](https://github.com/robertjallen)                               |
|       [![](https://avatars.githubusercontent.com/u/73200302?v=4)](https://github.com/Monicascz)       |        [![](https://avatars.githubusercontent.com/u/20561145?s=400)](https://github.com/robertjallen)       |
|                  [![](https://github.com/favicon.ico)](https://github.com/Monicascz)                  |                    [![](https://github.com/favicon.ico)](https://github.com/robertjallen)                   |
| [![](https://static.licdn.com/sc/h/al2o9zrvru7aqj8e1x2rzsrca)](https://www.linkedin.com/in/monicascz) | [![](https://static.licdn.com/sc/h/al2o9zrvru7aqj8e1x2rzsrca)](https://www.linkedin.com/in/robertallendev/) |

\


#### **Back-End Team (Labs 35)**

|                                                                                                          |                                                                                                               |                                                                                                             |                                                                                                        |
| :------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------: | :----------------------------------------------------------------------------------------------------: |
|                             [Adam Selter](https://github.com/blackcatwizard)                             |                            [Domenic Scarcella](https://github.com/DomenicScarcella)                           |                                [Jay Ponce de Leon](https://github.com/jaypdl)                               |                           [Matthew Ellis](https://github.com/MatthewEllisTx/)                          |
|      [![](https://avatars.githubusercontent.com/u/73545965?v=4)](https://github.com/blackcatwizard)      |       [![](https://avatars.githubusercontent.com/u/76451364?s=400)](https://github.com/DomenicScarcella)      |            [![](https://avatars.githubusercontent.com/u/20601752?v=4)](https://github.com/jaypdl)           |     [![](https://avatars.githubusercontent.com/u/77289520?v=4)](https://github.com/MatthewEllisTx/)    |
|                 [![](https://github.com/favicon.ico)](https://github.com/blackcatwizard)                 |                   [![](https://github.com/favicon.ico)](https://github.com/DomenicScarcella)                  |                       [![](https://github.com/favicon.ico)](https://github.com/jaypdl)                      |                [![](https://github.com/favicon.ico)](https://github.com/MatthewEllisTx/)               |
| [![](https://static.licdn.com/sc/h/al2o9zrvru7aqj8e1x2rzsrca)](https://www.linkedin.com/in/adam-selter/) | [![](https://static.licdn.com/sc/h/al2o9zrvru7aqj8e1x2rzsrca)](https://www.linkedin.com/in/domenicscarcella/) | [![](https://static.licdn.com/sc/h/al2o9zrvru7aqj8e1x2rzsrca)](https://www.linkedin.com/in/jayponcedeleon/) | [![](https://static.licdn.com/sc/h/al2o9zrvru7aqj8e1x2rzsrca)](https://www.linkedin.com/in/mbellistx/) |

|                                                                                                       |                                                                                                               |                                                                                                                      |
| :---------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------------------------------------: |
|                            [Monica Zwissler](https://github.com/Monicascz)                            |                                 [Nick Samples](https://github.com/samplesn08)                                 |                                  [Weston Woodard](https://github.com/SpicyLunchbox)                                  |
|       [![](https://avatars.githubusercontent.com/u/73200302?v=4)](https://github.com/Monicascz)       |           [![](https://avatars.githubusercontent.com/u/53315294?v=4)](https://github.com/samplesn08)          |            [![](https://avatars.githubusercontent.com/u/69223774?s=400)](https://github.com/SpicyLunchbox)           |
|                  [![](https://github.com/favicon.ico)](https://github.com/Monicascz)                  |                      [![](https://github.com/favicon.ico)](https://github.com/samplesn08)                     |                        [![](https://github.com/favicon.ico)](https://github.com/SpicyLunchbox)                       |
| [![](https://static.licdn.com/sc/h/al2o9zrvru7aqj8e1x2rzsrca)](https://www.linkedin.com/in/monicascz) | [![](https://static.licdn.com/sc/h/al2o9zrvru7aqj8e1x2rzsrca)](https://www.linkedin.com/in/nicholas-samples/) | [![](https://static.licdn.com/sc/h/al2o9zrvru7aqj8e1x2rzsrca)](https://www.linkedin.com/in/weston-woodard-76709988/) |

\


#### **Front-End Team (Labs 33)**

|                                                                                                                                       |                                                                                                                             |                                                                                                                      |                                                                                                                      |
| :-----------------------------------------------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------------------------------------: |
|                                             [Hussain Ali](https://github.com/princeali415)                                            |                                        [Ruben Ramirez](https://github.com/rubesworld)                                       |                                      [Bryan Diaz](https://github.com/bdiaz12345)                                     |                                    [Jose Robles](https://github.com/jcrobles1989)                                    |
| [![](https://res.cloudinary.com/dyp2opcpj/image/upload/v1618184678/images/gij4edsbp3709samouln.jpg)](https://github.com/princeali415) | [![](https://res.cloudinary.com/water-my-plants/image/upload/v1618698077/ruben-ramirez.jpg)](https://github.com/rubesworld) | [![](https://res.cloudinary.com/water-my-plants/image/upload/v1619463650/bryanD.png)](https://github.com/bdiaz12345) | [![](https://res.cloudinary.com/water-my-plants/image/upload/v1619477734/Jose.png)](https://github.com/jcrobles1989) |
|                                 [![](https://github.com/favicon.ico)](https://github.com/princeali415)                                |                             [![](https://github.com/favicon.ico)](https://github.com/rubesworld)                            |                         [![](https://github.com/favicon.ico)](https://github.com/bdiaz12345)                         |                        [![](https://github.com/favicon.ico)](https://github.com/jcrobles1989)                        |
|           [![](https://static.licdn.com/sc/h/al2o9zrvru7aqj8e1x2rzsrca)](https://www.linkedin.com/in/hussain-ali-58a9b690/)           |        [![](https://static.licdn.com/sc/h/al2o9zrvru7aqj8e1x2rzsrca)](https://www.linkedin.com/in/rubenandresramirez)       |   [![](https://static.licdn.com/sc/h/al2o9zrvru7aqj8e1x2rzsrca)](https://www.linkedin.com/in/bryan-diaz-816a081b9/)  |      [![](https://static.licdn.com/sc/h/al2o9zrvru7aqj8e1x2rzsrca)](https://www.linkedin.com/in/jcroblesorozco/)     |

\


#### **Back-End Team (Labs 33)**

|                                                                                                                             |                                                                                                                           |
| :-------------------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------: |
|                                     [Chris Sutton](https://github.com/suttonchristopher)                                    |                                     [Brandon O'Neal](https://github.com/brandononeal)                                     |
| [![](https://res.cloudinary.com/water-my-plants/image/upload/v1619474173/ChrisS.jpg)](https://github.com/suttonchristopher) | [![](https://res.cloudinary.com/water-my-plants/image/upload/v1619473829/BrandonON.jpg)](https://github.com/brandononeal) |
|                         [![](https://github.com/favicon.ico)](https://github.com/suttonchristopher)                         |                           [![](https://github.com/favicon.ico)](https://github.com/brandononeal)                          |
|        [![](https://static.licdn.com/sc/h/al2o9zrvru7aqj8e1x2rzsrca)](https://www.linkedin.com/in/suttonchristopher/)       |         [![](https://static.licdn.com/sc/h/al2o9zrvru7aqj8e1x2rzsrca)](https://www.linkedin.com/in/brandonaoneal)         |
