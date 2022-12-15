+++
title = "CLASS 12: Socket.io"
date = "2022-12-13T08:11:40-08:00"
author = "Kenny W. Lino"
authorTwitter = "" #do not include @
cover = ""
tags = ["socket.io"]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
hideComments = false
color = "" #color from the theme settings
draft = false
+++

## Web Sockets

Based on the [WebSocket](https://en.wikipedia.org/wiki/WebSocket) Wikipedia article.

1. What is a Web Socket?

    WebSocket is a communications protocol that allows for communication between a web browser/client and server. Unlike HTTP, we get "full-duplex communication" meaning we can have real-time back-and-forth.

2. Describe the Web Socket request/response handshake and what happens once the connection is established.

    The Web Socket request/response handshake works by starting with an HTTP request/response using the Upgrade headers on the request object to indicate Websocket usage. When the request is received by the server and the connection is established, communication changes to a bidirectional binary protocol.

3. Web Sockets provide a standardized way for the server to send content to a client without first receiving a **request** from that client.

## Socket.io Tutorial

Based on the TutorialsPoint [Socket.io](https://www.tutorialspoint.com/socket.io/socket.io_hello_world.htm) page.

1. What does the event handler io.on() do?

    The `io.on()` event handler is responsible for handling connections or disconnections, etc. whenever a certain event is triggered.

2. Describe some possible proof of life or proof that the code works as expected.

    For socket.io to work, we need to set up a basic Express server. We can create a basic event for connection/disconnection and `console.log()` whenever either event works. 

    Example code taken from [Hello World](https://www.tutorialspoint.com/socket.io/socket.io_hello_world.htm) section of the tutorial.

    ```javascript
    const app = require('express')();
    const http = require('http').Server(app);
    const io = require('socket.io')(http);

    app.get('/', function(req, res){ res.sendFile('E:/test/index.html');
    });

    //Whenever someone connects this gets executed
    io.on('connection', function(socket){
        console.log('A user connected');
    
        //Whenever someone disconnects this piece of code executed
        socket.on('disconnect', function () {
            console.log('A user disconnected');
        });
    });

    http.listen(3000, function(){
        console.log('listening on *:3000');
    });
    ```

3.What does socket.emit() do?

`socket.emit()` allows us to create and fire custom events.

### Socket.io vs Web Sockets

Based on this [article](https://www.educba.com/websocket-vs-socket-io/)

1. What is the difference between WebSocket and Socket.IO? (think Git and GitHub, or OAuth and Auth0).

    WebSocket is the protocol that defines how bi-directional communication occurs between the client and server, while Socket.IO is a library that takes advantage of WebSocket.

2. When would you use Socket.IO?

    It would be better to use Socket.IO for when we need features like broadcasting or in general when we want to abstract away the WebSocket connections and focus on events.

3. When would you use WebSockets?

    WebSockets are useful for when we need an open connection between the client and server.

### OSI Model Explained

Based on this [video](https://www.youtube.com/watch?v=vv4y_uOneC0).

1. What are a couple of key takeaways from this video?

    The Open System Interconnection model was defined by the ISO in 1984 to make sure computers communicated with each other in a standard way.

    There are 7 layers that define how computers handle or interact with data at different points including:

    1. Application
    2. Presentation
    3. Session
    4. Transport
    5. Network
    6. Data link
    7. Physical