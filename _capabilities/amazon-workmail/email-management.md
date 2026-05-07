---
categories:
- messaging
consumed_apis: []
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
- enterprise email provisioning and management
- list email groups.
- IT Administrator
- business communication
- mobile device access control.
- list mobile device access rules.
- list email distribution groups in an organization.
- list all workmail organizations.
- list groups
- list mobile device access rules
- create a new email user.
- mobile device access control and compliance
- exchange
- create a new workmail user with mailbox.
- workflow for it administrators to manage workmail organizations, users, groups, and mobile device access policies.
- list users
- administration
- email
- Email Operations
- user provisioning and management.
- list users in an organization.
- list all amazon workmail organizations in the account.
- list organizations
- enterprise
- handles day-to-day email user and group management.
- list mobile device access control rules.
- group management.
- create user
- manages workmail infrastructure, user provisioning, and security policies.
- aws
- list users in a workmail organization.
- it administration of email infrastructure
- calendar
- workmail organization management.
slug: email-management
source_filename: email-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon WorkMail Email Management\n  description: Unified workflow for IT administrators and email operations teams to manage Amazon WorkMail organizations,\n    users, groups, and mobile device access. Enables programmatic provisioning, deprovisioning, and governance of enterprise\n    email infrastructure.\n  tags:\n  - AWS\n  - Email\n  - Calendar\n  - Business Communication\n  - Administration\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: workmail\n    baseUri: https://workmail.us-east-1.amazonaws.com\n    description: Amazon WorkMail REST API for email organization management.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n\
  \    - name: organizations\n      path: /organizations\n      description: Manage WorkMail organizations.\n      operations:\n      - name: list-organizations\n        method: GET\n        description: List WorkMail organizations in the account.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-organization\n        method: POST\n        description: Create a new WorkMail organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Alias: '{{tools.alias}}'\n    - name: users\n      path: /organizations/{OrganizationId}/users\n      description: Manage users in a WorkMail organization.\n      operations:\n      - name: list-users\n        method: GET\n        description: List users in the organization.\n        inputParameters:\n        - name:\
  \ OrganizationId\n          in: path\n          type: string\n          required: true\n          description: The organization identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a new user.\n        inputParameters:\n        - name: OrganizationId\n          in: path\n          type: string\n          required: true\n          description: The organization identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Name: '{{tools.name}}'\n            DisplayName: '{{tools.display_name}}'\n            Password: '{{tools.password}}'\n    - name: groups\n      path: /organizations/{OrganizationId}/groups\n      description: Manage groups in a WorkMail organization.\n      operations:\n\
  \      - name: list-groups\n        method: GET\n        description: List groups in the organization.\n        inputParameters:\n        - name: OrganizationId\n          in: path\n          type: string\n          required: true\n          description: The organization identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mailboxes\n      path: /organizations/{OrganizationId}/mailbox-export-jobs\n      description: Manage mailbox export jobs.\n      operations:\n      - name: list-mailbox-export-jobs\n        method: GET\n        description: List mailbox export jobs.\n        inputParameters:\n        - name: OrganizationId\n          in: path\n          type: string\n          required: true\n          description: The organization identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mobile-device-access-rules\n\
  \      path: /organizations/{OrganizationId}/mobile-device-access/rules\n      description: Manage mobile device access rules.\n      operations:\n      - name: list-mobile-device-access-rules\n        method: GET\n        description: List mobile device access rules.\n        inputParameters:\n        - name: OrganizationId\n          in: path\n          type: string\n          required: true\n          description: The organization identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: email-management-api\n    description: Unified REST API for Amazon WorkMail email infrastructure management.\n    resources:\n    - path: /v1/organizations\n      name: organizations\n      description: WorkMail organization management.\n      operations:\n      - method: GET\n        name: list-organizations\n        description: List all WorkMail organizations.\n\
  \        call: workmail.list-organizations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: User provisioning and management.\n      operations:\n      - method: GET\n        name: list-users\n        description: List users in an organization.\n        call: workmail.list-users\n        with:\n          OrganizationId: rest.organization_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-user\n        description: Create a new email user.\n        call: workmail.create-user\n        with:\n          OrganizationId: rest.organization_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups\n      name: groups\n      description: Group management.\n      operations:\n      - method: GET\n        name: list-groups\n        description: List email groups.\n        call: workmail.list-groups\n\
  \        with:\n          OrganizationId: rest.organization_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/mobile-device-access\n      name: mobile-device-access\n      description: Mobile device access control.\n      operations:\n      - method: GET\n        name: list-mobile-device-access-rules\n        description: List mobile device access rules.\n        call: workmail.list-mobile-device-access-rules\n        with:\n          OrganizationId: rest.organization_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: email-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon WorkMail email infrastructure management.\n    tools:\n    - name: list-organizations\n      description: List all Amazon WorkMail organizations in the account.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: workmail.list-organizations\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List users in a WorkMail organization.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: workmail.list-users\n      with:\n        OrganizationId: tools.organization_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-user\n      description: Create a new WorkMail user with mailbox.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: workmail.create-user\n      with:\n        OrganizationId: tools.organization_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-groups\n      description: List email distribution groups in an organization.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: workmail.list-groups\n      with:\n        OrganizationId: tools.organization_id\n      outputParameters:\n \
  \     - type: object\n        mapping: $.\n    - name: list-mobile-device-access-rules\n      description: List mobile device access control rules.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: workmail.list-mobile-device-access-rules\n      with:\n        OrganizationId: tools.organization_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-workmail/refs/heads/main/capabilities/email-management.yaml
tags:
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
