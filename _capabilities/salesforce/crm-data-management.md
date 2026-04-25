---
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
- get current api limit usage and remaining quotas for the salesforce org.
- get ui-ready metadata about a salesforce object including fields, types, and permissions.
- get picklist values for all picklist fields on an object for a given record type.
- org api limits.
- ai
- get lookup records
- get failed records.
- individual query job operations.
- describe sobject
- create a new bulk api 2.0 query job for extracting large data volumes.
- execute a soql query against salesforce data.
- get list views
- delete ingest job
- bulk api 2.0 query job management.
- individual record crud operations.
- get query job results.
- get full metadata for a salesforce sobject type including all fields.
- get list views for an object.
- update record
- update ingest job
- sobjects
- collections update
- delete query job
- full describe sobject
- get recently viewed
- collections create
- crm
- get detailed information about an ingest job.
- update fields on a salesforce sobject record.
- full sobject type metadata.
- update up to 200 records in a single call.
- soql query execution.
- list all sobject types available in the salesforce org.
- get successful results
- execute a soql query.
- sales
- execute a sosl search across multiple objects.
- get basic metadata for a salesforce sobject type.
- sosl search execution.
- execute batch
- get recently viewed records.
- delete a salesforce sobject record.
- list query jobs
- delete up to 200 records in a single call.
- failed ingest results.
- sobject type metadata and record creation.
- get detailed information about a bulk api 2.0 query job.
- get full metadata for an sobject type including all fields.
- get results from a completed bulk query job.
- update an sobject record.
- platform
- get query job results
- get object info
- update or close a bulk api 2.0 ingest job.
- list sobjects
- update up to 200 sobject records in a single api call.
- list bulk api 2.0 query jobs in the org.
- recently viewed records.
- collections delete
- get detailed information about a query job.
- create a new bulk api 2.0 ingest job for bulk data operations.
- get successfully processed records from a bulk ingest job.
- commerce
- delete a bulk api 2.0 ingest job.
- sobject type listing and metadata.
- delete a query job.
- get an sobject record by id.
- execute composite
- get a salesforce sobject record by id.
- create query job
- enterprise
- execute search
- create up to 200 sobject records in a single api call.
- list all sobject types available in the org.
- customer service
- search lookup field records for typeahead suggestions.
- cloud
- get recently viewed records for the current user.
- delete an ingest job.
- query job results.
- object metadata from ui api.
- marketing
- execute a batch of independent requests.
- get successfully processed records.
- salesforce
- query result pagination.
- sobject collections bulk crud.
- list bulk api 2.0 ingest jobs in the org.
- execute a composite request with dependent subrequests.
- execute a batch of independent rest api requests.
- get record
- update or close an ingest job.
- execute a soql queryall including deleted records.
- execute a soql queryall including deleted and archived records.
- create up to 200 records in a single call.
- create record
- analytics
- get failed records from a bulk ingest job.
- list views for objects.
- get query job info
- execute query
- get the next page of soql query results.
- successful ingest results.
- create a new bulk ingest job.
- get org limits
- get next query page
- list bulk ingest jobs.
- get failed results
- bulk api 2.0 ingest job management.
- delete record
- bulk operations
- delete an sobject record.
- get detailed information about a bulk api 2.0 ingest job.
- get current api limit usage and quotas.
- get the next page of query results.
- individual ingest job operations.
- get picklist values
- create a new sobject record.
- create ingest job
- list bulk query jobs.
- execute a sosl search across multiple salesforce objects.
- list ingest jobs
- create a new bulk query job.
- data management
- execute query all
- create a new sobject record in salesforce.
- get object metadata including fields, types, and permissions.
- get basic metadata for an sobject type.
- composite request operations.
- get list views for a salesforce object.
- get ingest job info
- delete up to 200 sobject records in a single api call.
slug: crm-data-management
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
