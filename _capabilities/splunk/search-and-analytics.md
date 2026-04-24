---
consumed_apis:
- enterprise-rest
description: Unified search and analytics workflow combining SPL search, index management, data inputs, and HTTP Event Collector for SOC analysts, IT operations, and data engineers.
layout: capability
name: Splunk Search and Analytics
operations:
- description: List search jobs.
  method: GET
  name: list-search-jobs
  path: /v1/search-jobs
- description: Create a search job.
  method: POST
  name: create-search-job
  path: /v1/search-jobs
- description: List indexes.
  method: GET
  name: list-indexes
  path: /v1/indexes
- description: Create an index.
  method: POST
  name: create-index
  path: /v1/indexes
- description: Send an event.
  method: POST
  name: send-event
  path: /v1/events
personas: []
provider_name: Splunk
provider_slug: splunk
search_terms:
- observability
- data ingestion
- list search jobs
- index management.
- list http input tokens
- create monitor input
- logging
- search
- get search results
- create search job
- update index
- monitoring
- create a search job.
- search job management.
- event ingestion via hec.
- export search results
- update index settings.
- control search job
- analytics
- delete a search job.
- create http input token
- list indexes
- get search events
- send event
- get untransformed events from a search job.
- create a new spl search job.
- export search results directly without creating a job.
- send a json event via http event collector.
- list file monitor data inputs.
- list monitor inputs
- create an http event collector token.
- get search job
- delete an index.
- get search job status and details.
- get index
- data analysis
- machine data
- list current search jobs.
- list http event collector tokens.
- check ack status
- list all splunk indexes.
- send an event.
- get results from a completed search job.
- create index
- splunk
- list search jobs.
- delete search job
- control a search job (pause, unpause, finalize, cancel).
- delete index
- list indexes.
- create a file monitor data input.
- check hec indexing acknowledgment status.
- platform
- security
- siem
- create a new splunk index.
- create an index.
- get index details and settings.
slug: search-and-analytics
tags:
- Splunk
- Search
- Analytics
- Monitoring
- Data Ingestion
tools:
- description: List current search jobs.
  hints:
    readOnly: true
  name: list-search-jobs
- description: Create a new SPL search job.
  hints:
    readOnly: false
  name: create-search-job
- description: Get search job status and details.
  hints:
    readOnly: true
  name: get-search-job
- description: Delete a search job.
  hints:
    destructive: true
    readOnly: false
  name: delete-search-job
- description: Control a search job (pause, unpause, finalize, cancel).
  hints:
    readOnly: false
  name: control-search-job
- description: Get results from a completed search job.
  hints:
    readOnly: true
  name: get-search-results
- description: Get untransformed events from a search job.
  hints:
    readOnly: true
  name: get-search-events
- description: Export search results directly without creating a job.
  hints:
    readOnly: true
  name: export-search-results
- description: List all Splunk indexes.
  hints:
    readOnly: true
  name: list-indexes
- description: Create a new Splunk index.
  hints:
    readOnly: false
  name: create-index
- description: Get index details and settings.
  hints:
    readOnly: true
  name: get-index
- description: Update index settings.
  hints:
    idempotent: true
    readOnly: false
  name: update-index
- description: Delete an index.
  hints:
    destructive: true
    readOnly: false
  name: delete-index
- description: List file monitor data inputs.
  hints:
    readOnly: true
  name: list-monitor-inputs
- description: Create a file monitor data input.
  hints:
    readOnly: false
  name: create-monitor-input
- description: List HTTP Event Collector tokens.
  hints:
    readOnly: true
  name: list-http-input-tokens
- description: Create an HTTP Event Collector token.
  hints:
    readOnly: false
  name: create-http-input-token
- description: Send a JSON event via HTTP Event Collector.
  hints:
    readOnly: false
  name: send-event
- description: Check HEC indexing acknowledgment status.
  hints:
    readOnly: true
  name: check-ack-status
---
