---
categories:
- monitoring
consumed_apis:
- dd-logs
- dd-events
description: Unified workflow for log analytics combining logs and events. Used by platform engineers and developers for submitting, searching, and aggregating logs alongside event correlation.
layout: capability
name: Datadog Log Analytics
operations:
- description: Send log entries
  method: POST
  name: submitLogs
  path: /v1/logs
- description: Search log events
  method: POST
  name: searchLogs
  path: /v1/logs/search
- description: Aggregate log data
  method: POST
  name: aggregateLogs
  path: /v1/logs/aggregate
- description: List log indexes
  method: GET
  name: listLogIndexes
  path: /v1/logs/indexes
- description: Get a log index
  method: GET
  name: getLogIndex
  path: /v1/logs/indexes/{name}
- description: List events
  method: GET
  name: listEvents
  path: /v1/events
- description: Post an event
  method: POST
  name: createEvent
  path: /v1/events
- description: Search events
  method: POST
  name: searchEvents
  path: /v1/events/search
personas: []
provider_name: Datadog
provider_slug: datadog
search_terms:
- list configured log indexes
- search log events with query language
- search events
- compute aggregations over log events
- search events alongside log analysis
- get a log index
- aggregate log data
- events
- analytics
- aggregateLogs
- t1
- aggregate logs
- get event
- list events
- send log entries to datadog
- create event
- search log events
- get a specific event
- event correlation
- monitoring
- platform
- get a specific log index configuration
- submit logs
- logs
- log indexes
- search
- list log indexes
- submitLogs
- list events for correlation with logs
- post an event
- log analytics
- get log index
- visualizations
- getLogIndex
- listLogIndexes
- searchEvents
- search logs
- send log entries
- post an event to correlate with log data
- listEvents
- createEvent
- dashboards
- searchLogs
- datadog
- individual log index
slug: log-analytics
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Datadog Log Analytics\"\n  description: \"Unified workflow for log analytics combining logs and events. Used by platform engineers and developers for submitting, searching, and aggregating logs alongside event correlation.\"\n  tags:\n    - Datadog\n    - Log Analytics\n    - Logs\n    - Events\n    - Search\n  personas:\n    - Platform Engineer\n    - Developer\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      DATADOG_API_KEY: DATADOG_API_KEY\n      DATADOG_APP_KEY: DATADOG_APP_KEY\n\ncapability:\n  consumes:\n    - import: dd-logs\n      location: \"./shared/logs.yaml\"\n    - import: dd-events\n      location: \"./shared/events.yaml\"\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: dd-log-analytics-api\n      description: \"Unified REST API for log analytics workflows combining logs and events.\"\n      resources:\n        - path: /v1/logs\n          name:\
  \ logs\n          description: \"Submit logs\"\n          operations:\n            - method: POST\n              name: submitLogs\n              description: \"Send log entries\"\n              call: \"dd-logs.submitLogs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/logs/search\n          name: logs-search\n          description: \"Search logs\"\n          operations:\n            - method: POST\n              name: searchLogs\n              description: \"Search log events\"\n              call: \"dd-logs.searchLogs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/logs/aggregate\n          name: logs-aggregate\n          description: \"Aggregate logs\"\n          operations:\n            - method: POST\n              name: aggregateLogs\n              description: \"Aggregate log data\"\n              call: \"dd-logs.aggregateLogs\"\n \
  \             outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/logs/indexes\n          name: log-indexes\n          description: \"Log indexes\"\n          operations:\n            - method: GET\n              name: listLogIndexes\n              description: \"List log indexes\"\n              call: \"dd-logs.listLogIndexes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/logs/indexes/{name}\n          name: log-index\n          description: \"Individual log index\"\n          operations:\n            - method: GET\n              name: getLogIndex\n              description: \"Get a log index\"\n              call: \"dd-logs.getLogIndex\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/events\n          name: events\n          description: \"Event correlation\"\n          operations:\n\
  \            - method: GET\n              name: listEvents\n              description: \"List events\"\n              call: \"dd-events.listEvents\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: createEvent\n              description: \"Post an event\"\n              call: \"dd-events.createEvent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/events/search\n          name: events-search\n          description: \"Search events\"\n          operations:\n            - method: POST\n              name: searchEvents\n              description: \"Search events\"\n              call: \"dd-events.searchEvents\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9082\n      namespace: dd-log-analytics-mcp\n      transport: http\n      description:\
  \ \"MCP server for AI-assisted log analytics workflows.\"\n      tools:\n        - name: submit-logs\n          description: \"Send log entries to Datadog\"\n          call: \"dd-logs.submitLogs\"\n        - name: search-logs\n          description: \"Search log events with query language\"\n          call: \"dd-logs.searchLogs\"\n          hints:\n            readOnly: true\n        - name: aggregate-logs\n          description: \"Compute aggregations over log events\"\n          call: \"dd-logs.aggregateLogs\"\n          hints:\n            readOnly: true\n        - name: list-log-indexes\n          description: \"List configured log indexes\"\n          call: \"dd-logs.listLogIndexes\"\n          hints:\n            readOnly: true\n        - name: get-log-index\n          description: \"Get a specific log index configuration\"\n          call: \"dd-logs.getLogIndex\"\n          hints:\n            readOnly: true\n        - name: list-events\n          description: \"List events for\
  \ correlation with logs\"\n          call: \"dd-events.listEvents\"\n          hints:\n            readOnly: true\n        - name: get-event\n          description: \"Get a specific event\"\n          call: \"dd-events.getEvent\"\n          hints:\n            readOnly: true\n        - name: create-event\n          description: \"Post an event to correlate with log data\"\n          call: \"dd-events.createEvent\"\n        - name: search-events\n          description: \"Search events alongside log analysis\"\n          call: \"dd-events.searchEvents\"\n          hints:\n            readOnly: true\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/datadog/refs/heads/main/capabilities/log-analytics.yaml
tags:
- Datadog
- Log Analytics
- Logs
- Events
- Search
tools:
- description: Send log entries to Datadog
  hints: {}
  name: submit-logs
- description: Search log events with query language
  hints:
    readOnly: true
  name: search-logs
- description: Compute aggregations over log events
  hints:
    readOnly: true
  name: aggregate-logs
- description: List configured log indexes
  hints:
    readOnly: true
  name: list-log-indexes
- description: Get a specific log index configuration
  hints:
    readOnly: true
  name: get-log-index
- description: List events for correlation with logs
  hints:
    readOnly: true
  name: list-events
- description: Get a specific event
  hints:
    readOnly: true
  name: get-event
- description: Post an event to correlate with log data
  hints: {}
  name: create-event
- description: Search events alongside log analysis
  hints:
    readOnly: true
  name: search-events
---
