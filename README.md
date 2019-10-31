# Apache Cassandra® Reactive Demo

A demo application that interacts with Apache Cassandra® using the DSE Java driver and reactive programming.

This application was used as part of a presentation at DataStax Accelerate 2019, the video is available here:
[![YouTube Video Link](https://img.youtube.com/vi/Omck1ZGyUBU/0.jpg)](https://www.youtube.com/watch?v=Omck1ZGyUBU)

Contributors [Alexandre Dutra](https://github.com/adutra), [Cedrick Lunven](https://github.com/clun)

## Objectives
* To demonstrate how to build synchronous, asynchronous, and reactive API services using v2 of the DataStax Java Driver

## Project Layout

* `0_common` folder - 
* `1_sync` folder - 
* `2_async` folder - 
* `3_reactive` folder - 
* [docker_compose.yml](docker-compose.yaml) - A docker compose file which will create a local single node cluster of DSE 6.7 and a DataStax Studio instance.
* [schema.cql](schema.cql) - The CQL schema for the keyspace that needs to be created
* [application.yml](0_common/src/main/resources/application.yml) - The configuration file where you can set your parameters for connecting to the DSE cluster.

## How this Sample Works

## Setup and Running

### Prerequisites
* Java 11
* Either a running DSE 6.7 Cluster or you may start one up using the [docker-compose.yml](docker-compose.yml)
* A keyspace created with the schema from [schema.cql](schema.cql) installed

### Running
