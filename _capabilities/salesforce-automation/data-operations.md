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
- bulk data operations.
- describe all available sobjects in the salesforce org.
- integration
- automation
- record crud operations.
- create a new record.
- sobject metadata and describe.
- crud operations and data queries.
- create a new bulk ingest job.
- execute a sosl search across salesforce.
- flows, process automation, and approval management.
- describe all
- real-time event streaming and change data capture.
- create a bulk data ingest job for large datasets.
- list bulk ingest jobs
- create record
- enterprise
- create ingest job
- manages salesforce configuration, data, and automation.
- Salesforce Admin
- manages sales processes, reports, and pipeline.
- sosl search.
- list all bulk ingest jobs.
- builds integrations between salesforce and external systems.
- search salesforce data
- data operations
- soql query execution.
- create salesforce record
- describe all available sobjects.
- bulk data loading and external system integration.
- execute search
- create a new record in salesforce.
- create a bulk query job for large result sets.
- create bulk query job
- crud, queries, search, and bulk data operations.
- execute query
- execute a sosl search.
- list ingest jobs
- query salesforce data
- submit a record for approval in salesforce.
- execute a soql query against salesforce data.
- sales
- salesforce
- Integration Developer
- describe salesforce sobjects
- crm
- submit salesforce approval
- create bulk ingest job
- execute a soql query.
- cloud
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
