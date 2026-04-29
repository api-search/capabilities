---
categories:
- security
consumed_apis:
- 1password-connect
- 1password-events
- 1password-partnership
description: Unified secrets management and security monitoring workflow for 1Password. Combines the Connect Server API (vault and item management), Events API (audit log and sign-in monitoring), and Partnership API (account provisioning) into a single workflow for DevOps engineers, security operations teams, and 1Password partners.
layout: capability
name: 1Password Secrets Management
operations:
- description: List all accessible vaults.
  method: GET
  name: list-vaults
  path: /v1/vaults
- description: List all items in a vault.
  method: GET
  name: list-items
  path: /v1/vaults/{vaultId}/items
- description: Create a new item in a vault.
  method: POST
  name: create-item
  path: /v1/vaults/{vaultId}/items
- description: Retrieve sign-in attempt events for security monitoring.
  method: POST
  name: get-sign-in-events
  path: /v1/events/sign-ins
- description: Retrieve item usage events for compliance and auditing.
  method: POST
  name: get-item-usage-events
  path: /v1/events/item-usage
- description: Provision a new 1Password account for a partner customer.
  method: POST
  name: create-account
  path: /v1/accounts
personas: []
provider_name: 1Password
provider_slug: 1password
search_terms:
- create a new item in a vault.
- event streaming for sign-ins, item usage, and audit trails
- password manager
- list vault items
- get audit events
- manages secrets injection into applications and infrastructure using connect server
- list all accessible vaults.
- retrieve 1password sign-in attempt events for security monitoring.
- security
- update an existing item in a 1password vault.
- get item
- list vaults
- get item usage events
- manage items within a vault.
- list all items in a vault.
- update item
- create account
- monitors sign-in events, item usage, and audit logs for security compliance
- retrieve sign-in audit events.
- get sign in events
- retrieve item usage events for compliance and auditing.
- retrieve 1password item usage events for compliance auditing.
- DevOps Engineer
- Security Operations
- vault and item crud operations via connect server
- list all items stored in a specific 1password vault.
- devops
- manage 1password vaults.
- create item
- account provisioning for 1password partners
- list all api requests made to the 1password connect server.
- list items
- create a new item in a 1password vault.
- manage partner billing accounts.
- passwords
- list all 1password vaults accessible to the connect server.
- delete an item from a 1password vault.
- 1Password Partner
- unified secrets management, security monitoring, and account provisioning
- get a specific item from a 1password vault.
- provision a new 1password account for a partner customer.
- retrieve 1password audit events for compliance reporting.
- provisions and manages 1password accounts for partner customers
- retrieve sign-in attempt events for security monitoring.
- provision partner account
- delete item
- retrieve item usage audit events.
- secrets
- list api activity
slug: 1password-secrets-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: 1Password Secrets Management\n  description: >-\n    Unified secrets management and security monitoring workflow for 1Password.\n    Combines the Connect Server API (vault and item management), Events API\n    (audit log and sign-in monitoring), and Partnership API (account provisioning)\n    into a single workflow for DevOps engineers, security operations teams, and\n    1Password partners.\n  tags:\n    - Security\n    - Passwords\n    - Secrets\n    - DevOps\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      CONNECT_TOKEN: CONNECT_TOKEN\n      EVENTS_TOKEN: EVENTS_TOKEN\n      PARTNERSHIP_TOKEN: PARTNERSHIP_TOKEN\n\ncapability:\n  consumes:\n    - import: 1password-connect\n      location: ./shared/1password-connect.yaml\n    - import: 1password-events\n      location: ./shared/1password-events.yaml\n    - import: 1password-partnership\n      location: ./shared/1password-partnership.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8080\n      namespace: 1password-secrets-api\n      description: \"Unified REST API for 1Password secrets management.\"\n      resources:\n        - path: /v1/vaults\n          name: vaults\n          description: \"Manage 1Password vaults.\"\n          operations:\n            - method: GET\n              name: list-vaults\n              description: \"List all accessible vaults.\"\n              call: \"1password-connect.get---vaults\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/vaults/{vaultId}/items\n          name: items\n          description: \"Manage items within a vault.\"\n          operations:\n            - method: GET\n              name: list-items\n              description: \"List all items in a vault.\"\n              call: \"1password-connect.get---vaults--vaultUuid--items\"\n              with:\n                vaultUuid: \"rest.vaultId\"\n     \
  \         outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-item\n              description: \"Create a new item in a vault.\"\n              call: \"1password-connect.post---vaults--vaultUuid--items\"\n              with:\n                vaultUuid: \"rest.vaultId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/events/sign-ins\n          name: sign-in-events\n          description: \"Retrieve sign-in audit events.\"\n          operations:\n            - method: POST\n              name: get-sign-in-events\n              description: \"Retrieve sign-in attempt events for security monitoring.\"\n              call: \"1password-events.post--api-v1-signinattempts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/events/item-usage\n          name: item-usage-events\n\
  \          description: \"Retrieve item usage audit events.\"\n          operations:\n            - method: POST\n              name: get-item-usage-events\n              description: \"Retrieve item usage events for compliance and auditing.\"\n              call: \"1password-events.post--api-v1-itemusages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/accounts\n          name: partner-accounts\n          description: \"Manage partner billing accounts.\"\n          operations:\n            - method: POST\n              name: create-account\n              description: \"Provision a new 1Password account for a partner customer.\"\n              call: \"1password-partnership.post---accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: 1password-secrets-mcp\n      transport: http\n      description: \"\
  MCP server for AI-assisted 1Password secrets management and security monitoring.\"\n      tools:\n        - name: list-vaults\n          description: \"List all 1Password vaults accessible to the Connect Server.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"1password-connect.get---vaults\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-vault-items\n          description: \"List all items stored in a specific 1Password vault.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"1password-connect.get---vaults--vaultUuid--items\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-item\n          description: \"Get a specific item from a 1Password vault.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"1password-connect.get---vaults--vaultUuid--items--itemUuid-\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-item\n          description: \"Create a new item in a 1Password vault.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"1password-connect.post---vaults--vaultUuid--items\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-item\n          description: \"Update an existing item in a 1Password vault.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"1password-connect.put---vaults--vaultUuid--items--itemUuid-\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-item\n          description: \"Delete an item from a 1Password vault.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent:\
  \ true\n          call: \"1password-connect.delete---vaults--vaultUuid--items--itemUuid-\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-sign-in-events\n          description: \"Retrieve 1Password sign-in attempt events for security monitoring.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"1password-events.post--api-v1-signinattempts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-item-usage-events\n          description: \"Retrieve 1Password item usage events for compliance auditing.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"1password-events.post--api-v1-itemusages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-audit-events\n          description: \"Retrieve 1Password audit events for compliance\
  \ reporting.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"1password-events.post--api-v1-auditevents\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-api-activity\n          description: \"List all API requests made to the 1Password Connect Server.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"1password-connect.get--v1-activity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: provision-partner-account\n          description: \"Provision a new 1Password account for a partner customer.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"1password-partnership.post---accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/1password/refs/heads/main/capabilities/1password-secrets-management.yaml
tags:
- Security
- Passwords
- Secrets
- DevOps
tools:
- description: List all 1Password vaults accessible to the Connect Server.
  hints:
    openWorld: false
    readOnly: true
  name: list-vaults
- description: List all items stored in a specific 1Password vault.
  hints:
    openWorld: false
    readOnly: true
  name: list-vault-items
- description: Get a specific item from a 1Password vault.
  hints:
    openWorld: false
    readOnly: true
  name: get-item
- description: Create a new item in a 1Password vault.
  hints:
    destructive: false
    readOnly: false
  name: create-item
- description: Update an existing item in a 1Password vault.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-item
- description: Delete an item from a 1Password vault.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-item
- description: Retrieve 1Password sign-in attempt events for security monitoring.
  hints:
    openWorld: false
    readOnly: true
  name: get-sign-in-events
- description: Retrieve 1Password item usage events for compliance auditing.
  hints:
    openWorld: false
    readOnly: true
  name: get-item-usage-events
- description: Retrieve 1Password audit events for compliance reporting.
  hints:
    openWorld: false
    readOnly: true
  name: get-audit-events
- description: List all API requests made to the 1Password Connect Server.
  hints:
    openWorld: false
    readOnly: true
  name: list-api-activity
- description: Provision a new 1Password account for a partner customer.
  hints:
    destructive: false
    readOnly: false
  name: provision-partner-account
---
