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
- view management
- list schemas
- data management
- create a database
- fetch database
- create a dynamic table
- data lakes
- delete table
- create dynamic table
- resume a dynamic table
- snowflake
- resume dynamic table
- schema management
- list dynamic tables
- delete a database
- fetch schema
- create a new table
- create iceberg table
- create an external volume
- fetch a database
- delete database
- sql
- undrop database
- create view
- delete a schema
- create a schema
- create a new schema
- fetch table details
- fetch schema details
- list views in a schema
- suspend dynamic table
- list tables
- create schema
- list databases
- clone database
- create table
- create an event table
- delete a table
- create a table
- fetch table
- create a view
- list schemas in a database
- iceberg table management
- list event tables
- list all accessible databases
- suspend a dynamic table
- restore a dropped database
- data sharing
- create external volume
- list views
- database management
- list tables in a schema
- create a new database
- fetch database details by name
- delete schema
- create a new view
- clone a database
- create event table
- list iceberg tables
- single database operations
- list external volumes
- list all databases
- data warehousing
- table management
- dynamic table management
- create database
- database
- data engineering
- create an iceberg table
slug: data-management
source_filename: data-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Snowflake Data Management\"\n  description: \"Unified workflow for managing databases, schemas, tables, views, dynamic tables, iceberg tables, and event tables. Used by Data Engineers and Database Administrators to create, organize, and maintain data structures.\"\n  tags:\n    - Snowflake\n    - Data Management\n    - Data Engineering\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SNOWFLAKE_ACCOUNT_URL: SNOWFLAKE_ACCOUNT_URL\n      SNOWFLAKE_JWT_TOKEN: SNOWFLAKE_JWT_TOKEN\n\ncapability:\n  consumes:\n    - import: snowflake-database\n      location: ./shared/database.yaml\n    - import: snowflake-schema\n      location: ./shared/schema.yaml\n    - import: snowflake-table\n      location: ./shared/table.yaml\n    - import: snowflake-view\n      location: ./shared/view.yaml\n    - import: snowflake-dynamic-table\n      location: ./shared/dynamic-table.yaml\n    - import: snowflake-iceberg-table\n\
  \      location: ./shared/iceberg-table.yaml\n    - import: snowflake-event-table\n      location: ./shared/event-table.yaml\n    - import: snowflake-external-volume\n      location: ./shared/external-volume.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: snowflake-data-mgmt-api\n      description: \"Unified REST API for Snowflake data structure management.\"\n      resources:\n        - path: /v1/databases\n          name: databases\n          description: \"Database management\"\n          operations:\n            - method: GET\n              name: list-databases\n              description: \"List all databases\"\n              call: \"snowflake-database.list-databases\"\n            - method: POST\n              name: create-database\n              description: \"Create a database\"\n              call: \"snowflake-database.create-database\"\n        - path: /v1/databases/{name}\n          name: database\n          description: \"Single database operations\"\
  \n          operations:\n            - method: GET\n              name: fetch-database\n              description: \"Fetch a database\"\n              call: \"snowflake-database.fetch-database\"\n            - method: DELETE\n              name: delete-database\n              description: \"Delete a database\"\n              call: \"snowflake-database.delete-database\"\n        - path: /v1/schemas\n          name: schemas\n          description: \"Schema management\"\n          operations:\n            - method: GET\n              name: list-schemas\n              description: \"List schemas\"\n              call: \"snowflake-schema.list-schemas\"\n            - method: POST\n              name: create-schema\n              description: \"Create a schema\"\n              call: \"snowflake-schema.create-schema\"\n        - path: /v1/tables\n          name: tables\n          description: \"Table management\"\n          operations:\n            - method: GET\n              name: list-tables\n\
  \              description: \"List tables\"\n              call: \"snowflake-table.list-tables\"\n            - method: POST\n              name: create-table\n              description: \"Create a table\"\n              call: \"snowflake-table.create-table\"\n        - path: /v1/views\n          name: views\n          description: \"View management\"\n          operations:\n            - method: GET\n              name: list-views\n              description: \"List views\"\n              call: \"snowflake-view.list-views\"\n            - method: POST\n              name: create-view\n              description: \"Create a view\"\n              call: \"snowflake-view.create-view\"\n        - path: /v1/dynamic-tables\n          name: dynamic-tables\n          description: \"Dynamic table management\"\n          operations:\n            - method: GET\n              name: list-dynamic-tables\n              description: \"List dynamic tables\"\n              call: \"snowflake-dynamic-table.list-dynamic-tables\"\
  \n            - method: POST\n              name: create-dynamic-table\n              description: \"Create a dynamic table\"\n              call: \"snowflake-dynamic-table.create-dynamic-table\"\n        - path: /v1/iceberg-tables\n          name: iceberg-tables\n          description: \"Iceberg table management\"\n          operations:\n            - method: GET\n              name: list-iceberg-tables\n              description: \"List Iceberg tables\"\n              call: \"snowflake-iceberg-table.list-iceberg-tables\"\n            - method: POST\n              name: create-iceberg-table\n              description: \"Create an Iceberg table\"\n              call: \"snowflake-iceberg-table.create-iceberg-table\"\n\n    - type: mcp\n      port: 9080\n      namespace: snowflake-data-mgmt-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Snowflake data structure management.\"\n      tools:\n        - name: list-databases\n          description: \"List all accessible\
  \ databases\"\n          hints:\n            readOnly: true\n          call: \"snowflake-database.list-databases\"\n        - name: create-database\n          description: \"Create a new database\"\n          hints:\n            readOnly: false\n          call: \"snowflake-database.create-database\"\n        - name: fetch-database\n          description: \"Fetch database details by name\"\n          hints:\n            readOnly: true\n          call: \"snowflake-database.fetch-database\"\n        - name: delete-database\n          description: \"Delete a database\"\n          hints:\n            destructive: true\n          call: \"snowflake-database.delete-database\"\n        - name: clone-database\n          description: \"Clone a database\"\n          hints:\n            readOnly: false\n          call: \"snowflake-database.clone-database\"\n        - name: undrop-database\n          description: \"Restore a dropped database\"\n          hints:\n            readOnly: false\n       \
  \   call: \"snowflake-database.undrop-database\"\n        - name: list-schemas\n          description: \"List schemas in a database\"\n          hints:\n            readOnly: true\n          call: \"snowflake-schema.list-schemas\"\n        - name: create-schema\n          description: \"Create a new schema\"\n          hints:\n            readOnly: false\n          call: \"snowflake-schema.create-schema\"\n        - name: fetch-schema\n          description: \"Fetch schema details\"\n          hints:\n            readOnly: true\n          call: \"snowflake-schema.fetch-schema\"\n        - name: delete-schema\n          description: \"Delete a schema\"\n          hints:\n            destructive: true\n          call: \"snowflake-schema.delete-schema\"\n        - name: list-tables\n          description: \"List tables in a schema\"\n          hints:\n            readOnly: true\n          call: \"snowflake-table.list-tables\"\n        - name: create-table\n          description: \"Create\
  \ a new table\"\n          hints:\n            readOnly: false\n          call: \"snowflake-table.create-table\"\n        - name: fetch-table\n          description: \"Fetch table details\"\n          hints:\n            readOnly: true\n          call: \"snowflake-table.fetch-table\"\n        - name: delete-table\n          description: \"Delete a table\"\n          hints:\n            destructive: true\n          call: \"snowflake-table.delete-table\"\n        - name: list-views\n          description: \"List views in a schema\"\n          hints:\n            readOnly: true\n          call: \"snowflake-view.list-views\"\n        - name: create-view\n          description: \"Create a new view\"\n          hints:\n            readOnly: false\n          call: \"snowflake-view.create-view\"\n        - name: list-dynamic-tables\n          description: \"List dynamic tables\"\n          hints:\n            readOnly: true\n          call: \"snowflake-dynamic-table.list-dynamic-tables\"\n   \
  \     - name: create-dynamic-table\n          description: \"Create a dynamic table\"\n          hints:\n            readOnly: false\n          call: \"snowflake-dynamic-table.create-dynamic-table\"\n        - name: suspend-dynamic-table\n          description: \"Suspend a dynamic table\"\n          hints:\n            readOnly: false\n          call: \"snowflake-dynamic-table.suspend-dynamic-table\"\n        - name: resume-dynamic-table\n          description: \"Resume a dynamic table\"\n          hints:\n            readOnly: false\n          call: \"snowflake-dynamic-table.resume-dynamic-table\"\n        - name: list-iceberg-tables\n          description: \"List Iceberg tables\"\n          hints:\n            readOnly: true\n          call: \"snowflake-iceberg-table.list-iceberg-tables\"\n        - name: create-iceberg-table\n          description: \"Create an Iceberg table\"\n          hints:\n            readOnly: false\n          call: \"snowflake-iceberg-table.create-iceberg-table\"\
  \n        - name: list-event-tables\n          description: \"List event tables\"\n          hints:\n            readOnly: true\n          call: \"snowflake-event-table.list-event-tables\"\n        - name: create-event-table\n          description: \"Create an event table\"\n          hints:\n            readOnly: false\n          call: \"snowflake-event-table.create-event-table\"\n        - name: list-external-volumes\n          description: \"List external volumes\"\n          hints:\n            readOnly: true\n          call: \"snowflake-external-volume.list-external-volumes\"\n        - name: create-external-volume\n          description: \"Create an external volume\"\n          hints:\n            readOnly: false\n          call: \"snowflake-external-volume.create-external-volume\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/capabilities/data-management.yaml
tags:
- Snowflake
- Data Management
- Data Engineering
tools:
- description: List all accessible databases
  hints:
    readOnly: true
  name: list-databases
- description: Create a new database
  hints:
    readOnly: false
  name: create-database
- description: Fetch database details by name
  hints:
    readOnly: true
  name: fetch-database
- description: Delete a database
  hints:
    destructive: true
  name: delete-database
- description: Clone a database
  hints:
    readOnly: false
  name: clone-database
- description: Restore a dropped database
  hints:
    readOnly: false
  name: undrop-database
- description: List schemas in a database
  hints:
    readOnly: true
  name: list-schemas
- description: Create a new schema
  hints:
    readOnly: false
  name: create-schema
- description: Fetch schema details
  hints:
    readOnly: true
  name: fetch-schema
- description: Delete a schema
  hints:
    destructive: true
  name: delete-schema
- description: List tables in a schema
  hints:
    readOnly: true
  name: list-tables
- description: Create a new table
  hints:
    readOnly: false
  name: create-table
- description: Fetch table details
  hints:
    readOnly: true
  name: fetch-table
- description: Delete a table
  hints:
    destructive: true
  name: delete-table
- description: List views in a schema
  hints:
    readOnly: true
  name: list-views
- description: Create a new view
  hints:
    readOnly: false
  name: create-view
- description: List dynamic tables
  hints:
    readOnly: true
  name: list-dynamic-tables
- description: Create a dynamic table
  hints:
    readOnly: false
  name: create-dynamic-table
- description: Suspend a dynamic table
  hints:
    readOnly: false
  name: suspend-dynamic-table
- description: Resume a dynamic table
  hints:
    readOnly: false
  name: resume-dynamic-table
- description: List Iceberg tables
  hints:
    readOnly: true
  name: list-iceberg-tables
- description: Create an Iceberg table
  hints:
    readOnly: false
  name: create-iceberg-table
- description: List event tables
  hints:
    readOnly: true
  name: list-event-tables
- description: Create an event table
  hints:
    readOnly: false
  name: create-event-table
- description: List external volumes
  hints:
    readOnly: true
  name: list-external-volumes
- description: Create an external volume
  hints:
    readOnly: false
  name: create-external-volume
---
