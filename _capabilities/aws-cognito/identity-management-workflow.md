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
- list groups
- user pool lifecycle management
- creating and configuring user pools with authentication flows and policies
- authentication
- get details of a federated identity pool
- create a federated identity pool for credential vending
- create user
- list user groups
- identity provider
- user management
- list all user pools
- user account management
- manage cognito user pools, users, groups, and federated identity pools
- create identity pool
- create a federated identity pool
- create user pool
- identity management
- describe identity pool
- aws
- list users
- list identity pools
- create a new user account in a cognito user pool
- identity
- create a new user pool
- list all cognito user pools in the account
- list user groups in a cognito user pool
- list user pools
- user group management
- authorization
- list all federated identity pools
- list users in a cognito user pool
- configures cognito user pools and app clients for application authentication
- oidc
- federated identity pool management
- Identity Engineer
- managing federated identities and temporary aws credential vending
- amazon cognito
- list users in a user pool
- managing user accounts, groups, and access within user pools
- create a new cognito user pool for authentication
- create a user in a user pool
- oauth2
- manages cognito user pools, federation, and access control policies
- get user
- get configuration details of a cognito user pool
- Application Developer
- get details of a specific user in a cognito user pool
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
