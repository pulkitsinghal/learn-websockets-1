a) Stop the already running server by hitting Control+C in the terminal window.

b) Socket.IO is composed of two parts:
b.1) A server that integrates with (or mounts on) the Node.JS HTTP Server: `socket.io`
b.2) A client library that loads on the browser side: `socket.io-client`

c) Run:
```
cd ~/workspace/sample1
npm install --save --save-exact socket.io@1.3.6
```

d) Use it in [index.js](open_file sample/index.js)
```
var app = require('express')();
var http = require('http').Server(app);
var io = require('socket.io')(http); // ~~~~NEW~~~~

app.get('/', function(req, res){
  res.sendFile(__dirname + '/index.html');
});

io.on('connection', function(socket){ // ~~~~NEW~~~~
  console.log('a user connected'); // ~~~~NEW~~~~
}); // ~~~~NEW~~~~

http.listen(3000, function(){
  console.log('listening on *:3000');
});

```

e) In [index.html](open_file sample/index.html), add the following snippet before the `</body>`:
```
<script src="/socket.io/socket.io.js"></script>
<script>
  var socket = io();
</script>
```

f) Click the `Run App` dropdown option from the menu and then click the `Box Url` dropdown option to view what we've built so far.

You should see the console print `a user connected`.
Try opening several tabs, and you’ll see several messages.

g) Stop the already running server by hitting Control+C in the terminal window.

h) Update [index.html](open_file sample/index.html) to track disconnects too:
```
io.on('connection', function(socket){
  console.log('a user connected');
  socket.on('disconnect', function(){ // ~~~~NEW~~~~
    console.log('user disconnected'); // ~~~~NEW~~~~
  }); // ~~~~NEW~~~~
});
```

i) Click the `Run App` dropdown option from the menu and then click the `Box Url` dropdown option to view what we've built so far.

Now if you refresh a tab several times you can see it in action.
```
$ cd ~/workspace/sample1 && node index.js
listening on *:3000
a user connected
user disconnected
a user connected
user disconnected
a user connected
user disconnected
a user connected
```
