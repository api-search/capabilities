---
consumed_apis:
- event-api
- log-api
- metric-api
- trace-api
description: Telemetry data ingestion workflow combining event, log, metric, and trace APIs for ops engineers sending observability data to New Relic from external sources.
layout: capability
name: New Relic Telemetry Ingestion
operations:
- description: Send custom events to New Relic
  method: POST
  name: send-events
  path: /v1/events/{accountId}
- description: Send log records to New Relic
  method: POST
  name: send-logs
  path: /v1/logs
- description: Send metric data to New Relic
  method: POST
  name: send-metrics
  path: /v1/metrics
- description: Send distributed trace spans to New Relic
  method: POST
  name: send-traces
  path: /v1/traces
personas: []
provider_name: New Relic
provider_slug: new-relic
search_terms:
- devops
- telemetry
- send logs
- performance
- ops engineering
- analytics
- send metrics
- send log records to new relic
- send distributed trace spans to new relic
- send dimensional metric data to new relic
- platform
- send trace spans
- send custom events to a new relic account
- data ingestion
- new relic
- apm
- analysis
- monitoring
- infrastructure
- observability
- send log data
- send custom events
- send traces
- send metric data
- send events
- send metric data to new relic
- send custom events to new relic
slug: telemetry-ingestion
tags:
- New Relic
- Telemetry
- Data Ingestion
- Ops Engineering
- Observability
tools:
- description: Send custom events to a New Relic account
  hints:
    openWorld: true
    readOnly: false
  name: send-events
- description: Send log records to New Relic
  hints:
    openWorld: true
    readOnly: false
  name: send-logs
- description: Send dimensional metric data to New Relic
  hints:
    openWorld: true
    readOnly: false
  name: send-metrics
- description: Send distributed trace spans to New Relic
  hints:
    openWorld: true
    readOnly: false
  name: send-traces
---
