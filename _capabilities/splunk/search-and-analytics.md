---
categories:
- analytics
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
- data ingestion
- list file monitor data inputs.
- create search job
- send event
- check ack status
- list http input tokens
- get results from a completed search job.
- list search jobs.
- splunk
- data analysis
- get untransformed events from a search job.
- get search events
- event ingestion via hec.
- send a json event via http event collector.
- create an index.
- list indexes.
- export search results
- control search job
- get index details and settings.
- analytics
- list all splunk indexes.
- delete index
- platform
- create a search job.
- update index settings.
- list http event collector tokens.
- siem
- security
- check hec indexing acknowledgment status.
- create http input token
- list monitor inputs
- observability
- create monitor input
- create an http event collector token.
- get search job
- index management.
- create a file monitor data input.
- get search job status and details.
- monitoring
- delete search job
- create a new splunk index.
- update index
- delete an index.
- create index
- list indexes
- control a search job (pause, unpause, finalize, cancel).
- get search results
- list search jobs
- get index
- logging
- machine data
- delete a search job.
- search job management.
- list current search jobs.
- search
- export search results directly without creating a job.
- create a new spl search job.
- send an event.
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
