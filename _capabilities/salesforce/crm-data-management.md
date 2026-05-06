---
categories:
- crm-sales
consumed_apis: []
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
- get detailed information about a bulk api 2.0 query job.
- get ui-ready metadata about a salesforce object including fields, types, and permissions.
- list bulk api 2.0 ingest jobs in the org.
- get query job results
- get query job results.
- get detailed information about a bulk api 2.0 ingest job.
- create a new bulk query job.
- sobjects
- successful ingest results.
- analytics
- individual record crud operations.
- execute composite
- get record
- create a new bulk api 2.0 query job for extracting large data volumes.
- execute a batch of independent requests.
- cloud
- object metadata from ui api.
- get basic metadata for a salesforce sobject type.
- data management
- delete a query job.
- get detailed information about a query job.
- list bulk query jobs.
- sosl search execution.
- get recently viewed records for the current user.
- execute search
- create a new sobject record in salesforce.
- delete up to 200 records in a single call.
- individual query job operations.
- get list views
- list all sobject types available in the org.
- get successfully processed records.
- get the next page of query results.
- bulk api 2.0 ingest job management.
- get org limits
- get recently viewed
- get results from a completed bulk query job.
- sobject collections bulk crud.
- update up to 200 records in a single call.
- create up to 200 records in a single call.
- update ingest job
- get list views for an object.
- recently viewed records.
- create a new sobject record.
- search lookup field records for typeahead suggestions.
- full describe sobject
- ai
- bulk api 2.0 query job management.
- delete up to 200 sobject records in a single api call.
- crm
- list views for objects.
- get picklist values for all picklist fields on an object for a given record type.
- get ingest job info
- create up to 200 sobject records in a single api call.
- create record
- execute a sosl search across multiple salesforce objects.
- get the next page of soql query results.
- get detailed information about an ingest job.
- get next query page
- describe sobject
- get object info
- execute a soql query against salesforce data.
- get recently viewed records.
- get failed results
- get picklist values
- failed ingest results.
- create a new bulk api 2.0 ingest job for bulk data operations.
- delete record
- execute a sosl search across multiple objects.
- sobject type listing and metadata.
- create ingest job
- full sobject type metadata.
- update up to 200 sobject records in a single api call.
- composite request operations.
- execute a composite request with dependent subrequests.
- query result pagination.
- collections create
- list sobjects
- get failed records from a bulk ingest job.
- delete a bulk api 2.0 ingest job.
- commerce
- org api limits.
- soql query execution.
- execute a soql query.
- get current api limit usage and remaining quotas for the salesforce org.
- update or close an ingest job.
- sobject type metadata and record creation.
- get list views for a salesforce object.
- create a new bulk ingest job.
- get lookup records
- get successful results
- bulk operations
- get basic metadata for an sobject type.
- get current api limit usage and quotas.
- update fields on a salesforce sobject record.
- delete an ingest job.
- create query job
- delete query job
- list ingest jobs
- list bulk ingest jobs.
- query job results.
- delete a salesforce sobject record.
- individual ingest job operations.
- sales
- update an sobject record.
- list all sobject types available in the salesforce org.
- get failed records.
- marketing
- update record
- list bulk api 2.0 query jobs in the org.
- execute a soql queryall including deleted and archived records.
- get full metadata for a salesforce sobject type including all fields.
- execute query
- collections update
- enterprise
- get full metadata for an sobject type including all fields.
- get object metadata including fields, types, and permissions.
- execute a soql queryall including deleted records.
- get query job info
- delete ingest job
- update or close a bulk api 2.0 ingest job.
- get an sobject record by id.
- execute query all
- delete an sobject record.
- execute batch
- collections delete
- get successfully processed records from a bulk ingest job.
- execute a batch of independent rest api requests.
- platform
- customer service
- get a salesforce sobject record by id.
- list query jobs
- salesforce
slug: crm-data-management
source_filename: crm-data-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Salesforce CRM Data Management\n  description: Unified capability for CRM data management workflows combining the REST API, Bulk API 2.0, and UI API. Used\n    by Salesforce admins, developers, and data teams to manage SObject records, run queries, perform bulk data operations,\n    and build dynamic UIs.\n  tags:\n  - Salesforce\n  - CRM\n  - Data Management\n  - SObjects\n  - Bulk Operations\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SALESFORCE_ACCESS_TOKEN: SALESFORCE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: salesforce-rest\n    baseUri: https://{instance}.salesforce.com/services/data/v63.0\n    description: Salesforce REST API for SObject CRUD, SOQL queries, SOSL searches, composite requests, and org limits.\n    authentication:\n      type: bearer\n      token: '{{SALESFORCE_ACCESS_TOKEN}}'\n    resources:\n    - name: versions\n      path: /\n      description:\
  \ API version information.\n      operations:\n      - name: list-api-versions\n        method: GET\n        path: /\n        description: List available Salesforce REST API versions.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sobjects\n      path: /sobjects\n      description: SObject CRUD and metadata operations.\n      operations:\n      - name: list-sobjects\n        method: GET\n        path: /\n        description: List all SObject types available in the org.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-sobject\n        method: GET\n        path: /{sobjectType}\n        description: Get basic metadata for an SObject type.\n        inputParameters:\n        - name: sobjectType\n          in: path\n          type: string\n  \
  \        required: true\n          description: The SObject type API name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: full-describe-sobject\n        method: GET\n        path: /{sobjectType}/describe\n        description: Get full metadata for an SObject type including all fields.\n        inputParameters:\n        - name: sobjectType\n          in: path\n          type: string\n          required: true\n          description: The SObject type API name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-record\n        method: POST\n        path: /{sobjectType}\n        description: Create a new SObject record.\n        inputParameters:\n        - name: sobjectType\n          in: path\n          type: string\n          required: true\n          description: The SObject type API name.\n      \
  \  outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            fields: '{{tools.fields}}'\n      - name: get-record\n        method: GET\n        path: /{sobjectType}/{id}\n        description: Get an SObject record by ID.\n        inputParameters:\n        - name: sobjectType\n          in: path\n          type: string\n          required: true\n          description: The SObject type API name.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The 18-character record ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-record\n        method: PATCH\n        path: /{sobjectType}/{id}\n        description: Update an SObject record.\n        inputParameters:\n        - name: sobjectType\n          in: path\n\
  \          type: string\n          required: true\n          description: The SObject type API name.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The 18-character record ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            fields: '{{tools.fields}}'\n      - name: delete-record\n        method: DELETE\n        path: /{sobjectType}/{id}\n        description: Delete an SObject record.\n        inputParameters:\n        - name: sobjectType\n          in: path\n          type: string\n          required: true\n          description: The SObject type API name.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The 18-character record ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: get-blob-field\n        method: GET\n        path: /{sobjectType}/{id}/{blobField}\n        description: Get binary content of a blob field on an SObject record.\n        inputParameters:\n        - name: sobjectType\n          in: path\n          type: string\n          required: true\n          description: The SObject type API name.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The 18-character record ID.\n        - name: blobField\n          in: path\n          type: string\n          required: true\n          description: The blob field API name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: query\n      path: /\n      description: SOQL query operations.\n      operations:\n      - name: execute-query\n        method: POST\n        path: /query\n        description:\
  \ Execute a SOQL query.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            q: '{{tools.q}}'\n      - name: get-next-query-page\n        method: GET\n        path: /query/{queryId}\n        description: Get the next page of query results.\n        inputParameters:\n        - name: queryId\n          in: path\n          type: string\n          required: true\n          description: The query ID token from nextRecordsUrl.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: execute-query-all\n        method: POST\n        path: /queryAll\n        description: Execute a SOQL queryAll including deleted and archived records.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            q: '{{tools.q}}'\n    - name: search\n      path: /\n      description: SOSL search operations.\n      operations:\n      - name: execute-search\n        method: GET\n        path: /search\n        description: Execute a SOSL search across multiple objects.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: The SOSL search string.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: limits\n      path: /\n      description: Org limit operations.\n      operations:\n      - name: get-org-limits\n        method: GET\n        path: /limits\n        description: Get current API limit usage and quotas for the org.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n      \
  \  - name: result\n          type: object\n          value: $.\n    - name: recent\n      path: /\n      description: Recently viewed records.\n      operations:\n      - name: get-recently-viewed-records\n        method: GET\n        path: /recent\n        description: Get recently viewed records for the current user.\n        inputParameters:\n        - name: recentlyViewedCount\n          in: query\n          type: integer\n          required: false\n          description: Number of recently viewed records to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: app-menu\n      path: /\n      description: App menu operations.\n      operations:\n      - name: get-app-switcher-menu\n        method: GET\n        path: /appMenu/AppSwitcher\n        description: Get the app switcher menu items.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: composite\n      path: /composite\n      description: Composite and batch request operations.\n      operations:\n      - name: execute-batch-request\n        method: POST\n        path: /batch\n        description: Execute a batch of up to 25 independent requests.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            batchRequests: '{{tools.batch_requests}}'\n      - name: execute-composite-request\n        method: POST\n        path: /\n        description: Execute a composite request with dependent subrequests.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            compositeRequest: '{{tools.composite_request}}'\n\
  \      - name: collections-create\n        method: POST\n        path: /sobjects\n        description: Create up to 200 records in a single call.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            records: '{{tools.records}}'\n      - name: collections-update\n        method: PATCH\n        path: /sobjects\n        description: Update up to 200 records in a single call.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            records: '{{tools.records}}'\n      - name: collections-delete\n        method: DELETE\n        path: /sobjects\n        description: Delete up to 200 records in a single call.\n        inputParameters:\n        - name: ids\n      \
  \    in: query\n          type: string\n          required: true\n          description: Comma-separated list of record IDs to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: collections-retrieve\n        method: GET\n        path: /sobjects/{sobjectType}\n        description: Retrieve up to 2000 records of the same type.\n        inputParameters:\n        - name: sobjectType\n          in: path\n          type: string\n          required: true\n          description: The SObject type API name.\n        - name: ids\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of record IDs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: salesforce-bulk\n    baseUri: https://{instance}.salesforce.com/services/data/v63.0/jobs\n\
  \    description: Salesforce Bulk API 2.0 for asynchronous bulk data ingest and query operations.\n    authentication:\n      type: bearer\n      token: '{{SALESFORCE_ACCESS_TOKEN}}'\n    resources:\n    - name: ingest-jobs\n      path: /ingest\n      description: Ingest job management operations.\n      operations:\n      - name: create-ingest-job\n        method: POST\n        path: /\n        description: Create a new ingest job for bulk data operations.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            operation: '{{tools.operation}}'\n            object: '{{tools.object}}'\n      - name: list-ingest-jobs\n        method: GET\n        path: /\n        description: List ingest jobs in the org.\n        inputParameters:\n        - name: jobType\n          in: query\n          type: string\n          required: false\n\
  \          description: Filter by job type (Classic or V2Ingest).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-ingest-job-info\n        method: GET\n        path: /{jobId}\n        description: Get detailed information about a specific ingest job.\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: The ingest job ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-ingest-job\n        method: PATCH\n        path: /{jobId}\n        description: Update or close an ingest job.\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: The ingest job ID.\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            state: '{{tools.state}}'\n      - name: delete-ingest-job\n        method: DELETE\n        path: /{jobId}\n        description: Delete an ingest job.\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: The ingest job ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: upload-job-data\n        method: PUT\n        path: /{jobId}/batches\n        description: Upload CSV data to an ingest job.\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: The ingest job ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \     - name: get-successful-results\n        method: GET\n        path: /{jobId}/successfulResults\n        description: Get successfully processed records from an ingest job.\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: The ingest job ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-failed-results\n        method: GET\n        path: /{jobId}/failedResults\n        description: Get failed records from an ingest job.\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: The ingest job ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-unprocessed-records\n        method: GET\n        path: /{jobId}/unprocessedrecords\n\
  \        description: Get unprocessed records from an ingest job.\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: The ingest job ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: query-jobs\n      path: /query\n      description: Query job management operations.\n      operations:\n      - name: create-query-job\n        method: POST\n        path: /\n        description: Create a new query job to extract data using SOQL.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            operation: '{{tools.operation}}'\n            query: '{{tools.query}}'\n      - name: list-query-jobs\n        method: GET\n        path: /\n        description:\
  \ List query jobs in the org.\n        inputParameters:\n        - name: jobType\n          in: query\n          type: string\n          required: false\n          description: Filter by job type.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-query-job-info\n        method: GET\n        path: /{jobId}\n        description: Get detailed information about a specific query job.\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: The query job ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-query-job\n        method: PATCH\n        path: /{jobId}\n        description: Abort or close a query job.\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required:\
  \ true\n          description: The query job ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            state: '{{tools.state}}'\n      - name: delete-query-job\n        method: DELETE\n        path: /{jobId}\n        description: Delete a query job.\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: The query job ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-query-job-results\n        method: GET\n        path: /{jobId}/results\n        description: Get query job results as CSV data.\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: The query job ID.\n        - name:\
  \ maxRecords\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of records to return.\n        - name: locator\n          in: query\n          type: string\n          required: false\n          description: Locator token for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: salesforce-ui\n    baseUri: https://{instanceName}.salesforce.com/services/data/v59.0/ui-api\n    description: Salesforce UI API for records, object metadata, picklist values, list views, and lookups.\n    authentication:\n      type: bearer\n      token: '{{SALESFORCE_ACCESS_TOKEN}}'\n    resources:\n    - name: records\n      path: /records\n      description: Record CRUD operations with UI metadata.\n      operations:\n      - name: get-record\n        method: GET\n        path: /{recordId}\n        description: Get a record with field\
  \ values formatted for UI display.\n        inputParameters:\n        - name: recordId\n          in: path\n          type: string\n          required: true\n          description: The 18-character Salesforce record ID.\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of field API names.\n        - name: layoutTypes\n          in: query\n          type: string\n          required: false\n          description: Layout types (Full, Compact).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-record\n        method: POST\n        path: /\n        description: Create a new Salesforce record.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n   \
  \         apiName: '{{tools.api_name}}'\n            fields: '{{tools.fields}}'\n      - name: update-record\n        method: PATCH\n        path: /{recordId}\n        description: Update fields on a Salesforce record.\n        inputParameters:\n        - name: recordId\n          in: path\n          type: string\n          required: true\n          description: The 18-character Salesforce record ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            fields: '{{tools.fields}}'\n      - name: delete-record\n        method: DELETE\n        path: /{recordId}\n        description: Delete a Salesforce record.\n        inputParameters:\n        - name: recordId\n          in: path\n          type: string\n          required: true\n          description: The 18-character Salesforce record ID.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: object-info\n      path: /object-info\n      description: Object metadata operations.\n      operations:\n      - name: get-object-info\n        method: GET\n        path: /{objectApiName}\n        description: Get metadata about a Salesforce object including fields, types, and permissions.\n        inputParameters:\n        - name: objectApiName\n          in: path\n          type: string\n          required: true\n          description: The object API name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-picklist-values\n        method: GET\n        path: /{objectApiName}/picklist-values/{recordTypeId}\n        description: Get picklist values for all picklist fields on an object.\n        inputParameters:\n        - name: objectApiName\n          in: path\n          type: string\n          required: true\n\
  \          description: The object API name.\n        - name: recordTypeId\n          in: path\n          type: string\n          required: true\n          description: The record type ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: list-views\n      path: /list-ui\n      description: List view operations.\n      operations:\n      - name: get-lists-by-object\n        method: GET\n        path: /{objectApiName}\n        description: Get list views for an object.\n        inputParameters:\n        - name: objectApiName\n          in: path\n          type: string\n          required: true\n          description: The object API name.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of records per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n      - name: get-list-view\n        method: GET\n        path: /{objectApiName}/{listViewApiName}\n        description: Get a specific list view.\n        inputParameters:\n        - name: objectApiName\n          in: path\n          type: string\n          required: true\n          description: The object API name.\n        - name: listViewApiName\n          in: path\n          type: string\n          required: true\n          description: The list view API name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lookups\n      path: /lookups\n      description: Lookup field search operations.\n      operations:\n      - name: get-lookup-records\n        method: GET\n        path: /{objectApiName}/{fieldApiName}\n        description: Search lookup field records for typeahead.\n        inputParameters:\n        - name: objectApiName\n          in: path\n          type: string\n   \
  \       required: true\n          description: The object API name.\n        - name: fieldApiName\n          in: path\n          type: string\n          required: true\n          description: The lookup field API name.\n        - name: searchTerm\n          in: query\n          type: string\n          required: true\n          description: The search text.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: crm-data-management-api\n    description: Unified REST API for Salesforce CRM data management.\n    resources:\n    - path: /v1/sobjects\n      name: sobjects\n      description: SObject type listing and metadata.\n      operations:\n      - method: GET\n        name: list-sobjects\n        description: List all SObject types available in the org.\n        call: salesforce-rest.list-sobjects\n        outputParameters:\n        - type: object\n      \
  \    mapping: $.\n    - path: /v1/sobjects/{sobjectType}\n      name: sobject-type\n      description: SObject type metadata and record creation.\n      operations:\n      - method: GET\n        name: describe-sobject\n        description: Get basic metadata for an SObject type.\n        call: salesforce-rest.describe-sobject\n        with:\n          sobjectType: rest.sobjectType\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-record\n        description: Create a new SObject record.\n        call: salesforce-rest.create-record\n        with:\n          sobjectType: rest.sobjectType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sobjects/{sobjectType}/describe\n      name: sobject-describe\n      description: Full SObject type metadata.\n      operations:\n      - method: GET\n        name: full-describe-sobject\n        description: Get full metadata for an SObject type including\
  \ all fields.\n        call: salesforce-rest.full-describe-sobject\n        with:\n          sobjectType: rest.sobjectType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/records/{sobjectType}/{id}\n      name: records\n      description: Individual record CRUD operations.\n      operations:\n      - method: GET\n        name: get-record\n        description: Get an SObject record by ID.\n        call: salesforce-rest.get-record\n        with:\n          sobjectType: rest.sobjectType\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-record\n        description: Update an SObject record.\n        call: salesforce-rest.update-record\n        with:\n          sobjectType: rest.sobjectType\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-record\n        description:\
  \ Delete an SObject record.\n        call: salesforce-rest.delete-record\n        with:\n          sobjectType: rest.sobjectType\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/queries\n      name: queries\n      description: SOQL query execution.\n      operations:\n      - method: POST\n        name: execute-query\n        description: Execute a SOQL query.\n        call: salesforce-rest.execute-query\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: execute-query-all\n        path: /all\n        description: Execute a SOQL queryAll including deleted records.\n        call: salesforce-rest.execute-query-all\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/queries/{queryId}\n      name: query-pagination\n      description: Query result pagination.\n      operations:\n      - method: GET\n        name: get-next-query-page\n\
  \        description: Get the next page of query results.\n        call: salesforce-rest.get-next-query-page\n        with:\n          queryId: rest.queryId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/searches\n      name: searches\n      description: SOSL search execution.\n      operations:\n      - method: GET\n        name: execute-search\n        description: Execute a SOSL search across multiple objects.\n        call: salesforce-rest.execute-search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/limits\n      name: limits\n      description: Org API limits.\n      operations:\n      - method: GET\n        name: get-org-limits\n        description: Get current API limit usage and quotas.\n        call: salesforce-rest.get-org-limits\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/recent\n      name: recent\n      description: Recently viewed records.\n\
  \      operations:\n      - method: GET\n        name: get-recently-viewed\n        description: Get recently viewed records.\n        call: salesforce-rest.get-recently-viewed-records\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/collections\n      name: collections\n      description: SObject Collections bulk CRUD.\n      operations:\n      - method: POST\n        name: collections-create\n        description: Create up to 200 records in a single call.\n        call: salesforce-rest.collections-create\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: collections-update\n        description: Update up to 200 records in a single call.\n        call: salesforce-rest.collections-update\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: collections-delete\n        description: Delete up to 200 records in a single call.\n \
  \       call: salesforce-rest.collections-delete\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/composite\n      name: composite\n      description: Composite request operations.\n      operations:\n      - method: POST\n        name: execute-composite\n        description: Execute a composite request with dependent subrequests.\n        call: salesforce-rest.execute-composite-request\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: execute-batch\n        path: /batch\n        description: Execute a batch of independent requests.\n        call: salesforce-rest.execute-batch-request\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ingest-jobs\n      name: ingest-jobs\n      description: Bulk API 2.0 ingest job management.\n      operations:\n      - method: POST\n        name: create-ingest-job\n        description: Create a new bulk ingest\
  \ job.\n        call: salesforce-bulk.create-ingest-job\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-ingest-jobs\n        description: List bulk ingest jobs.\n        call: salesforce-bulk.list-ingest-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ingest-jobs/{jobId}\n      name: ingest-job\n      description: Individual ingest job operations.\n      operations:\n      - method: GET\n        name: get-ingest-job-info\n        description: Get detailed information about an ingest job.\n        call: salesforce-bulk.get-ingest-job-info\n        with:\n          jobId: rest.jobId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-ingest-job\n        description: Update or close an ingest job.\n        call: salesforce-bulk.update-ingest-job\n        with:\n          jobId: rest.jobId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-ingest-job\n        description: Delete an ingest job.\n        call: salesforce-bulk.delete-ingest-job\n        with:\n          jobId: rest.jobId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ingest-jobs/{jobId}/results/successful\n      name: ingest-job-successful\n      description: Successful ingest results.\n      operations:\n      - method: GET\n        name: get-successful-results\n        description: Get successfully processed records.\n        call: salesforce-bulk.get-successful-results\n        with:\n          jobId: rest.jobId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ingest-jobs/{jobId}/results/failed\n      name: ingest-job-failed\n \n\n# --- truncated at 32 KB (43 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/salesforce/refs/heads/main/capabilities/crm-data-management.yaml\n"
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
