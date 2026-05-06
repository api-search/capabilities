---
categories:
- data-engineering
consumed_apis: []
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
- delete a database
- create an external volume
- list views
- list views in a schema
- create a table
- suspend a dynamic table
- single database operations
- dynamic table management
- resume dynamic table
- snowflake
- create iceberg table
- create schema
- create dynamic table
- list schemas in a database
- create a dynamic table
- create a new database
- data engineering
- restore a dropped database
- iceberg table management
- list tables
- delete database
- sql
- create table
- fetch schema
- create view
- delete table
- database management
- data sharing
- fetch schema details
- list event tables
- list all accessible databases
- data lakes
- schema management
- view management
- create a view
- list dynamic tables
- database
- data management
- create an event table
- fetch database
- fetch table details
- table management
- delete a table
- suspend dynamic table
- create a database
- resume a dynamic table
- list all databases
- delete a schema
- list schemas
- create database
- list databases
- fetch database details by name
- clone a database
- list iceberg tables
- fetch table
- create a new view
- create event table
- delete schema
- create an iceberg table
- list external volumes
- data warehousing
- fetch a database
- create a new table
- create external volume
- create a new schema
- undrop database
- clone database
- list tables in a schema
- create a schema
slug: data-management
source_filename: data-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Snowflake Data Management\n  description: Unified workflow for managing databases, schemas, tables, views, dynamic tables, iceberg tables, and event\n    tables. Used by Data Engineers and Database Administrators to create, organize, and maintain data structures.\n  tags:\n  - Snowflake\n  - Data Management\n  - Data Engineering\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SNOWFLAKE_ACCOUNT_URL: SNOWFLAKE_ACCOUNT_URL\n    SNOWFLAKE_JWT_TOKEN: SNOWFLAKE_JWT_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: snowflake-database\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake Database API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: databases\n      path: /api/v2/databases\n      description: Database resources\n      operations:\n      - name: list-databases\n        method: GET\n        description:\
  \ List accessible databases\n        inputParameters:\n        - name: like\n          in: query\n          type: string\n          required: false\n          description: Filter by name pattern\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-database\n        method: POST\n        description: Create a new database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: fetch-database\n        method: GET\n        description: Fetch a database by name\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Database name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n      - name: delete-database\n        method: DELETE\n        description: Delete a database\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Database name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: clone-database\n        method: POST\n        description: Clone a database\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Source database name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: undrop-database\n        method: POST\n        description: Undrop a deleted database\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n \
  \         description: Database name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: enable-database-replication\n        method: POST\n        description: Enable replication for a database\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Database name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: disable-database-replication\n        method: POST\n        description: Disable replication for a database\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Database name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: enable-database-failover\n\
  \        method: POST\n        description: Enable failover for a database\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Database name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: snowflake-schema\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake Schema API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: schemas\n      path: /api/v2/databases/{database}/schemas\n      description: Schema resources\n      operations:\n      - name: list-schemas\n        method: GET\n        description: List schemas in a database\n        inputParameters:\n        - name: database\n          in: path\n          type: string\n          required: true\n          description: Database name\n        - name: like\n      \
  \    in: query\n          type: string\n          required: false\n          description: Filter by name pattern\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-schema\n        method: POST\n        description: Create a new schema\n        inputParameters:\n        - name: database\n          in: path\n          type: string\n          required: true\n          description: Database name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: fetch-schema\n        method: GET\n        description: Fetch a schema by name\n        inputParameters:\n        - name: database\n          in: path\n          type: string\n          required: true\n          description: Database name\n        - name: name\n          in:\
  \ path\n          type: string\n          required: true\n          description: Schema name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-schema\n        method: DELETE\n        description: Delete a schema\n        inputParameters:\n        - name: database\n          in: path\n          type: string\n          required: true\n          description: Database name\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Schema name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: clone-schema\n        method: POST\n        description: Clone a schema\n        inputParameters:\n        - name: database\n          in: path\n          type: string\n          required: true\n          description: Database name\n        - name: name\n   \
  \       in: path\n          type: string\n          required: true\n          description: Schema name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: undrop-schema\n        method: POST\n        description: Undrop a deleted schema\n        inputParameters:\n        - name: database\n          in: path\n          type: string\n          required: true\n          description: Database name\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Schema name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: snowflake-table\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake Table API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: tables\n      path:\
  \ /api/v2/databases/{database}/schemas/{schema}/tables\n      description: Table resources\n      operations:\n      - name: list-tables\n        method: GET\n        description: List tables in a schema\n        inputParameters:\n        - name: database\n          in: path\n          type: string\n          required: true\n          description: Database name\n        - name: schema\n          in: path\n          type: string\n          required: true\n          description: Schema name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-table\n        method: POST\n        description: Create a new table\n        inputParameters:\n        - name: database\n          in: path\n          type: string\n          required: true\n          description: Database name\n        - name: schema\n          in: path\n          type: string\n          required: true\n          description: Schema name\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: fetch-table\n        method: GET\n        description: Fetch a table by name\n        inputParameters:\n        - name: database\n          in: path\n          type: string\n          required: true\n          description: Database name\n        - name: schema\n          in: path\n          type: string\n          required: true\n          description: Schema name\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Table name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-table\n        method: DELETE\n        description: Delete a table\n        inputParameters:\n        - name: database\n    \
  \      in: path\n          type: string\n          required: true\n          description: Database name\n        - name: schema\n          in: path\n          type: string\n          required: true\n          description: Schema name\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Table name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: clone-table\n        method: POST\n        description: Clone a table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: undrop-table\n        method: POST\n        description: Undrop a deleted table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: snowflake-view\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n\
  \    description: Snowflake View API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: views\n      path: /api/v2/databases/{database}/schemas/{schema}/views\n      description: View resources\n      operations:\n      - name: list-views\n        method: GET\n        description: List views in a schema\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-view\n        method: POST\n        description: Create a new view\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: fetch-view\n        method: GET\n        description: Fetch a view by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-view\n        method: DELETE\n        description: Delete\
  \ a view\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: snowflake-dynamic-table\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake Dynamic Table API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: dynamic-tables\n      path: /api/v2/databases/{database}/schemas/{schema}/dynamic-tables\n      description: Dynamic table resources\n      operations:\n      - name: list-dynamic-tables\n        method: GET\n        description: List dynamic tables\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-dynamic-table\n        method: POST\n        description: Create a dynamic table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \     - name: fetch-dynamic-table\n        method: GET\n        description: Fetch a dynamic table by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-dynamic-table\n        method: DELETE\n        description: Delete a dynamic table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: suspend-dynamic-table\n        method: POST\n        description: Suspend a dynamic table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: resume-dynamic-table\n        method: POST\n        description: Resume a dynamic table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: refresh-dynamic-table\n        method: POST\n        description:\
  \ Refresh a dynamic table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: snowflake-iceberg-table\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake Iceberg Table API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: iceberg-tables\n      path: /api/v2/databases/{database}/schemas/{schema}/iceberg-tables\n      description: Iceberg table resources\n      operations:\n      - name: list-iceberg-tables\n        method: GET\n        description: List Iceberg tables\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-iceberg-table\n        method: POST\n        description: Create a managed Iceberg table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: fetch-iceberg-table\n        method: GET\n        description: Fetch an Iceberg table by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: drop-iceberg-table\n        method: DELETE\n        description: Drop an Iceberg table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: refresh-iceberg-table\n        method: POST\n        description: Refresh an Iceberg table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: snowflake-event-table\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake Event Table API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: event-tables\n      path: /api/v2/databases/{database}/schemas/{schema}/event-tables\n\
  \      description: Event table resources\n      operations:\n      - name: list-event-tables\n        method: GET\n        description: List event tables\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-event-table\n        method: POST\n        description: Create an event table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: fetch-event-table\n        method: GET\n        description: Fetch an event table by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-event-table\n        method: DELETE\n        description: Delete an event table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace:\
  \ snowflake-external-volume\n    baseUri: '{{SNOWFLAKE_ACCOUNT_URL}}'\n    description: Snowflake External Volume API\n    authentication:\n      type: bearer\n      token: '{{SNOWFLAKE_JWT_TOKEN}}'\n    resources:\n    - name: external-volumes\n      path: /api/v2/external-volumes\n      description: External volume resources\n      operations:\n      - name: list-external-volumes\n        method: GET\n        description: List external volumes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-external-volume\n        method: POST\n        description: Create an external volume\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: fetch-external-volume\n        method: GET\n        description: Fetch an external volume by name\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: delete-external-volume\n        method: DELETE\n        description: Delete an external volume\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: snowflake-data-mgmt-api\n    description: Unified REST API for Snowflake data structure management.\n    resources:\n    - path: /v1/databases\n      name: databases\n      description: Database management\n      operations:\n      - method: GET\n        name: list-databases\n        description: List all databases\n        call: snowflake-database.list-databases\n        inputParameters:\n        - name: like\n          in: query\n          type: string\n          required: false\n          description: Filter by name pattern\n          mapping: snowflake-database.list-databases.like\n        outputParameters:\n        - name: databases\n \
  \         type: array\n          description: Array of database objects\n          mapping: $.\n      - method: POST\n        name: create-database\n        description: Create a database\n        call: snowflake-database.create-database\n        inputParameters:\n        - name: name\n          in: body\n          type: string\n          required: true\n          description: Database name to create\n          mapping: snowflake-database.create-database.name\n        outputParameters:\n        - name: result\n          type: object\n          description: Created database metadata\n          mapping: $.\n    - path: /v1/databases/{name}\n      name: database\n      description: Single database operations\n      operations:\n      - method: GET\n        name: fetch-database\n        description: Fetch a database\n        call: snowflake-database.fetch-database\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n       \
  \   description: Database name\n          mapping: snowflake-database.fetch-database.name\n        outputParameters:\n        - name: result\n          type: object\n          description: Database metadata\n          mapping: $.\n      - method: DELETE\n        name: delete-database\n        description: Delete a database\n        call: snowflake-database.delete-database\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Database name\n          mapping: snowflake-database.delete-database.name\n        outputParameters:\n        - name: result\n          type: object\n          description: Delete status\n          mapping: $.\n    - path: /v1/schemas\n      name: schemas\n      description: Schema management\n      operations:\n      - method: GET\n        name: list-schemas\n        description: List schemas\n        call: snowflake-schema.list-schemas\n        inputParameters:\n        - name:\
  \ database\n          in: query\n          type: string\n          required: true\n          description: Database to list schemas from\n          mapping: snowflake-schema.list-schemas.database\n        - name: like\n          in: query\n          type: string\n          required: false\n          description: Filter by name pattern\n          mapping: snowflake-schema.list-schemas.like\n        outputParameters:\n        - name: schemas\n          type: array\n          description: Array of schema objects\n          mapping: $.\n      - method: POST\n        name: create-schema\n        description: Create a schema\n        call: snowflake-schema.create-schema\n        inputParameters:\n        - name: database\n          in: body\n          type: string\n          required: true\n          description: Database name\n          mapping: snowflake-schema.create-schema.database\n        - name: name\n          in: body\n          type: string\n          required: true\n          description:\
  \ Schema name\n          mapping: snowflake-schema.create-schema.name\n        outputParameters:\n        - name: result\n          type: object\n          description: Created schema metadata\n          mapping: $.\n    - path: /v1/tables\n      name: tables\n      description: Table management\n      operations:\n      - method: GET\n        name: list-tables\n        description: List tables\n        call: snowflake-table.list-tables\n        inputParameters:\n        - name: database\n          in: query\n          type: string\n          required: true\n          description: Database name\n          mapping: snowflake-table.list-tables.database\n        - name: schema\n          in: query\n          type: string\n          required: true\n          description: Schema name\n          mapping: snowflake-table.list-tables.schema\n        outputParameters:\n        - name: tables\n          type: array\n          description: Array of table objects\n          mapping: $.\n      - method:\
  \ POST\n        name: create-table\n        description: Create a table\n        call: snowflake-table.create-table\n        inputParameters:\n        - name: database\n          in: body\n          type: string\n          required: true\n          description: Database name\n          mapping: snowflake-table.create-table.database\n        - name: schema\n          in: body\n          type: string\n          required: true\n          description: Schema name\n          mapping: snowflake-table.create-table.schema\n        - name: name\n          in: body\n          type: string\n          required: true\n          description: Table name\n          mapping: snowflake-table.create-table.name\n        outputParameters:\n        - name: result\n          type: object\n          description: Created table metadata\n          mapping: $.\n    - path: /v1/views\n      name: views\n      description: View management\n      operations:\n      - method: GET\n        name: list-views\n        description:\
  \ List views\n        call: snowflake-view.list-views\n        inputParameters:\n        - name: database\n          in: query\n          type: string\n          required: true\n          description: Database name\n          mapping: snowflake-view.list-views.database\n        - name: schema\n          in: query\n          type: string\n          required: true\n          description: Schema name\n          mapping: snowflake-view.list-views.schema\n        outputParameters:\n        - name: views\n          type: array\n          description: Array of view objects\n          mapping: $.\n      - method: POST\n        name: create-view\n        description: Create a view\n        call: snowflake-view.create-view\n        inputParameters:\n        - name: database\n          in: body\n          type: string\n          required: true\n          description: Database name\n          mapping: snowflake-view.create-view.database\n        - name: schema\n          in: body\n          type:\
  \ string\n          required: true\n          description: Schema name\n          mapping: snowflake-view.create-view.schema\n        - name: name\n          in: body\n          type: string\n          required: true\n          description: View name\n          mapping: snowflake-view.create-view.name\n        outputParameters:\n        - name: result\n          type: object\n          description: Created view metadata\n          mapping: $.\n    - path: /v1/dynamic-tables\n      name: dynamic-tables\n      description: Dynamic table management\n      operations:\n      - method: GET\n        name: list-dynamic-tables\n        description: List dynamic tables\n        call: snowflake-dynamic-table.list-dynamic-tables\n        inputParameters:\n        - name: database\n          in: query\n          type: string\n          required: true\n          description: Database name\n          mapping: snowflake-dynamic-table.list-dynamic-tables.database\n        - name: schema\n          in:\
  \ query\n          type: string\n          required: true\n          description: Schema name\n          mapping: snowflake-dynamic-table.list-dynamic-tables.schema\n        outputParameters:\n        - name: dynamicTables\n          type: array\n          description: Array of dynamic table objects\n          mapping: $.\n      - method: POST\n        name: create-dynamic-table\n        description: Create a dynamic table\n        call: snowflake-dynamic-table.create-dynamic-table\n        inputParameters:\n        - name: database\n          in: body\n          type: string\n          required: true\n          description: Database name\n          mapping: snowflake-dynamic-table.create-dynamic-table.database\n        - name: schema\n          in: body\n          type: string\n          required: true\n          description: Schema name\n          mapping: snowflake-dynamic-table.create-dynamic-table.schema\n        - name: name\n          in: body\n          type: string\n         \
  \ required: true\n          description: Dynamic table name\n          mapping: snowflake-dynamic-table.create-dynamic-table.name\n        outputParameters:\n        - name: result\n          type: object\n          description: Created dynamic table metadata\n          mapping: $.\n    - path: /v1/iceberg-tables\n      name: iceberg-tables\n      description: Iceberg table management\n      operations:\n      - method: GET\n        name: list-iceberg-tables\n        description: List Iceberg tables\n        call: snowflake-iceberg-table.list-iceberg-tables\n        inputParameters:\n        - name: database\n          in: query\n          type: string\n          required: true\n          description: Database name\n          mapping: snowflake-iceberg-table.list-iceberg-tables.database\n        - name: schema\n          in: query\n          type: string\n          required: true\n          description: Schema name\n          mapping: snowflake-iceberg-table.list-iceberg-tables.schema\n\
  \        outputParameters:\n        - name: icebergTables\n          type: array\n          description: Array of Iceberg table objects\n          mapping: $.\n      - method: POST\n        name: create-iceberg-table\n        description: Create an Iceberg table\n        call: snowflake-iceberg-table.create-iceberg-table\n        inputParameters:\n        - name: database\n          in: body\n          type: string\n          required: true\n          description: Database name\n          mapping: snowflake-iceberg-table.create-iceberg-table.database\n        - name: schema\n          in: body\n          type: string\n          required: true\n          description: Schema name\n          mapping: snowflake-iceberg-table.create-iceberg-table.schema\n        - name: name\n          in: body\n          type: string\n          required: true\n          description: Iceberg table name\n          mapping: snowflake-iceberg-table.create-iceberg-table.name\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          description: Created Iceberg table metadata\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: snowflake-data-mgmt-mcp\n    transport: http\n    description: MCP server (HTTP transport) for AI-assisted Snowflake data structure management.\n    tools:\n    - name: list-databases\n      description: List all accessible databases\n      call: snowflake-database.list-databases\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      inputParameters:\n      - name: like\n        type: string\n        required: false\n        description: Filter by name pattern\n        mapping: snowflake-database.list-databases.like\n      outputParameters:\n      - name: databases\n        type: array\n        description: Array of database objects\n        mapping: $.\n    - name: create-database\n      description: Create a new database\n      call: snowflake-database.create-database\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      inputParameters:\n      - name: name\n        type: string\n        required: true\n        description: Database name to create\n        mapping: snowflake-database.create-database.name\n      outputParameters:\n      - name: result\n        type: object\n        description: Created database metadata\n        mapping: $.\n    - name: fetch-database\n      description: Fetch database details by name\n      call: snowflake-database.fetch-database\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      inputParameters:\n      - name: name\n        type: string\n        required: true\n        description: Database name\n        mapping: snowflake-database.fetch-database.name\n      outputParameters:\n      - name: result\n        type: object\n        description: Database metadata\n        mapping: $.\n    - name: delete-database\n      description: Delete a\
  \ database\n      call: snowflake-database.delete-database\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      inputParameters:\n      - name: name\n        type: string\n        required: true\n        description: Database name\n        mapping: snowflake-database.delete-database.name\n      outputParameters:\n      - name: result\n        type: object\n        description: Delete status\n        mapping: $.\n    - name: clone-database\n      description: Clone a database\n      call: snowflake-database.clone-database\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      inputParameters:\n      - name: name\n        type: string\n        required: true\n        description: Source database name\n        mapping: snowflake-database.clone-database.name\n      outputParameters:\n      - name: result\n        type: object\n        description: Cloned database metadata\n        mapping: $.\n    -\
  \ name: undrop-database\n      description: Restore a dropped database\n      call: snowflake-database.undrop-database\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      inputParameters:\n      - name: name\n        type: string\n        required: true\n        description: Database name\n        mapping: snowflake-database.undrop-database.name\n      outputParameters:\n      - name: result\n        type: object\n        description: Restore status\n        mapping: $.\n    - name: list-schemas\n      description: List schemas in a database\n      call: snowflake-schema.list-schemas\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      inputParameters:\n      - name: database\n        type: string\n        required: true\n        description: Database name\n        mapping: snowflake-schema.list-schemas.database\n      - name: like\n        type: string\n        required: false\n        description:\
  \ Filter by name pattern\n        mapping: snowflake-schema.list-schemas.like\n      outputParameters:\n      - name: schemas\n        type: array\n        description: Array of schema objects\n        mapping: $.\n    - name: create-schema\n      description: Create a new schema\n      call: snowflake-schema.create-schema\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      inputParameters:\n      - name: database\n        type: string\n        required: true\n        description: Database name\n        mapping: snowflake-schema.create-schema.database\n      - name: name\n        type: string\n        required: true\n        description: Schema name\n        mapping: snowflake-schema.create-schema.name\n      outputParameters:\n      - name: result\n        type: object\n   \n\n# --- truncated at 32 KB (51 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/snowflake/refs/heads/main/capabilities/data-management.yaml\n"
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
