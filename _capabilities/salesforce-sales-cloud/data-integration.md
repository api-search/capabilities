---
categories: []
consumed_apis: []
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
- list bulk query jobs
- data integration
- sales
- bulk query job management
- create a bulk ingest job
- create a new bulk data ingest job for large dataset loading
- get bulk ingest job
- create a bulk query job to extract large datasets via soql
- create ingest job
- get bulk job status
- cloud
- close bulk ingest job
- etl
- customer management
- enterprise
- close or abort a bulk ingest job
- get status and results of a bulk ingest job
- soql data extraction
- check api rate limits before running bulk operations
- query
- create a bulk query job
- crm
- get api limits
- extract salesforce data using soql for integration pipelines
- change data capture
- extract data soql
- individual job management
- extract data with soql
- create bulk ingest job
- list bulk ingest jobs
- sales cloud
- list all bulk data ingest jobs and their statuses
- create bulk query job
- bulk data ingest job management
- create query job
- bulk loading
- list ingest jobs
- events
- list query jobs
- salesforce
- get ingest job
slug: data-integration
source_filename: data-integration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Salesforce Sales Cloud Data Integration\n  description: Workflow capability for bulk data loading, real-time event streaming, and enterprise data integration in Salesforce\n    Sales Cloud. Combines Bulk API 2.0 for large dataset operations with Change Data Capture for real-time sync. Designed\n    for data engineers and ETL/ELT pipeline developers.\n  tags:\n  - Salesforce\n  - Sales Cloud\n  - Data Integration\n  - Bulk Loading\n  - ETL\n  - Change Data Capture\n  - Events\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SALESFORCE_ACCESS_TOKEN: SALESFORCE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: salesforce-bulk\n    baseUri: https://{instance}.salesforce.com/services/data/v59.0\n    description: Salesforce Bulk API 2.0\n    authentication:\n      type: bearer\n      token: '{{SALESFORCE_ACCESS_TOKEN}}'\n    resources:\n    - name: ingest-jobs\n      path: /jobs/ingest\n\
  \      description: Bulk ingest job management\n      operations:\n      - name: list-ingest-jobs\n        method: GET\n        description: List all bulk ingest jobs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-ingest-job\n        method: POST\n        description: Create a new bulk ingest job\n        body:\n          type: json\n          data:\n            object: '{{tools.object}}'\n            contentType: '{{tools.contentType}}'\n            operation: '{{tools.operation}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ingest-job\n      path: /jobs/ingest/{jobId}\n      description: Individual ingest job operations\n      operations:\n      - name: get-ingest-job\n        method: GET\n        description: Get status of a bulk ingest job\n        inputParameters:\n        - name: jobId\n\
  \          in: path\n          type: string\n          required: true\n          description: Bulk job ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: close-ingest-job\n        method: PATCH\n        description: Close or abort a bulk ingest job\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: Bulk job ID\n        body:\n          type: json\n          data:\n            state: '{{tools.state}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: query-jobs\n      path: /jobs/query\n      description: Bulk query job management\n      operations:\n      - name: list-query-jobs\n        method: GET\n        description: List all bulk query jobs\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: create-query-job\n        method: POST\n        description: Create a bulk query job\n        body:\n          type: json\n          data:\n            operation: '{{tools.operation}}'\n            query: '{{tools.query}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: salesforce-sales-rest\n    baseUri: https://{instance}.salesforce.com/services/data/v59.0\n    description: Salesforce Sales Cloud REST API\n    authentication:\n      type: bearer\n      token: '{{SALESFORCE_ACCESS_TOKEN}}'\n    resources:\n    - name: limits\n      path: /limits\n      description: Org API limits\n      operations:\n      - name: get-org-limits\n        method: GET\n        description: Get API limits and usage information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: sobjects\n      path: /sobjects\n      description: List sObject types\n      operations:\n      - name: list-sobjects\n        method: GET\n        description: List all sObject types in the org\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sobject-describe\n      path: /sobjects/{sObjectName}/describe\n      description: sObject metadata\n      operations:\n      - name: describe-sobject\n        method: GET\n        description: Get metadata description of a sObject type\n        inputParameters:\n        - name: sObjectName\n          in: path\n          type: string\n          required: true\n          description: API name of the sObject\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sobject-records\n      path: /sobjects/{sObjectName}\n      description: sObject\
  \ record operations\n      operations:\n      - name: create-sobject-record\n        method: POST\n        description: Create a new sObject record\n        inputParameters:\n        - name: sObjectName\n          in: path\n          type: string\n          required: true\n          description: API name of the sObject\n        body:\n          type: json\n          data:\n            fields: '{{tools.fields}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sobject-row\n      path: /sobjects/{sObjectName}/{id}\n      description: Individual sObject record operations\n      operations:\n      - name: get-sobject-record\n        method: GET\n        description: Get a specific sObject record by ID\n        inputParameters:\n        - name: sObjectName\n          in: path\n          type: string\n          required: true\n          description: API name of the sObject\n        - name: id\n       \
  \   in: path\n          type: string\n          required: true\n          description: Salesforce record ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-sobject-record\n        method: PATCH\n        description: Update a sObject record\n        inputParameters:\n        - name: sObjectName\n          in: path\n          type: string\n          required: true\n          description: API name of the sObject\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Salesforce record ID\n        body:\n          type: json\n          data:\n            fields: '{{tools.fields}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-sobject-record\n        method: DELETE\n        description: Delete a sObject record\n        inputParameters:\n\
  \        - name: sObjectName\n          in: path\n          type: string\n          required: true\n          description: API name of the sObject\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Salesforce record ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: soql-query\n      path: /query\n      description: SOQL query execution\n      operations:\n      - name: soql-query\n        method: GET\n        description: Execute a SOQL query\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: SOQL query string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sosl-search\n      path: /search\n      description: SOSL search execution\n      operations:\n   \
  \   - name: sosl-search\n        method: GET\n        description: Execute a SOSL search\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: SOSL search string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: process-approvals\n      path: /process/approvals\n      description: Approval process management\n      operations:\n      - name: list-approval-items\n        method: GET\n        description: List all approval items\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: submit-for-approval\n        method: POST\n        description: Submit a record for approval\n        body:\n          type: json\n          data:\n            requests: '{{tools.requests}}'\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: data-integration-api\n    description: Unified REST API for Salesforce data integration operations.\n    resources:\n    - path: /v1/bulk/ingest-jobs\n      name: ingest-jobs\n      description: Bulk data ingest job management\n      operations:\n      - method: GET\n        name: list-ingest-jobs\n        description: List bulk ingest jobs\n        call: salesforce-bulk.list-ingest-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-ingest-job\n        description: Create a bulk ingest job\n        call: salesforce-bulk.create-ingest-job\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bulk/ingest-jobs/{jobId}\n      name: ingest-job\n      description: Individual job management\n      operations:\n      - method: GET\n        name: get-ingest-job\n\
  \        description: Get bulk job status\n        call: salesforce-bulk.get-ingest-job\n        with:\n          jobId: rest.jobId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bulk/query-jobs\n      name: query-jobs\n      description: Bulk query job management\n      operations:\n      - method: GET\n        name: list-query-jobs\n        description: List bulk query jobs\n        call: salesforce-bulk.list-query-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-query-job\n        description: Create a bulk query job\n        call: salesforce-bulk.create-query-job\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/query\n      name: soql\n      description: SOQL data extraction\n      operations:\n      - method: GET\n        name: query\n        description: Extract data with SOQL\n        call: salesforce-sales-rest.soql-query\n\
  \        with:\n          q: rest.q\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: data-integration-mcp\n    transport: http\n    description: MCP server for AI-assisted Salesforce data integration and ETL operations.\n    tools:\n    - name: list-bulk-ingest-jobs\n      description: List all bulk data ingest jobs and their statuses\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-bulk.list-ingest-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-bulk-ingest-job\n      description: Create a new bulk data ingest job for large dataset loading\n      hints:\n        readOnly: false\n        destructive: false\n      call: salesforce-bulk.create-ingest-job\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-bulk-ingest-job\n      description: Get status and results of a bulk ingest job\n      hints:\n  \
  \      readOnly: true\n        idempotent: true\n      call: salesforce-bulk.get-ingest-job\n      with:\n        jobId: tools.jobId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: close-bulk-ingest-job\n      description: Close or abort a bulk ingest job\n      hints:\n        readOnly: false\n        idempotent: true\n      call: salesforce-bulk.close-ingest-job\n      with:\n        jobId: tools.jobId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-bulk-query-job\n      description: Create a bulk query job to extract large datasets via SOQL\n      hints:\n        readOnly: false\n        destructive: false\n      call: salesforce-bulk.create-query-job\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-bulk-query-jobs\n      description: List bulk query jobs\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-bulk.list-query-jobs\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: extract-data-soql\n      description: Extract Salesforce data using SOQL for integration pipelines\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-sales-rest.soql-query\n      with:\n        q: tools.q\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-limits\n      description: Check API rate limits before running bulk operations\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-sales-rest.get-org-limits\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
