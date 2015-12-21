Module管理
----
[node-red-admin](https://github.com/node-red/node-red-admin)
`npm install -g node-red-admin`

Bluemix Module List
---
`npm install node-red-bluemix-nodes`

#loop
https://www.ibm.com/developerworks/community/blogs/hickmat/entry/nodered_loop?lang=en

#Global Variable
context.global.foo = "bar";
http://nodered.org/docs/writing-functions.html

#Database 
[sqldb-dashdb](http://flows.nodered.org/node/node-red-nodes-cf-sqldb-dashdb`)
`npm install node-red-nodes-cf-sqldb-dashdb`
[Blog](http://blog.4loeser.net/2015/04/my-10-minute-db2-app-on-bluemix.html)
#SQLDB
```json
[{"id":"5f7d29ff.a082d8","type":"cloudant out","service":"intel-ants-node-red-cloudantNoSQLDB","cloudant":"","name":"bike-register(owner, bike, passcode, expire)","database":"elock","payonly":true,"operation":"insert","x":601.9166641235352,"y":812.7221183776855,"z":"d9fe84c2.260178","wires":[]},{"id":"70278548.8fd87c","type":"http in","name":"","url":"/elock/register","method":"post","swaggerDoc":"","x":92.5,"y":814.6666374206543,"z":"d9fe84c2.260178","wires":[["24dbc921.db2436","88a30b2e.775cf8"]]},{"id":"55cab58a.aa354c","type":"http in","name":"","url":"/elock/disapprove","method":"post","swaggerDoc":"","x":105.16666412353516,"y":1143.4447011947632,"z":"d9fe84c2.260178","wires":[["668c82a6.99737c","a908d5ab.56f728"]]},{"id":"7c7bc5fb.83843c","type":"cloudant out","service":"intel-ants-node-red-cloudantNoSQLDB","cloudant":"","name":"bike-disapprove(user, bike)","database":"elock","payonly":true,"operation":"delete","x":691.3809623718262,"y":1136.7937870025635,"z":"d9fe84c2.260178","wires":[]},{"id":"94896711.6b7698","type":"cloudant out","service":"intel-ants-node-red-cloudantNoSQLDB","cloudant":"","name":"bike-approve(user, bike)","database":"elock","payonly":true,"operation":"insert","x":665.4364280700684,"y":954.4445114135742,"z":"d9fe84c2.260178","wires":[]},{"id":"84f5da08.7b0a28","type":"http in","name":"","url":"/elock/approve","method":"post","swaggerDoc":"","x":97.83333587646484,"y":957.777928352356,"z":"d9fe84c2.260178","wires":[["d1f2f2e4.2e0d1","3f56cf4a.c0a93","3a8160fd.c57ea"]]},{"id":"24dbc921.db2436","type":"function","name":"Register","func":"msg.response = \"SUCCESS\";\nreturn {payload:{\n    ID: 1,\n    USER: msg.payload.userFbId,\n    BIKE: msg.payload.bikeUUID,\n    OWNER: msg.payload.userFbId,\n    EXPIRETIME: Date.now()/1000+3600*24*365*5,\n    PASSCODE: \"NULL\"    \n}};\n","outputs":1,"noerr":0,"x":283.24998474121094,"y":820.0000610351562,"z":"d9fe84c2.260178","wires":[["5f7d29ff.a082d8","19a736aa.e658c9"]]},{"id":"d1f2f2e4.2e0d1","type":"function","name":"Approve","func":"msg.response = \"SUCCESS\";\nreturn {payload:{\n    ID: 1,\n    USER: msg.payload.userFbId,\n    BIKE: msg.payload.bikeUUID,\n    OWNER: msg.payload.ownerFbId,\n    EXPIRETIME: Date.now()/1000+3600*24,\n    PASSCODE: \"NULL\"    \n}};\n","outputs":1,"noerr":0,"x":339.2619438171387,"y":954.8889598846436,"z":"d9fe84c2.260178","wires":[["bfd6c697.402938"]]},{"id":"cda992df.32567","type":"function","name":"Disapprove","func":"msg.response = \"SUCCESS\";\nreturn {payload:{\n    ID: 1,\n    USER: msg.payload.userFbId,\n    BIKE: msg.payload.bikeUUID,\n    OWNER: msg.payload.ownerFbId,\n    // EXPIRETIME: Date.now()/1000+3600*24,\n    PASSCODE: \"NULL\"    \n}};","outputs":1,"noerr":0,"x":383.3809127807617,"y":1136.1905555725098,"z":"d9fe84c2.260178","wires":[[]]},{"id":"19a736aa.e658c9","type":"sqldb out","service":"elock-sql","table":"DATA","name":"","x":487,"y":781,"z":"d9fe84c2.260178","wires":[]},{"id":"bfd6c697.402938","type":"sqldb out","service":"elock-sql","table":"DATA","name":"","x":606.5715026855469,"y":920.0953121185303,"z":"d9fe84c2.260178","wires":[]},{"id":"584648c4.a7b9b8","type":"sqldb out","service":"elock-sql","table":"DATA","name":"","x":539.190372467041,"y":1203.571499824524,"z":"d9fe84c2.260178","wires":[]},{"id":"3f56cf4a.c0a93","type":"sqldb in","service":"elock-sql","query":"SELECT COUNT (*) from DATA \nwhere BIKE = ?\nAND OWNER =?\nAND USER = ?","params":"msg.payload.bikeUUID,msg.payload.ownerFbId,msg.payload.userFbId","name":"EXIST?","x":337.00000762939453,"y":1026.4761791229248,"z":"d9fe84c2.260178","wires":[[]]},{"id":"668c82a6.99737c","type":"sqldb in","service":"elock-sql","query":"DELETE * from DATA \nwhere BIKE = ?\nAND OWNER =?\nAND USER = ?","params":"msg.payload.bikeUUID,msg.payload.ownerFbId,msg.payload.userFbId","name":"REMOVE","x":357.80956268310547,"y":1204.2856121063232,"z":"d9fe84c2.260178","wires":[["584648c4.a7b9b8","b4d43d26.4b2bc"]]},{"id":"26d02cf7.d92fd4","type":"debug","name":"","active":true,"console":"false","complete":"response","x":708.3334197998047,"y":1070.0000829696655,"z":"d9fe84c2.260178","wires":[]},{"id":"3a8160fd.c57ea","type":"function","name":"msg","func":"msg.response = \"approve request\";\nreturn msg;\n","outputs":1,"noerr":0,"x":479.9999542236328,"y":1006.6666660308838,"z":"d9fe84c2.260178","wires":[["26d02cf7.d92fd4","47426c81.b8bd94"]]},{"id":"a908d5ab.56f728","type":"function","name":"msg","func":"msg.response = \"disapprove request\";\nreturn msg;\n","outputs":1,"noerr":0,"x":479.9999580383301,"y":1090.0000019073486,"z":"d9fe84c2.260178","wires":[["26d02cf7.d92fd4","47426c81.b8bd94"]]},{"id":"47426c81.b8bd94","type":"http response","name":"","x":694.9999656677246,"y":1016.6666469573975,"z":"d9fe84c2.260178","wires":[]},{"id":"b4d43d26.4b2bc","type":"debug","name":"","active":true,"console":"false","complete":"true","x":555.0000038146973,"y":1258.3333826065063,"z":"d9fe84c2.260178","wires":[]}]
```

#Settings file
$HOME/.node-red/settings.js

#Watson: Text-to-Speech (using Websocket)
http://flows.nodered.org/flow/69782a1b2e814ac5e57d