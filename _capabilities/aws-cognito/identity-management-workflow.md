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
- authentication
- create user pool
- configures cognito user pools and app clients for application authentication
- list users in a user pool
- list all federated identity pools
- create identity pool
- creating and configuring user pools with authentication flows and policies
- create a new cognito user pool for authentication
- get configuration details of a cognito user pool
- Identity Engineer
- create a new user account in a cognito user pool
- list user groups
- user account management
- get details of a specific user in a cognito user pool
- authorization
- get user
- federated identity pool management
- create a federated identity pool for credential vending
- list groups
- create user
- describe user pool
- identity
- manages cognito user pools, federation, and access control policies
- list users
- list identity pools
- list all user pools
- get details of a federated identity pool
- list users in a cognito user pool
- describe identity pool
- list user pools
- list all cognito user pools in the account
- oauth2
- user group management
- Application Developer
- manage cognito user pools, users, groups, and federated identity pools
- amazon cognito
- aws
- user management
- managing user accounts, groups, and access within user pools
- list user groups in a cognito user pool
- oidc
- identity provider
- user pool lifecycle management
- create a new user pool
- create a user in a user pool
- managing federated identities and temporary aws credential vending
- create a federated identity pool
- identity management
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
