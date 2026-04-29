---
categories:
- identity-access
consumed_apis:
- sso-admin
- identitystore
description: Unified capability for IT administrators to manage workforce identities, provision access to AWS accounts, and configure SSO for enterprise applications.
layout: capability
name: Amazon IAM Identity Center - Identity and Access Management
operations:
- description: List users in the identity store
  method: GET
  name: list-users
  path: /v1/users
- description: List groups in the identity store
  method: GET
  name: list-groups
  path: /v1/groups
- description: List all permission sets
  method: GET
  name: list-permission-sets
  path: /v1/permission-sets
- description: Assign access to a user or group for an AWS account
  method: POST
  name: create-account-assignment
  path: /v1/account-assignments
personas: []
provider_name: Amazon IAM Identity Center
provider_slug: amazon-iam-identity-center
search_terms:
- create a new group for organizing users
- configures permission sets and account assignments
- list user groups in the identity store
- assign account access
- create account assignment
- single sign-on
- create user
- list permission sets for assigning aws account access
- managing workforce user and group identities
- list users in the identity store
- list groups
- assign a permission set to a user or group for an aws account
- manage workforce users
- IAM Administrator
- create group
- IT Administrator
- iam
- list workforce users in the identity store
- list permission sets
- manages workforce identities and provisions access to aws accounts
- manage user groups
- authentication
- identity management
- create a permission set defining what access a user gets to an aws account
- manage aws account access assignments
- assigning aws account access to users and groups
- remove account access
- create a new workforce user in iam identity center
- list instances
- manage permission sets for aws account access
- remove a user or group's access to an aws account
- aws
- workforce identity
- list all permission sets
- list groups in the identity store
- create permission set
- assign access to a user or group for an aws account
- access control
- list sso instances in the account
- list users
slug: identity-access-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: Amazon IAM Identity Center - Identity and Access Management\n  description: Unified capability for IT administrators to manage workforce identities, provision access to AWS accounts, and configure SSO for enterprise applications.\n  tags:\n    - AWS\n    - IAM\n    - Identity Management\n    - Single Sign-On\n    - Access Control\n    - Workforce Identity\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n    - import: sso-admin\n      location: ./shared/sso-admin.yaml\n    - import: identitystore\n      location: ./shared/identitystore.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: identity-access-api\n      description: Unified REST API for identity and access management.\n      resources:\n        - path: /v1/users\n          name: users\n  \
  \        description: Manage workforce users\n          operations:\n            - method: GET\n              name: list-users\n              description: List users in the identity store\n              call: \"identitystore.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups\n          name: groups\n          description: Manage user groups\n          operations:\n            - method: GET\n              name: list-groups\n              description: List groups in the identity store\n              call: \"identitystore.list-groups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/permission-sets\n          name: permission-sets\n          description: Manage permission sets for AWS account access\n          operations:\n            - method: GET\n              name: list-permission-sets\n              description: List all permission\
  \ sets\n              call: \"sso-admin.list-permission-sets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/account-assignments\n          name: account-assignments\n          description: Manage AWS account access assignments\n          operations:\n            - method: POST\n              name: create-account-assignment\n              description: Assign access to a user or group for an AWS account\n              call: \"sso-admin.create-account-assignment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9090\n      namespace: identity-access-mcp\n      transport: http\n      description: MCP server for AI-assisted identity and access management.\n      tools:\n        - name: list-users\n          description: List workforce users in the identity store\n          hints:\n            readOnly: true\n            openWorld: true\n\
  \          call: \"identitystore.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-user\n          description: Create a new workforce user in IAM Identity Center\n          hints:\n            readOnly: false\n          call: \"identitystore.create-user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-groups\n          description: List user groups in the identity store\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"identitystore.list-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-group\n          description: Create a new group for organizing users\n          hints:\n            readOnly: false\n          call: \"identitystore.create-group\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\
  \        - name: list-instances\n          description: List SSO instances in the account\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sso-admin.list-instances\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-permission-sets\n          description: List permission sets for assigning AWS account access\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sso-admin.list-permission-sets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-permission-set\n          description: Create a permission set defining what access a user gets to an AWS account\n          hints:\n            readOnly: false\n          call: \"sso-admin.create-permission-set\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: assign-account-access\n   \
  \       description: Assign a permission set to a user or group for an AWS account\n          hints:\n            readOnly: false\n          call: \"sso-admin.create-account-assignment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: remove-account-access\n          description: Remove a user or group's access to an AWS account\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"sso-admin.delete-account-assignment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-iam-identity-center/refs/heads/main/capabilities/identity-access-management.yaml
tags:
- AWS
- IAM
- Identity Management
- Single Sign-On
- Access Control
- Workforce Identity
tools:
- description: List workforce users in the identity store
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: Create a new workforce user in IAM Identity Center
  hints:
    readOnly: false
  name: create-user
- description: List user groups in the identity store
  hints:
    openWorld: true
    readOnly: true
  name: list-groups
- description: Create a new group for organizing users
  hints:
    readOnly: false
  name: create-group
- description: List SSO instances in the account
  hints:
    openWorld: true
    readOnly: true
  name: list-instances
- description: List permission sets for assigning AWS account access
  hints:
    openWorld: true
    readOnly: true
  name: list-permission-sets
- description: Create a permission set defining what access a user gets to an AWS account
  hints:
    readOnly: false
  name: create-permission-set
- description: Assign a permission set to a user or group for an AWS account
  hints:
    readOnly: false
  name: assign-account-access
- description: Remove a user or group's access to an AWS account
  hints:
    destructive: true
    readOnly: false
  name: remove-account-access
---
