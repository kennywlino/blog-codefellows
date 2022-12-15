+++
title = "Securing our back-end app with Bcrypt"
date = "2022-12-05T10:36:33-08:00"
author = ""
authorTwitter = "" #do not include @
cover = ""
tags = ["", ""]
keywords = ["", ""]
description = ""
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

- `base-64`
- `bcrypt`
- `cors`
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

### Other configurations

Copy over configs from Code Fellows set-up including:

`.github` for GitHub actions.


## Encoding and hashing

```javascript
let base64 = require('base-64');
let bcrypt = require('bcrypt');

// *** Encoding ***

let str = 'pass123';
let encodedStr = base64.encode(str);
let decodedStr = base64.decode(encodedStr);

console.log('str:', str); // str: pass123
console.log('encodedStr:', encodedStr); // encodedStr: cGFzczEyMw==
console.log('decodedStr:', decodedStr); // decodedStr: pass123

// *** Hashing w/ bcrypt ***

let password = 'pass123';
let complexity = 5;

async function encrypt(password, complexity) {
    return await bcrypt.hash(password, complexity);
}

let exampleOne = encrypt(password, complexity);
let exampleTwo = encrypt(password, complexity);

async function checkValidity(password, hashedPassword) {
    return await bcrypt.compare(password, hashedPassword);
}

let exampleOne = '$2b$05$AVpmLtqmMiagW2hTLLp.neg5x6yat1csHNOuJxnIqI2vf6hmb4f6W'
let 

checkValidity(password, exampleOne);
```
