```
touch ~/workspace/sample1/server.js
```

Open [server.js](open_file sample1/server.js) for editing

Edit it to have the following content:
```
/*
 * (1) Set up the server
 */
var express = require('express'),

    app = express.createServer();

/*
 * (2) Send a "public" folder which will contain
 * JavaScript, CSS and image files.
 */
app.set('views', __dirname + '/views');
app.set('view engine', 'jade');
app.set("view options", { layout: false });
app.configure(function() {
    app.use(express.static(__dirname + '/public'));
});

/*
 * (3) Set a default route
 */
app.get('/', function(req, res){
  res.render('home.jade');
});

/*
 * (4)Start the server
 */
app.listen(3000);
```
