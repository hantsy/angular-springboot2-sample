![Build Client](https://github.com/hantsy/angular-spring-reactive-sample/workflows/Client/badge.svg)
![Build Server Side](https://github.com/hantsy/angular-spring-reactive-sample/workflows/Server/badge.svg)

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Angular Spring Reactive Sample](#angular-spring-reactive-sample)
  - [Project structure](#project-structure)
  - [Build](#build)
    - [Server](#server)
    - [Client](#client)
  - [Contribute](#contribute)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

I've also created a series of  projects to demo Angular and Spring WebFlux using other protocols:

* [Angular and Websocket sample](https://github.com/hantsy/angular-spring-websocket-sample)
* [Angular and Server Sent Event  sample](https://github.com/hantsy/angular-spring-sse-sample)
* [Angular and RSocket  sample](https://github.com/hantsy/angular-spring-rsocket-sample)

# Angular Spring Reactive Sample

This application demonstrate building backend RESTful APIs with the newest Reactive stack introduced in Spring 5, and creating the frontend SPA with Angular 5.

**Read the [comprehensive step by step guide](GUIDE.md) to get more details**.

## Project structure

* client - The client application built with Angular CLI.
* server - The backend RESTful APIs.


## Build and Run

Clone the source codes into your local system.

```
git clone https://github.com/hantsy/angular-spring-reactive-sample
```

### Server 

The backend is a Spring Boot based application, make sure you have installed the following software:

* Apache Maven
* Oracle JDK 8
* Docker & Docker Compose 

There is a *docker-compose.yml* file in the project root folder. 

Starts up required MongoDb and Reids service in the background by executing the following command.

```
docker-compose up
```

> NOTE: You can also install a local MongoDb and Redis instead of using Docker.

Then run the application by Spring boot maven plugin directly.

```
mvn spring-boot:run
```

### Client

The **client** application is generated by Angular CLI. 

Enter **client** folder, execute the following command to run the frontend UI.

```
npm install
npm run start
```

Open your favorite browser, and navigate to http://localhost:4200.

## CORS

By default, I do not use a CORS config to run the Server side in this sample application. 

But if you do not like to use a `proxy.conf.js` in the Angular config, follow the following steps to active cors support in the backend, and connect to the backend directly in the client side.

### Server

Activate the **cors** profile when running the Spring Boot application.

```bash
java -jar target/app.jar --spring.profiles.active=cors
```

### Client

There is a standalone configuration added to connect the backend directly.

```bash
npm run start:cors
```

## Contribute

Welcome to contribute this project.  If you have some ideas do not hesitate to file an issue or send a PR directly.
