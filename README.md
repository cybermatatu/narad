Narad.js
=====

A pusher like nodejs implementation built on top of socket.io(http://socket.io/), to build real time apps.

It is a self hosted replacement of pusher.

It is in beta and not production ready yet.


Installation
============

Dependencies: 
	Node.js(http://nodejs.org/)

	socket.io(http://socket.io/)

	express js(http://expressjs.com/)

After installing the above download the narad code, and cd into the narad folder.

Open the file public/narad.js and replace your host in the 2nd line


```javascript
narad.url = 'http://192.168.0.46:3000'; // replace 192.168.0.46 with your host
```


Start the server 
================

node server.js



Publish data to server
======================

Sent post request to

/publish/:channel_name/:event_name
data = {}


Subscribe to Channels
=====================

include the following javascript files at client

replace host:port by the host and port where you would run naiad

```html
<script src="host:port/socket.io/socket.io.js"></script>
<script src="host:port/narad.js"></script>
```

Subscribing to channels
=======================

```javascript
var channelName = "event";
var eventName = "chat_room"
var channel = narad.subscribe(channelName);
channel.bind(eventName, function (data) {
        console.log("data: ", data);
});
```



Running in Daemon mode
======================

use the forever library

npm install forever -g

(https://github.com/nodejitsu/forever)

in the narad directory

forever start server.js

forever stop server.js




Pending Items
=============

publishing from client

configuring the host url

Adding npm

do not pollute the global namespace

add custom port

Securtiy: Channel authentication

Scalability

Logging


