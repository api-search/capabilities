---
api_specs:
- filename: airtable-metadata-api-openapi.yml
  format: yaml
  label: airtable-meta
  slug: airtable-meta
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/airtable/refs/heads/main/openapi/airtable-metadata-api-openapi.yml
categories: []
consumed_apis:
- airtable
- airtable-meta
description: Unified workflow for managing Airtable databases — reading and writing records, browsing base schemas, managing webhooks, and administering tables. Used by developers and data teams integrating Airtable with external systems.
layout: capability
name: Airtable Database Management
operations:
- description: List all accessible bases.
  method: GET
  name: list-bases
  path: /v1/bases
- description: List records from a table.
  method: GET
  name: list-records
  path: /v1/records
- description: Create records in a table.
  method: POST
  name: create-records
  path: /v1/records
- description: Update a record.
  method: PATCH
  name: update-record
  path: /v1/records/{recordId}
- description: Delete a record.
  method: DELETE
  name: delete-record
  path: /v1/records/{recordId}
personas: []
provider_name: Airtable
provider_slug: airtable
search_terms:
- low-code
- list all airtable bases the user has access to.
- Developer
- create one or more records in an airtable table.
- real-time event-driven integrations via webhooks.
- update a record.
- user management, audit logs, and access control.
- creating, reading, updating, and deleting data records.
- applications
- list records
- list records from a table.
- integrates airtable with external systems via the rest api.
- no-code
- list all accessible bases.
- airtable
- data
- records
- reads and analyzes airtable data programmatically.
- collaboration
- create records
- schema
- delete a record.
- delete record
- list records from an airtable table with optional filtering.
- read/write airtable records, browse schemas, manage webhooks. used by developers and data teams integrating airtable with external systems.
- productivity
- spreadsheets
- delete an airtable record permanently.
- create records in a table.
- managing the structure of bases, tables, and fields.
- update specific fields in an airtable record.
- Data Analyst
- databases
- manages users, audit logs, and shares across the organization.
- list bases
- update record
- get the schema of an airtable base with all tables and fields.
- airtable table records.
- get base schema
- airtable bases and schemas.
- database
- a specific airtable record.
slug: database-management
source_filename: database-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Airtable Database Management\"\n  description: \"Unified workflow for managing Airtable databases — reading and writing records, browsing base schemas, managing webhooks, and administering tables. Used by developers and data teams integrating Airtable with external systems.\"\n  tags:\n    - Airtable\n    - Database\n    - Low-Code\n    - No-Code\n    - Records\n    - Schema\n    - Collaboration\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AIRTABLE_API_TOKEN: AIRTABLE_API_TOKEN\n\ncapability:\n  consumes:\n    - import: airtable\n      location: ./shared/airtable-api.yaml\n    - import: airtable-meta\n      location: ./shared/airtable-metadata-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: airtable-db-api\n      description: \"Unified REST API for Airtable database management.\"\n      resources:\n        - path: /v1/bases\n          name: bases\n\
  \          description: \"Airtable bases and schemas.\"\n          operations:\n            - method: GET\n              name: list-bases\n              description: \"List all accessible bases.\"\n              call: \"airtable-meta.list-bases\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/records\n          name: records\n          description: \"Airtable table records.\"\n          operations:\n            - method: GET\n              name: list-records\n              description: \"List records from a table.\"\n              call: \"airtable.list-records\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-records\n              description: \"Create records in a table.\"\n              call: \"airtable.create-records\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n        - path: /v1/records/{recordId}\n          name: record\n          description: \"A specific Airtable record.\"\n          operations:\n            - method: PATCH\n              name: update-record\n              description: \"Update a record.\"\n              call: \"airtable.update-record\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-record\n              description: \"Delete a record.\"\n              call: \"airtable.delete-record\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: airtable-db-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Airtable database management.\"\n      tools:\n        - name: list-bases\n          description: \"List all Airtable bases the user has access to.\"\n          hints:\n            readOnly:\
  \ true\n            openWorld: true\n          call: \"airtable-meta.list-bases\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-base-schema\n          description: \"Get the schema of an Airtable base with all tables and fields.\"\n          hints:\n            readOnly: true\n          call: \"airtable-meta.get-base-schema\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-records\n          description: \"List records from an Airtable table with optional filtering.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"airtable.list-records\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-records\n          description: \"Create one or more records in an Airtable table.\"\n          hints:\n            readOnly: false\n          call: \"airtable.create-records\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-record\n          description: \"Update specific fields in an Airtable record.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"airtable.update-record\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-record\n          description: \"Delete an Airtable record permanently.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"airtable.delete-record\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/airtable/refs/heads/main/capabilities/database-management.yaml
tags:
- Airtable
- Database
- Low-Code
- No-Code
- Records
- Schema
- Collaboration
tools:
- description: List all Airtable bases the user has access to.
  hints:
    openWorld: true
    readOnly: true
  name: list-bases
- description: Get the schema of an Airtable base with all tables and fields.
  hints:
    readOnly: true
  name: get-base-schema
- description: List records from an Airtable table with optional filtering.
  hints:
    openWorld: true
    readOnly: true
  name: list-records
- description: Create one or more records in an Airtable table.
  hints:
    readOnly: false
  name: create-records
- description: Update specific fields in an Airtable record.
  hints:
    idempotent: false
    readOnly: false
  name: update-record
- description: Delete an Airtable record permanently.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-record
---
