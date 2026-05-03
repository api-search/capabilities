---
api_specs:
- filename: database.yaml
  format: yaml
  label: snowflake-database
  slug: snowflake-database
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/database.yaml
- filename: schema.yaml
  format: yaml
  label: snowflake-schema
  slug: snowflake-schema
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/schema.yaml
- filename: table.yaml
  format: yaml
  label: snowflake-table
  slug: snowflake-table
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/table.yaml
- filename: view.yaml
  format: yaml
  label: snowflake-view
  slug: snowflake-view
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/view.yaml
- filename: dynamic-table.yaml
  format: yaml
  label: snowflake-dynamic-table
  slug: snowflake-dynamic-table
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/dynamic-table.yaml
- filename: iceberg-table.yaml
  format: yaml
  label: snowflake-iceberg-table
  slug: snowflake-iceberg-table
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/iceberg-table.yaml
- filename: event-table.yaml
  format: yaml
  label: snowflake-event-table
  slug: snowflake-event-table
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/event-table.yaml
- filename: external-volume.yaml
  format: yaml
  label: snowflake-external-volume
  slug: snowflake-external-volume
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/openapi/external-volume.yaml
categories:
- data-engineering
consumed_apis:
- snowflake-database
- snowflake-schema
- snowflake-table
- snowflake-view
- snowflake-dynamic-table
- snowflake-iceberg-table
- snowflake-event-table
- snowflake-external-volume
description: Unified workflow for managing databases, schemas, tables, views, dynamic tables, iceberg tables, and event tables. Used by Data Engineers and Database Administrators to create, organize, and maintain data structures.
layout: capability
name: Snowflake Data Management
operations:
- description: List all databases
  method: GET
  name: list-databases
  path: /v1/databases
- description: Create a database
  method: POST
  name: create-database
  path: /v1/databases
- description: Fetch a database
  method: GET
  name: fetch-database
  path: /v1/databases/{name}
- description: Delete a database
  method: DELETE
  name: delete-database
  path: /v1/databases/{name}
- description: List schemas
  method: GET
  name: list-schemas
  path: /v1/schemas
- description: Create a schema
  method: POST
  name: create-schema
  path: /v1/schemas
- description: List tables
  method: GET
  name: list-tables
  path: /v1/tables
- description: Create a table
  method: POST
  name: create-table
  path: /v1/tables
- description: List views
  method: GET
  name: list-views
  path: /v1/views
- description: Create a view
  method: POST
  name: create-view
  path: /v1/views
- description: List dynamic tables
  method: GET
  name: list-dynamic-tables
  path: /v1/dynamic-tables
- description: Create a dynamic table
  method: POST
  name: create-dynamic-table
  path: /v1/dynamic-tables
- description: List Iceberg tables
  method: GET
  name: list-iceberg-tables
  path: /v1/iceberg-tables
- description: Create an Iceberg table
  method: POST
  name: create-iceberg-table
  path: /v1/iceberg-tables
personas: []
provider_name: Snowflake
provider_slug: snowflake
search_terms:
- list dynamic tables
- fetch table
- table management
- list iceberg tables
- create event table
- delete table
- create external volume
- data warehousing
- create database
- fetch database
- view management
- snowflake
- create a new database
- delete database
- list tables
- iceberg table management
- create a view
- resume a dynamic table
- create table
- resume dynamic table
- data lakes
- delete a schema
- clone a database
- suspend dynamic table
- data engineering
- list views in a schema
- fetch database details by name
- suspend a dynamic table
- list all accessible databases
- create view
- create a dynamic table
- fetch schema details
- restore a dropped database
- create a new table
- create a table
- dynamic table management
- list tables in a schema
- delete a table
- create an iceberg table
- fetch table details
- list schemas
- list schemas in a database
- list external volumes
- database
- database management
- sql
- schema management
- undrop database
- data management
- create a new schema
- delete schema
- list all databases
- create iceberg table
- list event tables
- create schema
- create an event table
- list databases
- create an external volume
- data sharing
- fetch schema
- list views
- single database operations
- delete a database
- create a schema
- create a new view
- create a database
- fetch a database
- create dynamic table
- clone database
slug: data-management
source_filename: data-management.yaml
source_heading: Capability Spec
source_yaml: "# Naftiko Snowflake Data Management capability.\n# Composes eight shared Snowflake sub-capabilities (database, schema, table,\n# view, dynamic-table, iceberg-table, event-table, external-volume) and\n# exposes them through a triple adapter surface: REST for conventional\n# clients, MCP (HTTP + stdio transports) for AI agents, and Agent Skills\n# for skill-aware AI clients. Input and output parameters use typed\n# JSONPath mappings so payloads are task-ready for both humans and agents.\nnaftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Snowflake Data Management\"\n  description: \"Unified workflow for managing databases, schemas, tables, views, dynamic tables, iceberg tables, and event tables. Used by Data Engineers and Database Administrators to create, organize, and maintain data structures.\"\n  tags:\n    - Snowflake\n    - Data Management\n    - Data Engineering\n  created: \"2026-04-18\"\n  modified: \"2026-04-23\"\n\nbinds:\n  - namespace: env\n    keys:\n      SNOWFLAKE_ACCOUNT_URL:\
  \ SNOWFLAKE_ACCOUNT_URL\n      SNOWFLAKE_JWT_TOKEN: SNOWFLAKE_JWT_TOKEN\n\ncapability:\n  consumes:\n    - import: snowflake-database\n      location: ./shared/database.yaml\n    - import: snowflake-schema\n      location: ./shared/schema.yaml\n    - import: snowflake-table\n      location: ./shared/table.yaml\n    - import: snowflake-view\n      location: ./shared/view.yaml\n    - import: snowflake-dynamic-table\n      location: ./shared/dynamic-table.yaml\n    - import: snowflake-iceberg-table\n      location: ./shared/iceberg-table.yaml\n    - import: snowflake-event-table\n      location: ./shared/event-table.yaml\n    - import: snowflake-external-volume\n      location: ./shared/external-volume.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: snowflake-data-mgmt-api\n      description: \"Unified REST API for Snowflake data structure management.\"\n      resources:\n        - path: /v1/databases\n          name: databases\n          description: \"Database management\"\
  \n          operations:\n            - method: GET\n              name: list-databases\n              description: \"List all databases\"\n              call: \"snowflake-database.list-databases\"\n              inputParameters:\n                - name: like\n                  in: query\n                  type: string\n                  required: false\n                  description: \"Filter by name pattern\"\n                  mapping: \"snowflake-database.list-databases.like\"\n              outputParameters:\n                - name: databases\n                  type: array\n                  description: \"Array of database objects\"\n                  mapping: \"$.\"\n            - method: POST\n              name: create-database\n              description: \"Create a database\"\n              call: \"snowflake-database.create-database\"\n              inputParameters:\n                - name: name\n                  in: body\n                  type: string\n                  required:\
  \ true\n                  description: \"Database name to create\"\n                  mapping: \"snowflake-database.create-database.name\"\n              outputParameters:\n                - name: result\n                  type: object\n                  description: \"Created database metadata\"\n                  mapping: \"$.\"\n        - path: /v1/databases/{name}\n          name: database\n          description: \"Single database operations\"\n          operations:\n            - method: GET\n              name: fetch-database\n              description: \"Fetch a database\"\n              call: \"snowflake-database.fetch-database\"\n              inputParameters:\n                - name: name\n                  in: path\n                  type: string\n                  required: true\n                  description: \"Database name\"\n                  mapping: \"snowflake-database.fetch-database.name\"\n              outputParameters:\n                - name: result\n          \
  \        type: object\n                  description: \"Database metadata\"\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-database\n              description: \"Delete a database\"\n              call: \"snowflake-database.delete-database\"\n              inputParameters:\n                - name: name\n                  in: path\n                  type: string\n                  required: true\n                  description: \"Database name\"\n                  mapping: \"snowflake-database.delete-database.name\"\n              outputParameters:\n                - name: result\n                  type: object\n                  description: \"Delete status\"\n                  mapping: \"$.\"\n        - path: /v1/schemas\n          name: schemas\n          description: \"Schema management\"\n          operations:\n            - method: GET\n              name: list-schemas\n              description: \"List schemas\"\n              call: \"\
  snowflake-schema.list-schemas\"\n              inputParameters:\n                - name: database\n                  in: query\n                  type: string\n                  required: true\n                  description: \"Database to list schemas from\"\n                  mapping: \"snowflake-schema.list-schemas.database\"\n                - name: like\n                  in: query\n                  type: string\n                  required: false\n                  description: \"Filter by name pattern\"\n                  mapping: \"snowflake-schema.list-schemas.like\"\n              outputParameters:\n                - name: schemas\n                  type: array\n                  description: \"Array of schema objects\"\n                  mapping: \"$.\"\n            - method: POST\n              name: create-schema\n              description: \"Create a schema\"\n              call: \"snowflake-schema.create-schema\"\n              inputParameters:\n                - name: database\n\
  \                  in: body\n                  type: string\n                  required: true\n                  description: \"Database name\"\n                  mapping: \"snowflake-schema.create-schema.database\"\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                  description: \"Schema name\"\n                  mapping: \"snowflake-schema.create-schema.name\"\n              outputParameters:\n                - name: result\n                  type: object\n                  description: \"Created schema metadata\"\n                  mapping: \"$.\"\n        - path: /v1/tables\n          name: tables\n          description: \"Table management\"\n          operations:\n            - method: GET\n              name: list-tables\n              description: \"List tables\"\n              call: \"snowflake-table.list-tables\"\n              inputParameters:\n                - name: database\n       \
  \           in: query\n                  type: string\n                  required: true\n                  description: \"Database name\"\n                  mapping: \"snowflake-table.list-tables.database\"\n                - name: schema\n                  in: query\n                  type: string\n                  required: true\n                  description: \"Schema name\"\n                  mapping: \"snowflake-table.list-tables.schema\"\n              outputParameters:\n                - name: tables\n                  type: array\n                  description: \"Array of table objects\"\n                  mapping: \"$.\"\n            - method: POST\n              name: create-table\n              description: \"Create a table\"\n              call: \"snowflake-table.create-table\"\n              inputParameters:\n                - name: database\n                  in: body\n                  type: string\n                  required: true\n                  description: \"Database\
  \ name\"\n                  mapping: \"snowflake-table.create-table.database\"\n                - name: schema\n                  in: body\n                  type: string\n                  required: true\n                  description: \"Schema name\"\n                  mapping: \"snowflake-table.create-table.schema\"\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                  description: \"Table name\"\n                  mapping: \"snowflake-table.create-table.name\"\n              outputParameters:\n                - name: result\n                  type: object\n                  description: \"Created table metadata\"\n                  mapping: \"$.\"\n        - path: /v1/views\n          name: views\n          description: \"View management\"\n          operations:\n            - method: GET\n              name: list-views\n              description: \"List views\"\n              call: \"snowflake-view.list-views\"\
  \n              inputParameters:\n                - name: database\n                  in: query\n                  type: string\n                  required: true\n                  description: \"Database name\"\n                  mapping: \"snowflake-view.list-views.database\"\n                - name: schema\n                  in: query\n                  type: string\n                  required: true\n                  description: \"Schema name\"\n                  mapping: \"snowflake-view.list-views.schema\"\n              outputParameters:\n                - name: views\n                  type: array\n                  description: \"Array of view objects\"\n                  mapping: \"$.\"\n            - method: POST\n              name: create-view\n              description: \"Create a view\"\n              call: \"snowflake-view.create-view\"\n              inputParameters:\n                - name: database\n                  in: body\n                  type: string\n      \
  \            required: true\n                  description: \"Database name\"\n                  mapping: \"snowflake-view.create-view.database\"\n                - name: schema\n                  in: body\n                  type: string\n                  required: true\n                  description: \"Schema name\"\n                  mapping: \"snowflake-view.create-view.schema\"\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                  description: \"View name\"\n                  mapping: \"snowflake-view.create-view.name\"\n              outputParameters:\n                - name: result\n                  type: object\n                  description: \"Created view metadata\"\n                  mapping: \"$.\"\n        - path: /v1/dynamic-tables\n          name: dynamic-tables\n          description: \"Dynamic table management\"\n          operations:\n            - method: GET\n              name:\
  \ list-dynamic-tables\n              description: \"List dynamic tables\"\n              call: \"snowflake-dynamic-table.list-dynamic-tables\"\n              inputParameters:\n                - name: database\n                  in: query\n                  type: string\n                  required: true\n                  description: \"Database name\"\n                  mapping: \"snowflake-dynamic-table.list-dynamic-tables.database\"\n                - name: schema\n                  in: query\n                  type: string\n                  required: true\n                  description: \"Schema name\"\n                  mapping: \"snowflake-dynamic-table.list-dynamic-tables.schema\"\n              outputParameters:\n                - name: dynamicTables\n                  type: array\n                  description: \"Array of dynamic table objects\"\n                  mapping: \"$.\"\n            - method: POST\n              name: create-dynamic-table\n              description:\
  \ \"Create a dynamic table\"\n              call: \"snowflake-dynamic-table.create-dynamic-table\"\n              inputParameters:\n                - name: database\n                  in: body\n                  type: string\n                  required: true\n                  description: \"Database name\"\n                  mapping: \"snowflake-dynamic-table.create-dynamic-table.database\"\n                - name: schema\n                  in: body\n                  type: string\n                  required: true\n                  description: \"Schema name\"\n                  mapping: \"snowflake-dynamic-table.create-dynamic-table.schema\"\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                  description: \"Dynamic table name\"\n                  mapping: \"snowflake-dynamic-table.create-dynamic-table.name\"\n              outputParameters:\n                - name: result\n                  type:\
  \ object\n                  description: \"Created dynamic table metadata\"\n                  mapping: \"$.\"\n        - path: /v1/iceberg-tables\n          name: iceberg-tables\n          description: \"Iceberg table management\"\n          operations:\n            - method: GET\n              name: list-iceberg-tables\n              description: \"List Iceberg tables\"\n              call: \"snowflake-iceberg-table.list-iceberg-tables\"\n              inputParameters:\n                - name: database\n                  in: query\n                  type: string\n                  required: true\n                  description: \"Database name\"\n                  mapping: \"snowflake-iceberg-table.list-iceberg-tables.database\"\n                - name: schema\n                  in: query\n                  type: string\n                  required: true\n                  description: \"Schema name\"\n                  mapping: \"snowflake-iceberg-table.list-iceberg-tables.schema\"\n\
  \              outputParameters:\n                - name: icebergTables\n                  type: array\n                  description: \"Array of Iceberg table objects\"\n                  mapping: \"$.\"\n            - method: POST\n              name: create-iceberg-table\n              description: \"Create an Iceberg table\"\n              call: \"snowflake-iceberg-table.create-iceberg-table\"\n              inputParameters:\n                - name: database\n                  in: body\n                  type: string\n                  required: true\n                  description: \"Database name\"\n                  mapping: \"snowflake-iceberg-table.create-iceberg-table.database\"\n                - name: schema\n                  in: body\n                  type: string\n                  required: true\n                  description: \"Schema name\"\n                  mapping: \"snowflake-iceberg-table.create-iceberg-table.schema\"\n                - name: name\n             \
  \     in: body\n                  type: string\n                  required: true\n                  description: \"Iceberg table name\"\n                  mapping: \"snowflake-iceberg-table.create-iceberg-table.name\"\n              outputParameters:\n                - name: result\n                  type: object\n                  description: \"Created Iceberg table metadata\"\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: snowflake-data-mgmt-mcp\n      transport: http\n      description: \"MCP server (HTTP transport) for AI-assisted Snowflake data structure management.\"\n      tools:\n        - name: list-databases\n          description: \"List all accessible databases\"\n          call: \"snowflake-database.list-databases\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          inputParameters:\n            - name: like\n              type: string\n              required: false\n\
  \              description: \"Filter by name pattern\"\n              mapping: \"snowflake-database.list-databases.like\"\n          outputParameters:\n            - name: databases\n              type: array\n              description: \"Array of database objects\"\n              mapping: \"$.\"\n        - name: create-database\n          description: \"Create a new database\"\n          call: \"snowflake-database.create-database\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          inputParameters:\n            - name: name\n              type: string\n              required: true\n              description: \"Database name to create\"\n              mapping: \"snowflake-database.create-database.name\"\n          outputParameters:\n            - name: result\n              type: object\n              description: \"Created database metadata\"\n              mapping: \"$.\"\n        - name: fetch-database\n         \
  \ description: \"Fetch database details by name\"\n          call: \"snowflake-database.fetch-database\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          inputParameters:\n            - name: name\n              type: string\n              required: true\n              description: \"Database name\"\n              mapping: \"snowflake-database.fetch-database.name\"\n          outputParameters:\n            - name: result\n              type: object\n              description: \"Database metadata\"\n              mapping: \"$.\"\n        - name: delete-database\n          description: \"Delete a database\"\n          call: \"snowflake-database.delete-database\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          inputParameters:\n            - name: name\n              type: string\n              required: true\n              description: \"Database name\"\
  \n              mapping: \"snowflake-database.delete-database.name\"\n          outputParameters:\n            - name: result\n              type: object\n              description: \"Delete status\"\n              mapping: \"$.\"\n        - name: clone-database\n          description: \"Clone a database\"\n          call: \"snowflake-database.clone-database\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          inputParameters:\n            - name: name\n              type: string\n              required: true\n              description: \"Source database name\"\n              mapping: \"snowflake-database.clone-database.name\"\n          outputParameters:\n            - name: result\n              type: object\n              description: \"Cloned database metadata\"\n              mapping: \"$.\"\n        - name: undrop-database\n          description: \"Restore a dropped database\"\n          call: \"snowflake-database.undrop-database\"\
  \n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          inputParameters:\n            - name: name\n              type: string\n              required: true\n              description: \"Database name\"\n              mapping: \"snowflake-database.undrop-database.name\"\n          outputParameters:\n            - name: result\n              type: object\n              description: \"Restore status\"\n              mapping: \"$.\"\n        - name: list-schemas\n          description: \"List schemas in a database\"\n          call: \"snowflake-schema.list-schemas\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          inputParameters:\n            - name: database\n              type: string\n              required: true\n              description: \"Database name\"\n              mapping: \"snowflake-schema.list-schemas.database\"\n            - name: like\n\
  \              type: string\n              required: false\n              description: \"Filter by name pattern\"\n              mapping: \"snowflake-schema.list-schemas.like\"\n          outputParameters:\n            - name: schemas\n              type: array\n              description: \"Array of schema objects\"\n              mapping: \"$.\"\n        - name: create-schema\n          description: \"Create a new schema\"\n          call: \"snowflake-schema.create-schema\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          inputParameters:\n            - name: database\n              type: string\n              required: true\n              description: \"Database name\"\n              mapping: \"snowflake-schema.create-schema.database\"\n            - name: name\n              type: string\n              required: true\n              description: \"Schema name\"\n              mapping: \"snowflake-schema.create-schema.name\"\
  \n          outputParameters:\n            - name: result\n              type: object\n              description: \"Created schema metadata\"\n              mapping: \"$.\"\n        - name: fetch-schema\n          description: \"Fetch schema details\"\n          call: \"snowflake-schema.fetch-schema\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          inputParameters:\n            - name: database\n              type: string\n              required: true\n              description: \"Database name\"\n              mapping: \"snowflake-schema.fetch-schema.database\"\n            - name: name\n              type: string\n              required: true\n              description: \"Schema name\"\n              mapping: \"snowflake-schema.fetch-schema.name\"\n          outputParameters:\n            - name: result\n              type: object\n              description: \"Schema metadata\"\n              mapping: \"$.\"\n   \
  \     - name: delete-schema\n          description: \"Delete a schema\"\n          call: \"snowflake-schema.delete-schema\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          inputParameters:\n            - name: database\n              type: string\n              required: true\n              description: \"Database name\"\n              mapping: \"snowflake-schema.delete-schema.database\"\n            - name: name\n              type: string\n              required: true\n              description: \"Schema name\"\n              mapping: \"snowflake-schema.delete-schema.name\"\n          outputParameters:\n            - name: result\n              type: object\n              description: \"Delete status\"\n              mapping: \"$.\"\n        - name: list-tables\n          description: \"List tables in a schema\"\n          call: \"snowflake-table.list-tables\"\n          hints:\n            readOnly: true\n      \
  \      destructive: false\n            idempotent: true\n          inputParameters:\n            - name: database\n              type: string\n              required: true\n              description: \"Database name\"\n              mapping: \"snowflake-table.list-tables.database\"\n            - name: schema\n              type: string\n              required: true\n              description: \"Schema name\"\n              mapping: \"snowflake-table.list-tables.schema\"\n          outputParameters:\n            - name: tables\n              type: array\n              description: \"Array of table objects\"\n              mapping: \"$.\"\n        - name: create-table\n          description: \"Create a new table\"\n          call: \"snowflake-table.create-table\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          inputParameters:\n            - name: database\n              type: string\n              required: true\n\
  \              description: \"Database name\"\n              mapping: \"snowflake-table.create-table.database\"\n            - name: schema\n              type: string\n              required: true\n              description: \"Schema name\"\n              mapping: \"snowflake-table.create-table.schema\"\n            - name: name\n              type: string\n              required: true\n              description: \"Table name\"\n              mapping: \"snowflake-table.create-table.name\"\n          outputParameters:\n            - name: result\n              type: object\n              description: \"Created table metadata\"\n              mapping: \"$.\"\n        - name: fetch-table\n          description: \"Fetch table details\"\n          call: \"snowflake-table.fetch-table\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          inputParameters:\n            - name: database\n              type: string\n            \
  \  required: true\n              description: \"Database name\"\n              mapping: \"snowflake-table.fetch-table.database\"\n            - name: schema\n              type: string\n              required: true\n              description: \"Schema name\"\n              mapping: \"snowflake-table.fetch-table.schema\"\n            - name: name\n              type: string\n              required: true\n              description: \"Table name\"\n              mapping: \"snowflake-table.fetch-table.name\"\n          outputParameters:\n            - name: result\n              type: object\n              description: \"Table metadata\"\n              mapping: \"$.\"\n        - name: delete-table\n          description: \"Delete a table\"\n          call: \"snowflake-table.delete-table\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          inputParameters:\n            - name: database\n              type: string\n        \
  \      required: true\n              description: \"Database name\"\n              mapping: \"snowflake-table.delete-table.database\"\n            - name: schema\n              type: string\n              required: true\n              description: \"Schema name\"\n              mapping: \"snowflake-table.delete-table.schema\"\n            - name: name\n              type: string\n              required: true\n              description: \"Table name\"\n              mapping: \"snowflake-table.delete-table.name\"\n          outputParameters:\n            - name: result\n              type: object\n              description: \"Delete status\"\n              mapping: \"$.\"\n        - name: list-views\n          description: \"List views in a schema\"\n          call: \"snowflake-view.list-views\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          inputParameters:\n            - name: database\n              type: string\n\
  \              required: true\n              description: \"Database name\"\n              mapping: \"snowflake-view.list-views.database\"\n            - name: schema\n              type: string\n              required: true\n              description: \"Schema name\"\n              mapping: \"snowflake-view.list-views.schema\"\n          outputParameters:\n            - name: views\n              type: array\n              description: \"Array of view objects\"\n              mapping: \"$.\"\n        - name: create-view\n          description: \"Create a new view\"\n          call: \"snowflake-view.create-view\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          inputParameters:\n            - name: database\n              type: string\n              required: true\n              description: \"Database name\"\n              mapping: \"snowflake-view.create-view.database\"\n            - name: schema\n             \
  \ type: string\n              required: true\n              description: \"Schema name\"\n              mapping: \"snowflake-view.create-view.schema\"\n            - name: name\n              type: string\n              required: true\n              description: \"View name\"\n              mapping: \"snowflake-view.create-view.name\"\n          outputParameters:\n            - name: result\n              type: object\n              description: \"Created view metadata\"\n              mapping: \"$.\"\n        - name: list-dynamic-tables\n          description: \"List dynamic tables\"\n          call: \"snowflake-dynamic-table.list-dynamic-tables\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          inputParameters:\n            - name: database\n              type: string\n              required: true\n              description: \"Database name\"\n              mapping: \"snowflake-dynamic-table.list-dynamic-tables.database\"\
  \n            - name: schema\n              type: string\n              required: true\n              description: \"Schema name\"\n              mapping: \"snowflake-dynamic-table.list-dynamic-tables.schema\"\n          outputParameters:\n            - name: dynamicTables\n              type: array\n              description: \"Array of dynamic table objects\"\n              mapping: \"$.\"\n        - name: create-dynamic-table\n          description: \"Create a dynamic table\"\n          call: \"snowflake-dynamic-table.create-dynamic-table\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          inputParameters:\n            - name: database\n              type: string\n              required: true\n              description: \"Database name\"\n              mapping: \"snowflake-dynamic-table.create-dynamic-table.database\"\n            - name: schema\n              type: string\n              required: true\n        \
  \      description: \"Schema name\"\n              mapping: \"snowflake-dynamic-table.create-dynamic-table.schema\"\n            - name: name\n              type: string\n              required: true\n              description: \"Dynamic table name\"\n              mapping: \"snowflake-dynamic-table.create-dynamic-table.name\"\n          outputParameters:\n            - name: result\n              type: object\n              description: \"Created dynamic table metadata\"\n              mapping: \"$.\"\n        - name: suspend-dynamic-table\n          description: \"Suspend a dynamic table\"\n          call: \"snowflake-dynamic-table.suspend-dynamic-table\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          inputParameters:\n            - name: database\n              type: string\n              required: true\n              description: \"Database name\"\n              mapping: \"snowflake-dynamic-table.suspend-dynamic-table.database\"\
  \n            - name: schema\n              type: string\n              required: true\n              description: \"Schema name\"\n              mapping: \"snowflake-dynamic-table.suspend-dynamic-table.schema\"\n            - name: name\n              type: string\n              required: true\n              description: \"Dynamic table name\"\n              mapping: \"snowflake-dynamic-table.suspend-dynamic-table.name\"\n          outputParameters:\n            - name: result\n              type: object\n              description: \"Suspend status\"\n              mapping: \"$.\"\n        - name: resume-dynamic-table\n          description: \"Resume a dynamic table\"\n          call: \"snowflake-dynamic-table.resume-dynamic-table\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          inputParameters:\n            - name: database\n              type: string\n              required: true\n              description: \"\
  Database name\"\n              mapping: \"snowflake-dynamic-table.resume-dynamic-table.database\"\n            - name: schema\n              type: string\n              required: true\n              description: \"Schema name\"\n              mapping: \"snowflake-dynamic-table.resume-dynamic-table.schema\"\n            - name: name\n              type: string\n              required: true\n              description: \"Dynamic table name\"\n              mapping: \"snowflake-dynamic-table.resume-dynamic-table.name\"\n          outputParameters:\n            - name: result\n              type: object\n              description: \"Resume status\"\n              mapping: \"$.\"\n        - name: list-iceberg-tables\n          description: \"List Iceberg tables\"\n          call: \"snowflake-iceberg-table.list-iceberg-tables\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          inputParameters:\n            - name: database\n\
  \              type: string\n              required: true\n              description: \"Database name\"\n              mapping: \"snowflake-iceberg-table.list-iceberg-tables.database\"\n            - name: schema\n              type: string\n              required: true\n              description: \"Schema name\"\n              mapping: \"snowflake-iceberg-table.list-iceberg-tables.schema\"\n          outputParameters:\n            - name: icebergTables\n              type: array\n              description: \"Array of Iceberg table objects\"\n              mapping: \"$.\"\n        - name: create-iceberg-table\n          description: \"Create an Iceberg table\"\n          call: \"snowflake-iceberg-table.create-iceberg-table\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          inputParameters:\n            - name: database\n              type: string\n              required: true\n              description: \"Database\
  \ name\"\n              mapping: \"snowflake-iceberg-table.create-iceberg-table.database\"\n            - name: schema\n              type: string\n              required: true\n         \n\n# --- truncated at 32 KB (43 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/capabilities/data-management.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/capabilities/data-management.yaml
tags:
- Snowflake
- Data Management
- Data Engineering
tools:
- description: List all accessible databases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-databases
- description: Create a new database
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-database
- description: Fetch database details by name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetch-database
- description: Delete a database
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-database
- description: Clone a database
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: clone-database
- description: Restore a dropped database
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: undrop-database
- description: List schemas in a database
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-schemas
- description: Create a new schema
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-schema
- description: Fetch schema details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetch-schema
- description: Delete a schema
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-schema
- description: List tables in a schema
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-tables
- description: Create a new table
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-table
- description: Fetch table details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetch-table
- description: Delete a table
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-table
- description: List views in a schema
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-views
- description: Create a new view
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-view
- description: List dynamic tables
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-dynamic-tables
- description: Create a dynamic table
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-dynamic-table
- description: Suspend a dynamic table
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: suspend-dynamic-table
- description: Resume a dynamic table
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: resume-dynamic-table
- description: List Iceberg tables
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-iceberg-tables
- description: Create an Iceberg table
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-iceberg-table
- description: List event tables
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-event-tables
- description: Create an event table
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-event-table
- description: List external volumes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-external-volumes
- description: Create an external volume
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-external-volume
- description: List all accessible databases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-databases
- description: Fetch database details by name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetch-database
- description: List schemas in a database
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-schemas
- description: List tables in a schema
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-tables
- description: List views in a schema
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-views
---
