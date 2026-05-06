---
categories:
- crm-sales
consumed_apis: []
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
- sales
- integration
- sobject metadata and describe.
- Salesforce Admin
- list all bulk ingest jobs.
- submit salesforce approval
- describe all available sobjects.
- create ingest job
- manages sales processes, reports, and pipeline.
- bulk data loading and external system integration.
- create salesforce record
- cloud
- create a new record in salesforce.
- execute query
- flows, process automation, and approval management.
- enterprise
- record crud operations.
- crud operations and data queries.
- crm
- execute a sosl search.
- describe all available sobjects in the salesforce org.
- query salesforce data
- soql query execution.
- describe salesforce sobjects
- execute a sosl search across salesforce.
- crud, queries, search, and bulk data operations.
- manages salesforce configuration, data, and automation.
- create a new record.
- execute a soql query.
- submit a record for approval in salesforce.
- create bulk ingest job
- list bulk ingest jobs
- create record
- create a new bulk ingest job.
- execute search
- search salesforce data
- create a bulk data ingest job for large datasets.
- real-time event streaming and change data capture.
- create bulk query job
- create a bulk query job for large result sets.
- bulk data operations.
- Integration Developer
- execute a soql query against salesforce data.
- list ingest jobs
- builds integrations between salesforce and external systems.
- data operations
- sosl search.
- describe all
- salesforce
- automation
slug: data-operations
source_filename: data-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Salesforce Data Operations\n  description: Unified workflow combining the Salesforce REST API and Bulk API for comprehensive data operations including\n    CRUD, queries, search, and bulk data loading. Used by Salesforce admins and integration developers.\n  tags:\n  - Salesforce\n  - Data Operations\n  - CRM\n  - Integration\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SALESFORCE_ACCESS_TOKEN: SALESFORCE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: salesforce-rest\n    baseUri: https://yourInstance.salesforce.com/services/data/v63.0\n    description: Salesforce REST API for data operations.\n    authentication:\n      type: bearer\n      token: '{{SALESFORCE_ACCESS_TOKEN}}'\n    resources:\n    - name: sobjects\n      path: /sobjects\n      description: SObject operations including describe, CRUD, and metadata.\n      operations:\n      - name: describe-global\n \
  \       method: GET\n        description: Describe all available SObjects.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-record\n        method: POST\n        description: Create a new SObject record.\n        inputParameters:\n        - name: sObjectName\n          in: path\n          type: string\n          required: true\n          description: SObject type name.\n        body:\n          type: json\n          data:\n            fieldName: '{{tools.fieldValue}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: query\n      path: /query\n      description: SOQL query execution.\n      operations:\n      - name: execute-query\n        method: GET\n        description: Execute a SOQL query.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required:\
  \ true\n          description: SOQL query string.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      description: SOSL search execution.\n      operations:\n      - name: execute-search\n        method: GET\n        description: Execute a SOSL search.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: SOSL search string.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: approvals\n      path: /process/approvals\n      description: Approval process operations.\n      operations:\n      - name: list-approvals\n        method: GET\n        description: List approval processes.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n        \
  \  value: $.\n      - name: submit-approval\n        method: POST\n        description: Submit an approval request.\n        body:\n          type: json\n          data:\n            requests: '{{tools.requests}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: salesforce-bulk\n    baseUri: https://yourInstance.salesforce.com/services/data/v63.0\n    description: Salesforce Bulk API 2.0 for large data operations.\n    authentication:\n      type: bearer\n      token: '{{SALESFORCE_ACCESS_TOKEN}}'\n    resources:\n    - name: ingest-jobs\n      path: /jobs/ingest\n      description: Bulk ingest job management.\n      operations:\n      - name: list-ingest-jobs\n        method: GET\n        description: List all ingest jobs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-ingest-job\n\
  \        method: POST\n        description: Create a new ingest job.\n        body:\n          type: json\n          data:\n            object: '{{tools.object}}'\n            operation: '{{tools.operation}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: query-jobs\n      path: /jobs/query\n      description: Bulk query job management.\n      operations:\n      - name: list-query-jobs\n        method: GET\n        description: List all query jobs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-query-job\n        method: POST\n        description: Create a new query job.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n\
  \  - type: rest\n    port: 8080\n    namespace: salesforce-data-api\n    description: Unified REST API for Salesforce data operations.\n    resources:\n    - path: /v1/sobjects\n      name: sobjects\n      description: SObject metadata and describe.\n      operations:\n      - method: GET\n        name: describe-all\n        description: Describe all available SObjects.\n        call: salesforce-rest.describe-global\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/records\n      name: records\n      description: Record CRUD operations.\n      operations:\n      - method: POST\n        name: create-record\n        description: Create a new record.\n        call: salesforce-rest.create-record\n        with:\n          sObjectName: rest.sObjectName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/query\n      name: query\n      description: SOQL query execution.\n      operations:\n      - method: GET\n  \
  \      name: execute-query\n        description: Execute a SOQL query.\n        call: salesforce-rest.execute-query\n        with:\n          q: rest.q\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search\n      name: search\n      description: SOSL search.\n      operations:\n      - method: GET\n        name: execute-search\n        description: Execute a SOSL search.\n        call: salesforce-rest.execute-search\n        with:\n          q: rest.q\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bulk-jobs\n      name: bulk-jobs\n      description: Bulk data operations.\n      operations:\n      - method: GET\n        name: list-ingest-jobs\n        description: List all bulk ingest jobs.\n        call: salesforce-bulk.list-ingest-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-ingest-job\n        description: Create a new bulk\
  \ ingest job.\n        call: salesforce-bulk.create-ingest-job\n        with:\n          object: rest.object\n          operation: rest.operation\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: salesforce-data-mcp\n    transport: http\n    description: MCP server for AI-assisted Salesforce data operations.\n    tools:\n    - name: describe-salesforce-sobjects\n      description: Describe all available SObjects in the Salesforce org.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-rest.describe-global\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-salesforce-record\n      description: Create a new record in Salesforce.\n      hints:\n        readOnly: false\n      call: salesforce-rest.create-record\n      with:\n        sObjectName: tools.sObjectName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-salesforce-data\n\
  \      description: Execute a SOQL query against Salesforce data.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-rest.execute-query\n      with:\n        q: tools.q\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-salesforce-data\n      description: Execute a SOSL search across Salesforce.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: salesforce-rest.execute-search\n      with:\n        q: tools.q\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-salesforce-approval\n      description: Submit a record for approval in Salesforce.\n      hints:\n        readOnly: false\n      call: salesforce-rest.submit-approval\n      with:\n        requests: tools.requests\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-bulk-ingest-job\n      description: Create a bulk data ingest job for large datasets.\n      hints:\n\
  \        readOnly: false\n      call: salesforce-bulk.create-ingest-job\n      with:\n        object: tools.object\n        operation: tools.operation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-bulk-query-job\n      description: Create a bulk query job for large result sets.\n      hints:\n        readOnly: false\n      call: salesforce-bulk.create-query-job\n      with:\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-bulk-ingest-jobs\n      description: List all bulk ingest jobs.\n      hints:\n        readOnly: true\n      call: salesforce-bulk.list-ingest-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
