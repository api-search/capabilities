---
categories:
- crm-sales
consumed_apis:
- dataverse-web-api
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
- list accounts
- retrieve multiple accounts
- low-code
- no-code
- business applications
- cloud
- delete an account
- create account
- delete contact
- create an account
- power platform
- create contact
- saas
- retrieve a single contact
- update a contact
- get contact
- list entities
- create a new account
- create a new contact
- get account
- retrieve a single account
- dataverse
- retrieve multiple contacts
- list contacts
- data platform
- delete a contact
- get entity
- retrieve entity definitions
- power apps
- enterprise
- update an account
- retrieve a single entity definition
- account management
- update account
- delete account
- update contact
- microsoft
slug: data-platform
source_filename: data-platform.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: \"Microsoft Power Apps Data Platform\"\n  description: \"Unified data platform capability combining Dataverse account, contact, and entity management with OData query support. Used by Power Platform developers and CRM integration teams.\"\n  tags: [Microsoft, Power Apps, Dataverse, Data Platform]\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\nbinds:\n  - namespace: env\n    keys:\n      DATAVERSE_OAUTH_TOKEN: DATAVERSE_OAUTH_TOKEN\ncapability:\n  consumes:\n    - import: dataverse-web-api\n      location: ./shared/dataverse-web-api.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: data-platform-api\n      description: \"Unified REST API for Microsoft Power Apps data platform.\"\n      resources:\n        - path: /v1/accounts\n          name: accounts\n          description: \"Account management\"\n          operations:\n            - { method: GET, name: list-accounts, description: \"List accounts\", call:\
  \ \"dataverse-web-api.list-accounts\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n            - { method: POST, name: create-account, description: \"Create an account\", call: \"dataverse-web-api.create-account\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n    - type: mcp\n      port: 9090\n      namespace: data-platform-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Dataverse data operations.\"\n      tools:\n        - { name: list-accounts, description: \"Retrieve multiple accounts\", hints: { readOnly: true, openWorld: true }, call: \"dataverse-web-api.list-accounts\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: get-account, description: \"Retrieve a single account\", hints: { readOnly: true }, call: \"dataverse-web-api.get-account\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: create-account, description: \"Create a new account\", call: \"dataverse-web-api.create-account\"\
  , outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: update-account, description: \"Update an account\", call: \"dataverse-web-api.update-account\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: delete-account, description: \"Delete an account\", hints: { destructive: true }, call: \"dataverse-web-api.delete-account\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-contacts, description: \"Retrieve multiple contacts\", hints: { readOnly: true, openWorld: true }, call: \"dataverse-web-api.list-contacts\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: get-contact, description: \"Retrieve a single contact\", hints: { readOnly: true }, call: \"dataverse-web-api.get-contact\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: create-contact, description: \"Create a new contact\", call: \"dataverse-web-api.create-contact\", outputParameters: [{ type: object,\
  \ mapping: \"$.\" }] }\n        - { name: update-contact, description: \"Update a contact\", call: \"dataverse-web-api.update-contact\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: delete-contact, description: \"Delete a contact\", hints: { destructive: true }, call: \"dataverse-web-api.delete-contact\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-entities, description: \"Retrieve entity definitions\", hints: { readOnly: true }, call: \"dataverse-web-api.list-entities\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: get-entity, description: \"Retrieve a single entity definition\", hints: { readOnly: true }, call: \"dataverse-web-api.get-entity\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n"
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
