---
categories:
- analytics
consumed_apis: []
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
- analytics
- list search jobs
- export search results directly without creating a job.
- list http event collector tokens.
- create a new spl search job.
- list all splunk indexes.
- search job management.
- list monitor inputs
- list indexes.
- create search job
- delete index
- list search jobs.
- create a file monitor data input.
- splunk
- platform
- control a search job (pause, unpause, finalize, cancel).
- monitoring
- export search results
- get search job status and details.
- create index
- control search job
- data analysis
- event ingestion via hec.
- get untransformed events from a search job.
- get search job
- get search events
- delete a search job.
- delete an index.
- send event
- get index
- observability
- delete search job
- list current search jobs.
- create monitor input
- create an http event collector token.
- get index details and settings.
- list http input tokens
- create a search job.
- create http input token
- list indexes
- list file monitor data inputs.
- data ingestion
- get search results
- check hec indexing acknowledgment status.
- update index settings.
- send a json event via http event collector.
- machine data
- search
- index management.
- send an event.
- create a new splunk index.
- update index
- security
- check ack status
- logging
- get results from a completed search job.
- siem
- create an index.
slug: search-and-analytics
source_filename: search-and-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Splunk Search and Analytics\n  description: Unified search and analytics workflow combining SPL search, index management, data inputs, and HTTP Event Collector\n    for SOC analysts, IT operations, and data engineers.\n  tags:\n  - Splunk\n  - Search\n  - Analytics\n  - Monitoring\n  - Data Ingestion\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPLUNK_AUTH_TOKEN: SPLUNK_AUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: enterprise-rest\n    baseUri: https://localhost:8089\n    description: Splunk Enterprise REST API for search, indexing, and data management.\n    authentication:\n      type: bearer\n      token: '{{SPLUNK_AUTH_TOKEN}}'\n    resources:\n    - name: search-jobs\n      path: /services/search/jobs\n      description: Manage search jobs.\n      operations:\n      - name: list-search-jobs\n        method: GET\n        description: List current search jobs.\n   \
  \     inputParameters:\n        - name: output_mode\n          in: query\n          type: string\n          required: false\n          description: Response format (json or xml).\n        - name: count\n          in: query\n          type: integer\n          required: false\n          description: Number of results.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Results offset.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-search-job\n        method: POST\n        description: Create a new search job.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            search: '{{tools.search}}'\n            earliest_time: '{{tools.earliest_time}}'\n            latest_time: '{{tools.latest_time}}'\n\
  \            exec_mode: '{{tools.exec_mode}}'\n      - name: get-search-job\n        method: GET\n        description: Get search job status and details.\n        inputParameters:\n        - name: sid\n          in: path\n          type: string\n          required: true\n          description: Search job ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-search-job\n        method: DELETE\n        description: Delete a search job.\n        inputParameters:\n        - name: sid\n          in: path\n          type: string\n          required: true\n          description: Search job ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: control-search-job\n        method: POST\n        description: Control a search job (pause, unpause, finalize, cancel).\n        inputParameters:\n        - name: sid\n\
  \          in: path\n          type: string\n          required: true\n          description: Search job ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            action: '{{tools.action}}'\n      - name: get-search-results\n        method: GET\n        description: Get results from a completed search job.\n        inputParameters:\n        - name: sid\n          in: path\n          type: string\n          required: true\n          description: Search job ID.\n        - name: count\n          in: query\n          type: integer\n          required: false\n          description: Number of results.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Results offset.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: get-search-events\n        method: GET\n        description: Get untransformed events from a search job.\n        inputParameters:\n        - name: sid\n          in: path\n          type: string\n          required: true\n          description: Search job ID.\n        - name: count\n          in: query\n          type: integer\n          required: false\n          description: Number of events.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: export-search-results\n        method: GET\n        description: Export search results.\n        inputParameters:\n        - name: search\n          in: query\n          type: string\n          required: true\n          description: SPL search string.\n        - name: earliest_time\n          in: query\n          type: string\n          required: false\n          description: Earliest time.\n        - name: latest_time\n          in: query\n\
  \          type: string\n          required: false\n          description: Latest time.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: indexes\n      path: /services/data/indexes\n      description: Manage indexes.\n      operations:\n      - name: list-indexes\n        method: GET\n        description: List all indexes.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-index\n        method: POST\n        description: Create a new index.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            datatype: '{{tools.datatype}}'\n      - name: get-index\n        method: GET\n        description: Get index details.\n        inputParameters:\n\
  \        - name: indexName\n          in: path\n          type: string\n          required: true\n          description: Index name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-index\n        method: POST\n        description: Update index settings.\n        inputParameters:\n        - name: indexName\n          in: path\n          type: string\n          required: true\n          description: Index name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-index\n        method: DELETE\n        description: Delete an index.\n        inputParameters:\n        - name: indexName\n          in: path\n          type: string\n          required: true\n          description: Index name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n    - name: data-inputs\n      path: /services/data/inputs\n      description: Manage data inputs.\n      operations:\n      - name: list-monitor-inputs\n        method: GET\n        description: List file monitor inputs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-monitor-input\n        method: POST\n        description: Create a file monitor input.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            index: '{{tools.index}}'\n            sourcetype: '{{tools.sourcetype}}'\n      - name: list-tcp-cooked-inputs\n        method: GET\n        description: List TCP cooked inputs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n      - name: list-tcp-raw-inputs\n        method: GET\n        description: List TCP raw inputs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-udp-inputs\n        method: GET\n        description: List UDP inputs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-http-input-tokens\n        method: GET\n        description: List HTTP Event Collector tokens.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-http-input-token\n        method: POST\n        description: Create an HEC token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n           \
  \ name: '{{tools.name}}'\n            index: '{{tools.index}}'\n    - name: hec\n      path: /services/collector\n      description: HTTP Event Collector.\n      operations:\n      - name: send-event\n        method: POST\n        description: Send a JSON event via HEC.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            event: '{{tools.event}}'\n            sourcetype: '{{tools.sourcetype}}'\n            index: '{{tools.index}}'\n      - name: send-raw-event\n        method: POST\n        description: Send raw event data via HEC.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: check-ack-status\n        method: POST\n        description: Check indexing acknowledgment status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: search-analytics-api\n    description: Unified REST API for Splunk search, indexing, and data ingestion.\n    resources:\n    - path: /v1/search-jobs\n      name: search-jobs\n      description: Search job management.\n      operations:\n      - method: GET\n        name: list-search-jobs\n        description: List search jobs.\n        call: enterprise-rest.list-search-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-search-job\n        description: Create a search job.\n        call: enterprise-rest.create-search-job\n        with:\n          search: rest.search\n          earliest_time: rest.earliest_time\n          latest_time: rest.latest_time\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/indexes\n      name: indexes\n      description: Index management.\n    \
  \  operations:\n      - method: GET\n        name: list-indexes\n        description: List indexes.\n        call: enterprise-rest.list-indexes\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-index\n        description: Create an index.\n        call: enterprise-rest.create-index\n        with:\n          name: rest.name\n          datatype: rest.datatype\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events\n      name: events\n      description: Event ingestion via HEC.\n      operations:\n      - method: POST\n        name: send-event\n        description: Send an event.\n        call: enterprise-rest.send-event\n        with:\n          event: rest.event\n          sourcetype: rest.sourcetype\n          index: rest.index\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: search-analytics-mcp\n    transport:\
  \ http\n    description: MCP server for AI-assisted Splunk search, analytics, and data management.\n    tools:\n    - name: list-search-jobs\n      description: List current search jobs.\n      hints:\n        readOnly: true\n      call: enterprise-rest.list-search-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-search-job\n      description: Create a new SPL search job.\n      hints:\n        readOnly: false\n      call: enterprise-rest.create-search-job\n      with:\n        search: tools.search\n        earliest_time: tools.earliest_time\n        latest_time: tools.latest_time\n        exec_mode: tools.exec_mode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-search-job\n      description: Get search job status and details.\n      hints:\n        readOnly: true\n      call: enterprise-rest.get-search-job\n      with:\n        sid: tools.sid\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: delete-search-job\n      description: Delete a search job.\n      hints:\n        readOnly: false\n        destructive: true\n      call: enterprise-rest.delete-search-job\n      with:\n        sid: tools.sid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: control-search-job\n      description: Control a search job (pause, unpause, finalize, cancel).\n      hints:\n        readOnly: false\n      call: enterprise-rest.control-search-job\n      with:\n        sid: tools.sid\n        action: tools.action\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-search-results\n      description: Get results from a completed search job.\n      hints:\n        readOnly: true\n      call: enterprise-rest.get-search-results\n      with:\n        sid: tools.sid\n        count: tools.count\n        offset: tools.offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-search-events\n\
  \      description: Get untransformed events from a search job.\n      hints:\n        readOnly: true\n      call: enterprise-rest.get-search-events\n      with:\n        sid: tools.sid\n        count: tools.count\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: export-search-results\n      description: Export search results directly without creating a job.\n      hints:\n        readOnly: true\n      call: enterprise-rest.export-search-results\n      with:\n        search: tools.search\n        earliest_time: tools.earliest_time\n        latest_time: tools.latest_time\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-indexes\n      description: List all Splunk indexes.\n      hints:\n        readOnly: true\n      call: enterprise-rest.list-indexes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-index\n      description: Create a new Splunk index.\n      hints:\n        readOnly:\
  \ false\n      call: enterprise-rest.create-index\n      with:\n        name: tools.name\n        datatype: tools.datatype\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-index\n      description: Get index details and settings.\n      hints:\n        readOnly: true\n      call: enterprise-rest.get-index\n      with:\n        indexName: tools.indexName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-index\n      description: Update index settings.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: enterprise-rest.update-index\n      with:\n        indexName: tools.indexName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-index\n      description: Delete an index.\n      hints:\n        readOnly: false\n        destructive: true\n      call: enterprise-rest.delete-index\n      with:\n        indexName: tools.indexName\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-monitor-inputs\n      description: List file monitor data inputs.\n      hints:\n        readOnly: true\n      call: enterprise-rest.list-monitor-inputs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-monitor-input\n      description: Create a file monitor data input.\n      hints:\n        readOnly: false\n      call: enterprise-rest.create-monitor-input\n      with:\n        name: tools.name\n        index: tools.index\n        sourcetype: tools.sourcetype\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-http-input-tokens\n      description: List HTTP Event Collector tokens.\n      hints:\n        readOnly: true\n      call: enterprise-rest.list-http-input-tokens\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-http-input-token\n      description: Create an HTTP Event Collector token.\n      hints:\n        readOnly:\
  \ false\n      call: enterprise-rest.create-http-input-token\n      with:\n        name: tools.name\n        index: tools.index\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-event\n      description: Send a JSON event via HTTP Event Collector.\n      hints:\n        readOnly: false\n      call: enterprise-rest.send-event\n      with:\n        event: tools.event\n        sourcetype: tools.sourcetype\n        index: tools.index\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-ack-status\n      description: Check HEC indexing acknowledgment status.\n      hints:\n        readOnly: true\n      call: enterprise-rest.check-ack-status\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
