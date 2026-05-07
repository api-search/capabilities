---
categories:
- security
consumed_apis: []
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
- devops
- retrieve 1password item usage events for compliance auditing.
- unified secrets management, security monitoring, and account provisioning
- retrieve item usage audit events.
- DevOps Engineer
- secrets
- list items
- get a specific item from a 1password vault.
- manage partner billing accounts.
- update item
- list api activity
- 1Password Partner
- event streaming for sign-ins, item usage, and audit trails
- retrieve sign-in audit events.
- update an existing item in a 1password vault.
- vault and item crud operations via connect server
- create item
- list all items in a vault.
- monitors sign-in events, item usage, and audit logs for security compliance
- retrieve 1password audit events for compliance reporting.
- password manager
- retrieve item usage events for compliance and auditing.
- provisions and manages 1password accounts for partner customers
- manage items within a vault.
- list all api requests made to the 1password connect server.
- create a new item in a vault.
- list all 1password vaults accessible to the connect server.
- list vault items
- manage 1password vaults.
- create account
- list vaults
- provision a new 1password account for a partner customer.
- retrieve 1password sign-in attempt events for security monitoring.
- passwords
- Security Operations
- account provisioning for 1password partners
- manages secrets injection into applications and infrastructure using connect server
- get sign in events
- provision partner account
- create a new item in a 1password vault.
- list all accessible vaults.
- delete item
- get item usage events
- get item
- security
- retrieve sign-in attempt events for security monitoring.
- delete an item from a 1password vault.
- get audit events
- list all items stored in a specific 1password vault.
slug: 1password-secrets-management
source_filename: 1password-secrets-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: 1Password Secrets Management\n  description: Unified secrets management and security monitoring workflow for 1Password. Combines the Connect Server API\n    (vault and item management), Events API (audit log and sign-in monitoring), and Partnership API (account provisioning)\n    into a single workflow for DevOps engineers, security operations teams, and 1Password partners.\n  tags:\n  - Security\n  - Passwords\n  - Secrets\n  - DevOps\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    CONNECT_TOKEN: CONNECT_TOKEN\n    EVENTS_TOKEN: EVENTS_TOKEN\n    PARTNERSHIP_TOKEN: PARTNERSHIP_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: 1password-connect\n    baseUri: http://localhost:8080/v1\n    description: 1Password Connect API\n    authentication:\n      type: bearer\n      token: '{{CONNECT_TOKEN}}'\n    resources:\n    - name: vaults\n      path: /v1/vaults\n      description: Vaults\
  \ operations\n      operations:\n      - name: get-v1-vaults\n        method: GET\n        description: 1Password List Vaults\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ''\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-v1-vaults-vaultUuid\n        method: GET\n        description: 1Password Get Vault Details\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ''\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: items\n      path: /v1/vaults/{vaultUuid}/items\n      description: Items operations\n      operations:\n      - name: get-v1-vaults-vaultUuid-items\n        method: GET\n        description: 1Password List\
  \ Items in a Vault\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ''\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ''\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-v1-vaults-vaultUuid-items\n        method: POST\n        description: 1Password Create a New Item\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ''\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: get-v1-vaults-vaultUuid-items-itemUuid\n        method: GET\n        description: 1Password Get Item Details\n        inputParameters:\n\
  \        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ''\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ''\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-v1-vaults-vaultUuid-items-itemUuid\n        method: PUT\n        description: 1Password Replace an Item\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ''\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ''\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: patch-v1-vaults-vaultUuid-items-itemUuid\n      \
  \  method: PATCH\n        description: 1Password Update an Item\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ''\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ''\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-v1-vaults-vaultUuid-items-itemUuid\n        method: DELETE\n        description: 1Password Delete an Item\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ''\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ''\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: files\n      path: /v1/vaults/{vaultUuid}/items/{itemUuid}/files\n      description: Files operations\n      operations:\n      - name: get-v1-vaults-vaultUuid-items-itemUuid-files\n        method: GET\n        description: 1Password List Files Attached to an Item\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ''\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ''\n        - name: inline_files\n          in: query\n          type: boolean\n          required: false\n          description: When set to true, file content is included inline in the response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-v1-vaults-vaultUuid-items-itemUuid-files-fileUuid\n        method: GET\n        description:\
  \ 1Password Get File Details\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ''\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ''\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ''\n        - name: inline_files\n          in: query\n          type: boolean\n          required: false\n          description: When set to true, file content is included inline in the response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-v1-vaults-vaultUuid-items-itemUuid-files-fileUuid-content\n        method: GET\n        description: 1Password Get File Content\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n\
  \          description: ''\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ''\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ''\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: activity\n      path: /v1/activity\n      description: Activity operations\n      operations:\n      - name: get-v1-activity\n        method: GET\n        description: 1Password List API Activity\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of activity records to return.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Number of activity records to skip before returning results.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: health\n      path: /heartbeat\n      description: Health operations\n      operations:\n      - name: get-heartbeat\n        method: GET\n        description: 1Password Check Server Status\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-health\n        method: GET\n        description: 1Password Get Server Health\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics\n      path: /metrics\n      description: Metrics operations\n      operations:\n      - name: get-metrics\n        method: GET\n        description: 1Password Get Server Metrics\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: 1password-events\n    baseUri: https://events.1password.com\n    description: 1Password Events API\n    authentication:\n      type: bearer\n      token: '{{EVENTS_TOKEN}}'\n    resources:\n    - name: sign-in-attempts\n      path: /api/v2/signinattempts\n      description: Sign-In Attempts operations\n      operations:\n      - name: post-api-v2-signinattempts\n        method: POST\n        description: 1Password List Sign-in Attempts\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n    - name: item-usages\n      path: /api/v2/itemusages\n      description: Item Usages operations\n      operations:\n      - name: post-api-v2-itemusages\n        method: POST\n        description: 1Password List Item Usages\n        inputParameters:\
  \ []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n    - name: audit-events\n      path: /api/v2/auditevents\n      description: Audit Events operations\n      operations:\n      - name: post-api-v2-auditevents\n        method: POST\n        description: 1Password List Audit Events\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n    - name: introspection\n      path: /api/v1/introspect\n      description: Introspection operations\n      operations:\n      - name: get-api-v1-introspect\n        method: GET\n        description: 1Password Introspect Authentication Token\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n  - type: http\n    namespace: 1password-partnership\n    baseUri: https://billing.b5test.eu/api/v1\n    description: 1Password Partnership API\n    authentication:\n      type: bearer\n      token: '{{PARTNERSHIP_TOKEN}}'\n    resources:\n    - name: accounts\n      path: /partners/accounts\n      description: Accounts operations\n      operations:\n      - name: post-partners-accounts\n        method: POST\n        description: 1Password Create a Partner Billing Account\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: get-partners-accounts-accountUid\n        method: GET\n        description: 1Password Get Partner Billing Account Details\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description:\
  \ ''\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-partners-accounts-accountUid\n        method: PATCH\n        description: 1Password Update a Partner Billing Account\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ''\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: delete-partners-accounts-accountUid\n        method: DELETE\n        description: 1Password Delete a Partner Billing Account\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ''\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n        \
  \  value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: 1password-secrets-api\n    description: Unified REST API for 1Password secrets management.\n    resources:\n    - path: /v1/vaults\n      name: vaults\n      description: Manage 1Password vaults.\n      operations:\n      - method: GET\n        name: list-vaults\n        description: List all accessible vaults.\n        call: 1password-connect.get---vaults\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vaults/{vaultId}/items\n      name: items\n      description: Manage items within a vault.\n      operations:\n      - method: GET\n        name: list-items\n        description: List all items in a vault.\n        call: 1password-connect.get---vaults--vaultUuid--items\n        with:\n          vaultUuid: rest.vaultId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-item\n        description: Create a new\
  \ item in a vault.\n        call: 1password-connect.post---vaults--vaultUuid--items\n        with:\n          vaultUuid: rest.vaultId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events/sign-ins\n      name: sign-in-events\n      description: Retrieve sign-in audit events.\n      operations:\n      - method: POST\n        name: get-sign-in-events\n        description: Retrieve sign-in attempt events for security monitoring.\n        call: 1password-events.post--api-v1-signinattempts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events/item-usage\n      name: item-usage-events\n      description: Retrieve item usage audit events.\n      operations:\n      - method: POST\n        name: get-item-usage-events\n        description: Retrieve item usage events for compliance and auditing.\n        call: 1password-events.post--api-v1-itemusages\n        outputParameters:\n        - type: object\n       \
  \   mapping: $.\n    - path: /v1/accounts\n      name: partner-accounts\n      description: Manage partner billing accounts.\n      operations:\n      - method: POST\n        name: create-account\n        description: Provision a new 1Password account for a partner customer.\n        call: 1password-partnership.post---accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: 1password-secrets-mcp\n    transport: http\n    description: MCP server for AI-assisted 1Password secrets management and security monitoring.\n    tools:\n    - name: list-vaults\n      description: List all 1Password vaults accessible to the Connect Server.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: 1password-connect.get---vaults\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-vault-items\n      description: List all items stored in a specific 1Password vault.\n      hints:\n\
  \        readOnly: true\n        openWorld: false\n      call: 1password-connect.get---vaults--vaultUuid--items\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-item\n      description: Get a specific item from a 1Password vault.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: 1password-connect.get---vaults--vaultUuid--items--itemUuid-\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-item\n      description: Create a new item in a 1Password vault.\n      hints:\n        readOnly: false\n        destructive: false\n      call: 1password-connect.post---vaults--vaultUuid--items\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-item\n      description: Update an existing item in a 1Password vault.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: 1password-connect.put---vaults--vaultUuid--items--itemUuid-\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-item\n      description: Delete an item from a 1Password vault.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: 1password-connect.delete---vaults--vaultUuid--items--itemUuid-\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-sign-in-events\n      description: Retrieve 1Password sign-in attempt events for security monitoring.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: 1password-events.post--api-v1-signinattempts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-item-usage-events\n      description: Retrieve 1Password item usage events for compliance auditing.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: 1password-events.post--api-v1-itemusages\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: get-audit-events\n      description: Retrieve 1Password audit events for compliance reporting.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: 1password-events.post--api-v1-auditevents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-api-activity\n      description: List all API requests made to the 1Password Connect Server.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: 1password-connect.get--v1-activity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: provision-partner-account\n      description: Provision a new 1Password account for a partner customer.\n      hints:\n        readOnly: false\n        destructive: false\n      call: 1password-partnership.post---accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
