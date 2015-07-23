```
mkdir -p ~/workspace/sample1/views
touch ~/workspace/sample1/views/home.jade
```

Edit [server.js](open_file sample1/server.js) to look like:
```

var express = require('express'),
    jade = require('jade'),
    app = express.createServer();
```

Open [home.jade](sample1/views/home.jade) for editing

Edit it to have the following content:
```
doctype 5
html
    head
        title Chat
        script(src='https://ajax.googleapis.com/ajax/libs/jquery/1.7.2/jquery.min.js')
        script(src="/socket.io/socket.io.js")
        script(src="script.js")
    body
        div.container
            header
                h1 A Chat application with Node.js and Socket.io
            input(type='text')#pseudoInput
            button#pseudoSet Set Pseudo
            div#chatEntries
            div#chatControls
                input(type='text')#messageInput
                button#submit Send
```
