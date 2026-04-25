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
- splunk
- list indexes.
- update index settings.
- create a search job.
- send event
- list search jobs.
- list http input tokens
- get search events
- get untransformed events from a search job.
- export search results directly without creating a job.
- logging
- create a file monitor data input.
- search
- data ingestion
- send an event.
- create http input token
- observability
- list current search jobs.
- machine data
- list monitor inputs
- create a new spl search job.
- siem
- create monitor input
- security
- index management.
- get search results
- search job management.
- check hec indexing acknowledgment status.
- platform
- delete search job
- monitoring
- list file monitor data inputs.
- create index
- get index details and settings.
- check ack status
- event ingestion via hec.
- get results from a completed search job.
- list indexes
- delete a search job.
- get search job
- control search job
- create search job
- update index
- list http event collector tokens.
- create a new splunk index.
- create an http event collector token.
- create an index.
- control a search job (pause, unpause, finalize, cancel).
- send a json event via http event collector.
- data analysis
- get index
- list search jobs
- analytics
- get search job status and details.
- export search results
- delete index
- list all splunk indexes.
- delete an index.
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
