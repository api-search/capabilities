---
categories:
- crm-sales
consumed_apis:
- salesforce-rest
- salesforce-bulk
description: Unified workflow combining the Salesforce REST API and Bulk API for comprehensive data operations including CRUD, queries, search, and bulk data loading. Used by Salesforce admins and integration developers.
layout: capability
name: Salesforce Data Operations
operations:
- description: Describe all available SObjects.
  method: GET
  name: describe-all
  path: /v1/sobjects
- description: Create a new record.
  method: POST
  name: create-record
  path: /v1/records
- description: Execute a SOQL query.
  method: GET
  name: execute-query
  path: /v1/query
- description: Execute a SOSL search.
  method: GET
  name: execute-search
  path: /v1/search
- description: List all bulk ingest jobs.
  method: GET
  name: list-ingest-jobs
  path: /v1/bulk-jobs
- description: Create a new bulk ingest job.
  method: POST
  name: create-ingest-job
  path: /v1/bulk-jobs
personas: []
provider_name: Salesforce Automation
provider_slug: salesforce-automation
search_terms:
- bulk data loading and external system integration.
- create salesforce record
- submit a record for approval in salesforce.
- Integration Developer
- manages sales processes, reports, and pipeline.
- crm
- execute query
- execute a sosl search.
- create ingest job
- create a new record in salesforce.
- create bulk ingest job
- crud operations and data queries.
- sales
- describe all
- create a new record.
- describe all available sobjects in the salesforce org.
- create record
- sobject metadata and describe.
- manages salesforce configuration, data, and automation.
- execute a soql query.
- list bulk ingest jobs
- Salesforce Admin
- salesforce
- execute search
- crud, queries, search, and bulk data operations.
- bulk data operations.
- search salesforce data
- record crud operations.
- create a bulk query job for large result sets.
- describe salesforce sobjects
- soql query execution.
- list ingest jobs
- submit salesforce approval
- cloud
- create a bulk data ingest job for large datasets.
- integration
- create a new bulk ingest job.
- list all bulk ingest jobs.
- automation
- enterprise
- query salesforce data
- sosl search.
- describe all available sobjects.
- real-time event streaming and change data capture.
- create bulk query job
- data operations
- execute a soql query against salesforce data.
- flows, process automation, and approval management.
- execute a sosl search across salesforce.
- builds integrations between salesforce and external systems.
slug: data-operations
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Salesforce Data Operations\"\n  description: \"Unified workflow combining the Salesforce REST API and Bulk API for comprehensive data operations including CRUD, queries, search, and bulk data loading. Used by Salesforce admins and integration developers.\"\n  tags:\n    - Salesforce\n    - Data Operations\n    - CRM\n    - Integration\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SALESFORCE_ACCESS_TOKEN: SALESFORCE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: salesforce-rest\n      location: ./shared/salesforce-rest-api.yaml\n    - import: salesforce-bulk\n      location: ./shared/salesforce-bulk-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: salesforce-data-api\n      description: \"Unified REST API for Salesforce data operations.\"\n      resources:\n        - path: /v1/sobjects\n          name: sobjects\n          description: \"\
  SObject metadata and describe.\"\n          operations:\n            - method: GET\n              name: describe-all\n              description: \"Describe all available SObjects.\"\n              call: \"salesforce-rest.describe-global\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/records\n          name: records\n          description: \"Record CRUD operations.\"\n          operations:\n            - method: POST\n              name: create-record\n              description: \"Create a new record.\"\n              call: \"salesforce-rest.create-record\"\n              with:\n                sObjectName: \"rest.sObjectName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/query\n          name: query\n          description: \"SOQL query execution.\"\n          operations:\n            - method: GET\n              name: execute-query\n  \
  \            description: \"Execute a SOQL query.\"\n              call: \"salesforce-rest.execute-query\"\n              with:\n                q: \"rest.q\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/search\n          name: search\n          description: \"SOSL search.\"\n          operations:\n            - method: GET\n              name: execute-search\n              description: \"Execute a SOSL search.\"\n              call: \"salesforce-rest.execute-search\"\n              with:\n                q: \"rest.q\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bulk-jobs\n          name: bulk-jobs\n          description: \"Bulk data operations.\"\n          operations:\n            - method: GET\n              name: list-ingest-jobs\n              description: \"List all bulk ingest jobs.\"\n              call: \"salesforce-bulk.list-ingest-jobs\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-ingest-job\n              description: \"Create a new bulk ingest job.\"\n              call: \"salesforce-bulk.create-ingest-job\"\n              with:\n                object: \"rest.object\"\n                operation: \"rest.operation\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: salesforce-data-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Salesforce data operations.\"\n      tools:\n        - name: describe-salesforce-sobjects\n          description: \"Describe all available SObjects in the Salesforce org.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-rest.describe-global\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: create-salesforce-record\n          description: \"Create a new record in Salesforce.\"\n          hints:\n            readOnly: false\n          call: \"salesforce-rest.create-record\"\n          with:\n            sObjectName: \"tools.sObjectName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-salesforce-data\n          description: \"Execute a SOQL query against Salesforce data.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-rest.execute-query\"\n          with:\n            q: \"tools.q\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-salesforce-data\n          description: \"Execute a SOSL search across Salesforce.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-rest.execute-search\"\n \
  \         with:\n            q: \"tools.q\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-salesforce-approval\n          description: \"Submit a record for approval in Salesforce.\"\n          hints:\n            readOnly: false\n          call: \"salesforce-rest.submit-approval\"\n          with:\n            requests: \"tools.requests\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-bulk-ingest-job\n          description: \"Create a bulk data ingest job for large datasets.\"\n          hints:\n            readOnly: false\n          call: \"salesforce-bulk.create-ingest-job\"\n          with:\n            object: \"tools.object\"\n            operation: \"tools.operation\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-bulk-query-job\n          description: \"Create a bulk query job for large\
  \ result sets.\"\n          hints:\n            readOnly: false\n          call: \"salesforce-bulk.create-query-job\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-bulk-ingest-jobs\n          description: \"List all bulk ingest jobs.\"\n          hints:\n            readOnly: true\n          call: \"salesforce-bulk.list-ingest-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/salesforce-automation/refs/heads/main/capabilities/data-operations.yaml
tags:
- Salesforce
- Data Operations
- CRM
- Integration
tools:
- description: Describe all available SObjects in the Salesforce org.
  hints:
    idempotent: true
    readOnly: true
  name: describe-salesforce-sobjects
- description: Create a new record in Salesforce.
  hints:
    readOnly: false
  name: create-salesforce-record
- description: Execute a SOQL query against Salesforce data.
  hints:
    idempotent: true
    readOnly: true
  name: query-salesforce-data
- description: Execute a SOSL search across Salesforce.
  hints:
    idempotent: true
    readOnly: true
  name: search-salesforce-data
- description: Submit a record for approval in Salesforce.
  hints:
    readOnly: false
  name: submit-salesforce-approval
- description: Create a bulk data ingest job for large datasets.
  hints:
    readOnly: false
  name: create-bulk-ingest-job
- description: Create a bulk query job for large result sets.
  hints:
    readOnly: false
  name: create-bulk-query-job
- description: List all bulk ingest jobs.
  hints:
    readOnly: true
  name: list-bulk-ingest-jobs
---
