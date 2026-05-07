---
categories: []
consumed_apis: []
description: The Apache Iceberg REST Catalog API is an open standard (OpenAPI spec) for interacting with Apache Iceberg table catalogs. It provides a common HTTP interface for catalog operations including namespace management, table lifecycle, view management, and metadata operations. Multiple catalog implementations support this specification including Apache Polaris, Project Nessie, AWS Glue, and Google BigLake.
layout: capability
name: Apache Iceberg REST Catalog API
operations:
- description: Get Catalog Configuration
  method: GET
  name: getconfig
  path: /v1/config
- description: Get OAuth2 Token
  method: POST
  name: gettoken
  path: /v1/oauth/tokens
- description: List Namespaces
  method: GET
  name: listnamespaces
  path: /v1/namespaces
- description: Create Namespace
  method: POST
  name: createnamespace
  path: /v1/namespaces
- description: Get Namespace Metadata
  method: GET
  name: loadnamespacemetadata
  path: /v1/namespaces/{namespace}
- description: Drop Namespace
  method: DELETE
  name: dropnamespace
  path: /v1/namespaces/{namespace}
- description: Update Namespace Properties
  method: POST
  name: updatenamespaceproperties
  path: /v1/namespaces/{namespace}/properties
- description: List Tables
  method: GET
  name: listtables
  path: /v1/namespaces/{namespace}/tables
- description: Create Table
  method: POST
  name: createtable
  path: /v1/namespaces/{namespace}/tables
- description: Load Table
  method: GET
  name: loadtable
  path: /v1/namespaces/{namespace}/tables/{table}
- description: Commit Table Update
  method: POST
  name: committable
  path: /v1/namespaces/{namespace}/tables/{table}
- description: Drop Table
  method: DELETE
  name: droptable
  path: /v1/namespaces/{namespace}/tables/{table}
- description: Report Table Metrics
  method: POST
  name: reportmetrics
  path: /v1/namespaces/{namespace}/tables/{table}/metrics
- description: List Views
  method: GET
  name: listviews
  path: /v1/namespaces/{namespace}/views
- description: Create View
  method: POST
  name: createview
  path: /v1/namespaces/{namespace}/views
- description: Load View
  method: GET
  name: loadview
  path: /v1/namespaces/{namespace}/views/{view}
- description: Drop View
  method: DELETE
  name: dropview
  path: /v1/namespaces/{namespace}/views/{view}
- description: Commit Multi-Table Transaction
  method: POST
  name: committransaction
  path: /v1/transactions/commit
personas: []
provider_name: Table Format
provider_slug: table-format
search_terms:
- commit multi-table transaction
- committable
- update namespace properties
- updatenamespaceproperties
- format
- drop table
- get catalog configuration
- drop view
- committransaction
- create view
- api
- drop namespace
- getconfig
- create table
- create namespace
- createtable
- delta lake
- commit table update
- acid transactions
- load view
- list tables
- apache iceberg
- dropview
- listtables
- droptable
- gettoken
- get namespace metadata
- reportmetrics
- data lakehouse
- table
- loadview
- loadnamespacemetadata
- load table
- open table format
- createnamespace
- list namespaces
- data lake
- apache hudi
- schema evolution
- listviews
- listnamespaces
- report table metrics
- list views
- time travel
- get oauth2 token
- dropnamespace
- loadtable
- createview
slug: table-format-capability
source_filename: table-format-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apache Iceberg REST Catalog API\n  description: The Apache Iceberg REST Catalog API is an open standard (OpenAPI spec) for interacting with Apache Iceberg\n    table catalogs. It provides a common HTTP interface for catalog operations including namespace management, table lifecycle,\n    view management, and metadata operations. Multiple catalog implementations support this specification including Apache\n    Polaris, Project Nessie, AWS Glue, and Google BigLake.\n  tags:\n  - Table\n  - Format\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: table-format\n    baseUri: https://localhost:8181\n    description: Apache Iceberg REST Catalog API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{TABLE_FORMAT_TOKEN}}'\n    resources:\n    - name: v1-config\n      path: /v1/config\n      operations:\n      - name: getconfig\n        method: GET\n        description:\
  \ Get Catalog Configuration\n        inputParameters:\n        - name: warehouse\n          in: query\n          type: string\n          description: Warehouse identifier for multi-tenant catalogs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-oauth-tokens\n      path: /v1/oauth/tokens\n      operations:\n      - name: gettoken\n        method: POST\n        description: Get OAuth2 Token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-namespaces\n      path: /v1/namespaces\n      operations:\n      - name: listnamespaces\n        method: GET\n        description: List Namespaces\n        inputParameters:\n        - name: parent\n          in: query\n          type: string\n          description: Parent namespace (for nested namespaces)\n        - name: pageToken\n          in: query\n          type:\
  \ string\n        - name: pageSize\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnamespace\n        method: POST\n        description: Create Namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-namespaces-namespace\n      path: /v1/namespaces/{namespace}\n      operations:\n      - name: loadnamespacemetadata\n        method: GET\n        description: Get Namespace Metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: dropnamespace\n        method: DELETE\n        description: Drop Namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-namespaces-namespace-properties\n\
  \      path: /v1/namespaces/{namespace}/properties\n      operations:\n      - name: updatenamespaceproperties\n        method: POST\n        description: Update Namespace Properties\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-namespaces-namespace-tables\n      path: /v1/namespaces/{namespace}/tables\n      operations:\n      - name: listtables\n        method: GET\n        description: List Tables\n        inputParameters:\n        - name: pageToken\n          in: query\n          type: string\n        - name: pageSize\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtable\n        method: POST\n        description: Create Table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: v1-namespaces-namespace-tables-table\n      path: /v1/namespaces/{namespace}/tables/{table}\n      operations:\n      - name: loadtable\n        method: GET\n        description: Load Table\n        inputParameters:\n        - name: snapshots\n          in: query\n          type: string\n          description: Which snapshots to return (all, refs, or none)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: committable\n        method: POST\n        description: Commit Table Update\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: droptable\n        method: DELETE\n        description: Drop Table\n        inputParameters:\n        - name: purgeRequested\n          in: query\n          type: boolean\n          description: Whether to purge table data files\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-namespaces-namespace-tables-table-metrics\n      path: /v1/namespaces/{namespace}/tables/{table}/metrics\n      operations:\n      - name: reportmetrics\n        method: POST\n        description: Report Table Metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-namespaces-namespace-views\n      path: /v1/namespaces/{namespace}/views\n      operations:\n      - name: listviews\n        method: GET\n        description: List Views\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createview\n        method: POST\n        description: Create View\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-namespaces-namespace-views-view\n\
  \      path: /v1/namespaces/{namespace}/views/{view}\n      operations:\n      - name: loadview\n        method: GET\n        description: Load View\n        inputParameters:\n        - name: view\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: dropview\n        method: DELETE\n        description: Drop View\n        inputParameters:\n        - name: view\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-transactions-commit\n      path: /v1/transactions/commit\n      operations:\n      - name: committransaction\n        method: POST\n        description: Commit Multi-Table Transaction\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: table-format-rest\n    description: REST adapter for Apache Iceberg REST Catalog API.\n    resources:\n    - path: /v1/config\n      name: getconfig\n      operations:\n      - method: GET\n        name: getconfig\n        description: Get Catalog Configuration\n        call: table-format.getconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/oauth/tokens\n      name: gettoken\n      operations:\n      - method: POST\n        name: gettoken\n        description: Get OAuth2 Token\n        call: table-format.gettoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/namespaces\n      name: listnamespaces\n      operations:\n      - method: GET\n        name: listnamespaces\n        description: List Namespaces\n        call: table-format.listnamespaces\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/namespaces\n      name: createnamespace\n      operations:\n      - method: POST\n        name: createnamespace\n        description: Create Namespace\n        call: table-format.createnamespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/namespaces/{namespace}\n      name: loadnamespacemetadata\n      operations:\n      - method: GET\n        name: loadnamespacemetadata\n        description: Get Namespace Metadata\n        call: table-format.loadnamespacemetadata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/namespaces/{namespace}\n      name: dropnamespace\n      operations:\n      - method: DELETE\n        name: dropnamespace\n        description: Drop Namespace\n        call: table-format.dropnamespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/namespaces/{namespace}/properties\n      name: updatenamespaceproperties\n\
  \      operations:\n      - method: POST\n        name: updatenamespaceproperties\n        description: Update Namespace Properties\n        call: table-format.updatenamespaceproperties\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/namespaces/{namespace}/tables\n      name: listtables\n      operations:\n      - method: GET\n        name: listtables\n        description: List Tables\n        call: table-format.listtables\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/namespaces/{namespace}/tables\n      name: createtable\n      operations:\n      - method: POST\n        name: createtable\n        description: Create Table\n        call: table-format.createtable\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/namespaces/{namespace}/tables/{table}\n      name: loadtable\n      operations:\n      - method: GET\n        name: loadtable\n        description: Load\
  \ Table\n        call: table-format.loadtable\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/namespaces/{namespace}/tables/{table}\n      name: committable\n      operations:\n      - method: POST\n        name: committable\n        description: Commit Table Update\n        call: table-format.committable\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/namespaces/{namespace}/tables/{table}\n      name: droptable\n      operations:\n      - method: DELETE\n        name: droptable\n        description: Drop Table\n        call: table-format.droptable\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/namespaces/{namespace}/tables/{table}/metrics\n      name: reportmetrics\n      operations:\n      - method: POST\n        name: reportmetrics\n        description: Report Table Metrics\n        call: table-format.reportmetrics\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/namespaces/{namespace}/views\n      name: listviews\n      operations:\n      - method: GET\n        name: listviews\n        description: List Views\n        call: table-format.listviews\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/namespaces/{namespace}/views\n      name: createview\n      operations:\n      - method: POST\n        name: createview\n        description: Create View\n        call: table-format.createview\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/namespaces/{namespace}/views/{view}\n      name: loadview\n      operations:\n      - method: GET\n        name: loadview\n        description: Load View\n        call: table-format.loadview\n        with:\n          view: rest.view\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/namespaces/{namespace}/views/{view}\n      name: dropview\n    \
  \  operations:\n      - method: DELETE\n        name: dropview\n        description: Drop View\n        call: table-format.dropview\n        with:\n          view: rest.view\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/transactions/commit\n      name: committransaction\n      operations:\n      - method: POST\n        name: committransaction\n        description: Commit Multi-Table Transaction\n        call: table-format.committransaction\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: table-format-mcp\n    transport: http\n    description: MCP adapter for Apache Iceberg REST Catalog API for AI agent use.\n    tools:\n    - name: getconfig\n      description: Get Catalog Configuration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: table-format.getconfig\n      with:\n        warehouse: tools.warehouse\n      inputParameters:\n\
  \      - name: warehouse\n        type: string\n        description: Warehouse identifier for multi-tenant catalogs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettoken\n      description: Get OAuth2 Token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: table-format.gettoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnamespaces\n      description: List Namespaces\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: table-format.listnamespaces\n      with:\n        parent: tools.parent\n        pageToken: tools.pageToken\n        pageSize: tools.pageSize\n      inputParameters:\n      - name: parent\n        type: string\n        description: Parent namespace (for nested namespaces)\n      - name: pageToken\n        type: string\n        description: pageToken\n      - name: pageSize\n        type: integer\n\
  \        description: pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnamespace\n      description: Create Namespace\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: table-format.createnamespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: loadnamespacemetadata\n      description: Get Namespace Metadata\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: table-format.loadnamespacemetadata\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dropnamespace\n      description: Drop Namespace\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: table-format.dropnamespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatenamespaceproperties\n      description: Update Namespace Properties\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: table-format.updatenamespaceproperties\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtables\n      description: List Tables\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: table-format.listtables\n      with:\n        pageToken: tools.pageToken\n        pageSize: tools.pageSize\n      inputParameters:\n      - name: pageToken\n        type: string\n        description: pageToken\n      - name: pageSize\n        type: integer\n        description: pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtable\n      description: Create Table\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: table-format.createtable\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ loadtable\n      description: Load Table\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: table-format.loadtable\n      with:\n        snapshots: tools.snapshots\n      inputParameters:\n      - name: snapshots\n        type: string\n        description: Which snapshots to return (all, refs, or none)\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: committable\n      description: Commit Table Update\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: table-format.committable\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: droptable\n      description: Drop Table\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: table-format.droptable\n      with:\n        purgeRequested: tools.purgeRequested\n      inputParameters:\n      - name: purgeRequested\n        type:\
  \ boolean\n        description: Whether to purge table data files\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reportmetrics\n      description: Report Table Metrics\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: table-format.reportmetrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listviews\n      description: List Views\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: table-format.listviews\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createview\n      description: Create View\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: table-format.createview\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: loadview\n      description: Load View\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: table-format.loadview\n      with:\n        view: tools.view\n      inputParameters:\n      - name: view\n        type: string\n        description: view\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dropview\n      description: Drop View\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: table-format.dropview\n      with:\n        view: tools.view\n      inputParameters:\n      - name: view\n        type: string\n        description: view\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: committransaction\n      description: Commit Multi-Table Transaction\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: table-format.committransaction\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\nbinds:\n- namespace: env\n  keys:\n    TABLE_FORMAT_TOKEN: TABLE_FORMAT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/table-format/refs/heads/main/capabilities/table-format-capability.yaml
tags:
- Table
- Format
- API
tools:
- description: Get Catalog Configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconfig
- description: Get OAuth2 Token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: gettoken
- description: List Namespaces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnamespaces
- description: Create Namespace
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnamespace
- description: Get Namespace Metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: loadnamespacemetadata
- description: Drop Namespace
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: dropnamespace
- description: Update Namespace Properties
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatenamespaceproperties
- description: List Tables
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtables
- description: Create Table
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtable
- description: Load Table
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: loadtable
- description: Commit Table Update
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: committable
- description: Drop Table
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: droptable
- description: Report Table Metrics
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: reportmetrics
- description: List Views
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listviews
- description: Create View
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createview
- description: Load View
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: loadview
- description: Drop View
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: dropview
- description: Commit Multi-Table Transaction
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: committransaction
---
