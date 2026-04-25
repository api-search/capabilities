---
consumed_apis:
- cognito-idp
- cognito-identity
description: Unified workflow for identity and access management engineers to manage Cognito user pools, user accounts, groups, and federated identity pools. Combines the Identity Provider and Federated Identity APIs for complete user lifecycle and credential management.
layout: capability
name: Amazon Cognito Identity Management Workflow
operations:
- description: List all user pools
  method: GET
  name: list-user-pools
  path: /v1/user-pools
- description: Create a new user pool
  method: POST
  name: create-user-pool
  path: /v1/user-pools
- description: List users in a user pool
  method: GET
  name: list-users
  path: /v1/user-pools/{userPoolId}/users
- description: Create a user in a user pool
  method: POST
  name: create-user
  path: /v1/user-pools/{userPoolId}/users
- description: List user groups
  method: GET
  name: list-groups
  path: /v1/user-pools/{userPoolId}/groups
- description: List all federated identity pools
  method: GET
  name: list-identity-pools
  path: /v1/identity-pools
- description: Create a federated identity pool
  method: POST
  name: create-identity-pool
  path: /v1/identity-pools
personas: []
provider_name: Amazon Cognito
provider_slug: aws-cognito
search_terms:
- describe user pool
- federated identity pool management
- oidc
- oauth2
- get configuration details of a cognito user pool
- user account management
- user pool lifecycle management
- list user groups
- manage cognito user pools, users, groups, and federated identity pools
- configures cognito user pools and app clients for application authentication
- authorization
- identity management
- list identity pools
- identity provider
- amazon cognito
- list all federated identity pools
- list groups
- identity
- create a new user account in a cognito user pool
- creating and configuring user pools with authentication flows and policies
- user group management
- aws
- list all cognito user pools in the account
- user management
- list users
- get user
- create a user in a user pool
- list user pools
- manages cognito user pools, federation, and access control policies
- create a new cognito user pool for authentication
- list user groups in a cognito user pool
- get details of a specific user in a cognito user pool
- managing user accounts, groups, and access within user pools
- create a new user pool
- get details of a federated identity pool
- create user pool
- create a federated identity pool for credential vending
- create identity pool
- list all user pools
- managing federated identities and temporary aws credential vending
- Identity Engineer
- create a federated identity pool
- Application Developer
- authentication
- list users in a cognito user pool
- describe identity pool
- list users in a user pool
- create user
slug: identity-management-workflow
tags:
- Amazon Cognito
- AWS
- Authentication
- Authorization
- Identity Management
- User Management
tools:
- description: List all Cognito user pools in the account
  hints:
    openWorld: true
    readOnly: true
  name: list-user-pools
- description: Create a new Cognito user pool for authentication
  hints:
    readOnly: false
  name: create-user-pool
- description: Get configuration details of a Cognito user pool
  hints:
    readOnly: true
  name: describe-user-pool
- description: List users in a Cognito user pool
  hints:
    readOnly: true
  name: list-users
- description: Create a new user account in a Cognito user pool
  hints:
    readOnly: false
  name: create-user
- description: Get details of a specific user in a Cognito user pool
  hints:
    readOnly: true
  name: get-user
- description: List user groups in a Cognito user pool
  hints:
    readOnly: true
  name: list-groups
- description: List all federated identity pools
  hints:
    openWorld: true
    readOnly: true
  name: list-identity-pools
- description: Create a federated identity pool for credential vending
  hints:
    readOnly: false
  name: create-identity-pool
- description: Get details of a federated identity pool
  hints:
    readOnly: true
  name: describe-identity-pool
---
