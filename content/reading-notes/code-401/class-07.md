+++
title = "CLASS-07: Bearer Authorization"
date = "2022-12-04T17:24:00-08:00"
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

## Intro to JWT

Based on this [article](https://jwt.io/introduction/).

1. What is a JSON Web Token (JWT)?

    A JWT is a JSON object that securely transmits information between entities in a compact manner.

2. When should we use JSON Web Tokens?

    We should use JSON Web Tokens when we want authorization in our application or for general information exchange.

3. Claims are expected in which structural component of a JWT?

    Claims are expected within the payload portion of the token. Claims can tell us about the entity such as the issuer, expiration time, subject, and audience.

## Are JWTs Secure

Based on this [StackOverflow discussion](https://stackoverflow.com/questions/27301557/if-you-can-decode-jwt-how-are-they-secure).

1. If I get a JWT and I can decode the payload, how can we call that secure?

    We can say that JWT is secure because the private key ensures that the key is authentic. Even if an attacker tried to change the user information in the payload, the receiver would know because the message would not be signed.

2. If sending a JWT, what must sender and receiver both know? Hint, it’s appended in the signature.

    They both need to know the secret.

3. Explain how concatenated content and secret can be sent and received securely to a non-technical recruiter.

    With JWT, the concatenated content and secret can be sent and received securely using a hash function to protect the JWT. A hash function is a special function that transforms the data to prevent attackers from seeing the plain data. When the receiver gets the JWT, they can use the same hash function to decode the JWT along side the secret to get the plain data back.

## JWTs Explain

Based on ["What is JWT ? JSON Web Token Explained"](https://www.youtube.com/watch?v=926mknSW9Lo) video from YouTube.

1. Why use JWT?

    JWT is useful because it's very compact and self-contained, and also because it's an open standard.

2. JWT is Compact and self-contained. Describe how this is useful to a non-technical friend.

    The fact that JWT is compact and self-contained is useful because it saves time when we send the token, allowing us to retrieve data or perform our actions much quicker. It also has all the information about the user we need inside, so we don't waste time querying our database multiple times or gather extra data separately.

3. What are the three components (the structure) of a JWT signature?

    - Header -- tells us what algorithm (e.g. HMAC SHA256, RSA) and the type of token (JWT).
    - Payload -- contains the claims(i.e. the info about the user)
    - Signature -- the signature takes the base64 encoded header and payload along with a secret and uses the algorithm from the header to secure the token

## Reflection

1. What are your learning goals after reading and reviewing the class README?

After reading the README for this lesson, my learning goals are to understand how to use Bearer Tokens for reauthentification and think about ways to use the Sequelize Virtual properties in my own schemas.