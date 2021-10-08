# Examples:

## Example Models

The following examples can be found in the `/api` folder.

## Database Model using Knex

The model at `api/profile/profileModel.js` provides all CRUD operations for the profile resource using a knex connection.

## API Model using Axios

The model in `api/dsService` is an example of using a model to wrap the calls to an internally created API.

## Example routes of resources

Some examples of routes are provided.

## Simple Non-resource route

The `/` \(index\) route is a simple `GET` route that is not tied to a resource.

## Full CRUD for a single resource

The `/profile` route is dedicated to a single resource \(model\).

This route provides CRUD operations on the profile model. Profile is a replacement for the notion of a User when using an identity provider \(Okta\) where Users are owned by the third party service.

## Wrapper Routes

The `/data` routes are wrappers around an internal API \(DS resources\)

When working on a project that has other services being created Labs wants you to keep those behind a single authenticated server. This API starter shows an example of wrapping these services.

Notice that the `/data/predict` route is not merely a copy of the DS service but creates a path that may be esasier for the FE to consume. Make sure to work with the owner of the service to understand it's use and if such a change will work.

## Swagger Setup

Swagger docs are created using [open api v3 notations](https://swagger.io/specification/). There are 2 libraries used to generate the swagger formatted docs:

* [swagger-ui-express](https://github.com/scottie1984/swagger-ui-express)
* [swagger-jsdoc](https://github.com/Surnet/swagger-jsdoc)

Quick review of the swagger setup in Labs projects.

{% embed url="https://youtu.be/edczzXdoBvw" caption="" %}

## Swagger UI Express

This library is used to setup and serve the offical swager ui resources \(html,css,js\). The express app is setup to send requests to the route `/api-docs` to the `swagger-ui-express` library.

## Swagger JS Doc

This library is used to parse the root definition file and inline JsDoc comments. The api documentation entries are found inline on the router files in `api/**/*Router.js` and use the yaml notation format. This is the most common format found in swagger reference docs and resources found online.

The `jsdoc.js` definition file contains the application level information, like app name, version, description and license. You can define reusable components in this file and reference them throughout your jsdoc comments.

> Take note in the `jsdoc.js` file that tags are used to group routes together.

## Testing

You will be using jest to write function or endpoint/route unit tests in your application. Please put all of your tests for your code in the `__tests__` directory. You should get into the habit of ensuring that you have coverage for your code _before submitting a pull request_.

### Running your tests <a id="running-your-tests"></a>

Follow these steps when writing tests:

* `cd into` the root of this directory
* `npm run test` to run your test suite
  * _if you're prompted_ select `a` to run tests in watch mode. This will re-run your test suite when you save any file in your application.
* In your terminal you will see a test runner that looks something like this:

  ​​

* When you're not actively writing tests its best to close that terminal window so that you don't keep running tests when your files are saved.

![Test screenshot](https://tk-assets.lambdaschool.com/bc9ca7b9-4fce-45de-9a16-705cbec062d8_ScreenShot2020-06-25at7.52.52AM.png)

### Coverage <a id="coverage"></a>

> 💡 Code coverage should be a good goal to have and a good starting place. But every application will be different.

* ​[Kent Dodds put it nicely](https://kentcdodds.com/blog/common-testing-mistakes#mistake-number-2-100-code-coverage). Strive for solid coverage as we strive to hand you over well-tested code in which we have extreme confidence.
* To run a coverage report for your application simply run `npm run coverage`.
* You should see a print out in your console that looks like this:

  ​![code coverage](https://tk-assets.lambdaschool.com/5abec98b-2b61-483f-bd85-71002a9f755a_ScreenShot2020-06-25at7.59.14AM.png)

