---
layout: default
title: How it works
nav_order: 1
---

# How the [iDempiere micro](https://idempiere-micro.github.io/) microservices work 
The [iDempiere micro](https://idempiere-micro.github.io/) microservices are standalone Java 1.8 applications packaged as self-contained executable JARs.

## Runtime Prerequisities
To run [iDempiere micro](https://idempiere-micro.github.io/) microservices Java Runtime Environment (JRE) 8 or higher e.g. [OpenJDK 8](https://openjdk.java.net/projects/jdk8/) is required.

## Database
The [iDempiere micro](https://idempiere-micro.github.io/) microservices use the same database as [iDempiere](http://www.idempiere.org/). Since not only the same object-relational mapping engine is used, but also the same iDempiere business logic classes are shared between these two project, the data are stored exactly in the same way making them directly usable from the iDempiere User Interface.

## Web API
Each of the [iDempiere micro](https://idempiere-micro.github.io/) microservices opens an HTTP endpoint allowing REST and GraphQL calls to be made.
