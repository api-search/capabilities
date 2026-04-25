---
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
- record crud operations.
- create bulk query job
- bulk data loading and external system integration.
- crm
- salesforce
- query salesforce data
- crud operations and data queries.
- list bulk ingest jobs
- execute a sosl search across salesforce.
- integration
- bulk data operations.
- automation
- data operations
- crud, queries, search, and bulk data operations.
- sobject metadata and describe.
- execute a sosl search.
- submit a record for approval in salesforce.
- manages salesforce configuration, data, and automation.
- soql query execution.
- describe all available sobjects in the salesforce org.
- enterprise
- create bulk ingest job
- Salesforce Admin
- describe all
- execute search
- describe salesforce sobjects
- manages sales processes, reports, and pipeline.
- sosl search.
- execute a soql query.
- create salesforce record
- create a bulk query job for large result sets.
- create record
- create a new record.
- execute a soql query against salesforce data.
- submit salesforce approval
- flows, process automation, and approval management.
- builds integrations between salesforce and external systems.
- sales
- create ingest job
- create a new bulk ingest job.
- create a new record in salesforce.
- Integration Developer
- search salesforce data
- create a bulk data ingest job for large datasets.
- describe all available sobjects.
- execute query
- list all bulk ingest jobs.
- cloud
- list ingest jobs
- real-time event streaming and change data capture.
slug: data-operations
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
