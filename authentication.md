---
layout: default
title: Authentication
nav_order: 2
---

# Authentication in the [iDempiere micro](https://idempiere-micro.github.io/) microservices

## Login
The authentication in the [iDempiere micro](https://idempiere-micro.github.io/) microservices is done by calling the REST Login endpoint. The REST Login endpoint is a `GET` HTTP call to the login URL `/session/{USERNAME}/login/{PASSWORD}` where you pass the `USERNAME` and `PASSWORD` parameters in the URL path.

The underlying `UserService` processes the login request and logs the user if the `USERNAME` and `PASSWORD` parameters match the values stored in the iDempiere database. Please note several configuration parameters (similar to the iDempiere configuration parameters) are involved in the process namely:

- `User.password-hash` - if passwords are hashed in the `AD_User` table. Default is `false` being compatible with the iDempiere default installation. Please note however we strongly recommend the passwords to be hashed except for local development environments. If set to `true` the user password (to compare with the value in the database) is first hashed using the SHA512 algorithm with `user.salt` as salt and 1000 iterations.
- `Locking.max-account-lock-minutes` - maximum number of minutes for a user to be locked out after unsuccessful logins
- `Locking.max-inactive-period-day` - maximum number of days the user is allowed not to log in. If the users tries to log in after the period, the account is locked.
- `Locking.max-login-attempt` - maximum number of unsuccessful login attempts before the user is locked.

Please note currently only users with an access to exactly one client are supported. Also please note the `orgId` parameter is not used and set so the functionality to distinguish between different organizations in a client is currently not supported.

When the user is successfully authenticated a JSON Web Token (JWT) is returned. 

## JSON Web Token (JWT)
The JSON Web Token is used to authorize all the GraphQL calls to a [iDempiere micro](https://idempiere-micro.github.io/) microservice. The JWT is obtained by a successful login. 