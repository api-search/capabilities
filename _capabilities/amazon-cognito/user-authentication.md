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
- create user
- get temporary aws credentials for a federated cognito identity.
- initiate auth
- manage cognito user pools.
- describe identity pool
- end-to-end user authentication using user pools and identity pools.
- list users in a user pool.
- create identity pool
- get temporary aws credentials for a federated identity.
- federated identity
- amazon
- create a new user pool.
- delete a user from a cognito user pool.
- create a new amazon cognito user pool.
- oauth
- list all user pools.
- authentication
- get details of a specific cognito identity pool.
- aws
- get temporary aws credentials.
- Application Developer
- create user pool
- manages user pools, groups, and identity pool configurations.
- start the authentication flow.
- list identity pools
- get credentials
- initiate an authentication flow in cognito.
- delete user
- manage users within a user pool.
- list users
- user management
- manage cognito identity pools.
- list all cognito identity pools.
- list all amazon cognito user pools in the account.
- list all identity pools.
- create a new user in the pool.
- get configuration details of a specific cognito user pool.
- integrates cognito authentication into web and mobile applications.
- identity
- list user pools
- get user
- get details of a specific user in a cognito user pool.
- create a new cognito identity pool for federated identity management.
- Platform Administrator
- describe user pool
- create a new user in a cognito user pool.
- list users in a cognito user pool.
- initiate authentication flows.
slug: user-authentication
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon Cognito User Authentication\"\n  description: \"Workflow capability for managing user authentication, identity federation, and access control using Amazon Cognito User Pools and Identity Pools. Used by application developers and platform administrators to implement secure sign-up, sign-in, and AWS resource access for web and mobile apps.\"\n  tags:\n    - Amazon\n    - AWS\n    - Authentication\n    - Identity\n    - User Management\n    - OAuth\n    - Federated Identity\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n      COGNITO_USER_POOL_ID: COGNITO_USER_POOL_ID\n      COGNITO_CLIENT_ID: COGNITO_CLIENT_ID\n      COGNITO_IDENTITY_POOL_ID: COGNITO_IDENTITY_POOL_ID\n\ncapability:\n  consumes:\n    - import: cognito-user-pools\n      location: ./shared/cognito-user-pools.yaml\n\
  \    - import: cognito-identity-pools\n      location: ./shared/cognito-identity-pools.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: user-auth-api\n      description: \"Unified REST API for Amazon Cognito user authentication and identity management.\"\n      resources:\n        - path: /v1/user-pools\n          name: user-pools\n          description: \"Manage Cognito user pools.\"\n          operations:\n            - method: GET\n              name: list-user-pools\n              description: \"List all user pools.\"\n              call: \"cognito-user-pools.list-user-pools\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: POST\n              name: create-user-pool\n              description: \"Create a new user pool.\"\n              call: \"cognito-user-pools.create-user-pool\"\n              with:\n                pool_name: \"rest.pool_name\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/user-pools/{user_pool_id}/users\n          name: users\n          description: \"Manage users within a user pool.\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List users in a user pool.\"\n              call: \"cognito-user-pools.list-users\"\n              with:\n                user_pool_id: \"rest.user_pool_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: POST\n              name: create-user\n              description: \"Create a new user in the pool.\"\n              call: \"cognito-user-pools.admin-create-user\"\n              with:\n                user_pool_id: \"rest.user_pool_id\"\n                username: \"rest.username\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path:\
  \ /v1/identity-pools\n          name: identity-pools\n          description: \"Manage Cognito identity pools.\"\n          operations:\n            - method: GET\n              name: list-identity-pools\n              description: \"List all identity pools.\"\n              call: \"cognito-identity-pools.list-identity-pools\"\n              with:\n                max_results: \"rest.max_results\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/auth/initiate\n          name: auth-initiate\n          description: \"Initiate authentication flows.\"\n          operations:\n            - method: POST\n              name: initiate-auth\n              description: \"Start the authentication flow.\"\n              call: \"cognito-user-pools.initiate-auth\"\n              with:\n                auth_flow: \"rest.auth_flow\"\n                client_id: \"rest.client_id\"\n              outputParameters:\n                -\
  \ type: object\n                  mapping: \"$.\"\n\n        - path: /v1/credentials\n          name: credentials\n          description: \"Get temporary AWS credentials.\"\n          operations:\n            - method: POST\n              name: get-credentials\n              description: \"Get temporary AWS credentials for a federated identity.\"\n              call: \"cognito-identity-pools.get-credentials-for-identity\"\n              with:\n                identity_id: \"rest.identity_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: user-auth-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon Cognito user authentication and identity management.\"\n      tools:\n        - name: list-user-pools\n          description: \"List all Amazon Cognito user pools in the account.\"\n          hints:\n            readOnly: true\n          call: \"cognito-user-pools.list-user-pools\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-user-pool\n          description: \"Get configuration details of a specific Cognito user pool.\"\n          hints:\n            readOnly: true\n          call: \"cognito-user-pools.describe-user-pool\"\n          with:\n            user_pool_id: \"tools.user_pool_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-user-pool\n          description: \"Create a new Amazon Cognito user pool.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"cognito-user-pools.create-user-pool\"\n          with:\n            pool_name: \"tools.pool_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-users\n          description: \"List users in a Cognito user pool.\"\n          hints:\n            readOnly: true\n\
  \          call: \"cognito-user-pools.list-users\"\n          with:\n            user_pool_id: \"tools.user_pool_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-user\n          description: \"Get details of a specific user in a Cognito user pool.\"\n          hints:\n            readOnly: true\n          call: \"cognito-user-pools.admin-get-user\"\n          with:\n            user_pool_id: \"tools.user_pool_id\"\n            username: \"tools.username\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-user\n          description: \"Create a new user in a Cognito user pool.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"cognito-user-pools.admin-create-user\"\n          with:\n            user_pool_id: \"tools.user_pool_id\"\n            username: \"tools.username\"\n          outputParameters:\n       \
  \     - type: object\n              mapping: \"$.\"\n\n        - name: delete-user\n          description: \"Delete a user from a Cognito user pool.\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"cognito-user-pools.admin-delete-user\"\n          with:\n            user_pool_id: \"tools.user_pool_id\"\n            username: \"tools.username\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: initiate-auth\n          description: \"Initiate an authentication flow in Cognito.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"cognito-user-pools.initiate-auth\"\n          with:\n            auth_flow: \"tools.auth_flow\"\n            client_id: \"tools.client_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-identity-pools\n          description: \"List all Cognito identity\
  \ pools.\"\n          hints:\n            readOnly: true\n          call: \"cognito-identity-pools.list-identity-pools\"\n          with:\n            max_results: \"tools.max_results\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-identity-pool\n          description: \"Get details of a specific Cognito identity pool.\"\n          hints:\n            readOnly: true\n          call: \"cognito-identity-pools.describe-identity-pool\"\n          with:\n            identity_pool_id: \"tools.identity_pool_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-credentials\n          description: \"Get temporary AWS credentials for a federated Cognito identity.\"\n          hints:\n            readOnly: true\n          call: \"cognito-identity-pools.get-credentials-for-identity\"\n          with:\n            identity_id: \"tools.identity_id\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: create-identity-pool\n          description: \"Create a new Cognito identity pool for federated identity management.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"cognito-identity-pools.create-identity-pool\"\n          with:\n            pool_name: \"tools.pool_name\"\n            allow_unauth: \"tools.allow_unauth\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-cognito/refs/heads/main/capabilities/user-authentication.yaml
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
