+++
title = "CLASS-02: Express, NPM, TDD, CI/CD"
date = "2022-11-28T09:12:43-08:00"
author = "Kenny W. Lino"
authorTwitter = "" #do not include @
cover = ""
tags = ["express", "npm", "tdd", "ci/cd"]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
hideComments = false
color = "" #color from the theme settings
draft = false
+++

## An Introduction to NodeJS and Express

Based on the [MDN documents](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/Introduction).

1. Explain middleware, answer as though I were a non-technical recruiter.

    Middleware is software that can help us better process the request/data that comes from our servers. For example, there's the `body-parser` middleware that makes it easier for us to work with the data, or the `cors` middleware which allows systems to 'talk' to each other.

2. Express is the most popular **Node web framework**.

3. Express is “unopinionated.” What does that mean?

    "Unopinionated" means that Express doesn't have a lot of restrictions on how to combine its various components or what components we need to use in order to create a server.

    This is in contrast to other applications that might be "opinionated" meaning that they have a "right way" to do certain tasks.

4. What is a module and why is modularity useful to us as developers?

A module is code that has been organized into separate files/libraries that can be imported into different JS files as needed. Having modules is useful because it allows us to ensure that certain functionality works as expected and because it can allow better readability.

## What is NPM

Based on the [NPM documents](https://docs.npmjs.com/about-npm).

1. What version of npm are you running on your machine?

    ```bash
    npm --version
    8.19.3
    ```

2. What command would you type to install a library/package called ‘jshint’ into your node project?

    In order to install a package called `jshint`:

    ```bash
    npm install jshint
    npm i jshint
    ```

## What is Test Driven Development

Based on this [article](https://www.agilealliance.org/glossary/tdd/#q=~(infinite~false~filters~(postType~(~'page~'post~'aa_book~'aa_event_session~'aa_experience_report~'aa_glossary~'aa_research_paper~'aa_video)~tags~(~'tdd))~searchTerm~'~sort~false~sortDirection~'asc~page~1)).

1. Explain why tests are important. Please explain as though I were your non technical elder.

    Tests in programming are important as they help us make sure that each component of our code works as expected and let's us know if it doesn't.

    This is similar to doing a "phone, keys, wallet" check before leaving the house. If we have all 3 items, we can leave the house-- if not something is wrong and we need to correct it before leaving.

2. What are three expected benefits of testing.

    The 3 benefits of testing are:
    - decreases in the # of bugs
    - less efforts in project final phase
    - improved design quality

3. Name at least 2 individual pitfalls and at least 2 team pitfalls commonly encountered while writing tests.

    individual pitfalls:
    - not running tests frequent enough
    - writing tests that are too large/coarse

    team pitfalls:
    - whole team hasn't adopted TDD
    - poorly maintained / abandoned test suite

## What is CI/CD

Based on this [video](https://www.youtube.com/watch?v=xSv_m3KhUO8).

1. What are three benefits of Continuous Integration?

    Continuous Integration helps us:

    - ensure everyone's changes are integrated
    - catch bugs
    - reduce merge conflicts

2. What is the difference between Continuous Delivery and Continuous Deployment?

    Continuous Delivery is when we develop our software so that it *could* be released at any time.
    Continuous Deployment is a level beyond that where the newly developed feeatures *are* being deployed.

3. Explain how GitHub fits into this process assuming the listener comes from a non-technical background.

    GitHub allows developers to store their code and work on different drafts of it, often with a `main` branch that holds the main code that we use and a `dev` branch to test new features.

    GitHub also has something called *webhooks* which can automatically send messages to other systems regarding the activity of our projects. With CI/CD, GitHub can use webhooks to notify our CI/CD server whenever there's a new update in our project. The server will then take the newly added feature, run the tests, and let's GitHub know whether those tests passed.

## Reflection

1. What are your learning goals after reading and reviewing the class README?

    After reading and reviewing the README, my goals are to learn how to write effective tests for our servers that give enough coverage to ensure good code quality.