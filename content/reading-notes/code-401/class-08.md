+++
title = "CLASS-08: Access Control (ACL)"
date = "2022-12-05T22:05:42-08:00"
author = "Kenny W. Lino"
authorTwitter = "" #do not include @
cover = ""
tags = ["access control"]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
hideComments = false
color = "" #color from the theme settings
draft = false
+++

## 5 Steps to RBAC

Based on the article ["5 steps to simple role-based access control"](https://www.csoonline.com/article/3060780/5-steps-to-simple-role-based-access-control.html) from CSO.

1. What is Role Based Access Control (RBAC) and why do we care?

    RBAC is a way to define a user's system access based on their role within an organization. RBAC is useful because it helps secure important info or system and limits them to only those that need access to it. In systems without RBAC, there's been instances of a single user's credentials causing a whole company's infrastructure to be compromised.

2. Describe a Role/Permission hierarchy that you might implement using RBAC.

    A simple hierarchy might look like the following:

    - Basic -- no access to certain files
    - Admin -- access to everything


3. What approach might you take to implement RBAC?

    The article suggests taking the following 5 steps to implement RBAC.

    1. Inventory your system -- make a list of the data and systems you need to control access to (e.g. e-mail, databases, important folders on a server)
    2. Analyze your workforce and create roles -- look for common patterns of who needs access to what and define simple roles
    3. Assign people to roles
    4. Never make one-off changes - do not make exceptions for a single user; if necessary create new roles.
    5. Audit -- take a look at the roles, the people assigned to them and the permissions they have and update as necessary.

## Wiki - RBAC

Based on the [Wikipedia article](https://en.wikipedia.org/wiki/Role-based_access_control).

1. If Authentication is “you are who you say you are,” what is Authorization?

    Authorization in contrast refers to the access permissions you have-- "Are you allowed to do the thing you're asking to do?"

2. Name three primary rules defined for RBAC.

    The three primary rules defined are:

    1. Role assignment: A user can only use a permission if they have been assigned a role.
    2. Role authorization: A user can only take on roles they are authorized for.
    3. Permission authorization: A user can use a permission only if the permission is authorized for the user's active role(s).

3. Describe RBAC to a non-technical friend.

    RBAC is a way to secure a user system such as at a company by limiting access to users based on their role in the system. For example, in a hospital setting, a receptionist might only be able to see a patient's contact info and appointments, but a doctor would be able to see that and their complete medical record.

## RBAC Tutorial

1. What Are access rights associated with? The User? or The Role? Explain.

    Access rights are associated with the role and not the user. This is by design of RBAC, which strives to keep us from defining permissions per user but instead by common roles. In this way, we can update the permissions for a role and all users assigned / have permissions for that role will be updated as opposed to updating users individually.

2. Access Rights, or Authorization, is activated after a user successfully does what?

    Access rights is activated after a user is successfully *authenticated*. 

3. Explain how RBAC might benefit a business.

    RBAC can be beneficially for likely many businesses as in most cases, everyone should not be able to access the exact same systems and files. For example, a company with a secret recipe or confidential product information would likely want to limit access to very few people, while other information like salary might be more open but still limited to higher management and HR. 

## Reflection

1. What are your learning goals after reading and reviewing the class README?

    After reviewing the README, my learning goals are to learn how to implement RBAC in our back-end and also understand when to give users multiple roles or create roles with overlapping permissions.