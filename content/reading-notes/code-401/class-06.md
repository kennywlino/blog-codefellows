+++
title = "CLASS-06: Authentication"
date = "2022-12-04T14:12:11-08:00"
author = "Kenny W. Lino"
authorTwitter = "" #do not include @
cover = ""
tags = ["authentication"]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
hideComments = false
color = "" #color from the theme settings
draft = false
+++

## Securing Passwords

Based on [Securing Passwords with Bcrypt Hashing Function](https://thehackernews.com/2014/04/securing-passwords-with-bcrypt-hashing.html) article from The Hacker News.

1. Explain to a non-technical friend how you would safely hash and store a password.

    Storing passwords without any encryption leaves us susceptile to attacks from hackers or other harmdoers. Instead of storing passwords directly in a database, we can use a hashing algorithm which calculates a new value given your password. This makes it so if an attacker gains access to the database, they will only see the hashed passwords. Hashing algorithms also have another layer to make the hashed passwords safer called "salts", which randomizes the hashed passwords further. Thus without knowledge of the hashing algorithm and salt, the password is much harder to uncover.

2. What is Bcrypt?

    Bcrypt is a particular type of hashing algorithm that is less susceptible to brute force attacks using a technique called Key Searching. Brute force attacks are when an attacker attempts as many inputs as possible until they find the values that generate the same hash value.

3. Why might you use something like Bcrypt?

    You would use Bcrypt when you need a strong hash algorithm to protect your passwords as best as possible that makes brute force attacks much slower.

## Basic Auth

Based on this [article](https://en.wikipedia.org/wiki/Basic_access_authentication) from Wikipedia.

1. What is Basic Access Authentication?

    Basic Access Authentication is a method used by the browser (or other HTTP user agents) that allows us to provide a user name and password when making requests.

2. What properties are necessary in the header of a Basic Auth request?

    A Basic Access Authentication request should take the format of:

    `Authorization: Basic <credentials>`

    with an ID and password joined with `:`.

3. How are username:password in Basic Auth encoded?

    They are encoded in Base64.

## OWASP auth cheatsheet

Based on this [article](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html).

1. Define the authentication process to a non-technical recruiter.

    Authentication works by our application taking in a username/ID and a password or another secret piece of information to verify our user. This is then compared to information in our database, which usually stores relations between our users and passwords, with the passwords stored as a hash in order to prevent attacks. Using the hashing algorithm, we can compare the given password and its hashed value to see if what's in the database matches, granting or denying our user access based on whether there's match.

2. How should your error messaging respond (both HTTP and HTML)? Why?

    Our error messaging should respond as generically as possible. In text, this should be something like "Login failed; Invalid user ID or password," as opposed to "Login for user foo; invalid password" or "Login failed; account disabled." For HTTP, the codes should be 200 for positive (OK) responses or 403 (Forbidden) for negative responses.

    This is because anything too specific will reveal unnecessary information to attackers. By having this variation, we could create discrepency factors that will give hints to attackers about specific users and/or passwords that they're targeting.

Bookmark this link also and consider OWASP fundamentals any time you interact with authentication. Applications developed with security in mind from inception have fewer vulnerabilities throughout their lifecycle.

## Additional Questions

1. Looking ahead at this module’s course schedule, What do you look forward to learning?

    This week, I'm looking forward to learning about role-based access control as I'm curious to see how we modularize our code to limit or share access to certain things in our database or application based on the user roles.

2. What are your learning goals after reading and reviewing the class README?

    After reading the class README for this lesson, my learning goal is to learn how to integrate Bcrypt to protect our data.
