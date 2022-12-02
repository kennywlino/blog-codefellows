+++
title= "CLASS-04: Data Modeling"
date=  2022-12-01T08:21:56-08:00
authorTwitter = "" #do not include @
cover = ""
tags = ["express"]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
hideComments = false
color = "" #color from the theme settings
draft = false
+++

## NoSQL vs. SQL

Based on this [article](https://www.thegeekstuff.com/2014/01/sql-vs-nosql-db/?utm_source=tuicool).

1. What type of database is the best fit for the complex query intensive environment?

    SQL databases are the best for for complex queries as NoSQL doesn't have standard interfaces to do them. Therefore their queries also aren't as powerful.

2. What type of database is the best fit for hierarchical data storage?

    NoSQL databases are the best fit for hierarchical data storage because of the way it uses key-value pairs much like JSON data.

3. Describe the differences in scalability between a SQl and NoSQL database as though you were speaking to a non-technical friend.

    SQL and NoSQL databases differ in scalability in that SQL databases scale *vertically* while NoSQL databases scale *horiziontally*. 

    I heard a great analogy for the difference from this [Mission Cloud article](<https://www.missioncloud.com/blog/horizontal-vs-vertical-scaling-which-is-right-for-your-app#:~:text=With%20vertical%20scaling%20(%E2%80%9Cscaling%20up,memory%20workload%20across%20multiple%20devices>).

    They say the difference is that vertical scalability is like trading in a Toyota for a Ferrari. It's faster but it can get extremely expensive and you're still limited to one car. Horiziontal scaling is like getting multiple Toyotas to add to a fleet. One alone might not be great, but having multiple can give us the power we need to get what we want done.

## SQL Modeling Techniques

Based on this [article](https://www.essentialsql.com/get-ready-to-learn-sql-7-simplified-data-modeling/).

1. Among data tables, what is a one-to-many relationship and how do we “relate” them?

    A one-to-many relationship is when we have one table that is related to more than one entry in another table. This can be something like a `class` table that is related to many `students` in another table.

    We can relate them by using *foreign keys* which is equivalent to the *primary key* of another table.

2. Prior to designing your relational database, it might be useful to **create a diagram** of the database tables and their relationships.

3. Explain the difference between a primary and foreign key.

    A primary key is a unique key that identifies a row in a table. A foreign key refers to a primary key in *another* table. With the `class` / `student` example, we might have a single `class` with the ID of `111`, which would be its primary key in that table. When referencing this from the `student` table, the `111` would be the foreign key in reference to the `class` table.

## SQL vs. NoSQL

Based on this [video](https://www.youtube.com/watch?v=ZS_kXvOeQ5Y).

1. How do we treat keywords and parameters differently in SQL syntax?

    SQL keywords should be in all caps such as `SELECT` or `FROM` while the parameters remain lowercase. 

    e.g. `SELECT price FROM products`

2. Define normalization within the context of schemas and data.

    Normalization refers to how we manage the data that comes into our table to ensure it follows our schema. We may have missing columns or even extra data coming in, but we want to make sure everything follows the same structure.

3. Explain the difference between one-to-one, one-to-many, and many-to-many relationships to a non-technical recruiter.

    - one-to-one: One row of data in a table matches one other row in another table. This can be like a customer and a *billing* address.

    - one-to-many: One row of data in a table matches multiple other rows in another table. This can be like a customer and their multiple orders.

    - many-to-many: Multiple rows of data in a table correspond to multiple rows in another table. This can be like when there are multiple designers working on multiple products.

## Reflection

1. What are your learning goals after reading and reviewing the class README?

    After reading the README, my goals are to become more proficient with running basic SQL commands and being able to scaffold the designs of our table better.