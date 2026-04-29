---
categories:
- messaging
consumed_apis:
- workmail
description: Unified workflow for IT administrators and email operations teams to manage Amazon WorkMail organizations, users, groups, and mobile device access. Enables programmatic provisioning, deprovisioning, and governance of enterprise email infrastructure.
layout: capability
name: Amazon WorkMail Email Management
operations:
- description: List all WorkMail organizations.
  method: GET
  name: list-organizations
  path: /v1/organizations
- description: List users in an organization.
  method: GET
  name: list-users
  path: /v1/users
- description: Create a new email user.
  method: POST
  name: create-user
  path: /v1/users
- description: List email groups.
  method: GET
  name: list-groups
  path: /v1/groups
- description: List mobile device access rules.
  method: GET
  name: list-mobile-device-access-rules
  path: /v1/mobile-device-access
personas: []
provider_name: Amazon WorkMail
provider_slug: amazon-workmail
search_terms:
- list users in an organization.
- list users in a workmail organization.
- handles day-to-day email user and group management.
- user provisioning and management.
- create user
- list groups
- group management.
- list mobile device access rules
- list email groups.
- it administration of email infrastructure
- exchange
- list organizations
- email
- Email Operations
- enterprise email provisioning and management
- aws
- calendar
- mobile device access control.
- administration
- IT Administrator
- create a new email user.
- list mobile device access rules.
- business communication
- list all amazon workmail organizations in the account.
- workflow for it administrators to manage workmail organizations, users, groups, and mobile device access policies.
- workmail organization management.
- list users
- list mobile device access control rules.
- list all workmail organizations.
- create a new workmail user with mailbox.
- manages workmail infrastructure, user provisioning, and security policies.
- enterprise
- list email distribution groups in an organization.
- mobile device access control and compliance
slug: email-management
source_filename: email-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon WorkMail Email Management\"\n  description: >-\n    Unified workflow for IT administrators and email operations teams to manage\n    Amazon WorkMail organizations, users, groups, and mobile device access.\n    Enables programmatic provisioning, deprovisioning, and governance of\n    enterprise email infrastructure.\n  tags:\n    - AWS\n    - Email\n    - Calendar\n    - Business Communication\n    - Administration\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: workmail\n      location: ./shared/workmail.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: email-management-api\n      description: \"Unified REST API for Amazon WorkMail email infrastructure management.\"\n      resources:\n\
  \        - path: /v1/organizations\n          name: organizations\n          description: \"WorkMail organization management.\"\n          operations:\n            - method: GET\n              name: list-organizations\n              description: \"List all WorkMail organizations.\"\n              call: \"workmail.list-organizations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users\n          name: users\n          description: \"User provisioning and management.\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List users in an organization.\"\n              call: \"workmail.list-users\"\n              with:\n                OrganizationId: \"rest.organization_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-user\n              description:\
  \ \"Create a new email user.\"\n              call: \"workmail.create-user\"\n              with:\n                OrganizationId: \"rest.organization_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/groups\n          name: groups\n          description: \"Group management.\"\n          operations:\n            - method: GET\n              name: list-groups\n              description: \"List email groups.\"\n              call: \"workmail.list-groups\"\n              with:\n                OrganizationId: \"rest.organization_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/mobile-device-access\n          name: mobile-device-access\n          description: \"Mobile device access control.\"\n          operations:\n            - method: GET\n              name: list-mobile-device-access-rules\n              description: \"List mobile device\
  \ access rules.\"\n              call: \"workmail.list-mobile-device-access-rules\"\n              with:\n                OrganizationId: \"rest.organization_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: email-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Amazon WorkMail email infrastructure management.\"\n      tools:\n        - name: list-organizations\n          description: \"List all Amazon WorkMail organizations in the account.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"workmail.list-organizations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-users\n          description: \"List users in a WorkMail organization.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"workmail.list-users\"\
  \n          with:\n            OrganizationId: \"tools.organization_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-user\n          description: \"Create a new WorkMail user with mailbox.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"workmail.create-user\"\n          with:\n            OrganizationId: \"tools.organization_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-groups\n          description: \"List email distribution groups in an organization.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"workmail.list-groups\"\n          with:\n            OrganizationId: \"tools.organization_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-mobile-device-access-rules\n\
  \          description: \"List mobile device access control rules.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"workmail.list-mobile-device-access-rules\"\n          with:\n            OrganizationId: \"tools.organization_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-workmail/refs/heads/main/capabilities/email-management.yaml
tags:
- AWS
- Email
- Calendar
- Business Communication
- Administration
tools:
- description: List all Amazon WorkMail organizations in the account.
  hints:
    openWorld: true
    readOnly: true
  name: list-organizations
- description: List users in a WorkMail organization.
  hints:
    openWorld: false
    readOnly: true
  name: list-users
- description: Create a new WorkMail user with mailbox.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-user
- description: List email distribution groups in an organization.
  hints:
    openWorld: false
    readOnly: true
  name: list-groups
- description: List mobile device access control rules.
  hints:
    openWorld: false
    readOnly: true
  name: list-mobile-device-access-rules
---
