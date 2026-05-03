---
categories:
- identity-access
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
- amazon cognito
- create a new user account in a cognito user pool
- get details of a federated identity pool
- list users in a user pool
- authentication
- identity
- creating and configuring user pools with authentication flows and policies
- list user groups
- configures cognito user pools and app clients for application authentication
- create a new user pool
- list all federated identity pools
- create a user in a user pool
- create a new cognito user pool for authentication
- user group management
- aws
- list all cognito user pools in the account
- oauth2
- create user
- describe user pool
- Identity Engineer
- get details of a specific user in a cognito user pool
- list identity pools
- create identity pool
- federated identity pool management
- get configuration details of a cognito user pool
- user pool lifecycle management
- create a federated identity pool
- oidc
- identity management
- create a federated identity pool for credential vending
- create user pool
- manages cognito user pools, federation, and access control policies
- describe identity pool
- list all user pools
- list user groups in a cognito user pool
- list users
- list groups
- list user pools
- Application Developer
- manage cognito user pools, users, groups, and federated identity pools
- get user
- user management
- identity provider
- managing user accounts, groups, and access within user pools
- authorization
- user account management
- managing federated identities and temporary aws credential vending
- list users in a cognito user pool
slug: identity-management-workflow
source_filename: identity-management-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon Cognito Identity Management Workflow\"\n  description: \"Unified workflow for identity and access management engineers to manage Cognito user pools, user accounts, groups, and federated identity pools. Combines the Identity Provider and Federated Identity APIs for complete user lifecycle and credential management.\"\n  tags:\n    - Amazon Cognito\n    - AWS\n    - Authentication\n    - Authorization\n    - Identity Management\n    - User Management\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: cognito-idp\n      location: ./shared/cognito-identity-provider.yaml\n    - import: cognito-identity\n      location: ./shared/cognito-identity.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace:\
  \ cognito-workflow-api\n      description: \"Unified REST API for Amazon Cognito identity management.\"\n      resources:\n        - path: /v1/user-pools\n          name: user-pools\n          description: \"User pool lifecycle management\"\n          operations:\n            - method: GET\n              name: list-user-pools\n              description: \"List all user pools\"\n              call: \"cognito-idp.list-user-pools\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-user-pool\n              description: \"Create a new user pool\"\n              call: \"cognito-idp.create-user-pool\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/user-pools/{userPoolId}/users\n          name: users\n          description: \"User account management\"\n          operations:\n            - method: GET\n              name:\
  \ list-users\n              description: \"List users in a user pool\"\n              call: \"cognito-idp.list-users\"\n              with:\n                user_pool_id: \"rest.userPoolId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-user\n              description: \"Create a user in a user pool\"\n              call: \"cognito-idp.admin-create-user\"\n              with:\n                user_pool_id: \"rest.userPoolId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/user-pools/{userPoolId}/groups\n          name: groups\n          description: \"User group management\"\n          operations:\n            - method: GET\n              name: list-groups\n              description: \"List user groups\"\n              call: \"cognito-idp.list-groups\"\n              with:\n                user_pool_id: \"\
  rest.userPoolId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/identity-pools\n          name: identity-pools\n          description: \"Federated identity pool management\"\n          operations:\n            - method: GET\n              name: list-identity-pools\n              description: \"List all federated identity pools\"\n              call: \"cognito-identity.list-identity-pools\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-identity-pool\n              description: \"Create a federated identity pool\"\n              call: \"cognito-identity.create-identity-pool\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: cognito-workflow-mcp\n      transport: http\n      description: \"MCP server for\
  \ AI-assisted Amazon Cognito identity management.\"\n      tools:\n        - name: list-user-pools\n          description: \"List all Cognito user pools in the account\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cognito-idp.list-user-pools\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-user-pool\n          description: \"Create a new Cognito user pool for authentication\"\n          hints:\n            readOnly: false\n          call: \"cognito-idp.create-user-pool\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-user-pool\n          description: \"Get configuration details of a Cognito user pool\"\n          hints:\n            readOnly: true\n          call: \"cognito-idp.describe-user-pool\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-users\n\
  \          description: \"List users in a Cognito user pool\"\n          hints:\n            readOnly: true\n          call: \"cognito-idp.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-user\n          description: \"Create a new user account in a Cognito user pool\"\n          hints:\n            readOnly: false\n          call: \"cognito-idp.admin-create-user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-user\n          description: \"Get details of a specific user in a Cognito user pool\"\n          hints:\n            readOnly: true\n          call: \"cognito-idp.admin-get-user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-groups\n          description: \"List user groups in a Cognito user pool\"\n          hints:\n            readOnly: true\n          call: \"cognito-idp.list-groups\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-identity-pools\n          description: \"List all federated identity pools\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"cognito-identity.list-identity-pools\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-identity-pool\n          description: \"Create a federated identity pool for credential vending\"\n          hints:\n            readOnly: false\n          call: \"cognito-identity.create-identity-pool\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-identity-pool\n          description: \"Get details of a federated identity pool\"\n          hints:\n            readOnly: true\n          call: \"cognito-identity.describe-identity-pool\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/aws-cognito/refs/heads/main/capabilities/identity-management-workflow.yaml
tags:
- Amazon Cognito
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
