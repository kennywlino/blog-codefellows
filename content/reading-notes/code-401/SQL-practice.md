+++
title = "SQL Practice"
date = "2022-11-26T21:47:06-08:00"
author = "Kenny W. Lino"
authorTwitter = "" #do not include @
cover = ""
tags = ["sql"]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
hideComments = false
color = "" #color from the theme settings
draft = false
+++

Based on [SQL Bolt](https://sqlbolt.com/lesson/select_queries_introduction).

## SELECT queries

In order to get data from our SQL database, we can use the `SELECT` statement. One of the fundamental queries is the `SELECT` query which will grab all rows of the given columns.

```SQL
SELECT colA, colB, ...
FROM mytable;
```

For example, given this data:

TABLE: Movies

 | ID  | Title          | Director      | Year | Length (minutes) |
 | --- | -------------- | ------------- | ---- | ---------------- |
 | 1   | Toy Story      | John Lasseter | 1995 | 81               |
 | 2   | Monsters, Inc. | Pete Docter   | 2001 | 92               |
 | 3   | Up             | Pete Docter   | 2009 | 101              |

This command would give us only the title and director information.

 ```SQL
SELECT title, director FROM movies;
 ```
## Queries with constraints

When we work with larger datasets, simply grabbing every row per column may not be the most effective way to get the data we need. To filter to just the data we want, we can use the `WHERE` clause in our queries. The `WHERE` clause is used on each row to decide if that row should be included or not.

```SQL
SELECT colA, colB, ...
FROM mytable
WHERE <conditionA>
    AND/OR <conditionB>
    AND/OR ...;
```

There are multiple operators we can use within our conditions.

For numbers:

| Operator                  | Condition                                | SQL Examples              |
| ------------------------- | ---------------------------------------- | ------------------------- |
| `=`, `!=`, `<`, `>=`      | numerical operators                      | `col < 4`                 |
| `BETWEEN ... AND ...`     | within range of 2 values (inclusive)     | `col BETWEEN 2 AND 8`     |
| `NOT BETWEEN ... AND ...` | not within range of 2 values (inclusive) | `col NOT BETWEEN 2 AND 8` |
| `IN (...)`                | element is in a given list               | `col IN (1, 5, 10)`       |
| `NOT IN (...)`            | element not in a given list              | `col NOT IN (1, 5, 10)`   |

For text:

| Operator      | Condition                                                          | SQL Examples                                                             |
| ------------- | ------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| `=`           | case sensitive comparison                                          | `col = "wheels"`                                                         |
| `!=`          | case sensitive inequality comparison                               | `col != "distance"`                                                      |
| `LIKE`        | case insensitive comparison                                        | `col LIKE "PRICE"`                                                       |
| `NOT LIKE`    | case insensitive inequality comparison                             | `col NOT LIKE "year"`                                                    |
| `%`           | match a sequence of 0 or more characters with `LIKE` or `NOT LIKE` | `col LIKE "%AT%"` (matches "**AT**", "**AT**TIC", "C**AT**", "B**AT**S") |
| `_`           | match a single character with `LIKE` or `NOT LIKE`                 | `col LIKE "AN_"` (matches "BR**AND**", but not "**AN**")                 |
| `IN(...)`     | same as numbers                                                    |                                                                          |
| `NOT IN(...)` | same as numbers                                                    |                                                                          |

## Filtering and sorting query results

There are other keywords that allow us to sift through our data even more.

To get only the unique values in a column, we can use the keyword `DISTINCT`. For example, in the movie database example, `DISTINCT` can give us the unique list of directors even if multiiple films from the same director are listed.

```SQL
SELECT DISTINCT <colA>, <colB>, ...
FROM mytable
WHERE <conditionA>;
...
```

If we want to sort our data, we can use the `ORDER BY` keyword. To use it, we write `ORDER BY <col> ASC/DESC` This comes in handy since it's not guaranteed that the database will keep the data sorted.

```SQL
SELECT <colA>, <colB>, ...
FROM mytable
WHERE <conditionA>
ORDER BY <col> ASC/DESC;
```

In some cases, we might only way to grab a certain subset of results from the database. In that case, we can use the `LIMIT` keyword to define how many rows to retrieve and `OFFSET` to decide what row to start counting from.

```SQL
SELECT <colA>, <colB>, ...
FROM mytable
WHERE <conditionA>
ORDER BY <colA> ASC/DESC;
LIMIT <num> OFFSET <num>;
```

## Multi-table queries with JOINs

In practice, SQL data is usually split into multiple tables. For example, on SQLBolt, they give us an example of a table with Movie data and another table with Box Office data. This practice is called *normalization*. In order to get all of the data we need in one table, we can use `JOIN`s.

In order to use a join, all rows need to have a key to identify that row uniquely across all of the tables. There are a few types of `JOIN`s, but the most basic one is called the `INNER JOIN`. The `INNER JOIN` works by using the unique key to combine the row data.

```SQL
SELECT <colA>, <colB>, ...
FROM mytable
INNER JOIN another_table
    ON mytable.id = another_table.id
WHERE <conditionA>
ORDER BY <col> ASC/DESC
LIMIT <num> OFFSET <num>;

```

## Inserting rows

To insert new data, we can use the `INSERT` statement. With the `INSERT` statement, we can insert multiple rows at a time. In some cases, we can also define default values for a column. In those instances, we can also define specific columns we have data for by specifying which columns before writing the values.

```SQL
INSERT INTO mytable
(<colA>, <colB>, ...)
VALUES (<val_or_expr>, <val_or_expr>),
       (<val_or_expr>, <val_or_expr>),
       ...;
```

## Updating rows

To update data in a table, we can use the `UPDATE` statement. To use the `UPDATE` statement, we must include the table name, columns and rows to update.

```SQL
UPDATE mytable
SET <columnA> = <val_or_expr>,
    <columnB> = <val_or_expr>,
    ....
WHERE <condition>;
```

## Deleting rows

To delete rows, we can use the `DELETE` statement. To use it, we can specify a condition with `WHERE`.

```SQL
DELETE FROM mytable
WHERE <condition>;
```

## Creating tables

To create tables, we can use the `CREATE TABLE` statement. Since SQL will throw an error if there's another table with the same name, we can use the `CREATE TABLE` function in conjunction with the `IF NOT EXISTS` clause.

```SQL
CREATE TABLE IF NOT EXISTS <new_table> (
    <colA> <data_type> <table_constraint> DEFAULT <def_val>,
    <colB> <data_type> <table_constraint> DEFAULT <def_val>,
    ...
);
```

Data types can include:

`INTEGER`, `BOOLEAN`, `FLOAT`, `DOUBLE`, `CHARACTER(num_chars)`, `VARCHAR(num_chars)`, `TEXT`, `DATE`, `DATETIME`

Table constraints are optional values that can limit what values get inserted into that column. Some include:

`PRIMARY KEY`, `AUTOINCREMENT`, `UNIQUE`, `NOT NULL`, `CHECK(expression)`

## Altering tables

When we want to make changes to our table such as adding new or deleting new columns or rename it, we can use the `ALTER TABLE` statement.

Adding columns

```SQL
ALTER TABLE mytable 
ADD <col><data_type> <table_constraint>
    DEFAULT <def_val>;
```

Deleting columns

```SQL
ALTER TABLE mytable
DROP <col>;
```

Renaming the table

```SQL
ALTER TABLE mytable
RENAME TO <new_name>;
```

## Dropping tables

If we want to completely remove a table, we can use the `DROP TABLE` command.

```SQL
DROP TABLE IF EXISTS mytable;
```


## Lesson Exercise Screenshots

### Lesson 1

![lesson-1](/blog/SQL-practice/lesson-1.png)

### Lesson 2

![lesson-2](/blog/SQL-practice/lesson-2.png)

### Lesson 3

![lesson-3](/blog/SQL-practice/lesson-3.png)

### Lesson 4

![lesson-4](/blog/SQL-practice/lesson-4.png)

### Lesson 5

![lesson-5](/blog/SQL-practice/lesson-5.png)

### Lesson 6

![lesson-6](/blog/SQL-practice/lesson-6.png)

### Lesson 13

![lesson-13](/blog/SQL-practice/lesson-13.png)

### Lesson 14

![lesson-14](/blog/SQL-practice/lesson-14.png)

### Lesson 15

![lesson-15](/blog/SQL-practice/lesson-15.png)

### Lesson 16

![lesson-16](/blog/SQL-practice/lesson-16.png)

### Lesson 17

![lesson-17](/blog/SQL-practice/lesson-17.png)

### Lesson 18

![lesson-18](/blog/SQL-practice/lesson-18.png)