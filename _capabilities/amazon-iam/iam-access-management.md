---
categories:
- identity-access
consumed_apis:
- iam
description: Unified capability for cloud administrators to manage IAM users, roles, groups, and policies for AWS account access control and security governance.
layout: capability
name: Amazon IAM - Access Management
operations:
- description: List all IAM users
  method: GET
  name: list-users
  path: /v1/users
- description: Create a new IAM user
  method: POST
  name: create-user
  path: /v1/users
- description: List all IAM roles
  method: GET
  name: list-roles
  path: /v1/roles
- description: Create a new IAM role
  method: POST
  name: create-role
  path: /v1/roles
- description: List all IAM policies
  method: GET
  name: list-policies
  path: /v1/policies
- description: Create a new IAM policy
  method: POST
  name: create-policy
  path: /v1/policies
personas: []
provider_name: Amazon IAM
provider_slug: amazon-iam
search_terms:
- create a new iam policy
- list iam policies available for attachment
- manage iam policies
- iam
- create policy
- attach user policy
- create a new iam role
- list policies
- Cloud Administrator
- access control
- list access keys for an iam user
- policy management
- access management
- aws
- authorization
- defining and enforcing what users and services can do
- attach a managed policy to an iam user
- attach role policy
- create a new iam policy with specified permissions
- Security Engineer
- reviews and audits iam configurations for security compliance
- creating and attaching permission policies
- create user
- manage iam roles
- list all iam users
- list all iam roles
- create role
- manages iam users, roles, and policies for aws account governance
- security
- create a new iam role with a trust policy
- create a new iam user with the specified username
- list roles
- list all iam roles in the account
- authentication
- manage iam users
- list users
- create a new iam user
- list all iam users in the account
- delete an iam user from the account
- delete user
- list access keys
- list all iam policies
- creating and managing aws user identities
- identity
- attach a managed policy to an iam role
slug: iam-access-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: Amazon IAM - Access Management\n  description: Unified capability for cloud administrators to manage IAM users, roles, groups, and policies for AWS account access control and security governance.\n  tags:\n    - AWS\n    - IAM\n    - Security\n    - Access Control\n    - Identity\n    - Policy Management\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n    - import: iam\n      location: ./shared/iam.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: iam-access-api\n      description: Unified REST API for IAM access management.\n      resources:\n        - path: /v1/users\n          name: users\n          description: Manage IAM users\n          operations:\n            - method: GET\n              name: list-users\n              description: List\
  \ all IAM users\n              call: \"iam.list-users\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-user\n              description: Create a new IAM user\n              call: \"iam.create-user\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/roles\n          name: roles\n          description: Manage IAM roles\n          operations:\n            - method: GET\n              name: list-roles\n              description: List all IAM roles\n              call: \"iam.list-roles\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-role\n              description: Create a new IAM role\n              call: \"iam.create-role\"\n              outputParameters:\n                - type: object\n             \
  \     mapping: \"$.\"\n        - path: /v1/policies\n          name: policies\n          description: Manage IAM policies\n          operations:\n            - method: GET\n              name: list-policies\n              description: List all IAM policies\n              call: \"iam.list-policies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-policy\n              description: Create a new IAM policy\n              call: \"iam.create-policy\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9090\n      namespace: iam-access-mcp\n      transport: http\n      description: MCP server for AI-assisted IAM access management.\n      tools:\n        - name: list-users\n          description: List all IAM users in the account\n          hints:\n            readOnly: true\n            openWorld: true\n    \
  \      call: \"iam.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-user\n          description: Create a new IAM user with the specified username\n          hints:\n            readOnly: false\n          call: \"iam.create-user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-user\n          description: Delete an IAM user from the account\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"iam.delete-user\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-roles\n          description: List all IAM roles in the account\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iam.list-roles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-role\n\
  \          description: Create a new IAM role with a trust policy\n          hints:\n            readOnly: false\n          call: \"iam.create-role\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-policies\n          description: List IAM policies available for attachment\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iam.list-policies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-policy\n          description: Create a new IAM policy with specified permissions\n          hints:\n            readOnly: false\n          call: \"iam.create-policy\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: attach-user-policy\n          description: Attach a managed policy to an IAM user\n          hints:\n            readOnly: false\n          call: \"iam.attach-user-policy\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: attach-role-policy\n          description: Attach a managed policy to an IAM role\n          hints:\n            readOnly: false\n          call: \"iam.attach-role-policy\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-access-keys\n          description: List access keys for an IAM user\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"iam.list-access-keys\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-iam/refs/heads/main/capabilities/iam-access-management.yaml
tags:
- AWS
- IAM
- Security
- Access Control
- Identity
- Policy Management
tools:
- description: List all IAM users in the account
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: Create a new IAM user with the specified username
  hints:
    readOnly: false
  name: create-user
- description: Delete an IAM user from the account
  hints:
    destructive: true
    readOnly: false
  name: delete-user
- description: List all IAM roles in the account
  hints:
    openWorld: true
    readOnly: true
  name: list-roles
- description: Create a new IAM role with a trust policy
  hints:
    readOnly: false
  name: create-role
- description: List IAM policies available for attachment
  hints:
    openWorld: true
    readOnly: true
  name: list-policies
- description: Create a new IAM policy with specified permissions
  hints:
    readOnly: false
  name: create-policy
- description: Attach a managed policy to an IAM user
  hints:
    readOnly: false
  name: attach-user-policy
- description: Attach a managed policy to an IAM role
  hints:
    readOnly: false
  name: attach-role-policy
- description: List access keys for an IAM user
  hints:
    openWorld: true
    readOnly: true
  name: list-access-keys
---
