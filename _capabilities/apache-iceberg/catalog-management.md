---
categories: []
consumed_apis: []
description: Workflow capability for data engineers and lakehouse architects to manage namespaces, tables, and views in Apache Iceberg catalogs via the REST Catalog API.
layout: capability
name: Apache Iceberg Catalog Management
operations:
- description: Get Iceberg catalog configuration settings
  method: GET
  name: get-config
  path: /v1/config
- description: List all namespaces in the catalog
  method: GET
  name: list-namespaces
  path: /v1/namespaces
- description: Create a new namespace
  method: POST
  name: create-namespace
  path: /v1/namespaces
- description: Load namespace metadata
  method: GET
  name: load-namespace-metadata
  path: /v1/namespaces/{namespace}
- description: Drop a namespace
  method: DELETE
  name: drop-namespace
  path: /v1/namespaces/{namespace}
- description: List all tables in a namespace
  method: GET
  name: list-tables
  path: /v1/namespaces/{namespace}/tables
- description: Create a new Iceberg table
  method: POST
  name: create-table
  path: /v1/namespaces/{namespace}/tables
- description: Load a table from the catalog
  method: GET
  name: load-table
  path: /v1/namespaces/{namespace}/tables/{table}
- description: Drop a table from the catalog
  method: DELETE
  name: drop-table
  path: /v1/namespaces/{namespace}/tables/{table}
- description: List all views in a namespace
  method: GET
  name: list-views
  path: /v1/namespaces/{namespace}/views
personas: []
provider_name: Apache Iceberg
provider_slug: apache-iceberg
search_terms:
- drop a namespace
- list all view identifiers in a namespace
- list views
- data engineers and lakehouse architects managing namespaces, tables, and views
- drop namespace
- commit updates and schema changes to an iceberg table
- create a new iceberg table in a namespace
- analytics
- server-side scan planning for compute engine integration
- individual table operations
- get iceberg catalog configuration settings
- catalog configuration
- object storage credential management
- namespace management
- engineers who build and maintain data pipelines and manage iceberg tables and namespaces
- get config
- Lakehouse Architect
- create a new namespace in the iceberg catalog
- Data Engineer
- lakehouse
- data engineering
- list all namespaces in the catalog
- create a new iceberg table
- list tables
- table management within a namespace
- load an iceberg table and its metadata from the catalog
- commit table
- drop an iceberg table from the catalog
- create table
- create view
- open source
- data lake
- list all views in a namespace
- list namespaces
- get catalog config
- list all tables in a namespace
- load a table from the catalog
- list all namespaces in the iceberg catalog, optionally filtered by parent namespace
- retrieve iceberg catalog configuration settings
- create a new view in the iceberg catalog
- create namespace
- acid
- create a new namespace
- load namespace metadata
- list all iceberg table identifiers in a namespace
- table format
- load metadata and properties for a specific iceberg namespace
- individual namespace
- catalog management
- table and namespace discovery and management
- architects who design lakehouse schemas, partition strategies, and catalog topology
- metrics collection and reporting
- drop a table from the catalog
- load table
- apache
- drop table
- apache iceberg
- view management within a namespace
- drop an empty namespace from the iceberg catalog
slug: catalog-management
source_filename: catalog-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apache Iceberg Catalog Management\n  description: Workflow capability for data engineers and lakehouse architects to manage namespaces, tables, and views in\n    Apache Iceberg catalogs via the REST Catalog API.\n  tags:\n  - Apache Iceberg\n  - Catalog Management\n  - Data Engineering\n  - Lakehouse\n  - Table Format\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    ICEBERG_CATALOG_TOKEN: ICEBERG_CATALOG_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: iceberg-rest-catalog\n    baseUri: https://localhost:8181\n    description: Apache Iceberg REST Catalog API for managing namespaces, tables, and views.\n    authentication:\n      type: bearer\n      token: '{{ICEBERG_CATALOG_TOKEN}}'\n    resources:\n    - name: config\n      path: /v1/config\n      description: Catalog configuration management\n      operations:\n      - name: get-config\n        method: GET\n        description:\
  \ List all catalog configuration settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: namespaces\n      path: /v1/namespaces\n      description: Namespace management\n      operations:\n      - name: list-namespaces\n        method: GET\n        description: List namespaces, optionally providing a parent namespace to list underneath\n        inputParameters:\n        - name: parent\n          in: query\n          type: string\n          required: false\n          description: Parent namespace to list underneath\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-namespace\n        method: POST\n        description: Create a namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n\
  \          data:\n            namespace: '{{tools.namespace}}'\n            properties: {}\n    - name: namespace\n      path: /v1/namespaces/{namespace}\n      description: Individual namespace operations\n      operations:\n      - name: load-namespace-metadata\n        method: GET\n        description: Load the metadata properties for a namespace\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Namespace identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: drop-namespace\n        method: DELETE\n        description: Drop a namespace from the catalog\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Namespace identifier\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: tables\n      path: /v1/namespaces/{namespace}/tables\n      description: Table management\n      operations:\n      - name: list-tables\n        method: GET\n        description: List all table identifiers underneath a given namespace\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Namespace identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-table\n        method: POST\n        description: Create a table in the given namespace\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Namespace identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n        body:\n          type: json\n          data:\n            name: '{{tools.table_name}}'\n            schema: {}\n    - name: table\n      path: /v1/namespaces/{namespace}/tables/{table}\n      description: Individual table operations\n      operations:\n      - name: load-table\n        method: GET\n        description: Load a table from the catalog\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Namespace identifier\n        - name: table\n          in: path\n          type: string\n          required: true\n          description: Table identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: commit-table\n        method: POST\n        description: Commit updates to a table\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n         \
  \ required: true\n          description: Namespace identifier\n        - name: table\n          in: path\n          type: string\n          required: true\n          description: Table identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: drop-table\n        method: DELETE\n        description: Drop a table from the catalog\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Namespace identifier\n        - name: table\n          in: path\n          type: string\n          required: true\n          description: Table identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: views\n      path: /v1/namespaces/{namespace}/views\n      description: View management\n      operations:\n      - name: list-views\n\
  \        method: GET\n        description: List all view identifiers underneath a given namespace\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Namespace identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-view\n        method: POST\n        description: Create a view in the given namespace\n        inputParameters:\n        - name: namespace\n          in: path\n          type: string\n          required: true\n          description: Namespace identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: iceberg-catalog-management-api\n    description: Unified REST API for Apache Iceberg catalog management workflows.\n    resources:\n    - path:\
  \ /v1/config\n      name: catalog-config\n      description: Catalog configuration\n      operations:\n      - method: GET\n        name: get-config\n        description: Get Iceberg catalog configuration settings\n        call: iceberg-rest-catalog.get-config\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/namespaces\n      name: namespaces\n      description: Namespace management\n      operations:\n      - method: GET\n        name: list-namespaces\n        description: List all namespaces in the catalog\n        call: iceberg-rest-catalog.list-namespaces\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-namespace\n        description: Create a new namespace\n        call: iceberg-rest-catalog.create-namespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/namespaces/{namespace}\n      name: namespace\n      description: Individual\
  \ namespace\n      operations:\n      - method: GET\n        name: load-namespace-metadata\n        description: Load namespace metadata\n        call: iceberg-rest-catalog.load-namespace-metadata\n        with:\n          namespace: rest.namespace\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: drop-namespace\n        description: Drop a namespace\n        call: iceberg-rest-catalog.drop-namespace\n        with:\n          namespace: rest.namespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/namespaces/{namespace}/tables\n      name: tables\n      description: Table management within a namespace\n      operations:\n      - method: GET\n        name: list-tables\n        description: List all tables in a namespace\n        call: iceberg-rest-catalog.list-tables\n        with:\n          namespace: rest.namespace\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n      - method: POST\n        name: create-table\n        description: Create a new Iceberg table\n        call: iceberg-rest-catalog.create-table\n        with:\n          namespace: rest.namespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/namespaces/{namespace}/tables/{table}\n      name: table\n      description: Individual table operations\n      operations:\n      - method: GET\n        name: load-table\n        description: Load a table from the catalog\n        call: iceberg-rest-catalog.load-table\n        with:\n          namespace: rest.namespace\n          table: rest.table\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: drop-table\n        description: Drop a table from the catalog\n        call: iceberg-rest-catalog.drop-table\n        with:\n          namespace: rest.namespace\n          table: rest.table\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/namespaces/{namespace}/views\n      name: views\n      description: View management within a namespace\n      operations:\n      - method: GET\n        name: list-views\n        description: List all views in a namespace\n        call: iceberg-rest-catalog.list-views\n        with:\n          namespace: rest.namespace\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: iceberg-catalog-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Apache Iceberg catalog management.\n    tools:\n    - name: get-catalog-config\n      description: Retrieve Iceberg catalog configuration settings\n      hints:\n        readOnly: true\n        openWorld: true\n      call: iceberg-rest-catalog.get-config\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-namespaces\n      description: List all namespaces in the Iceberg catalog, optionally\
  \ filtered by parent namespace\n      hints:\n        readOnly: true\n        openWorld: true\n      call: iceberg-rest-catalog.list-namespaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-namespace\n      description: Create a new namespace in the Iceberg catalog\n      hints:\n        readOnly: false\n      call: iceberg-rest-catalog.create-namespace\n      with:\n        namespace: tools.namespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: load-namespace-metadata\n      description: Load metadata and properties for a specific Iceberg namespace\n      hints:\n        readOnly: true\n        openWorld: true\n      call: iceberg-rest-catalog.load-namespace-metadata\n      with:\n        namespace: tools.namespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: drop-namespace\n      description: Drop an empty namespace from the Iceberg catalog\n      hints:\n        readOnly:\
  \ false\n        destructive: true\n      call: iceberg-rest-catalog.drop-namespace\n      with:\n        namespace: tools.namespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tables\n      description: List all Iceberg table identifiers in a namespace\n      hints:\n        readOnly: true\n        openWorld: true\n      call: iceberg-rest-catalog.list-tables\n      with:\n        namespace: tools.namespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-table\n      description: Create a new Iceberg table in a namespace\n      hints:\n        readOnly: false\n      call: iceberg-rest-catalog.create-table\n      with:\n        namespace: tools.namespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: load-table\n      description: Load an Iceberg table and its metadata from the catalog\n      hints:\n        readOnly: true\n        openWorld: true\n      call: iceberg-rest-catalog.load-table\n\
  \      with:\n        namespace: tools.namespace\n        table: tools.table\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: commit-table\n      description: Commit updates and schema changes to an Iceberg table\n      hints:\n        readOnly: false\n        idempotent: true\n      call: iceberg-rest-catalog.commit-table\n      with:\n        namespace: tools.namespace\n        table: tools.table\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: drop-table\n      description: Drop an Iceberg table from the catalog\n      hints:\n        readOnly: false\n        destructive: true\n      call: iceberg-rest-catalog.drop-table\n      with:\n        namespace: tools.namespace\n        table: tools.table\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-views\n      description: List all view identifiers in a namespace\n      hints:\n        readOnly: true\n        openWorld: true\n      call:\
  \ iceberg-rest-catalog.list-views\n      with:\n        namespace: tools.namespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-view\n      description: Create a new view in the Iceberg catalog\n      hints:\n        readOnly: false\n      call: iceberg-rest-catalog.create-view\n      with:\n        namespace: tools.namespace\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-iceberg/refs/heads/main/capabilities/catalog-management.yaml
tags:
- Apache Iceberg
- Catalog Management
- Data Engineering
- Lakehouse
- Table Format
tools:
- description: Retrieve Iceberg catalog configuration settings
  hints:
    openWorld: true
    readOnly: true
  name: get-catalog-config
- description: List all namespaces in the Iceberg catalog, optionally filtered by parent namespace
  hints:
    openWorld: true
    readOnly: true
  name: list-namespaces
- description: Create a new namespace in the Iceberg catalog
  hints:
    readOnly: false
  name: create-namespace
- description: Load metadata and properties for a specific Iceberg namespace
  hints:
    openWorld: true
    readOnly: true
  name: load-namespace-metadata
- description: Drop an empty namespace from the Iceberg catalog
  hints:
    destructive: true
    readOnly: false
  name: drop-namespace
- description: List all Iceberg table identifiers in a namespace
  hints:
    openWorld: true
    readOnly: true
  name: list-tables
- description: Create a new Iceberg table in a namespace
  hints:
    readOnly: false
  name: create-table
- description: Load an Iceberg table and its metadata from the catalog
  hints:
    openWorld: true
    readOnly: true
  name: load-table
- description: Commit updates and schema changes to an Iceberg table
  hints:
    idempotent: true
    readOnly: false
  name: commit-table
- description: Drop an Iceberg table from the catalog
  hints:
    destructive: true
    readOnly: false
  name: drop-table
- description: List all view identifiers in a namespace
  hints:
    openWorld: true
    readOnly: true
  name: list-views
- description: Create a new view in the Iceberg catalog
  hints:
    readOnly: false
  name: create-view
---
