+++
title = "Setting Up a back-end app with Sequelize and Collection Interface"
date = "2022-12-05T09:46:19-08:00"
author = "Kenny W. Lino"
authorTwitter = "" #do not include @
cover = ""
tags = ["backend", "express", "sql", "tdd"]
keywords = ["", ""]
description = "Goes over how to set up a back-end server using Sequelize, an SQL object-relational model (ORM). Also shows how to write a collection interface that performs generic CRUD operations as oppose to writing separate route handlers per data model. Includes test-driven development (TDD) to ensure our features work as expected."
showFullContent = false
readingTime = false
hideComments = false
color = "" #color from the theme settings
draft = true
+++

## npm set-up

When we set-up our application, we need to use `npm` to initialize it and add the following tools and scripts below. We can use `npm init -y` to answer yes to the set-up questions and get our `package.json` quickly.

### Tools needed

We should `npm install` the following packages:

- `dotenv` -- Handles all of the environment variables such as database URLs, server URLS, and API keys
- `eslint`
- `express` -- Manages the HTTP requests between client and server
- `jest`
- `pg`-- Postgres SQL
- `sequelize`
- `sequelize-cli`
- `sqlite3` -- SQLite
- `supertest` -- used for testing HTTP servers

### Scripts needed

These should be added under `"scripts"` in `package.json`.

- `"test"`: `"NODE_ENV=test jest --verbose --coverage"`
- `"test-watch"`: `"NODE_ENV=test jest --watchAll --verbose --coverage"`
- `"db:config"`: `"sequelize init:config"`
- `"db:create"`: `"sequelize db:create"`

