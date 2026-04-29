---
api_specs:
- filename: wql.yml
  format: yaml
  label: workday-wql
  slug: workday-wql
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/workday/refs/heads/main/openapi/wql.yml
- filename: raas.yml
  format: yaml
  label: workday-raas
  slug: workday-raas
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/workday/refs/heads/main/openapi/raas.yml
categories:
- analytics
consumed_apis:
- workday-prism
- workday-wql
- workday-raas
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
- wql execute query
- prism list tables
- prism list data change tasks
- wql query endpoint
- create a new prism analytics dataset
- workday
- create a data change task
- cloud computing
- raas get report
- reporting
- prism create data change task
- get fields for a wql data source
- wql get data source fields
- enterprise software
- prism analytics datasets
- prism get dataset
- get a dataset by id
- list all prism tables
- saas
- hcm
- business intelligence
- execute a wql query
- analytics
- prism delete dataset
- delete a dataset
- financial management
- execute query
- prism list datasets
- prism create dataset
- wql get data source
- execute a wql query against workday data
- retrieve a custom workday report
- list available wql data sources
- list data change tasks
- get a wql data source by id
- list datasets
- wql list data sources
- list all prism analytics datasets
slug: analytics-and-reporting
source_filename: analytics-and-reporting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Workday Analytics and Reporting\"\n  description: \"Unified analytics and reporting combining Prism Analytics, WQL, and Report-as-a-Service APIs for business analysts to query data, manage datasets, and access custom reports.\"\n  tags:\n    - Workday\n    - Analytics\n    - Reporting\n    - Business Intelligence\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      WORKDAY_OAUTH_TOKEN: WORKDAY_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: workday-prism\n      location: ./shared/prism-analytics.yaml\n    - import: workday-wql\n      location: ./shared/wql.yaml\n    - import: workday-raas\n      location: ./shared/raas.yaml\n\n  exposes:\n    - type: rest\n      port: 8085\n      namespace: analytics-reporting-api\n      description: \"Unified REST API for analytics and reporting.\"\n      resources:\n        - path: /v1/datasets\n          name: datasets\n          description:\
  \ \"Prism Analytics datasets\"\n          operations:\n            - method: GET\n              name: list-datasets\n              description: \"List datasets\"\n              call: \"workday-prism.get-datasets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/wql-query\n          name: wql\n          description: \"WQL query endpoint\"\n          operations:\n            - method: POST\n              name: execute-query\n              description: \"Execute a WQL query\"\n              call: \"workday-wql.execute-wql-query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9085\n      namespace: analytics-reporting-mcp\n      transport: http\n      description: \"MCP server for AI-assisted analytics and reporting.\"\n      tools:\n        - name: prism-list-datasets\n          description: \"List all Prism Analytics datasets\"\n \
  \         hints:\n            readOnly: true\n          call: \"workday-prism.get-datasets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: prism-create-dataset\n          description: \"Create a new Prism Analytics dataset\"\n          hints:\n            readOnly: false\n          call: \"workday-prism.create-dataset\"\n          with:\n            name: \"tools.name\"\n            fields: \"tools.fields\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: prism-get-dataset\n          description: \"Get a dataset by ID\"\n          hints:\n            readOnly: true\n          call: \"workday-prism.get-dataset-by-id\"\n          with:\n            ID: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: prism-delete-dataset\n          description: \"Delete a dataset\"\n          hints:\n            readOnly: false\n\
  \            destructive: true\n          call: \"workday-prism.delete-dataset\"\n          with:\n            ID: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: prism-list-data-change-tasks\n          description: \"List data change tasks\"\n          hints:\n            readOnly: true\n          call: \"workday-prism.get-data-change-tasks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: prism-create-data-change-task\n          description: \"Create a data change task\"\n          hints:\n            readOnly: false\n          call: \"workday-prism.create-data-change-task\"\n          with:\n            targetDataset: \"tools.targetDataset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: prism-list-tables\n          description: \"List all Prism tables\"\n          hints:\n            readOnly: true\n\
  \          call: \"workday-prism.get-tables\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: wql-execute-query\n          description: \"Execute a WQL query against Workday data\"\n          hints:\n            readOnly: true\n          call: \"workday-wql.execute-wql-query\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: wql-list-data-sources\n          description: \"List available WQL data sources\"\n          hints:\n            readOnly: true\n          call: \"workday-wql.get-data-sources\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: wql-get-data-source\n          description: \"Get a WQL data source by ID\"\n          hints:\n            readOnly: true\n          call: \"workday-wql.get-data-source-by-id\"\n          with:\n            ID: \"tools.id\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: wql-get-data-source-fields\n          description: \"Get fields for a WQL data source\"\n          hints:\n            readOnly: true\n          call: \"workday-wql.get-data-source-fields\"\n          with:\n            ID: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: raas-get-report\n          description: \"Retrieve a custom Workday report\"\n          hints:\n            readOnly: true\n          call: \"workday-raas.get-custom-report\"\n          with:\n            report_owner: \"tools.report_owner\"\n            report_name: \"tools.report_name\"\n            format: \"tools.format\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
