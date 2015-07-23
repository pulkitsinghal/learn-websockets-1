a) Stop the already running server by hitting Control+C in the terminal window.

b) Update [index.js](open_file sample/index.js)
```
    socket.on('chat message', function(msg) {
        console.log('message: ' + msg);
        //socket.broadcast.emit('chat message', msg); // sends to everyone other than the person who sent it
        io.emit('chat message', msg); // send to everyone
    });
```

c) Update [index.html](open_file sample/index.html)
```
        socket.on('chat message', function(msg) {
            $('#messages').append($('<li>').text(msg));
        });
```

d) Click the `Run App` dropdown option from the menu and then click the `Box Url` dropdown option to view what we've built so far.
