# Reading Connection Details
---


## About
---

This example demonstrates how to read important connection information. Connection information may include things like usage statistics, client remote address, client protocol information etc. This can be particularly useful if you are interested in measuring usage by clients or where the clients are coming from etc.

For more information you can browse through the [IConnection](#http://red5.org/javadoc/red5-server-common/index.html?org/red5/server/api/class-use/IConnection.html) javaDocs.



## Build & Deploy
---

### Build
---

To build this application : open a shell prompt in the application's project directory (where the pom.xml file resides). run the following maven command in your shell -> 

``` 
mvn clean package 

```

The above command will generate a `war` file in the `target` directory inside the project directory. 


### Deploy
---

To deploy the war to red5 / red5 pro server :

1. Stop server if it is running.

2. Extract the content of the `war file` to directory by war name. 

> The java war file is simply a `archive file` similar to `zip` format. you can extract it using a archive tool such as [7zip](#http://www.7-zip.org/), [Winrar trial](#http://www.rarlab.com/download.htm) etc

3. Copy the folder into `RED5_HOME/webapps/` directory.

4. Start server.




## How To Use Example
---

In this example we call the method `logConnectionStatistics` whenever a client disconnects from the application. The method logs out necessary information such as data usage, client remote address , server host used to connect, protocol used, connection parameters used while connecting etc:


Given below is a sample output from the console when a RTMP client exits.

```

[INFO] [NioProcessor-2] org.red5.connection.examples.stats.Application - Client disconnect RTMPMinaConnection from 127.0.0.1 (in: 540933 out: 3564) session: 8FVJYOWBS4RRM state: disconnecting
[INFO] [NioProcessor-2] org.red5.connection.examples.stats.Application - Client connection Id : 8FVJYOWBS4RRM
[INFO] [NioProcessor-2] org.red5.connection.examples.stats.Application - Client connection protocol : rtmp
[INFO] [NioProcessor-2] org.red5.connection.examples.stats.Application - Client connection host : localhost
[INFO] [NioProcessor-2] org.red5.connection.examples.stats.Application - Client connection address : 127.0.0.1
[INFO] [NioProcessor-2] org.red5.connection.examples.stats.Application - Client connection last ping : 1
[INFO] [NioProcessor-2] org.red5.connection.examples.stats.Application - Client connection path : connection-statistics-demo
[INFO] [NioProcessor-2] org.red5.connection.examples.stats.Application - Connection parameters passed by client : {app=connection-statistics-demo, flashVer=WIN 26,0,0,131, swfUrl=http://rajdeeprath.github.io/red5-server/demos/publisher.swf, tcUrl=rtmp://localhost/connection-statistics-demo, fpad=false, capabilities=239.0, audioCodecs=3575.0, videoCodecs=252.0, videoFunction=1.0, pageUrl=http://rajdeeprath.github.io/red5-server/demos/publisher.html, objectEncoding=0.0, path=connection-statistics-demo}
[INFO] [NioProcessor-2] org.red5.connection.examples.stats.Application - Bytes read from client : 540933
[INFO] [NioProcessor-2] org.red5.connection.examples.stats.Application - Bytes written to client : 3564
[INFO] [NioProcessor-2] org.red5.connection.examples.stats.Application - Messages read from connection : 257
[INFO] [NioProcessor-2] org.red5.connection.examples.stats.Application - Messages written to connection : 9
[INFO] [NioProcessor-2] org.red5.connection.examples.stats.Application - Messages dropped : 0

```


You can connect to the application using a RTMP or RTSP (Android/IOS) or WebRTC (Red5Pro HTML5 SDK) type client. You can then broadcast / subscribe a stream for a few seconds and then close the client. The application will log out your connection details in the console.



## Eclipse
---

You can edit the server side code in your eclipse JEE IDE such as Luna, Mars, Neon etc. To import the code into your IDE:

1. Navigate to the repository folder
2. Execute maven command `mvn eclipse:eclipse`. This will generate files necessary for eclipse to read the maven project properly.
3. In eclipse go to `File -> Import -> Existing Maven Projects` and click `Next`.
4. Browse and select `the project root` and Click `Finish` to import the project.



## Additional Notes
---

NA



