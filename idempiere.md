---
layout: default
title: iDempiere relation
nav_order: 7
---

# iDempiere to [iDempiere micro](https://idempiere-micro.github.io/) microservices relation

[iDempiere micro](https://idempiere-micro.github.io/) microservices are a separate project creating a set of microservices to provide front-end developers a stable and working backend with all the advanced ERP functionality like

- products
- price lists
- orders
- quantity on hand

being in the same time compatible with [iDempiere](http://www.idempiere.org/), an open source Enterprise Resource Planning (ERP) software with also customer relationship management (CRM) and supply chain management (SCM) functions.

## Why?
The iDempiere micro project was created because the current [integration points](http://wiki.idempiere.org/en/Main_Page) were not sufficient to create a separate web application in e.g. Angular, React or even Elm or to provide the users with a mobile experience.
This does not mean that the iDempiere integration point are not useful or could not work in other projects.

## How?
We forked the business logic of iDempiere, the [org.adempiere.base project](https://bitbucket.org/idempiere/idempiere/src/551a9203bf1be05d3b81de0fd97bc0ea3caf66a6/org.adempiere.base/?at=default). We divided the project into smaller parts like [Tax](https://github.com/iDempiere-micro/idempiere-micro-tax-core). Those are the core libraries you can use later e.g. to combine them to an application like [standalone iDempiere Micro All-In-One OpenLiberty Java EE 8 microservice ](https://github.com/iDempiere-micro/idempiere-micro-liberty-standalone).

## OSGi?
The OSGi Framework is a great framework to write huge complex extensible applications like iDempiere. Each of the bundles can be seen as a separate microservice easily communicating with the other bundles.
However we decided not to use any runtime environment and produce self-contained JAR file capable running inside a Docker image with just a JRE installed.

## Cloud? Serverless?
Absolutely! The [standalone iDempiere Micro All-In-One OpenLiberty Java EE 8 microservice ](https://github.com/iDempiere-micro/idempiere-micro-liberty-standalone) can be already deployed to  
a Cloud Foundry environment like e.g. IBM Cloud.
For some parts we are also considering real serverless lambdas to allow predictable running times and costs.
