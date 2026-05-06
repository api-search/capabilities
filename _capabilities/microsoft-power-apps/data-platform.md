---
categories:
- crm-sales
consumed_apis: []
description: Unified data platform capability combining Dataverse account, contact, and entity management with OData query support. Used by Power Platform developers and CRM integration teams.
layout: capability
name: Microsoft Power Apps Data Platform
operations:
- description: List accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: Create an account
  method: POST
  name: create-account
  path: /v1/accounts
personas: []
provider_name: Microsoft Power Apps
provider_slug: microsoft-power-apps
search_terms:
- dataverse
- no-code
- account management
- low-code
- power platform
- get contact
- create contact
- update an account
- create a new account
- update contact
- power apps
- cloud
- retrieve a single entity definition
- list entities
- update account
- retrieve a single contact
- enterprise
- retrieve multiple accounts
- create an account
- retrieve entity definitions
- update a contact
- saas
- get entity
- business applications
- create a new contact
- delete an account
- create account
- delete contact
- delete a contact
- list accounts
- retrieve a single account
- list contacts
- get account
- delete account
- data platform
- microsoft
- retrieve multiple contacts
slug: data-platform
source_filename: data-platform.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Microsoft Power Apps Data Platform\n  description: Unified data platform capability combining Dataverse account, contact, and entity management with OData query\n    support. Used by Power Platform developers and CRM integration teams.\n  tags:\n  - Microsoft\n  - Power Apps\n  - Dataverse\n  - Data Platform\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    DATAVERSE_OAUTH_TOKEN: DATAVERSE_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: dataverse-web-api\n    baseUri: https://yourorg.api.crm.dynamics.com/api/data/v9.2\n    description: Dataverse Web API for account, contact, and entity CRUD operations.\n    authentication:\n      type: bearer\n      token: '{{DATAVERSE_OAUTH_TOKEN}}'\n    resources:\n    - name: accounts\n      path: /accounts\n      description: Account entity operations\n      operations:\n      - name: list-accounts\n        method: GET\n        description:\
  \ Retrieve multiple accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-account\n        method: POST\n        description: Create a new account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-account\n        method: GET\n        description: Retrieve a single account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-account\n        method: PATCH\n        description: Update an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-account\n        method: DELETE\n        description: Delete an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n \
  \         type: object\n          value: $.\n    - name: contacts\n      path: /contacts\n      description: Contact entity operations\n      operations:\n      - name: list-contacts\n        method: GET\n        description: Retrieve multiple contacts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-contact\n        method: POST\n        description: Create a new contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-contact\n        method: GET\n        description: Retrieve a single contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-contact\n        method: PATCH\n        description: Update a contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: delete-contact\n        method: DELETE\n        description: Delete a contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entities\n      path: /entities\n      description: Entity definition operations\n      operations:\n      - name: list-entities\n        method: GET\n        description: Retrieve entity definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-entity\n        method: GET\n        description: Retrieve a single entity definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: data-platform-api\n    description: Unified REST API for Microsoft Power Apps data platform.\n    resources:\n\
  \    - path: /v1/accounts\n      name: accounts\n      description: Account management\n      operations:\n      - method: GET\n        name: list-accounts\n        description: List accounts\n        call: dataverse-web-api.list-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-account\n        description: Create an account\n        call: dataverse-web-api.create-account\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: data-platform-mcp\n    transport: http\n    description: MCP server for AI-assisted Dataverse data operations.\n    tools:\n    - name: list-accounts\n      description: Retrieve multiple accounts\n      hints:\n        readOnly: true\n        openWorld: true\n      call: dataverse-web-api.list-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account\n      description: Retrieve\
  \ a single account\n      hints:\n        readOnly: true\n      call: dataverse-web-api.get-account\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-account\n      description: Create a new account\n      call: dataverse-web-api.create-account\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-account\n      description: Update an account\n      call: dataverse-web-api.update-account\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-account\n      description: Delete an account\n      hints:\n        destructive: true\n      call: dataverse-web-api.delete-account\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-contacts\n      description: Retrieve multiple contacts\n      hints:\n        readOnly: true\n        openWorld: true\n      call: dataverse-web-api.list-contacts\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: get-contact\n      description: Retrieve a single contact\n      hints:\n        readOnly: true\n      call: dataverse-web-api.get-contact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-contact\n      description: Create a new contact\n      call: dataverse-web-api.create-contact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-contact\n      description: Update a contact\n      call: dataverse-web-api.update-contact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-contact\n      description: Delete a contact\n      hints:\n        destructive: true\n      call: dataverse-web-api.delete-contact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-entities\n      description: Retrieve entity definitions\n      hints:\n        readOnly: true\n      call: dataverse-web-api.list-entities\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: get-entity\n      description: Retrieve a single entity definition\n      hints:\n        readOnly: true\n      call: dataverse-web-api.get-entity\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-power-apps/refs/heads/main/capabilities/data-platform.yaml
tags:
- Microsoft
- Power Apps
- Dataverse
- Data Platform
tools:
- description: Retrieve multiple accounts
  hints:
    openWorld: true
    readOnly: true
  name: list-accounts
- description: Retrieve a single account
  hints:
    readOnly: true
  name: get-account
- description: Create a new account
  hints: {}
  name: create-account
- description: Update an account
  hints: {}
  name: update-account
- description: Delete an account
  hints:
    destructive: true
  name: delete-account
- description: Retrieve multiple contacts
  hints:
    openWorld: true
    readOnly: true
  name: list-contacts
- description: Retrieve a single contact
  hints:
    readOnly: true
  name: get-contact
- description: Create a new contact
  hints: {}
  name: create-contact
- description: Update a contact
  hints: {}
  name: update-contact
- description: Delete a contact
  hints:
    destructive: true
  name: delete-contact
- description: Retrieve entity definitions
  hints:
    readOnly: true
  name: list-entities
- description: Retrieve a single entity definition
  hints:
    readOnly: true
  name: get-entity
---
