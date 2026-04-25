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
- execute a sosl search.
- bulk data loading and external system integration.
- create a new bulk ingest job.
- execute a soql query.
- enterprise
- execute search
- Integration Developer
- real-time event streaming and change data capture.
- sales
- automation
- create salesforce record
- cloud
- search salesforce data
- integration
- execute a soql query against salesforce data.
- crud operations and data queries.
- create bulk ingest job
- query salesforce data
- Salesforce Admin
- describe all available sobjects in the salesforce org.
- flows, process automation, and approval management.
- create a bulk data ingest job for large datasets.
- salesforce
- crud, queries, search, and bulk data operations.
- create a new record in salesforce.
- create ingest job
- describe salesforce sobjects
- create a new record.
- data operations
- describe all available sobjects.
- submit a record for approval in salesforce.
- bulk data operations.
- list ingest jobs
- describe all
- sosl search.
- manages sales processes, reports, and pipeline.
- submit salesforce approval
- sobject metadata and describe.
- list all bulk ingest jobs.
- crm
- create bulk query job
- manages salesforce configuration, data, and automation.
- builds integrations between salesforce and external systems.
- create record
- record crud operations.
- create a bulk query job for large result sets.
- list bulk ingest jobs
- execute query
- execute a sosl search across salesforce.
- soql query execution.
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
