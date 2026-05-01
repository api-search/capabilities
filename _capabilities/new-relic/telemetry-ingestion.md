---
categories:
- monitoring
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
- analytics
- send log records to new relic
- send distributed trace spans to new relic
- send metrics
- send log data
- analysis
- send events
- send dimensional metric data to new relic
- send custom events to new relic
- send trace spans
- new relic
- ops engineering
- data ingestion
- devops
- monitoring
- send traces
- send custom events
- infrastructure
- apm
- send logs
- send metric data to new relic
- performance
- observability
- telemetry
- send metric data
- platform
- send custom events to a new relic account
slug: telemetry-ingestion
source_filename: telemetry-ingestion.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"New Relic Telemetry Ingestion\"\n  description: \"Telemetry data ingestion workflow combining event, log, metric, and trace APIs for ops engineers sending observability data to New Relic from external sources.\"\n  tags:\n    - New Relic\n    - Telemetry\n    - Data Ingestion\n    - Ops Engineering\n    - Observability\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      NEW_RELIC_INSERT_KEY: NEW_RELIC_INSERT_KEY\n\ncapability:\n  consumes:\n    - import: event-api\n      location: ./shared/event-api.yaml\n    - import: log-api\n      location: ./shared/log-api.yaml\n    - import: metric-api\n      location: ./shared/metric-api.yaml\n    - import: trace-api\n      location: ./shared/trace-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: telemetry-ingestion-api\n      description: \"Unified REST API for New Relic telemetry data ingestion.\"\n      resources:\n\
  \        - path: /v1/events/{accountId}\n          name: events\n          description: \"Send custom events\"\n          operations:\n            - method: POST\n              name: send-events\n              description: \"Send custom events to New Relic\"\n              call: \"event-api.send-events\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/logs\n          name: logs\n          description: \"Send log data\"\n          operations:\n            - method: POST\n              name: send-logs\n              description: \"Send log records to New Relic\"\n              call: \"log-api.send-logs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/metrics\n          name: metrics\n          description: \"Send metric data\"\n          operations:\n            - method: POST\n\
  \              name: send-metrics\n              description: \"Send metric data to New Relic\"\n              call: \"metric-api.send-metrics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/traces\n          name: traces\n          description: \"Send trace spans\"\n          operations:\n            - method: POST\n              name: send-traces\n              description: \"Send distributed trace spans to New Relic\"\n              call: \"trace-api.send-traces\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: telemetry-ingestion-mcp\n      transport: http\n      description: \"MCP server for AI-assisted New Relic telemetry data ingestion.\"\n      tools:\n        - name: send-events\n          description: \"Send custom events to a New Relic account\"\n          hints:\n            readOnly: false\n  \
  \          openWorld: true\n          call: \"event-api.send-events\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-logs\n          description: \"Send log records to New Relic\"\n          hints:\n            readOnly: false\n            openWorld: true\n          call: \"log-api.send-logs\"\n          with:\n            log_data: \"tools.log_data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-metrics\n          description: \"Send dimensional metric data to New Relic\"\n          hints:\n            readOnly: false\n            openWorld: true\n          call: \"metric-api.send-metrics\"\n          with:\n            metric_data: \"tools.metric_data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-traces\n          description: \"Send\
  \ distributed trace spans to New Relic\"\n          hints:\n            readOnly: false\n            openWorld: true\n          call: \"trace-api.send-traces\"\n          with:\n            trace_data: \"tools.trace_data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/new-relic/refs/heads/main/capabilities/telemetry-ingestion.yaml
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
