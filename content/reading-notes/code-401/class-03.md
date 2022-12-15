+++
title = "CLASS-03: Express REST API"
date = "2022-11-29T23:21:29-08:00"
author = "Kenny W. Lino"
authorTwitter = "" #do not include @
cover = ""
tags = ["express", "javascript"]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
hideComments = false
color = "" #color from the theme settings
draft = false
+++

## ES6 Classes

Based on this article from [MDN Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes).

1. Classes are a template for creating **objects**.

2. Can a class declaration be hoisted?

    No, a class declaration cannot be hoisted because their values are not initialized.

3. How would you describe a constructor and contextual “this” to a non-technical friend?

    A constructor is like a recipe for creating an object. For example, we can have a recipe for cake, which we can use to make multiple cakes, such as vanilla, chocolate, strawberry. When working with objects, contextutal "this" tells us which cake we're working with in particular.


## Using Express Routing

Based on this [article](https://expressjs.com/en/guide/routing.html).

1. Within Express, what does routing refer to?

    Within Express, routing is when we have various endpoints that are set up to send responses to client requests.

2. What is the difference between a route path and a route method?

    A route path refers to the name of the endpoint that we've defined, such as `/` or `/about`. It can also be constructed with a regular expression.

    A route method refers to any of the HTTP request methods such as `GET` `POST`, etc.

    ```javascript
    // route path: '/about'
    // route method: GET
    app.get('/about', (req, res) => {
        res.send("It's all about me");
    })
    ```

3. When is it appropriate to add `next` as a parameter to a route handler and what must you do if `next` has been passed to your middleware as a parameter?

    We can use `next` as a parameter to a route handler when we add more than one callback function per route. When `next` has been passed to our middleware, we must make sure that it's called in beetween each callback.


## Express Routing

Based on this [article](https://www.digitalocean.com/community/tutorials/learn-to-use-the-new-router-in-expressjs-4).

1. What is an Express Router?

    An Express Router is "like a mini-Express application" that handles solely the routing.

2. By what means do we initialize express.Router() in an express server?

    To initialize it:

    ```javascript
    let router = express.Router();
    ```

3. What do we use route middleware for?

    We use route middleware to handle anything we'd like before the request is complete. This can include verifying whether the data is correct, confirming the user is authenticated, logging data, etc.

## Reflection

1. What are your learning goals after reading and reviewing the class README?

Afrer reviewing the README, my learning goals are to become proficient with writing Express servers in a way that is more clear using `Express.router()` and become comfortable with SQL and `sequelize`.