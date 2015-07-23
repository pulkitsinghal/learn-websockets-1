a) Stop the already running server by hitting Control+C in the terminal window.

b) Let’s make it so that when the user types in a message, the server gets it as a chat message event. The scripts section in [index.html](open_file sample/index.html) should now look as follows:

```
    <script src="/socket.io/socket.io.js"></script>
    <script src="http://code.jquery.com/jquery-1.11.1.js"></script>
    <script>
        var socket = io();
        $('form').submit(function() {
            socket.emit('chat message', $('#m').val()); // send it
            $('#m').val(''); // empty it
            return false; // stops a form from being submitted so that the page does NOT reload automatically
        });
    </script>
```

c) And in [index.js](open_file sample/index.js) we print out the chat message event:
```
io.on('connection', function(socket) {
    console.log('a user connected');
    socket.on('disconnect', function() {
        console.log('user disconnected');
    });
    socket.on('chat message', function(msg) {
        console.log('message: ' + msg);
    });
});
```

d) Click the `Run App` dropdown option from the menu and then click the `Box Url` dropdown option to view what we've built so far.

Here's video from the [original tutorial](http://socket.io/get-started/chat/) of what all you can now do with this sample app: https://i.cloudup.com/transcoded/zboNrGSsai.mp4
