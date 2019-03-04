---
layout: default
title: Web API
nav_order: 2
---

# How to call the [iDempiere micro](https://idempiere-micro.github.io/) microservices through the Web application programming interface (API)
Each of the [iDempiere micro](https://idempiere-micro.github.io/) microservices opens a HTTP endpoint to receive REST and GraphQL calls.

## REST
REST is used to log in the user on the login endpoint `/session/{USERNAME}/login/{PASSWORD}`.

##GraphQL
GraphQL `POST`s can be executed agains the `/graphql` GraphQL endpoint. Each GraphQL call is wrapped in a transaction to ensure data consistency.
