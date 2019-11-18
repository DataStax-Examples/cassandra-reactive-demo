# Reactive Programming with Apache Cassandra Demo

Full demo application that interacts with Apache Cassandra using the Java DataStax driver, reactive programming and the [Spring Framework](https://spring.io/).

This was used as part of a presentation at [DataStax Accelerate](https://www.datastax.com/accelerate) 2019, the video is available below and walks you through taking an application from synchronous to asynchronous to reactive.

[![YouTube Video Link](https://img.youtube.com/vi/Omck1ZGyUBU/0.jpg)](https://www.youtube.com/watch?v=Omck1ZGyUBU)

Contributor(s): [Alexandre Dutra](https://github.com/adutra), [Cedrick Lunven](https://github.com/clun)

## Objectives
* Demonstrate how to build synchronous, asynchronous, and reactive API services using the Java DataStax Driver

## Project Layout

* `0_common` folder - Contains files shared across all three version of the application such as data models, DSE connection files, spring configuration files, and prepared statements for use with DSE
* `1_sync` folder - Contains the repository and controller for the synchronous version of the application
* `2_async` folder - Contains the repository and controller for the asynchronous version of the application
* `3_reactive` folder - Contains the repository and controller for the reactive version of the application
* [docker_compose.yml](docker-compose.yaml) - A docker compose file which will create a local single node cluster of DSE 6.7 and a DataStax Studio instance.
* [schema.cql](schema.cql) - The CQL schema for the keyspace that needs to be created
* [application.yml](0_common/src/main/resources/application.yml) - The configuration file where you can set your parameters for connecting to the DSE cluster.

## How this Sample Works
This sample contains 3 separate Spring Boot applications and a module that contains shared code between them.  The first application shows
how to develop a synchronous api endpoint against the `Stock` data model schema found in `schema.cql`.  The second application extends
that first application to show how to perform the same tasks asynchronously.  The third application takes that asynchronous application
and modifies it to build it using the reactive programming methods available in the Java DataStax Driver.

For details on how the code works we recommend watching the presentation video from DataStax Accelerate 2019 which explains the differences between the applications.
This can be found here: [https://www.youtube.com/watch?v=Omck1ZGyUBU](https://www.youtube.com/watch?v=Omck1ZGyUBU).

## Setup and Running

### Prerequisites
* Java 11
* Maven
* Either a running DSE 6.7 Cluster or you may start one up using the [docker-compose.yml](docker-compose.yml)
* A keyspace created with the schema from [schema.cql](schema.cql) installed

### Running

**Note:** When running the commands below be sure that you have Java 11 set as your Java version.  If you are not sure you can use `java -version`
on the command line to check the currently configured version.

To build the application:

`mvn clean compile`

**Note:** For the next 4 commands you must have a version of DSE running, the `schema.cql` configured and all the appropriate parameters configured in the  [application.yml](0_common/src/main/resources/application.yml) file.
To run the associated unit tests:

`mvn test`

IntelliJ will automatically detect the 3 Spring Boot applications included as part of this repo and create three run configurations, one for each.

To run the synchronous version of the application run the `SyncApplication` Configuration

To run the asynchronous version of the application run the `AsyncApplication` Configuration

To run the reactive version of the application run the `ReactiveApplication` Configuration

