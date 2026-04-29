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
- list http input tokens
- search job management.
- list current search jobs.
- search
- get results from a completed search job.
- logging
- security
- create search job
- list indexes.
- monitoring
- get search job
- update index settings.
- get index
- list search jobs.
- send event
- list file monitor data inputs.
- siem
- export search results directly without creating a job.
- delete an index.
- create monitor input
- list all splunk indexes.
- export search results
- observability
- delete index
- control a search job (pause, unpause, finalize, cancel).
- create a file monitor data input.
- delete search job
- data analysis
- data ingestion
- list http event collector tokens.
- create http input token
- splunk
- send an event.
- list monitor inputs
- list search jobs
- get untransformed events from a search job.
- create a search job.
- get index details and settings.
- analytics
- delete a search job.
- get search results
- list indexes
- create index
- platform
- event ingestion via hec.
- update index
- send a json event via http event collector.
- check ack status
- machine data
- get search job status and details.
- create an http event collector token.
- check hec indexing acknowledgment status.
- index management.
- create an index.
- create a new spl search job.
- get search events
- create a new splunk index.
- control search job
slug: search-and-analytics
source_filename: search-and-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Splunk Search and Analytics\"\n  description: \"Unified search and analytics workflow combining SPL search, index management, data inputs, and HTTP Event Collector for SOC analysts, IT operations, and data engineers.\"\n  tags:\n    - Splunk\n    - Search\n    - Analytics\n    - Monitoring\n    - Data Ingestion\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SPLUNK_AUTH_TOKEN: SPLUNK_AUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: enterprise-rest\n      location: ./shared/enterprise-rest.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: search-analytics-api\n      description: \"Unified REST API for Splunk search, indexing, and data ingestion.\"\n      resources:\n        - path: /v1/search-jobs\n          name: search-jobs\n          description: \"Search job management.\"\n          operations:\n            - method: GET\n              name: list-search-jobs\n\
  \              description: \"List search jobs.\"\n              call: \"enterprise-rest.list-search-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-search-job\n              description: \"Create a search job.\"\n              call: \"enterprise-rest.create-search-job\"\n              with:\n                search: \"rest.search\"\n                earliest_time: \"rest.earliest_time\"\n                latest_time: \"rest.latest_time\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/indexes\n          name: indexes\n          description: \"Index management.\"\n          operations:\n            - method: GET\n              name: list-indexes\n              description: \"List indexes.\"\n              call: \"enterprise-rest.list-indexes\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n            - method: POST\n              name: create-index\n              description: \"Create an index.\"\n              call: \"enterprise-rest.create-index\"\n              with:\n                name: \"rest.name\"\n                datatype: \"rest.datatype\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/events\n          name: events\n          description: \"Event ingestion via HEC.\"\n          operations:\n            - method: POST\n              name: send-event\n              description: \"Send an event.\"\n              call: \"enterprise-rest.send-event\"\n              with:\n                event: \"rest.event\"\n                sourcetype: \"rest.sourcetype\"\n                index: \"rest.index\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: search-analytics-mcp\n\
  \      transport: http\n      description: \"MCP server for AI-assisted Splunk search, analytics, and data management.\"\n      tools:\n        - name: list-search-jobs\n          description: \"List current search jobs.\"\n          hints:\n            readOnly: true\n          call: \"enterprise-rest.list-search-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-search-job\n          description: \"Create a new SPL search job.\"\n          hints:\n            readOnly: false\n          call: \"enterprise-rest.create-search-job\"\n          with:\n            search: \"tools.search\"\n            earliest_time: \"tools.earliest_time\"\n            latest_time: \"tools.latest_time\"\n            exec_mode: \"tools.exec_mode\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-search-job\n          description: \"Get search job status and details.\"\n          hints:\n\
  \            readOnly: true\n          call: \"enterprise-rest.get-search-job\"\n          with:\n            sid: \"tools.sid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-search-job\n          description: \"Delete a search job.\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"enterprise-rest.delete-search-job\"\n          with:\n            sid: \"tools.sid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: control-search-job\n          description: \"Control a search job (pause, unpause, finalize, cancel).\"\n          hints:\n            readOnly: false\n          call: \"enterprise-rest.control-search-job\"\n          with:\n            sid: \"tools.sid\"\n            action: \"tools.action\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-search-results\n\
  \          description: \"Get results from a completed search job.\"\n          hints:\n            readOnly: true\n          call: \"enterprise-rest.get-search-results\"\n          with:\n            sid: \"tools.sid\"\n            count: \"tools.count\"\n            offset: \"tools.offset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-search-events\n          description: \"Get untransformed events from a search job.\"\n          hints:\n            readOnly: true\n          call: \"enterprise-rest.get-search-events\"\n          with:\n            sid: \"tools.sid\"\n            count: \"tools.count\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: export-search-results\n          description: \"Export search results directly without creating a job.\"\n          hints:\n            readOnly: true\n          call: \"enterprise-rest.export-search-results\"\n        \
  \  with:\n            search: \"tools.search\"\n            earliest_time: \"tools.earliest_time\"\n            latest_time: \"tools.latest_time\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-indexes\n          description: \"List all Splunk indexes.\"\n          hints:\n            readOnly: true\n          call: \"enterprise-rest.list-indexes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-index\n          description: \"Create a new Splunk index.\"\n          hints:\n            readOnly: false\n          call: \"enterprise-rest.create-index\"\n          with:\n            name: \"tools.name\"\n            datatype: \"tools.datatype\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-index\n          description: \"Get index details and settings.\"\n          hints:\n            readOnly: true\n\
  \          call: \"enterprise-rest.get-index\"\n          with:\n            indexName: \"tools.indexName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-index\n          description: \"Update index settings.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"enterprise-rest.update-index\"\n          with:\n            indexName: \"tools.indexName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-index\n          description: \"Delete an index.\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"enterprise-rest.delete-index\"\n          with:\n            indexName: \"tools.indexName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-monitor-inputs\n          description: \"List file monitor data inputs.\"\
  \n          hints:\n            readOnly: true\n          call: \"enterprise-rest.list-monitor-inputs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-monitor-input\n          description: \"Create a file monitor data input.\"\n          hints:\n            readOnly: false\n          call: \"enterprise-rest.create-monitor-input\"\n          with:\n            name: \"tools.name\"\n            index: \"tools.index\"\n            sourcetype: \"tools.sourcetype\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-http-input-tokens\n          description: \"List HTTP Event Collector tokens.\"\n          hints:\n            readOnly: true\n          call: \"enterprise-rest.list-http-input-tokens\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-http-input-token\n          description: \"Create an HTTP Event\
  \ Collector token.\"\n          hints:\n            readOnly: false\n          call: \"enterprise-rest.create-http-input-token\"\n          with:\n            name: \"tools.name\"\n            index: \"tools.index\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-event\n          description: \"Send a JSON event via HTTP Event Collector.\"\n          hints:\n            readOnly: false\n          call: \"enterprise-rest.send-event\"\n          with:\n            event: \"tools.event\"\n            sourcetype: \"tools.sourcetype\"\n            index: \"tools.index\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-ack-status\n          description: \"Check HEC indexing acknowledgment status.\"\n          hints:\n            readOnly: true\n          call: \"enterprise-rest.check-ack-status\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/splunk/refs/heads/main/capabilities/search-and-analytics.yaml
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
