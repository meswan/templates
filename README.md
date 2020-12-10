![](https://github.com/OpenLiberty/open-liberty/blob/master/logos/logo_horizontal_light_navy.png)

This repository contains starter templates for Open Liberty.

## Navigate to the templates directory.
`cd templates`
	
## Choose a template
 - gradle
    - This template contains the core files needed for Open Liberty and Gradle to run.
 - maven
    - This template contains the core files needed for Open Liberty and Maven to run.
  - simple-rest-template	
    - This template contains both Gradle and Maven core files to run a simple greeting REST endpoint.
    - Once started, the endpoint can be reached at http://localhost:9080/app/resource/greeting

## Navigate to the template directory and start the OpenLiberty server in development mode.
```
mvn liberty:dev
or
gradle libertyDev
```

## Docker
 - gradle
```
docker build -t gradle-core-template:1.0-SNAPSHOT ./gradle

docker run -d --name gradle-core-template -p 9080:9080 gradle-core-template:1.0-SNAPSHOT
```
 - maven
```
mvn package

docker build -t maven-core-template:1.0-SNAPSHOT ./maven

docker run -d --name maven-core-template -p 9080:9080 maven-core-template:1.0-SNAPSHOT
```
 - simple-rest-template (maven)
```
mvn package

docker build -t maven-simple-rest-template:1.0-SNAPSHOT ./simple-rest-template

docker run -d --name maven-simple-rest-template -p 9080:9080 maven-simple-rest-template:1.0-SNAPSHOT
```
 - simple-rest-template (gradle)
 
```
docker build -f ./simple-rest-template/Dockerfile-gradle -t gradle-simple-rest-template:1.0-SNAPSHOT ./simple-rest-template

docker run -d --name gradle-simple-rest-template -p 9080:9080 gradle-simple-rest-template:1.0-SNAPSHOT
```