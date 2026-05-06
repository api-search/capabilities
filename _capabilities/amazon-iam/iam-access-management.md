---
categories:
- identity-access
consumed_apis: []
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
- creating and managing aws user identities
- list iam policies available for attachment
- list policies
- aws
- delete an iam user from the account
- identity
- defining and enforcing what users and services can do
- reviews and audits iam configurations for security compliance
- manages iam users, roles, and policies for aws account governance
- attach a managed policy to an iam role
- list all iam policies
- policy management
- create a new iam policy with specified permissions
- create user
- manage iam roles
- list all iam users in the account
- security
- list access keys
- manage iam users
- create a new iam policy
- list all iam roles in the account
- delete user
- create a new iam role with a trust policy
- list access keys for an iam user
- attach a managed policy to an iam user
- authorization
- create policy
- list all iam roles
- Cloud Administrator
- authentication
- Security Engineer
- attach user policy
- access control
- access management
- create role
- list all iam users
- list users
- create a new iam user
- manage iam policies
- create a new iam user with the specified username
- attach role policy
- iam
- creating and attaching permission policies
- create a new iam role
- list roles
slug: iam-access-management
source_filename: iam-access-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon IAM - Access Management\n  description: Unified capability for cloud administrators to manage IAM users, roles, groups, and policies for AWS account\n    access control and security governance.\n  tags:\n  - AWS\n  - IAM\n  - Security\n  - Access Control\n  - Identity\n  - Policy Management\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: iam\n    baseUri: https://iam.amazonaws.com\n    description: AWS IAM REST API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: users\n      path: /users\n      description: IAM users\n      operations:\n      - name: list-users\n        method: GET\n        description: List IAM users\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create an IAM user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: roles\n      path: /roles\n      description: IAM roles\n      operations:\n      - name: list-roles\n        method: GET\n        description: List IAM roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-role\n        method: POST\n        description: Create an IAM role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: policies\n      path: /policies\n      description: IAM policies\n      operations:\n      - name: list-policies\n        method: GET\n        description:\
  \ List IAM policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-policy\n        method: POST\n        description: Create an IAM policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: iam-access-api\n    description: Unified REST API for IAM access management.\n    resources:\n    - path: /v1/users\n      name: users\n      description: Manage IAM users\n      operations:\n      - method: GET\n        name: list-users\n        description: List all IAM users\n        call: iam.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-user\n        description: Create a new IAM user\n        call: iam.create-user\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/roles\n      name: roles\n      description: Manage IAM roles\n      operations:\n      - method: GET\n        name: list-roles\n        description: List all IAM roles\n        call: iam.list-roles\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-role\n        description: Create a new IAM role\n        call: iam.create-role\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/policies\n      name: policies\n      description: Manage IAM policies\n      operations:\n      - method: GET\n        name: list-policies\n        description: List all IAM policies\n        call: iam.list-policies\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-policy\n        description: Create a new IAM policy\n        call: iam.create-policy\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n  - type: mcp\n    port: 9090\n    namespace: iam-access-mcp\n    transport: http\n    description: MCP server for AI-assisted IAM access management.\n    tools:\n    - name: list-users\n      description: List all IAM users in the account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: iam.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-user\n      description: Create a new IAM user with the specified username\n      hints:\n        readOnly: false\n      call: iam.create-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-user\n      description: Delete an IAM user from the account\n      hints:\n        readOnly: false\n        destructive: true\n      call: iam.delete-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-roles\n      description: List all IAM roles in the account\n      hints:\n        readOnly: true\n  \
  \      openWorld: true\n      call: iam.list-roles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-role\n      description: Create a new IAM role with a trust policy\n      hints:\n        readOnly: false\n      call: iam.create-role\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-policies\n      description: List IAM policies available for attachment\n      hints:\n        readOnly: true\n        openWorld: true\n      call: iam.list-policies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-policy\n      description: Create a new IAM policy with specified permissions\n      hints:\n        readOnly: false\n      call: iam.create-policy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: attach-user-policy\n      description: Attach a managed policy to an IAM user\n      hints:\n        readOnly: false\n      call: iam.attach-user-policy\n  \
  \    outputParameters:\n      - type: object\n        mapping: $.\n    - name: attach-role-policy\n      description: Attach a managed policy to an IAM role\n      hints:\n        readOnly: false\n      call: iam.attach-role-policy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-access-keys\n      description: List access keys for an IAM user\n      hints:\n        readOnly: true\n        openWorld: true\n      call: iam.list-access-keys\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-iam/refs/heads/main/capabilities/iam-access-management.yaml
tags:
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
