---
api_specs:
- filename: 1password-connect-openapi.yml
  format: yaml
  label: 1password-connect
  slug: 1password-connect
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/1password/refs/heads/main/openapi/1password-connect-openapi.yml
- filename: 1password-events-openapi.yml
  format: yaml
  label: 1password-events
  slug: 1password-events
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/1password/refs/heads/main/openapi/1password-events-openapi.yml
- filename: 1password-partnership-openapi.yml
  format: yaml
  label: 1password-partnership
  slug: 1password-partnership
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/1password/refs/heads/main/openapi/1password-partnership-openapi.yml
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
- passwords
- create item
- get item usage events
- provision a new 1password account for a partner customer.
- get item
- delete an item from a 1password vault.
- create a new item in a vault.
- retrieve item usage events for compliance and auditing.
- password manager
- 1Password Partner
- retrieve 1password sign-in attempt events for security monitoring.
- list all api requests made to the 1password connect server.
- provision partner account
- manage items within a vault.
- secrets
- manage 1password vaults.
- list all items in a vault.
- update item
- retrieve item usage audit events.
- unified secrets management, security monitoring, and account provisioning
- create a new item in a 1password vault.
- list api activity
- manages secrets injection into applications and infrastructure using connect server
- event streaming for sign-ins, item usage, and audit trails
- update an existing item in a 1password vault.
- list all 1password vaults accessible to the connect server.
- list vaults
- provisions and manages 1password accounts for partner customers
- devops
- retrieve sign-in audit events.
- retrieve 1password item usage events for compliance auditing.
- get a specific item from a 1password vault.
- create account
- retrieve 1password audit events for compliance reporting.
- delete item
- list vault items
- monitors sign-in events, item usage, and audit logs for security compliance
- vault and item crud operations via connect server
- Security Operations
- security
- DevOps Engineer
- list all items stored in a specific 1password vault.
- list items
- retrieve sign-in attempt events for security monitoring.
- get sign in events
- get audit events
- account provisioning for 1password partners
- list all accessible vaults.
- manage partner billing accounts.
slug: 1password-secrets-management
source_filename: 1password-secrets-management.yaml
source_heading: Capability Spec
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
