---
categories:
- identity-access
consumed_apis:
- cognito-user-pools
- cognito-identity-pools
description: Workflow capability for managing user authentication, identity federation, and access control using Amazon Cognito User Pools and Identity Pools. Used by application developers and platform administrators to implement secure sign-up, sign-in, and AWS resource access for web and mobile apps.
layout: capability
name: Amazon Cognito User Authentication
operations:
- description: List all user pools.
  method: GET
  name: list-user-pools
  path: /v1/user-pools
- description: Create a new user pool.
  method: POST
  name: create-user-pool
  path: /v1/user-pools
- description: List users in a user pool.
  method: GET
  name: list-users
  path: /v1/user-pools/{user_pool_id}/users
- description: Create a new user in the pool.
  method: POST
  name: create-user
  path: /v1/user-pools/{user_pool_id}/users
- description: List all identity pools.
  method: GET
  name: list-identity-pools
  path: /v1/identity-pools
- description: Start the authentication flow.
  method: POST
  name: initiate-auth
  path: /v1/auth/initiate
- description: Get temporary AWS credentials for a federated identity.
  method: POST
  name: get-credentials
  path: /v1/credentials
personas: []
provider_name: Amazon Cognito
provider_slug: amazon-cognito
search_terms:
- oauth
- create user pool
- list all user pools.
- describe identity pool
- manage cognito user pools.
- Platform Administrator
- get temporary aws credentials for a federated cognito identity.
- list users in a user pool.
- authentication
- list all amazon cognito user pools in the account.
- initiate an authentication flow in cognito.
- create a new amazon cognito user pool.
- describe user pool
- list all cognito identity pools.
- get details of a specific cognito identity pool.
- create a new user in the pool.
- identity
- delete a user from a cognito user pool.
- list users
- list user pools
- get temporary aws credentials.
- create a new user pool.
- get temporary aws credentials for a federated identity.
- federated identity
- get user
- start the authentication flow.
- Application Developer
- integrates cognito authentication into web and mobile applications.
- get credentials
- manage users within a user pool.
- list all identity pools.
- initiate authentication flows.
- end-to-end user authentication using user pools and identity pools.
- user management
- aws
- list identity pools
- initiate auth
- create a new cognito identity pool for federated identity management.
- get details of a specific user in a cognito user pool.
- create user
- create a new user in a cognito user pool.
- create identity pool
- manages user pools, groups, and identity pool configurations.
- manage cognito identity pools.
- list users in a cognito user pool.
- delete user
- get configuration details of a specific cognito user pool.
- amazon
slug: user-authentication
tags:
- Amazon
- AWS
- Authentication
- Identity
- User Management
- OAuth
- Federated Identity
tools:
- description: List all Amazon Cognito user pools in the account.
  hints:
    readOnly: true
  name: list-user-pools
- description: Get configuration details of a specific Cognito user pool.
  hints:
    readOnly: true
  name: describe-user-pool
- description: Create a new Amazon Cognito user pool.
  hints:
    destructive: false
    readOnly: false
  name: create-user-pool
- description: List users in a Cognito user pool.
  hints:
    readOnly: true
  name: list-users
- description: Get details of a specific user in a Cognito user pool.
  hints:
    readOnly: true
  name: get-user
- description: Create a new user in a Cognito user pool.
  hints:
    destructive: false
    readOnly: false
  name: create-user
- description: Delete a user from a Cognito user pool.
  hints:
    destructive: true
    readOnly: false
  name: delete-user
- description: Initiate an authentication flow in Cognito.
  hints:
    destructive: false
    readOnly: false
  name: initiate-auth
- description: List all Cognito identity pools.
  hints:
    readOnly: true
  name: list-identity-pools
- description: Get details of a specific Cognito identity pool.
  hints:
    readOnly: true
  name: describe-identity-pool
- description: Get temporary AWS credentials for a federated Cognito identity.
  hints:
    readOnly: true
  name: get-credentials
- description: Create a new Cognito identity pool for federated identity management.
  hints:
    destructive: false
    readOnly: false
  name: create-identity-pool
---
