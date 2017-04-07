# api documentation for  [node-ipc (v8.10.3)](http://riaevangelist.github.io/node-ipc/)  [![npm package](https://img.shields.io/npm/v/npmdoc-node-ipc.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-node-ipc) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-node-ipc.svg)](https://travis-ci.org/npmdoc/node-npmdoc-node-ipc)
#### A nodejs module for local and remote Inter Process Communication (IPC), Neural Networking, and able to facilitate machine learning.

[![NPM](https://nodei.co/npm/node-ipc.png?downloads=true)](https://www.npmjs.com/package/node-ipc)

[![apidoc](https://npmdoc.github.io/node-npmdoc-node-ipc/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-node-ipc_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-node-ipc/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-node-ipc/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-node-ipc/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Brandon Nozaki Miller"
    },
    "bugs": {
        "url": "https://github.com/RIAEvangelist/node-ipc/issues"
    },
    "dependencies": {
        "colors": "*",
        "event-pubsub": "4.2.3",
        "js-message": ">=1.0.5",
        "js-queue": ">=2.0.0"
    },
    "description": "A nodejs module for local and remote Inter Process Communication (IPC), Neural Networking, and able to facilitate machine learning.",
    "devDependencies": {
        "codacy-coverage": "^2.0.0",
        "istanbul": "^0.4.1",
        "jasmine": "^2.4.1",
        "node-cmd": ">=1.2.0"
    },
    "directories": {
        "example": "example"
    },
    "dist": {
        "shasum": "223bd431ad7fb2e40c5434f8a5e4558be2568fbd",
        "tarball": "https://registry.npmjs.org/node-ipc/-/node-ipc-8.10.3.tgz"
    },
    "engines": {
        "node": ">=4.0.0"
    },
    "gitHead": "e79e8064f40f43d23e2443bb0c1f946e87495187",
    "homepage": "http://riaevangelist.github.io/node-ipc/",
    "keywords": [
        "IPC",
        "Neural Networking",
        "Machine Learning",
        "inter",
        "process",
        "communication",
        "unix",
        "windows",
        "win",
        "socket",
        "TCP",
        "UDP",
        "domain",
        "sockets",
        "threaded",
        "communication",
        "multi",
        "process",
        "shared",
        "memory"
    ],
    "license": "DBAD",
    "main": "node-ipc.js",
    "maintainers": [
        {
            "name": "riaevangelist",
            "email": "brandon@diginow.it"
        }
    ],
    "name": "node-ipc",
    "optionalDependencies": {},
    "pre-commit": [
        "cover"
    ],
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/RIAEvangelist/node-ipc.git"
    },
    "scripts": {
        "cover": "istanbul cover -x **/spec/** -dir ./spec/coverage jasmine",
        "coverup": "cat ./spec/coverage/lcov.info | codacy-coverage",
        "test": "istanbul cover -x **/spec/** -dir ./spec/coverage jasmine",
        "test-windows": "istanbul cover -x **/spec/** -dir ./spec/coverage ./node_modules/jasmine/bin/jasmine.js"
    },
    "version": "8.10.3"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module node-ipc](#apidoc.module.node-ipc)
1.  boolean <span class="apidocSignatureSpan">node-ipc.</span>server
1.  [function <span class="apidocSignatureSpan">node-ipc.</span>IPC ()](#apidoc.element.node-ipc.IPC)
1.  [function <span class="apidocSignatureSpan">node-ipc.</span>connectTo (id, path, callback)](#apidoc.element.node-ipc.connectTo)
1.  [function <span class="apidocSignatureSpan">node-ipc.</span>connectToNet (id, host, port, callback)](#apidoc.element.node-ipc.connectToNet)
1.  [function <span class="apidocSignatureSpan">node-ipc.</span>disconnect (id)](#apidoc.element.node-ipc.disconnect)
1.  [function <span class="apidocSignatureSpan">node-ipc.</span>log ()](#apidoc.element.node-ipc.log)
1.  [function <span class="apidocSignatureSpan">node-ipc.</span>serve (path, callback)](#apidoc.element.node-ipc.serve)
1.  [function <span class="apidocSignatureSpan">node-ipc.</span>serveNet (host, port, UDPType, callback)](#apidoc.element.node-ipc.serveNet)
1.  object <span class="apidocSignatureSpan">node-ipc.</span>config
1.  object <span class="apidocSignatureSpan">node-ipc.</span>eventParser
1.  object <span class="apidocSignatureSpan">node-ipc.</span>of

#### [module node-ipc.eventParser](#apidoc.module.node-ipc.eventParser)
1.  [function <span class="apidocSignatureSpan">node-ipc.eventParser.</span>format (message)](#apidoc.element.node-ipc.eventParser.format)
1.  [function <span class="apidocSignatureSpan">node-ipc.eventParser.</span>parse (data)](#apidoc.element.node-ipc.eventParser.parse)
1.  string <span class="apidocSignatureSpan">node-ipc.eventParser.</span>delimiter



# <a name="apidoc.module.node-ipc"></a>[module node-ipc](#apidoc.module.node-ipc)

#### <a name="apidoc.element.node-ipc.IPC"></a>[function <span class="apidocSignatureSpan">node-ipc.</span>IPC ()](#apidoc.element.node-ipc.IPC)
- description and source-code
```javascript
class IPC{
    constructor(){
        Object.defineProperties(
            this,
            {
                config      : {
                    enumerable:true,
                    writable:true,
                    value:new Defaults
                },
                connectTo   : {
                    enumerable:true,
                    writable:false,
                    value:connect
                },
                connectToNet: {
                    enumerable:true,
                    writable:false,
                    value:connectNet
                },
                disconnect  : {
                    enumerable:true,
                    writable:false,
                    value:disconnect
                },
                serve       : {
                    enumerable:true,
                    writable:false,
                    value:serve
                },
                serveNet    : {
                    enumerable:true,
                    writable:false,
                    value:serveNet
                },
                of          : {
                    enumerable:true,
                    writable:true,
                    value:{}
                },
                server      : {
                    enumerable:true,
                    writable:true,
                    configurable:true,
                    value:false
                },
                log         : {
                    enumerable:true,
                    writable:false,
                    value:log
                }
            }
        );
    }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.node-ipc.connectTo"></a>[function <span class="apidocSignatureSpan">node-ipc.</span>connectTo (id, path, callback)](#apidoc.element.node-ipc.connectTo)
- description and source-code
```javascript
function connect(id, path, callback){
    if(typeof path == 'function'){
        callback=path;
        path=false;
    }

    if(!callback){
        callback=emptyCallback;
    }

    if(!id){
        this.log(
            'Service id required'.warn,
            'Requested service connection without specifying service id. Aborting connection attempt'.notice
        );
        return;
    }

    if(!path){
        this.log(
            'Service path not specified, so defaulting to'.notice,
            'ipc.config.socketRoot + ipc.config.appspace + id'.variable,
            (this.config.socketRoot+this.config.appspace+id).data
        );
        path=this.config.socketRoot+this.config.appspace+id;
    }

    if(this.of[id]){
        if(!this.of[id].socket.destroyed){
            this.log(
                'Already Connected to'.notice,
                id.variable,
                '- So executing success without connection'.notice
            );
            callback();
            return;
        }
        this.of[id].socket.destroy();
    }

    this.of[id] = new Client(this.config,this.log);
    this.of[id].id = id;
    this.of[id].path = path;

    this.of[id].connect();

    callback(this);
}
```
- example usage
```shell
...
    ipc.config.logDepth=5; //default

'''

----
##### connectTo

'ipc.connectTo(id,path,callback);'

Used for connecting as a client to local Unix Sockets and Windows Sockets. ***This is the fastest way for processes on the same
machine to communicate*** because it bypasses the network card which TCP and UDP must both use.

| variable | required | definition |
|----------|----------|------------|
| id       | required |  is the string id of the socket being connected to. The socket with this id is added to the ipc.of object
 when created. |
| path     | optional | is the path of the Unix Domain Socket File, if the System is Windows, this will automatically be converted
 to an appropriate pipe with the same information as the Unix Domain Socket File. If not set this will default to ' ipc.config.socketRoot
 '+' ipc.config.appspace '+' id ' |
...
```

#### <a name="apidoc.element.node-ipc.connectToNet"></a>[function <span class="apidocSignatureSpan">node-ipc.</span>connectToNet (id, host, port, callback)](#apidoc.element.node-ipc.connectToNet)
- description and source-code
```javascript
function connectNet(id, host, port, callback){
    if(!id){
        this.log(
            'Service id required'.warn,
            'Requested service connection without specifying service id. Aborting connection attempt'.notice
        );
        return;
    }
    if(typeof host=='number'){
        callback=port;
        port=host;
        host=false;
    }
    if(typeof host=='function'){
        callback=host;
        host=false;
        port=false;
    }
    if(!host){
        this.log(
            'Server host not specified, so defaulting to'.notice,
            'ipc.config.networkHost'.variable,
            this.config.networkHost.data
        );
        host=this.config.networkHost;
    }

    if(typeof port=='function'){
        callback=port;
        port=false;
    }
    if(!port){
        this.log(
            'Server port not specified, so defaulting to'.notice,
            'ipc.config.networkPort'.variable,
            this.config.networkPort
        );
        port=this.config.networkPort;
    }

    if(typeof callback == 'string'){
        UDPType=callback;
        callback=false;
    }
    if(!callback){
        callback=emptyCallback;
    }

    if(this.of[id]){
        if(!this.of[id].socket.destroyed){
            this.log(
                'Already Connected to'.notice,
                id.variable,
                '- So executing success without connection'.notice
            );
            callback();
            return;
        }
        this.of[id].socket.destroy();
    }

    this.of[id] = new Client(this.config,this.log);
    this.of[id].id = id;
    this.of[id].path = host;
    this.of[id].port = port;

    this.of[id].connect();

    callback(this);
}
```
- example usage
```shell
...
    );

'''

----
##### connectToNet

'ipc.connectToNet(id,host,port,callback)'

Used to connect as a client to a TCP or [TLS socket](https://github.com/RIAEvangelist/node-ipc/tree/master/example/TLSSocket) via
 the network card. This can be local or remote, if local, it is recommended that you use the Unix and Windows Socket Implementaion
 of 'connectTo' instead as it is much faster since it avoids the network card altogether.

For TLS and SSL Sockets see the [node-ipc TLS and SSL docs](https://github.com/RIAEvangelist/node-ipc/tree/master/example/TLSSocket
). They have a few additional requirements, and things to know about and so have their own doc.

| variable | required | definition |
|----------|----------|------------|
...
```

#### <a name="apidoc.element.node-ipc.disconnect"></a>[function <span class="apidocSignatureSpan">node-ipc.</span>disconnect (id)](#apidoc.element.node-ipc.disconnect)
- description and source-code
```javascript
function disconnect(id){
    if(!this.of[id]){
        return;
    }

    this.of[id].explicitlyDisconnected=true;

    this.of[id].off('*','*');
    if(this.of[id].socket){
        if(this.of[id].socket.destroy){
            this.of[id].socket.destroy();
        }
    }

    delete this.of[id];
}
```
- example usage
```shell
...
    );

'''

----
##### disconnect

'ipc.disconnect(id)'

Used to disconnect a client from a Unix, Windows, TCP or TLS socket. The socket and its refrence will be removed from memory and
 the 'ipc.of' scope. This can be local or remote. UDP clients do not maintain connections and so there are no Clients and this method
 has no value to them.

| variable | required | definition |
|----------|----------|------------|
| id       | required | is the string id of the socket from which to disconnect. |
...
```

#### <a name="apidoc.element.node-ipc.log"></a>[function <span class="apidocSignatureSpan">node-ipc.</span>log ()](#apidoc.element.node-ipc.log)
- description and source-code
```javascript
function log(){
    if(this.config.silent){
        return;
    }

    const args=Array.prototype.slice.call(arguments);

    for(let i=0, count=args.length; i<count; i++){
        if(typeof args[i] != 'object'){
            continue;
        }

        args[i]=util.inspect(
            args[i],
            {
                depth:this.config.logDepth,
                colors:this.config.logInColor
            }
        );
    }

    console.log(
        args.join(' ')
    );
}
```
- example usage
```shell
...

#### IPC Methods
These methods are available in the IPC Scope.

----
##### log

'ipc.log(a,b,c,d,e...);'

ipc.log will accept any number of arguments and if 'ipc.config.silent' is not set, it will concat them all with a single space ' '
between them and then log them to the console. This is fast because it prevents any concatenation from happening if the ipc.config
.silent is set ' true '. That way if you leave your logging in place it should have almost no effect on performance.

The log also uses util.inspect You can control if it should log in color as well as the log depth via ' ipc.config '

'''javascript
...
```

#### <a name="apidoc.element.node-ipc.serve"></a>[function <span class="apidocSignatureSpan">node-ipc.</span>serve (path, callback)](#apidoc.element.node-ipc.serve)
- description and source-code
```javascript
function serve(path, callback){
    if(typeof path=='function'){
        callback=path;
        path=false;
    }
    if(!path){
        this.log(
            'Server path not specified, so defaulting to'.notice,
            'ipc.config.socketRoot + ipc.config.appspace + ipc.config.id'.variable,
            (this.config.socketRoot+this.config.appspace+this.config.id).data
        );
        path=this.config.socketRoot+this.config.appspace+this.config.id;
    }

    if(!callback){
        callback=emptyCallback;
    }

    this.server=new Server(
        path,
        this.config,
        log
    );

    this.server.on(
        'start',
        callback
    );
}
```
- example usage
```shell
...

    ipc.disconnect('world');

'''

----
##### serve
'ipc.serve(path,callback);'

Used to create local Unix Socket Server or Windows Socket Server to which Clients can bind. The server can 'emit' events to specific
 Client Sockets, or 'broadcast' events to all known Client Sockets.

| variable | required | definition |
|----------|----------|------------|
| path     | optional | This  is the path of the Unix Domain Socket File, if the System is Windows, this will automatically be converted
 to an appropriate pipe with the same information as the Unix Domain Socket File. If not set this will default to ' ipc.config.socketRoot
 '+' ipc.config.appspace '+' id ' |
| callback | optional | This is a function to be called after the Server has started. This can also be done by binding an event
to the start event like 'ipc.server.on('start',function(){});' |
...
```

#### <a name="apidoc.element.node-ipc.serveNet"></a>[function <span class="apidocSignatureSpan">node-ipc.</span>serveNet (host, port, UDPType, callback)](#apidoc.element.node-ipc.serveNet)
- description and source-code
```javascript
function serveNet(host, port, UDPType, callback){
    if(typeof host=='number'){
        callback=UDPType;
        UDPType=port;
        port=host;
        host=false;
    }
    if(typeof host=='function'){
        callback=host;
        UDPType=false;
        host=false;
        port=false;
    }
    if(!host){
        this.log(
            'Server host not specified, so defaulting to'.notice,
            'ipc.config.networkHost'.variable,
            this.config.networkHost.data
        );
        host=this.config.networkHost;
    }
    if(host.toLowerCase()=='udp4' || host.toLowerCase()=='udp6'){
        callback=port;
        UDPType=host.toLowerCase();
        port=false;
        host=this.config.networkHost;
    }

    if(typeof port=='string'){
        callback=UDPType;
        UDPType=port;
        port=false;
    }
    if(typeof port=='function'){
        callback=port;
        UDPType=false;
        port=false;
    }
    if(!port){
        this.log(
            'Server port not specified, so defaulting to'.notice,
            'ipc.config.networkPort'.variable,
            this.config.networkPort
        );
        port=this.config.networkPort;
    }

    if(typeof UDPType=='function'){
        callback=UDPType;
        UDPType=false;
    }

    if(!callback){
        callback=emptyCallback;
    }

    this.server=new Server(
        host,
        this.config,
        log,
        port
    );

    if(UDPType){
        this.server[UDPType]=true;
        if(UDPType === "udp4" && host === "::1") {
            // bind udp4 socket to an ipv4 address
            this.server.path = "127.0.0.1";
        }
    }

    this.server.on(
        'start',
        callback
    );
}
```
- example usage
```shell
...

***examples*** arguments can be ommitted solong as they are still in order.

default tcp server

'''javascript

    ipc.serveNet();

'''

default udp server

'''javascript
...
```



# <a name="apidoc.module.node-ipc.eventParser"></a>[module node-ipc.eventParser](#apidoc.module.node-ipc.eventParser)

#### <a name="apidoc.element.node-ipc.eventParser.format"></a>[function <span class="apidocSignatureSpan">node-ipc.eventParser.</span>format (message)](#apidoc.element.node-ipc.eventParser.format)
- description and source-code
```javascript
function formatData(message){
    if(!message.data && message.data!==false && message.data!==0){
        message.data={};
    }
    if(message.data['_maxListeners']){
        message.data={};
    }

    message=message.JSON+parser.delimiter;
    return message;
}
```
- example usage
```shell
...
let message=new Message;
message.type=type;
message.data=data;

if(this.config.rawBuffer){
    message=new Buffer(type,this.config.encoding);
}else{
    message=eventParser.format(message);
}

if(!this.config.sync){
    this.socket.write(message);
    return;
}
...
```

#### <a name="apidoc.element.node-ipc.eventParser.parse"></a>[function <span class="apidocSignatureSpan">node-ipc.eventParser.</span>parse (data)](#apidoc.element.node-ipc.eventParser.parse)
- description and source-code
```javascript
function parseDataEvents(data){
    let events=data.split(parser.delimiter);
    events.pop();
    return events;
}
```
- example usage
```shell
...
            if(data.slice(-1)!=eventParser.delimiter || data.indexOf(eventParser.delimiter) == -1){
client.log('Messages are large, You may want to consider smaller messages.');
return;
            }

            this.ipcBuffer='';

            const events = eventParser.parse(data);
            const eCount = events.length;
            for(let i=0; i<eCount; i++){
let message=new Message;
message.load(events[i]);

client.log('detected event', message.type, message.data);
client.publish(
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
