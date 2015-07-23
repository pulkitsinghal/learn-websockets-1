a) Stop the already running server by hitting Control+C in the terminal window.

b) Refactor the route handler in [index.js](open_file sample/index.js) to use sendFile instead:
```
app.get('/', function(req, res){
  res.sendFile(__dirname + '/index.html');
});
```

c) Create an index.html file:
```
echo '<!doctype html>
<html>
  <head>
    <title>Socket.IO chat</title>
    <style>
      * { margin: 0; padding: 0; box-sizing: border-box; }
      body { font: 13px Helvetica, Arial; }
      form { background: #000; padding: 3px; position: fixed; bottom: 0; width: 100%; }
      form input { border: 0; padding: 10px; width: 90%; margin-right: .5%; }
      form button { width: 9%; background: rgb(130, 224, 255); border: none; padding: 10px; }
      #messages { list-style-type: none; margin: 0; padding: 0; }
      #messages li { padding: 5px 10px; }
      #messages li:nth-child(odd) { background: #eee; }
    </style>
  </head>
  <body>
    <ul id="messages"></ul>
    <form action="">
      <input id="m" autocomplete="off" /><button>Send</button>
    </form>
  </body>
</html>' >> index.html
```

You may also open the [index.html](open_file sample/index.html) directly for editing.

d) Click the `Run App` dropdown option from the menu and then click the `Box Url` dropdown option to view what we've built so far.