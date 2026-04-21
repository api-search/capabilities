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
- data operations
- create bulk ingest job
- builds integrations between salesforce and external systems.
- describe salesforce sobjects
- flows, process automation, and approval management.
- query salesforce data
- create salesforce record
- manages sales processes, reports, and pipeline.
- enterprise
- sosl search.
- create a new record in salesforce.
- create bulk query job
- create a new bulk ingest job.
- create ingest job
- bulk data operations.
- describe all available sobjects in the salesforce org.
- execute search
- integration
- real-time event streaming and change data capture.
- list ingest jobs
- create a bulk query job for large result sets.
- execute a sosl search across salesforce.
- automation
- soql query execution.
- sobject metadata and describe.
- create a bulk data ingest job for large datasets.
- describe all available sobjects.
- Integration Developer
- execute query
- describe all
- create a new record.
- crm
- execute a sosl search.
- list bulk ingest jobs
- submit a record for approval in salesforce.
- crud operations and data queries.
- cloud
- sales
- salesforce
- bulk data loading and external system integration.
- search salesforce data
- manages salesforce configuration, data, and automation.
- submit salesforce approval
- execute a soql query.
- record crud operations.
- crud, queries, search, and bulk data operations.
- list all bulk ingest jobs.
- execute a soql query against salesforce data.
- Salesforce Admin
- create record
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
