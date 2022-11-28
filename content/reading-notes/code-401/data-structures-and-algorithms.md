+++
title = "Data Structures & Algorithms"
date = "2022-11-24T17:49:32-08:00"
author = "Kenny W. Lino"
authorTwitter = "" #do not include @
cover = ""
tags = ["dsa"]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
hideComments = false
color = "" #color from the theme settings
draft = false
+++

## Videos

- [Recursion in software development](https://www.youtube.com/watch?v=vPEJSJMg4jY)
- [DATA STRUCTURES you MUST know (as a Software Developer)](https://www.youtube.com/watch?v=sVxBVvlnJsM)
- [Big O Notation](https://www.youtube.com/watch?v=v4cd1O4zkGw)

## Articles

- [8 Common Data Structures every Programmer must know](https://towardsdatascience.com/8-common-data-structures-every-programmer-must-know-171acf6a1a42)
- [Why you should learn Big-O and stop hacking your way through algorithms](https://triplebyte.com/blog/why-you-should-learn-big-o-and-stop-hacking-your-way-through-algorithms)

## Why this topic matters

This topic is important as we work with different types of data and learn how to manage them best in our applications. DS&A is also an important part of interviewing, so having strong knowledge in it will allow us to be better prepared.

## Discussion questions

1. What is 1 of the more important things you should consider when deciding which data structure is best suited to solve a particular problem?

    When considering which data structure is best suited to solve a particular problem, we should consider the size of the data and the operations we intend to do most frequently with the data. That is because certain data structures require more time to do functions like a `get` or `add` / `delete` while others can be more efficient. 

2. How can we ensure that we’ll avoid an infinite recursive call stack?

    We can make sure to avoid an infinite recursive call stack by having a base case and a recursive case. The base case will allow us to exit the call stack once we've got what we needed, and the recursive call will call the function itself until we trigger the base case.
