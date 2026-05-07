---
categories:
- identity-access
consumed_apis: []
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
- IT Administrator
- create group
- manage workforce users
- list permission sets
- manage permission sets for aws account access
- list sso instances in the account
- list permission sets for assigning aws account access
- list groups
- identity management
- workforce identity
- authentication
- list users in the identity store
- create a permission set defining what access a user gets to an aws account
- assign a permission set to a user or group for an aws account
- access control
- list all permission sets
- list instances
- assign access to a user or group for an aws account
- create account assignment
- list users
- create a new workforce user in iam identity center
- managing workforce user and group identities
- IAM Administrator
- iam
- manage user groups
- list groups in the identity store
- manage aws account access assignments
- configures permission sets and account assignments
- list user groups in the identity store
- manages workforce identities and provisions access to aws accounts
- create user
- aws
- create permission set
- remove account access
- single sign-on
- assigning aws account access to users and groups
- list workforce users in the identity store
- assign account access
- remove a user or group's access to an aws account
- create a new group for organizing users
slug: identity-access-management
source_filename: identity-access-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon IAM Identity Center - Identity and Access Management\n  description: Unified capability for IT administrators to manage workforce identities, provision access to AWS accounts,\n    and configure SSO for enterprise applications.\n  tags:\n  - AWS\n  - IAM\n  - Identity Management\n  - Single Sign-On\n  - Access Control\n  - Workforce Identity\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: sso-admin\n    baseUri: https://sso.amazonaws.com\n    description: AWS SSO Admin REST API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: instances\n      path: /instances\n      description: SSO instances\n      operations:\n      - name: list-instances\n\
  \        method: GET\n        description: List SSO instances\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: permission-sets\n      path: /instances/{instanceArn}/permission-sets\n      description: Permission sets\n      operations:\n      - name: list-permission-sets\n        method: GET\n        description: List permission sets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-permission-set\n        method: POST\n        description: Create a permission set\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-assignments\n      path: /instances/{instanceArn}/account-assignments\n      description: Account assignments\n      operations:\n      - name: create-account-assignment\n        method: POST\n\
  \        description: Assign access to an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-account-assignment\n        method: DELETE\n        description: Remove account assignment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: identitystore\n    baseUri: https://identitystore.amazonaws.com\n    description: AWS Identity Store REST API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: users\n      path: /identitystores/{IdentityStoreId}/users\n      description: Identity store users\n      operations:\n      - name: list-users\n        method: GET\n        description: List users in the identity store\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /identitystores/{IdentityStoreId}/groups\n      description: Identity store groups\n      operations:\n      - name: list-groups\n        method: GET\n        description: List groups in the identity store\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-group\n        method: POST\n        description: Create a new group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: identity-access-api\n    description: Unified REST API for identity and\
  \ access management.\n    resources:\n    - path: /v1/users\n      name: users\n      description: Manage workforce users\n      operations:\n      - method: GET\n        name: list-users\n        description: List users in the identity store\n        call: identitystore.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups\n      name: groups\n      description: Manage user groups\n      operations:\n      - method: GET\n        name: list-groups\n        description: List groups in the identity store\n        call: identitystore.list-groups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/permission-sets\n      name: permission-sets\n      description: Manage permission sets for AWS account access\n      operations:\n      - method: GET\n        name: list-permission-sets\n        description: List all permission sets\n        call: sso-admin.list-permission-sets\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/account-assignments\n      name: account-assignments\n      description: Manage AWS account access assignments\n      operations:\n      - method: POST\n        name: create-account-assignment\n        description: Assign access to a user or group for an AWS account\n        call: sso-admin.create-account-assignment\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: identity-access-mcp\n    transport: http\n    description: MCP server for AI-assisted identity and access management.\n    tools:\n    - name: list-users\n      description: List workforce users in the identity store\n      hints:\n        readOnly: true\n        openWorld: true\n      call: identitystore.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-user\n      description: Create a new workforce user in IAM Identity Center\n      hints:\n\
  \        readOnly: false\n      call: identitystore.create-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-groups\n      description: List user groups in the identity store\n      hints:\n        readOnly: true\n        openWorld: true\n      call: identitystore.list-groups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-group\n      description: Create a new group for organizing users\n      hints:\n        readOnly: false\n      call: identitystore.create-group\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-instances\n      description: List SSO instances in the account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: sso-admin.list-instances\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-permission-sets\n      description: List permission sets for assigning AWS account access\n      hints:\n      \
  \  readOnly: true\n        openWorld: true\n      call: sso-admin.list-permission-sets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-permission-set\n      description: Create a permission set defining what access a user gets to an AWS account\n      hints:\n        readOnly: false\n      call: sso-admin.create-permission-set\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: assign-account-access\n      description: Assign a permission set to a user or group for an AWS account\n      hints:\n        readOnly: false\n      call: sso-admin.create-account-assignment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: remove-account-access\n      description: Remove a user or group's access to an AWS account\n      hints:\n        readOnly: false\n        destructive: true\n      call: sso-admin.delete-account-assignment\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-iam-identity-center/refs/heads/main/capabilities/identity-access-management.yaml
tags:
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
