```
# create the directories if they don't already exist
mkdir -p ~/workspace/sample1

# clean up any old content that the tutor may have left lyign around
rm -rf ~/workspace/sample1/*

# make sure that the sample1 directory exists under workspace
cd ~/workspace && ls -alrt

# make sure that the sample1 directory has nothing inside it anymore, so we may start fresh
cd ~/workspace && ls -alrt sample1

# work inside the sample1 directory
cd ~/workspace/sample1

# create the package.json file
echo '{
  "name": "socket-chat-example",
  "version": "0.0.1",
  "description": "my first socket.io app",
  "dependencies": {}
}' >> package.json

# spit out the file to cmd line and make sure its contents look good
cat package.json
```

You may also open the [package.json](open_file sample/package.json) directly for editing.

```
# install a dependency
npm install --save --save-exact express@4.10.2

# create the index.js file
echo "var app = require('express')();
var http = require('http').Server(app);

app.get('/', function(req, res){
  res.send('<h1>Hello world</h1>');
});

http.listen(3000, function(){
  console.log('listening on *:3000');
});" >> index.js
```

You may also open the [index.js](open_file sample/index.js) directly for editing.

Click the `Run App` dropdown option from the menu. This will run result in the code being run from inside a terminal window automatically. And then click the `Box Url` dropdown option to view what we've built so far.