+++
title = "CLASS-13: Message Queues"
date = "2022-12-13T22:48:39-08:00"
author = "Kenny W. Lino"
authorTwitter = "" #do not include @
cover = ""
tags = ["message queues"]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
hideComments = false
color = "" #color from the theme settings
draft = false
+++

## Socket.io Chat Example

Based on the [Get started](https://socket.io/get-started/chat/) page from the Socket.IO docs.

1. Explain to a non-technical recruiter what the Chat Example (above) does.

    The Chat Example above walks through how to create a basic chat app using a library called Socket.io. With chat systems, we want to be able to send a message and notify others when there's a new message.

    Socket.io can handle this for us by managing various events, such as 'user connected', 'user disconnected', and when a message is 'sent'. Socket.io is set up to listen to these events, and can trigger (or emit) new events based on other actions. In the case of the Chat Example here, it is set up to emit a message on click of the 'Send' button, and on the recipient side, it is set up to listen for any incoming messages, allowing the user to receive it as soon as it's sent.

2. What proof of life are we getting on the backend from the above app?

    We are using the `io.on('connection`, ...) to trigger a `console.log()` whenever a user connects to the Socket.io() server.

3. Socket.IO gives us the i0.emit() method to send an event to everyone. What flag would you use if you want to send a message to everyone except for a certain emitting socket?

    If we wanted to send a message to everyone except for a certain emitting socket, we use the `broadcast` flag.

    e.g. `socket.broadcast.emit('hi')`

## Rooms

Based on the [Rooms](https://socket.io/docs/v4/rooms) Socket.io documentation.

1. What is a room and how might a room be useful?

    A room is a channel that sockets can choose to join or leave. It allows us to broadcast events to a specific group of clients.

2. How do you join a room?

    To join a room, we call `join` on the socket and pass it the name of a room.

    From the docs:

    ```javascript
    io.on("connection", (socket) => {
        socket.join("room");
    });
    ```

    Use `to` or `in` to broadcast or emit:

    ```javascript
    io.to("room").emit("some event");
    ```

3. how do you leave a room?

    To leave a room, we do the same as `join` but call `leave` instead.

### Namespace

1. What is a Namespace and what does it allow you to do?

    A namespace is a communication channel. It provides us with a way to separate the logic of an application that uses a single shared connection.

2. Each namespace potentially has its own what? (hint: 3 things)

    - event handlers
    - rooms
    - middlewares

3. Discuss a possible use case for separate namespaces.

    One possible use case is when we want to separate sections that only authorized users should be able to access, vs. sections that everyone can access.

### Reflection

1. What are your learning goals after reading and reviewing the class README?

    After reviewing the README, I'm looking forward to seeing how using a queue to handle incoming messages and holding on to them when we're offline could extend to building chat applications.