---
categories:
- crm-sales
consumed_apis:
- salesforce-rest
- salesforce-bulk
- salesforce-ui
description: Unified capability for CRM data management workflows combining the REST API, Bulk API 2.0, and UI API. Used by Salesforce admins, developers, and data teams to manage SObject records, run queries, perform bulk data operations, and build dynamic UIs.
layout: capability
name: Salesforce CRM Data Management
operations:
- description: List all SObject types available in the org.
  method: GET
  name: list-sobjects
  path: /v1/sobjects
- description: Get basic metadata for an SObject type.
  method: GET
  name: describe-sobject
  path: /v1/sobjects/{sobjectType}
- description: Create a new SObject record.
  method: POST
  name: create-record
  path: /v1/sobjects/{sobjectType}
- description: Get full metadata for an SObject type including all fields.
  method: GET
  name: full-describe-sobject
  path: /v1/sobjects/{sobjectType}/describe
- description: Get an SObject record by ID.
  method: GET
  name: get-record
  path: /v1/records/{sobjectType}/{id}
- description: Update an SObject record.
  method: PATCH
  name: update-record
  path: /v1/records/{sobjectType}/{id}
- description: Delete an SObject record.
  method: DELETE
  name: delete-record
  path: /v1/records/{sobjectType}/{id}
- description: Execute a SOQL query.
  method: POST
  name: execute-query
  path: /v1/queries
- description: Execute a SOQL queryAll including deleted records.
  method: POST
  name: execute-query-all
  path: /v1/queries
- description: Get the next page of query results.
  method: GET
  name: get-next-query-page
  path: /v1/queries/{queryId}
- description: Execute a SOSL search across multiple objects.
  method: GET
  name: execute-search
  path: /v1/searches
- description: Get current API limit usage and quotas.
  method: GET
  name: get-org-limits
  path: /v1/limits
- description: Get recently viewed records.
  method: GET
  name: get-recently-viewed
  path: /v1/recent
- description: Create up to 200 records in a single call.
  method: POST
  name: collections-create
  path: /v1/collections
- description: Update up to 200 records in a single call.
  method: PATCH
  name: collections-update
  path: /v1/collections
- description: Delete up to 200 records in a single call.
  method: DELETE
  name: collections-delete
  path: /v1/collections
- description: Execute a composite request with dependent subrequests.
  method: POST
  name: execute-composite
  path: /v1/composite
- description: Execute a batch of independent requests.
  method: POST
  name: execute-batch
  path: /v1/composite
- description: Create a new bulk ingest job.
  method: POST
  name: create-ingest-job
  path: /v1/ingest-jobs
- description: List bulk ingest jobs.
  method: GET
  name: list-ingest-jobs
  path: /v1/ingest-jobs
- description: Get detailed information about an ingest job.
  method: GET
  name: get-ingest-job-info
  path: /v1/ingest-jobs/{jobId}
- description: Update or close an ingest job.
  method: PATCH
  name: update-ingest-job
  path: /v1/ingest-jobs/{jobId}
- description: Delete an ingest job.
  method: DELETE
  name: delete-ingest-job
  path: /v1/ingest-jobs/{jobId}
- description: Get successfully processed records.
  method: GET
  name: get-successful-results
  path: /v1/ingest-jobs/{jobId}/results/successful
- description: Get failed records.
  method: GET
  name: get-failed-results
  path: /v1/ingest-jobs/{jobId}/results/failed
- description: Create a new bulk query job.
  method: POST
  name: create-query-job
  path: /v1/query-jobs
- description: List bulk query jobs.
  method: GET
  name: list-query-jobs
  path: /v1/query-jobs
- description: Get detailed information about a query job.
  method: GET
  name: get-query-job-info
  path: /v1/query-jobs/{jobId}
- description: Delete a query job.
  method: DELETE
  name: delete-query-job
  path: /v1/query-jobs/{jobId}
- description: Get query job results.
  method: GET
  name: get-query-job-results
  path: /v1/query-jobs/{jobId}/results
- description: Get object metadata including fields, types, and permissions.
  method: GET
  name: get-object-info
  path: /v1/object-info/{objectApiName}
- description: Get list views for an object.
  method: GET
  name: get-list-views
  path: /v1/list-views/{objectApiName}
personas: []
provider_name: Salesforce
provider_slug: salesforce
search_terms:
- get query job results
- execute a batch of independent requests.
- get successfully processed records from a bulk ingest job.
- get results from a completed bulk query job.
- commerce
- sales
- list all sobject types available in the salesforce org.
- get failed records.
- get query job results.
- get detailed information about a query job.
- ai
- individual ingest job operations.
- execute composite
- list bulk api 2.0 query jobs in the org.
- delete up to 200 records in a single call.
- customer service
- update record
- get detailed information about a bulk api 2.0 ingest job.
- sobject type listing and metadata.
- soql query execution.
- platform
- sobject type metadata and record creation.
- full describe sobject
- delete a bulk api 2.0 ingest job.
- delete record
- enterprise
- update an sobject record.
- create record
- list sobjects
- get failed results
- execute query
- collections delete
- get current api limit usage and quotas.
- data management
- get list views
- create a new bulk api 2.0 query job for extracting large data volumes.
- create a new bulk api 2.0 ingest job for bulk data operations.
- recently viewed records.
- sobject collections bulk crud.
- execute a sosl search across multiple objects.
- update or close a bulk api 2.0 ingest job.
- get recently viewed records for the current user.
- list views for objects.
- create a new sobject record.
- get successfully processed records.
- list ingest jobs
- create up to 200 records in a single call.
- delete query job
- get full metadata for an sobject type including all fields.
- execute a batch of independent rest api requests.
- list query jobs
- get detailed information about a bulk api 2.0 query job.
- execute a soql queryall including deleted records.
- bulk operations
- create a new bulk ingest job.
- execute a sosl search across multiple salesforce objects.
- get detailed information about an ingest job.
- sosl search execution.
- execute batch
- get basic metadata for a salesforce sobject type.
- create a new bulk query job.
- get record
- delete ingest job
- bulk api 2.0 ingest job management.
- get current api limit usage and remaining quotas for the salesforce org.
- get ingest job info
- delete a salesforce sobject record.
- update up to 200 records in a single call.
- cloud
- execute a composite request with dependent subrequests.
- get the next page of query results.
- get basic metadata for an sobject type.
- get query job info
- get recently viewed records.
- list all sobject types available in the org.
- crm
- update ingest job
- failed ingest results.
- update up to 200 sobject records in a single api call.
- get full metadata for a salesforce sobject type including all fields.
- get an sobject record by id.
- org api limits.
- marketing
- bulk api 2.0 query job management.
- get the next page of soql query results.
- delete up to 200 sobject records in a single api call.
- execute a soql query.
- execute search
- execute query all
- search lookup field records for typeahead suggestions.
- get picklist values for all picklist fields on an object for a given record type.
- get org limits
- collections create
- create ingest job
- successful ingest results.
- salesforce
- query result pagination.
- get list views for a salesforce object.
- query job results.
- sobjects
- composite request operations.
- list bulk api 2.0 ingest jobs in the org.
- get next query page
- get list views for an object.
- delete an sobject record.
- full sobject type metadata.
- get picklist values
- object metadata from ui api.
- list bulk ingest jobs.
- delete a query job.
- execute a soql queryall including deleted and archived records.
- update or close an ingest job.
- get object metadata including fields, types, and permissions.
- get object info
- get a salesforce sobject record by id.
- get successful results
- analytics
- get failed records from a bulk ingest job.
- collections update
- create query job
- create a new sobject record in salesforce.
- get recently viewed
- list bulk query jobs.
- describe sobject
- individual query job operations.
- delete an ingest job.
- update fields on a salesforce sobject record.
- execute a soql query against salesforce data.
- get lookup records
- create up to 200 sobject records in a single api call.
- get ui-ready metadata about a salesforce object including fields, types, and permissions.
- individual record crud operations.
slug: crm-data-management
source_filename: crm-data-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Salesforce CRM Data Management\"\n  description: \"Unified capability for CRM data management workflows combining the REST API, Bulk API 2.0, and UI API. Used by Salesforce admins, developers, and data teams to manage SObject records, run queries, perform bulk data operations, and build dynamic UIs.\"\n  tags:\n    - Salesforce\n    - CRM\n    - Data Management\n    - SObjects\n    - Bulk Operations\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SALESFORCE_ACCESS_TOKEN: SALESFORCE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: salesforce-rest\n      location: ./shared/rest-api.yaml\n    - import: salesforce-bulk\n      location: ./shared/bulk-api.yaml\n    - import: salesforce-ui\n      location: ./shared/ui-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: crm-data-management-api\n      description: \"Unified REST API for Salesforce CRM\
  \ data management.\"\n      resources:\n        - path: /v1/sobjects\n          name: sobjects\n          description: \"SObject type listing and metadata.\"\n          operations:\n            - method: GET\n              name: list-sobjects\n              description: \"List all SObject types available in the org.\"\n              call: \"salesforce-rest.list-sobjects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sobjects/{sobjectType}\n          name: sobject-type\n          description: \"SObject type metadata and record creation.\"\n          operations:\n            - method: GET\n              name: describe-sobject\n              description: \"Get basic metadata for an SObject type.\"\n              call: \"salesforce-rest.describe-sobject\"\n              with:\n                sobjectType: \"rest.sobjectType\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n            - method: POST\n              name: create-record\n              description: \"Create a new SObject record.\"\n              call: \"salesforce-rest.create-record\"\n              with:\n                sobjectType: \"rest.sobjectType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sobjects/{sobjectType}/describe\n          name: sobject-describe\n          description: \"Full SObject type metadata.\"\n          operations:\n            - method: GET\n              name: full-describe-sobject\n              description: \"Get full metadata for an SObject type including all fields.\"\n              call: \"salesforce-rest.full-describe-sobject\"\n              with:\n                sobjectType: \"rest.sobjectType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/records/{sobjectType}/{id}\n          name: records\n  \
  \        description: \"Individual record CRUD operations.\"\n          operations:\n            - method: GET\n              name: get-record\n              description: \"Get an SObject record by ID.\"\n              call: \"salesforce-rest.get-record\"\n              with:\n                sobjectType: \"rest.sobjectType\"\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-record\n              description: \"Update an SObject record.\"\n              call: \"salesforce-rest.update-record\"\n              with:\n                sobjectType: \"rest.sobjectType\"\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-record\n              description: \"Delete an SObject record.\"\n              call: \"salesforce-rest.delete-record\"\
  \n              with:\n                sobjectType: \"rest.sobjectType\"\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/queries\n          name: queries\n          description: \"SOQL query execution.\"\n          operations:\n            - method: POST\n              name: execute-query\n              description: \"Execute a SOQL query.\"\n              call: \"salesforce-rest.execute-query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: execute-query-all\n              path: /all\n              description: \"Execute a SOQL queryAll including deleted records.\"\n              call: \"salesforce-rest.execute-query-all\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/queries/{queryId}\n          name: query-pagination\n\
  \          description: \"Query result pagination.\"\n          operations:\n            - method: GET\n              name: get-next-query-page\n              description: \"Get the next page of query results.\"\n              call: \"salesforce-rest.get-next-query-page\"\n              with:\n                queryId: \"rest.queryId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/searches\n          name: searches\n          description: \"SOSL search execution.\"\n          operations:\n            - method: GET\n              name: execute-search\n              description: \"Execute a SOSL search across multiple objects.\"\n              call: \"salesforce-rest.execute-search\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/limits\n          name: limits\n          description: \"Org API limits.\"\n          operations:\n            - method:\
  \ GET\n              name: get-org-limits\n              description: \"Get current API limit usage and quotas.\"\n              call: \"salesforce-rest.get-org-limits\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/recent\n          name: recent\n          description: \"Recently viewed records.\"\n          operations:\n            - method: GET\n              name: get-recently-viewed\n              description: \"Get recently viewed records.\"\n              call: \"salesforce-rest.get-recently-viewed-records\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/collections\n          name: collections\n          description: \"SObject Collections bulk CRUD.\"\n          operations:\n            - method: POST\n              name: collections-create\n              description: \"Create up to 200 records in a single call.\"\n              call:\
  \ \"salesforce-rest.collections-create\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: collections-update\n              description: \"Update up to 200 records in a single call.\"\n              call: \"salesforce-rest.collections-update\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: collections-delete\n              description: \"Delete up to 200 records in a single call.\"\n              call: \"salesforce-rest.collections-delete\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/composite\n          name: composite\n          description: \"Composite request operations.\"\n          operations:\n            - method: POST\n              name: execute-composite\n              description: \"Execute a composite\
  \ request with dependent subrequests.\"\n              call: \"salesforce-rest.execute-composite-request\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: execute-batch\n              path: /batch\n              description: \"Execute a batch of independent requests.\"\n              call: \"salesforce-rest.execute-batch-request\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ingest-jobs\n          name: ingest-jobs\n          description: \"Bulk API 2.0 ingest job management.\"\n          operations:\n            - method: POST\n              name: create-ingest-job\n              description: \"Create a new bulk ingest job.\"\n              call: \"salesforce-bulk.create-ingest-job\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n\
  \              name: list-ingest-jobs\n              description: \"List bulk ingest jobs.\"\n              call: \"salesforce-bulk.list-ingest-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ingest-jobs/{jobId}\n          name: ingest-job\n          description: \"Individual ingest job operations.\"\n          operations:\n            - method: GET\n              name: get-ingest-job-info\n              description: \"Get detailed information about an ingest job.\"\n              call: \"salesforce-bulk.get-ingest-job-info\"\n              with:\n                jobId: \"rest.jobId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-ingest-job\n              description: \"Update or close an ingest job.\"\n              call: \"salesforce-bulk.update-ingest-job\"\n              with:\n               \
  \ jobId: \"rest.jobId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-ingest-job\n              description: \"Delete an ingest job.\"\n              call: \"salesforce-bulk.delete-ingest-job\"\n              with:\n                jobId: \"rest.jobId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ingest-jobs/{jobId}/results/successful\n          name: ingest-job-successful\n          description: \"Successful ingest results.\"\n          operations:\n            - method: GET\n              name: get-successful-results\n              description: \"Get successfully processed records.\"\n              call: \"salesforce-bulk.get-successful-results\"\n              with:\n                jobId: \"rest.jobId\"\n              outputParameters:\n                - type: object\n                  mapping: \"\
  $.\"\n        - path: /v1/ingest-jobs/{jobId}/results/failed\n          name: ingest-job-failed\n          description: \"Failed ingest results.\"\n          operations:\n            - method: GET\n              name: get-failed-results\n              description: \"Get failed records.\"\n              call: \"salesforce-bulk.get-failed-results\"\n              with:\n                jobId: \"rest.jobId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/query-jobs\n          name: query-jobs\n          description: \"Bulk API 2.0 query job management.\"\n          operations:\n            - method: POST\n              name: create-query-job\n              description: \"Create a new bulk query job.\"\n              call: \"salesforce-bulk.create-query-job\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-query-jobs\n\
  \              description: \"List bulk query jobs.\"\n              call: \"salesforce-bulk.list-query-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/query-jobs/{jobId}\n          name: query-job\n          description: \"Individual query job operations.\"\n          operations:\n            - method: GET\n              name: get-query-job-info\n              description: \"Get detailed information about a query job.\"\n              call: \"salesforce-bulk.get-query-job-info\"\n              with:\n                jobId: \"rest.jobId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-query-job\n              description: \"Delete a query job.\"\n              call: \"salesforce-bulk.delete-query-job\"\n              with:\n                jobId: \"rest.jobId\"\n              outputParameters:\n  \
  \              - type: object\n                  mapping: \"$.\"\n        - path: /v1/query-jobs/{jobId}/results\n          name: query-job-results\n          description: \"Query job results.\"\n          operations:\n            - method: GET\n              name: get-query-job-results\n              description: \"Get query job results.\"\n              call: \"salesforce-bulk.get-query-job-results\"\n              with:\n                jobId: \"rest.jobId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/object-info/{objectApiName}\n          name: object-info\n          description: \"Object metadata from UI API.\"\n          operations:\n            - method: GET\n              name: get-object-info\n              description: \"Get object metadata including fields, types, and permissions.\"\n              call: \"salesforce-ui.get-object-info\"\n              with:\n                objectApiName: \"rest.objectApiName\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/list-views/{objectApiName}\n          name: list-views\n          description: \"List views for objects.\"\n          operations:\n            - method: GET\n              name: get-list-views\n              description: \"Get list views for an object.\"\n              call: \"salesforce-ui.get-lists-by-object\"\n              with:\n                objectApiName: \"rest.objectApiName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: crm-data-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Salesforce CRM data management.\"\n      tools:\n        - name: list-sobjects\n          description: \"List all SObject types available in the Salesforce org.\"\n          hints:\n            readOnly: true\n            idempotent: true\n\
  \          call: \"salesforce-rest.list-sobjects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-sobject\n          description: \"Get basic metadata for a Salesforce SObject type.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-rest.describe-sobject\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: full-describe-sobject\n          description: \"Get full metadata for a Salesforce SObject type including all fields.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-rest.full-describe-sobject\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-record\n          description: \"Create a new SObject record in Salesforce.\"\n          hints:\n            readOnly: false\n            idempotent:\
  \ false\n          call: \"salesforce-rest.create-record\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-record\n          description: \"Get a Salesforce SObject record by ID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-rest.get-record\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-record\n          description: \"Update fields on a Salesforce SObject record.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"salesforce-rest.update-record\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-record\n          description: \"Delete a Salesforce SObject record.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"salesforce-rest.delete-record\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: execute-query\n          description: \"Execute a SOQL query against Salesforce data.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-rest.execute-query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: execute-query-all\n          description: \"Execute a SOQL queryAll including deleted and archived records.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-rest.execute-query-all\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-next-query-page\n          description: \"Get the next page of SOQL query results.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-rest.get-next-query-page\"\n    \
  \      outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: execute-search\n          description: \"Execute a SOSL search across multiple Salesforce objects.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-rest.execute-search\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-org-limits\n          description: \"Get current API limit usage and remaining quotas for the Salesforce org.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-rest.get-org-limits\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-recently-viewed\n          description: \"Get recently viewed records for the current user.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-rest.get-recently-viewed-records\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: collections-create\n          description: \"Create up to 200 SObject records in a single API call.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"salesforce-rest.collections-create\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: collections-update\n          description: \"Update up to 200 SObject records in a single API call.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"salesforce-rest.collections-update\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: collections-delete\n          description: \"Delete up to 200 SObject records in a single API call.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n \
  \         call: \"salesforce-rest.collections-delete\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: execute-composite\n          description: \"Execute a composite request with dependent subrequests.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"salesforce-rest.execute-composite-request\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: execute-batch\n          description: \"Execute a batch of independent REST API requests.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"salesforce-rest.execute-batch-request\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-ingest-job\n          description: \"Create a new Bulk API 2.0 ingest job for bulk data operations.\"\n          hints:\n            readOnly: false\n\
  \            idempotent: false\n          call: \"salesforce-bulk.create-ingest-job\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-ingest-jobs\n          description: \"List Bulk API 2.0 ingest jobs in the org.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-bulk.list-ingest-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-ingest-job-info\n          description: \"Get detailed information about a Bulk API 2.0 ingest job.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-bulk.get-ingest-job-info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-ingest-job\n          description: \"Update or close a Bulk API 2.0 ingest job.\"\n          hints:\n            readOnly: false\n     \
  \       idempotent: true\n          call: \"salesforce-bulk.update-ingest-job\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-ingest-job\n          description: \"Delete a Bulk API 2.0 ingest job.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"salesforce-bulk.delete-ingest-job\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-successful-results\n          description: \"Get successfully processed records from a bulk ingest job.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-bulk.get-successful-results\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-failed-results\n          description: \"Get failed records from a bulk ingest job.\"\n          hints:\n      \
  \      readOnly: true\n            idempotent: true\n          call: \"salesforce-bulk.get-failed-results\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-query-job\n          description: \"Create a new Bulk API 2.0 query job for extracting large data volumes.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"salesforce-bulk.create-query-job\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-query-jobs\n          description: \"List Bulk API 2.0 query jobs in the org.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-bulk.list-query-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-query-job-info\n          description: \"Get detailed information about a Bulk API 2.0 query job.\"\n         \
  \ hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-bulk.get-query-job-info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-query-job-results\n          description: \"Get results from a completed bulk query job.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-bulk.get-query-job-results\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-object-info\n          description: \"Get UI-ready metadata about a Salesforce object including fields, types, and permissions.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-ui.get-object-info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-picklist-values\n          description: \"Get picklist values for all\
  \ picklist fields on an object for a given record type.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-ui.get-picklist-values\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-list-views\n          description: \"Get list views for a Salesforce object.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-ui.get-lists-by-object\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-lookup-records\n          description: \"Search lookup field records for typeahead suggestions.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-ui.get-lookup-records\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/salesforce/refs/heads/main/capabilities/crm-data-management.yaml
tags:
- Salesforce
- CRM
- Data Management
- SObjects
- Bulk Operations
tools:
- description: List all SObject types available in the Salesforce org.
  hints:
    idempotent: true
    readOnly: true
  name: list-sobjects
- description: Get basic metadata for a Salesforce SObject type.
  hints:
    idempotent: true
    readOnly: true
  name: describe-sobject
- description: Get full metadata for a Salesforce SObject type including all fields.
  hints:
    idempotent: true
    readOnly: true
  name: full-describe-sobject
- description: Create a new SObject record in Salesforce.
  hints:
    idempotent: false
    readOnly: false
  name: create-record
- description: Get a Salesforce SObject record by ID.
  hints:
    idempotent: true
    readOnly: true
  name: get-record
- description: Update fields on a Salesforce SObject record.
  hints:
    idempotent: true
    readOnly: false
  name: update-record
- description: Delete a Salesforce SObject record.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-record
- description: Execute a SOQL query against Salesforce data.
  hints:
    idempotent: true
    readOnly: true
  name: execute-query
- description: Execute a SOQL queryAll including deleted and archived records.
  hints:
    idempotent: true
    readOnly: true
  name: execute-query-all
- description: Get the next page of SOQL query results.
  hints:
    idempotent: true
    readOnly: true
  name: get-next-query-page
- description: Execute a SOSL search across multiple Salesforce objects.
  hints:
    idempotent: true
    readOnly: true
  name: execute-search
- description: Get current API limit usage and remaining quotas for the Salesforce org.
  hints:
    idempotent: true
    readOnly: true
  name: get-org-limits
- description: Get recently viewed records for the current user.
  hints:
    idempotent: true
    readOnly: true
  name: get-recently-viewed
- description: Create up to 200 SObject records in a single API call.
  hints:
    idempotent: false
    readOnly: false
  name: collections-create
- description: Update up to 200 SObject records in a single API call.
  hints:
    idempotent: true
    readOnly: false
  name: collections-update
- description: Delete up to 200 SObject records in a single API call.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: collections-delete
- description: Execute a composite request with dependent subrequests.
  hints:
    idempotent: false
    readOnly: false
  name: execute-composite
- description: Execute a batch of independent REST API requests.
  hints:
    idempotent: false
    readOnly: false
  name: execute-batch
- description: Create a new Bulk API 2.0 ingest job for bulk data operations.
  hints:
    idempotent: false
    readOnly: false
  name: create-ingest-job
- description: List Bulk API 2.0 ingest jobs in the org.
  hints:
    idempotent: true
    readOnly: true
  name: list-ingest-jobs
- description: Get detailed information about a Bulk API 2.0 ingest job.
  hints:
    idempotent: true
    readOnly: true
  name: get-ingest-job-info
- description: Update or close a Bulk API 2.0 ingest job.
  hints:
    idempotent: true
    readOnly: false
  name: update-ingest-job
- description: Delete a Bulk API 2.0 ingest job.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-ingest-job
- description: Get successfully processed records from a bulk ingest job.
  hints:
    idempotent: true
    readOnly: true
  name: get-successful-results
- description: Get failed records from a bulk ingest job.
  hints:
    idempotent: true
    readOnly: true
  name: get-failed-results
- description: Create a new Bulk API 2.0 query job for extracting large data volumes.
  hints:
    idempotent: false
    readOnly: false
  name: create-query-job
- description: List Bulk API 2.0 query jobs in the org.
  hints:
    idempotent: true
    readOnly: true
  name: list-query-jobs
- description: Get detailed information about a Bulk API 2.0 query job.
  hints:
    idempotent: true
    readOnly: true
  name: get-query-job-info
- description: Get results from a completed bulk query job.
  hints:
    idempotent: true
    readOnly: true
  name: get-query-job-results
- description: Get UI-ready metadata about a Salesforce object including fields, types, and permissions.
  hints:
    idempotent: true
    readOnly: true
  name: get-object-info
- description: Get picklist values for all picklist fields on an object for a given record type.
  hints:
    idempotent: true
    readOnly: true
  name: get-picklist-values
- description: Get list views for a Salesforce object.
  hints:
    idempotent: true
    readOnly: true
  name: get-list-views
- description: Search lookup field records for typeahead suggestions.
  hints:
    idempotent: true
    readOnly: true
  name: get-lookup-records
---
