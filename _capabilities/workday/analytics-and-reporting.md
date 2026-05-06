---
categories:
- analytics
consumed_apis: []
description: Unified analytics and reporting combining Prism Analytics, WQL, and Report-as-a-Service APIs for business analysts to query data, manage datasets, and access custom reports.
layout: capability
name: Workday Analytics and Reporting
operations:
- description: List datasets
  method: GET
  name: list-datasets
  path: /v1/datasets
- description: Execute a WQL query
  method: POST
  name: execute-query
  path: /v1/wql-query
personas: []
provider_name: Workday
provider_slug: workday
search_terms:
- create a new prism analytics dataset
- get a dataset by id
- reporting
- prism get dataset
- analytics
- delete a dataset
- list data change tasks
- list datasets
- create a data change task
- wql query endpoint
- wql list data sources
- list all prism tables
- wql get data source fields
- raas get report
- wql get data source
- prism create data change task
- execute query
- get a wql data source by id
- prism list tables
- list available wql data sources
- prism delete dataset
- cloud computing
- execute a wql query against workday data
- workday
- prism create dataset
- financial management
- execute a wql query
- get fields for a wql data source
- saas
- retrieve a custom workday report
- hcm
- prism list data change tasks
- prism list datasets
- business intelligence
- enterprise software
- wql execute query
- prism analytics datasets
- list all prism analytics datasets
slug: analytics-and-reporting
source_filename: analytics-and-reporting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Workday Analytics and Reporting\n  description: Unified analytics and reporting combining Prism Analytics, WQL, and Report-as-a-Service APIs for business analysts\n    to query data, manage datasets, and access custom reports.\n  tags:\n  - Workday\n  - Analytics\n  - Reporting\n  - Business Intelligence\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WORKDAY_OAUTH_TOKEN: WORKDAY_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: workday-prism\n    baseUri: https://wd2-impl-services1.workday.com/ccx/api/v1/{tenant}/prismAnalytics\n    description: Workday Prism Analytics REST API.\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_OAUTH_TOKEN}}'\n    resources:\n    - name: prism\n      path: /\n      description: Prism Analytics operations\n      operations:\n      - name: get-datasets\n        method: GET\n        description: Returns datasets.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-dataset\n        method: POST\n        description: Creates a new dataset.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            fields: '{{tools.fields}}'\n      - name: get-dataset-by-id\n        method: GET\n        description: Returns a dataset by ID.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: Dataset ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-dataset\n        method: PUT\n        description: Updates a dataset.\n        inputParameters:\n        - name: ID\n          in: path\n   \
  \       type: string\n          required: true\n          description: Dataset ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-dataset\n        method: DELETE\n        description: Deletes a dataset.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: Dataset ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-data-change-tasks\n        method: GET\n        description: Returns data change tasks.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-data-change-task\n        method: POST\n        description: Creates a data change task.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            targetDataset: '{{tools.targetDataset}}'\n      - name: get-tables\n        method: GET\n        description: Returns tables.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-table-by-id\n        method: GET\n        description: Returns a table by ID.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: Table ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-file-container\n        method: POST\n        description: Creates a file container for data upload.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: get-file-container-by-id\n        method: GET\n        description: Returns a file container by ID.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: File container ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-data-change-task-activities\n        method: GET\n        description: Returns activities for a data change task.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: Data change task ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: workday-wql\n    baseUri: https://wd2-impl-services1.workday.com/ccx/api/v1/{tenant}/wql\n    description: Workday WQL REST API.\n    authentication:\n\
  \      type: bearer\n      token: '{{WORKDAY_OAUTH_TOKEN}}'\n    resources:\n    - name: wql\n      path: /\n      description: WQL query operations\n      operations:\n      - name: execute-wql-query\n        method: POST\n        description: Executes a WQL query.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n      - name: get-data-sources\n        method: GET\n        description: Returns available data sources.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-data-source-by-id\n        method: GET\n        description: Returns a data source by ID.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: Data source ID.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-data-source-fields\n        method: GET\n        description: Returns fields for a data source.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: Data source ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: workday-raas\n    baseUri: https://wd2-impl-services1.workday.com/ccx/service/{tenant}\n    description: Workday Report-as-a-Service API.\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_OAUTH_TOKEN}}'\n    resources:\n    - name: reports\n      path: /\n      description: Report operations\n      operations:\n      - name: get-custom-report\n        method: GET\n        description: Retrieves a custom report by owner and name.\n        inputParameters:\n\
  \        - name: report_owner\n          in: path\n          type: string\n          required: true\n          description: Report owner username.\n        - name: report_name\n          in: path\n          type: string\n          required: true\n          description: Report name.\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: Output format (json, csv, xml).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8085\n    namespace: analytics-reporting-api\n    description: Unified REST API for analytics and reporting.\n    resources:\n    - path: /v1/datasets\n      name: datasets\n      description: Prism Analytics datasets\n      operations:\n      - method: GET\n        name: list-datasets\n        description: List datasets\n        call: workday-prism.get-datasets\n        outputParameters:\n     \
  \   - type: object\n          mapping: $.\n    - path: /v1/wql-query\n      name: wql\n      description: WQL query endpoint\n      operations:\n      - method: POST\n        name: execute-query\n        description: Execute a WQL query\n        call: workday-wql.execute-wql-query\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9085\n    namespace: analytics-reporting-mcp\n    transport: http\n    description: MCP server for AI-assisted analytics and reporting.\n    tools:\n    - name: prism-list-datasets\n      description: List all Prism Analytics datasets\n      hints:\n        readOnly: true\n      call: workday-prism.get-datasets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: prism-create-dataset\n      description: Create a new Prism Analytics dataset\n      hints:\n        readOnly: false\n      call: workday-prism.create-dataset\n      with:\n        name: tools.name\n        fields: tools.fields\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: prism-get-dataset\n      description: Get a dataset by ID\n      hints:\n        readOnly: true\n      call: workday-prism.get-dataset-by-id\n      with:\n        ID: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: prism-delete-dataset\n      description: Delete a dataset\n      hints:\n        readOnly: false\n        destructive: true\n      call: workday-prism.delete-dataset\n      with:\n        ID: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: prism-list-data-change-tasks\n      description: List data change tasks\n      hints:\n        readOnly: true\n      call: workday-prism.get-data-change-tasks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: prism-create-data-change-task\n      description: Create a data change task\n      hints:\n        readOnly: false\n      call: workday-prism.create-data-change-task\n\
  \      with:\n        targetDataset: tools.targetDataset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: prism-list-tables\n      description: List all Prism tables\n      hints:\n        readOnly: true\n      call: workday-prism.get-tables\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: wql-execute-query\n      description: Execute a WQL query against Workday data\n      hints:\n        readOnly: true\n      call: workday-wql.execute-wql-query\n      with:\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: wql-list-data-sources\n      description: List available WQL data sources\n      hints:\n        readOnly: true\n      call: workday-wql.get-data-sources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: wql-get-data-source\n      description: Get a WQL data source by ID\n      hints:\n        readOnly: true\n      call: workday-wql.get-data-source-by-id\n\
  \      with:\n        ID: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: wql-get-data-source-fields\n      description: Get fields for a WQL data source\n      hints:\n        readOnly: true\n      call: workday-wql.get-data-source-fields\n      with:\n        ID: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: raas-get-report\n      description: Retrieve a custom Workday report\n      hints:\n        readOnly: true\n      call: workday-raas.get-custom-report\n      with:\n        report_owner: tools.report_owner\n        report_name: tools.report_name\n        format: tools.format\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday/refs/heads/main/capabilities/analytics-and-reporting.yaml
tags:
- Workday
- Analytics
- Reporting
- Business Intelligence
tools:
- description: List all Prism Analytics datasets
  hints:
    readOnly: true
  name: prism-list-datasets
- description: Create a new Prism Analytics dataset
  hints:
    readOnly: false
  name: prism-create-dataset
- description: Get a dataset by ID
  hints:
    readOnly: true
  name: prism-get-dataset
- description: Delete a dataset
  hints:
    destructive: true
    readOnly: false
  name: prism-delete-dataset
- description: List data change tasks
  hints:
    readOnly: true
  name: prism-list-data-change-tasks
- description: Create a data change task
  hints:
    readOnly: false
  name: prism-create-data-change-task
- description: List all Prism tables
  hints:
    readOnly: true
  name: prism-list-tables
- description: Execute a WQL query against Workday data
  hints:
    readOnly: true
  name: wql-execute-query
- description: List available WQL data sources
  hints:
    readOnly: true
  name: wql-list-data-sources
- description: Get a WQL data source by ID
  hints:
    readOnly: true
  name: wql-get-data-source
- description: Get fields for a WQL data source
  hints:
    readOnly: true
  name: wql-get-data-source-fields
- description: Retrieve a custom Workday report
  hints:
    readOnly: true
  name: raas-get-report
---
