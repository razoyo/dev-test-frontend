# Razoyo frontend dev test
This is a test geared towards frontend developers. You will be using an API to build a UI that displays a car catalog. You can build your frontend in any language / framework that you would like (i.e. React, Angular, Vue, etc). The important thing is that you organize your code well and that your code can be easily run by another developer.

## Wireframe
There are no requirements to what the UI looks like, be as creative as you'd like with the layout and styling. We have a Figma mockup create here to give you an idea of what the UI should do.
[Frontend dev test wireframe](https://www.figma.com/file/IdAwya41Fb4FqKp4TJs81s/Frontend-dev-test-wireframe?node-id=0%3A1)

## Requirements
The requirements are as follows:

* When the page loads, it should render the cars that are returned by the `GET /cars` endpoint.
* When the user clicks on the "open" icon, the UI should make another API call to `GET /cars/:id` to retrieve the car details and appear them underneath the name of the car.
* When the user clicks on the "close" icon, the car details show disappear.
* When the user selects a car make in the filter, the UI should make an API call to `GET /cars` with the `make` query parameter and then render the cars in the response.

## API

The API that will power your UI lives here:
`https://dev-test-frontend-werpwe2p3q-uc.a.run.app`

It has 2 endpoints that you will use.

### List cars

```
GET /cars?make=:make
```

Returns a list of cars based on the `make` query filter (optional).
The response also includes a list all the possible `make` options.
The response will have a header called `Your-Token` is used when calling the "get car" endpoint.

For example:
```
curl -i \
    -H 'Accept: application/json' \
    https://dev-test-frontend-werpwe2p3q-uc.a.run.app/cars?make=Honda
```

### Get car

```
GET /cars/:id
```
Returns the car details for a specific car ID.
You must include the `Your-Token` value from the "list cars" response to authenticate with this endpoint. If you do not, you will receive a 401 unauthorized response.

For example:
```
curl -i \
    -H 'Accept: application/json' \
    -H 'Authorization: {Your-Token}' \
    https://dev-test-frontend-werpwe2p3q-uc.a.run.app/cars/wj6qg7zpt09udm1m
```

## Extra Credit
The better looking the UI, the more extra credit you get.
Implement the ability to save the animal selection so that refreshing the page keeps your animal selection.

## Submit your work
When you have completed the feature, send an email to: assessments@razoyo.com

The email needs to contain a link to your own git repository branch with the code submission.

Do *not* submit a pull request.
