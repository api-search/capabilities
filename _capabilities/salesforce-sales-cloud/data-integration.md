---
categories: []
consumed_apis:
- salesforce-bulk
- salesforce-sales-rest
description: Workflow capability for bulk data loading, real-time event streaming, and enterprise data integration in Salesforce Sales Cloud. Combines Bulk API 2.0 for large dataset operations with Change Data Capture for real-time sync. Designed for data engineers and ETL/ELT pipeline developers.
layout: capability
name: Salesforce Sales Cloud Data Integration
operations:
- description: List bulk ingest jobs
  method: GET
  name: list-ingest-jobs
  path: /v1/bulk/ingest-jobs
- description: Create a bulk ingest job
  method: POST
  name: create-ingest-job
  path: /v1/bulk/ingest-jobs
- description: Get bulk job status
  method: GET
  name: get-ingest-job
  path: /v1/bulk/ingest-jobs/{jobId}
- description: List bulk query jobs
  method: GET
  name: list-query-jobs
  path: /v1/bulk/query-jobs
- description: Create a bulk query job
  method: POST
  name: create-query-job
  path: /v1/bulk/query-jobs
- description: Extract data with SOQL
  method: GET
  name: query
  path: /v1/query
personas: []
provider_name: Salesforce Sales Cloud
provider_slug: salesforce-sales-cloud
search_terms:
- list bulk ingest jobs
- create bulk ingest job
- change data capture
- create a bulk query job
- extract data with soql
- create a new bulk data ingest job for large dataset loading
- close bulk ingest job
- create a bulk ingest job
- close or abort a bulk ingest job
- individual job management
- bulk query job management
- check api rate limits before running bulk operations
- list ingest jobs
- get bulk ingest job
- salesforce
- create query job
- get bulk job status
- list query jobs
- get api limits
- extract salesforce data using soql for integration pipelines
- cloud
- etl
- create bulk query job
- get status and results of a bulk ingest job
- data integration
- bulk data ingest job management
- enterprise
- events
- extract data soql
- query
- create a bulk query job to extract large datasets via soql
- sales
- bulk loading
- soql data extraction
- customer management
- sales cloud
- create ingest job
- crm
- get ingest job
- list all bulk data ingest jobs and their statuses
- list bulk query jobs
slug: data-integration
source_filename: data-integration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Salesforce Sales Cloud Data Integration\"\n  description: >-\n    Workflow capability for bulk data loading, real-time event streaming, and\n    enterprise data integration in Salesforce Sales Cloud. Combines Bulk API 2.0\n    for large dataset operations with Change Data Capture for real-time sync.\n    Designed for data engineers and ETL/ELT pipeline developers.\n  tags:\n    - Salesforce\n    - Sales Cloud\n    - Data Integration\n    - Bulk Loading\n    - ETL\n    - Change Data Capture\n    - Events\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SALESFORCE_ACCESS_TOKEN: SALESFORCE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: salesforce-bulk\n      location: ./shared/sales-cloud-bulk-api.yaml\n    - import: salesforce-sales-rest\n      location: ./shared/sales-cloud-rest-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: data-integration-api\n\
  \      description: \"Unified REST API for Salesforce data integration operations.\"\n      resources:\n        - path: /v1/bulk/ingest-jobs\n          name: ingest-jobs\n          description: \"Bulk data ingest job management\"\n          operations:\n            - method: GET\n              name: list-ingest-jobs\n              description: \"List bulk ingest jobs\"\n              call: \"salesforce-bulk.list-ingest-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-ingest-job\n              description: \"Create a bulk ingest job\"\n              call: \"salesforce-bulk.create-ingest-job\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bulk/ingest-jobs/{jobId}\n          name: ingest-job\n          description: \"Individual job management\"\n          operations:\n            - method: GET\n       \
  \       name: get-ingest-job\n              description: \"Get bulk job status\"\n              call: \"salesforce-bulk.get-ingest-job\"\n              with:\n                jobId: \"rest.jobId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bulk/query-jobs\n          name: query-jobs\n          description: \"Bulk query job management\"\n          operations:\n            - method: GET\n              name: list-query-jobs\n              description: \"List bulk query jobs\"\n              call: \"salesforce-bulk.list-query-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-query-job\n              description: \"Create a bulk query job\"\n              call: \"salesforce-bulk.create-query-job\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n     \
  \   - path: /v1/query\n          name: soql\n          description: \"SOQL data extraction\"\n          operations:\n            - method: GET\n              name: query\n              description: \"Extract data with SOQL\"\n              call: \"salesforce-sales-rest.soql-query\"\n              with:\n                q: \"rest.q\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: data-integration-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Salesforce data integration and ETL operations.\"\n      tools:\n        - name: list-bulk-ingest-jobs\n          description: \"List all bulk data ingest jobs and their statuses\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-bulk.list-ingest-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-bulk-ingest-job\n\
  \          description: \"Create a new bulk data ingest job for large dataset loading\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"salesforce-bulk.create-ingest-job\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-bulk-ingest-job\n          description: \"Get status and results of a bulk ingest job\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-bulk.get-ingest-job\"\n          with:\n            jobId: \"tools.jobId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: close-bulk-ingest-job\n          description: \"Close or abort a bulk ingest job\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"salesforce-bulk.close-ingest-job\"\n          with:\n            jobId: \"tools.jobId\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: create-bulk-query-job\n          description: \"Create a bulk query job to extract large datasets via SOQL\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"salesforce-bulk.create-query-job\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-bulk-query-jobs\n          description: \"List bulk query jobs\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-bulk.list-query-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: extract-data-soql\n          description: \"Extract Salesforce data using SOQL for integration pipelines\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-sales-rest.soql-query\"\n          with:\n            q: \"\
  tools.q\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-api-limits\n          description: \"Check API rate limits before running bulk operations\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-sales-rest.get-org-limits\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/salesforce-sales-cloud/refs/heads/main/capabilities/data-integration.yaml
tags:
- Salesforce
- Sales Cloud
- Data Integration
- Bulk Loading
- ETL
- Change Data Capture
- Events
tools:
- description: List all bulk data ingest jobs and their statuses
  hints:
    idempotent: true
    readOnly: true
  name: list-bulk-ingest-jobs
- description: Create a new bulk data ingest job for large dataset loading
  hints:
    destructive: false
    readOnly: false
  name: create-bulk-ingest-job
- description: Get status and results of a bulk ingest job
  hints:
    idempotent: true
    readOnly: true
  name: get-bulk-ingest-job
- description: Close or abort a bulk ingest job
  hints:
    idempotent: true
    readOnly: false
  name: close-bulk-ingest-job
- description: Create a bulk query job to extract large datasets via SOQL
  hints:
    destructive: false
    readOnly: false
  name: create-bulk-query-job
- description: List bulk query jobs
  hints:
    idempotent: true
    readOnly: true
  name: list-bulk-query-jobs
- description: Extract Salesforce data using SOQL for integration pipelines
  hints:
    idempotent: true
    readOnly: true
  name: extract-data-soql
- description: Check API rate limits before running bulk operations
  hints:
    idempotent: true
    readOnly: true
  name: get-api-limits
---
