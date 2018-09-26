<pre>
               _____ _     _             _____                     
              / ____| |   (_)           |  __ \                    
             | (___ | |__  _ _ __  _   _| |__) | __ _____  ___   _ 
              \___ \| '_ \| | '_ \| | | |  ___/ '__/ _ \ \/ / | | |
              ____) | | | | | | | | |_| | |   | | | (_) >  <| |_| |
             |_____/|_| |_|_|_| |_|\__, |_|   |_|  \___/_/\_\\__, |
                                    __/ |                     __/ |
                                   |___/                     |___/ 

</pre>

[![Build Status](https://travis-ci.org/openanalytics/shinyproxy.svg?branch=master)](https://travis-ci.org/openanalytics/shinyproxy)

# ShinyProxy

Open Source Enterprise Deployment for Shiny Apps

Learn more at https://shinyproxy.io

#### (c) Copyright Open Analytics NV, 2016-2018 - Apache License 2.0

## Building from source

Clone this repository and run

```
mvn -U clean install
```

The build will result in a single `.jar` file that is made available in the `target` directory.

## Running the application

```
java -jar shinyproxy-2.0.3.jar 
```

Navigate to http://localhost:8080 to access the application.  If the default configuration is used, authentication will be done against the LDAP server at *ldap.forumsys.com*; to log in one can use the user name "tesla" and password "password".


## Further information

https://shinyproxy.io


## Docker
 * Build the image
```
docker build -t shinyproxy .
```
 * Tag the image
```
docker tag shinyproxy:latest bbonnin/shinyproxy-saagie:2.0.4
```
 * Run the image
```
docker run  -p 8080:8080 -d --name shinyproxy shinyproxy
```
 > For testing on Mac, maybe it will necessary to start a container for accessing Docker on port 2375
```
docker run -d -v /var/run/docker.sock:/var/run/docker.sock -p 127.0.0.1:2375:2375 bobrik/socat TCP-LISTEN:2375,fork UNIX-CONNECT:/var/run/docker.sock
```