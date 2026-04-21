---
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
- createEvent
- individual log index
- submitLogs
- datadog
- getLogIndex
- search events
- search
- search log events
- aggregateLogs
- search log events with query language
- list events for correlation with logs
- platform
- search events alongside log analysis
- listEvents
- get event
- post an event to correlate with log data
- logs
- create event
- search logs
- get a specific log index configuration
- dashboards
- compute aggregations over log events
- listLogIndexes
- post an event
- searchEvents
- list log indexes
- visualizations
- send log entries
- send log entries to datadog
- monitoring
- aggregate log data
- log analytics
- get log index
- event correlation
- get a specific event
- aggregate logs
- log indexes
- events
- get a log index
- list events
- submit logs
- analytics
- list configured log indexes
- searchLogs
- t1
slug: log-analytics
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
