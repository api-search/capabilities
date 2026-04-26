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
- execute batch
- collections create
- update up to 200 sobject records in a single api call.
- search lookup field records for typeahead suggestions.
- delete ingest job
- create a new sobject record.
- get list views
- list bulk query jobs.
- recently viewed records.
- get query job results
- create query job
- list query jobs
- get failed records.
- get the next page of soql query results.
- get current api limit usage and quotas.
- get detailed information about a query job.
- get object info
- marketing
- create a new bulk api 2.0 query job for extracting large data volumes.
- get basic metadata for a salesforce sobject type.
- get successfully processed records.
- list bulk api 2.0 ingest jobs in the org.
- get next query page
- get list views for a salesforce object.
- get record
- object metadata from ui api.
- individual ingest job operations.
- sobjects
- execute a batch of independent requests.
- update or close a bulk api 2.0 ingest job.
- execute query all
- sales
- get detailed information about an ingest job.
- create a new bulk ingest job.
- crm
- create up to 200 records in a single call.
- get full metadata for an sobject type including all fields.
- get results from a completed bulk query job.
- bulk api 2.0 ingest job management.
- data management
- sobject collections bulk crud.
- delete up to 200 records in a single call.
- execute a composite request with dependent subrequests.
- execute a soql queryall including deleted and archived records.
- get successfully processed records from a bulk ingest job.
- get successful results
- delete a bulk api 2.0 ingest job.
- individual query job operations.
- collections update
- get object metadata including fields, types, and permissions.
- customer service
- platform
- get ui-ready metadata about a salesforce object including fields, types, and permissions.
- list sobjects
- delete a query job.
- sobject type metadata and record creation.
- update record
- update or close an ingest job.
- full describe sobject
- get basic metadata for an sobject type.
- get ingest job info
- get detailed information about a bulk api 2.0 ingest job.
- collections delete
- get recently viewed records.
- get lookup records
- soql query execution.
- delete up to 200 sobject records in a single api call.
- get failed results
- execute a soql query against salesforce data.
- execute composite
- query result pagination.
- create record
- composite request operations.
- query job results.
- create a new bulk api 2.0 ingest job for bulk data operations.
- create up to 200 sobject records in a single api call.
- list all sobject types available in the salesforce org.
- cloud
- execute a sosl search across multiple objects.
- delete a salesforce sobject record.
- full sobject type metadata.
- sobject type listing and metadata.
- get query job info
- update ingest job
- create ingest job
- ai
- salesforce
- get picklist values for all picklist fields on an object for a given record type.
- enterprise
- execute a soql query.
- delete record
- get failed records from a bulk ingest job.
- delete an ingest job.
- delete an sobject record.
- get the next page of query results.
- get recently viewed
- failed ingest results.
- commerce
- bulk operations
- get org limits
- analytics
- get an sobject record by id.
- get recently viewed records for the current user.
- org api limits.
- list bulk api 2.0 query jobs in the org.
- bulk api 2.0 query job management.
- get full metadata for a salesforce sobject type including all fields.
- get picklist values
- get list views for an object.
- list views for objects.
- execute query
- create a new bulk query job.
- individual record crud operations.
- list all sobject types available in the org.
- get a salesforce sobject record by id.
- get query job results.
- update an sobject record.
- execute a sosl search across multiple salesforce objects.
- delete query job
- update up to 200 records in a single call.
- update fields on a salesforce sobject record.
- list ingest jobs
- execute a soql queryall including deleted records.
- get current api limit usage and remaining quotas for the salesforce org.
- execute a batch of independent rest api requests.
- get detailed information about a bulk api 2.0 query job.
- sosl search execution.
- create a new sobject record in salesforce.
- describe sobject
- successful ingest results.
- list bulk ingest jobs.
- execute search
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
