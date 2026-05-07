---
categories:
- monitoring
consumed_apis: []
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
- send dimensional metric data to new relic
- devops
- send custom events to new relic
- send custom events
- send metric data to new relic
- platform
- send metrics
- apm
- telemetry
- monitoring
- analysis
- infrastructure
- send log data
- send trace spans
- observability
- new relic
- send logs
- data ingestion
- ops engineering
- send distributed trace spans to new relic
- performance
- send metric data
- send traces
- send custom events to a new relic account
- send events
- send log records to new relic
slug: telemetry-ingestion
source_filename: telemetry-ingestion.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: New Relic Telemetry Ingestion\n  description: Telemetry data ingestion workflow combining event, log, metric, and trace APIs for ops engineers sending observability\n    data to New Relic from external sources.\n  tags:\n  - New Relic\n  - Telemetry\n  - Data Ingestion\n  - Ops Engineering\n  - Observability\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    NEW_RELIC_INSERT_KEY: NEW_RELIC_INSERT_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: event-api\n    baseUri: https://insights-collector.newrelic.com\n    description: New Relic Event API for ingesting custom events.\n    authentication:\n      type: apikey\n      key: Api-Key\n      value: '{{NEW_RELIC_INSERT_KEY}}'\n      placement: header\n    resources:\n    - name: events\n      path: /v1/accounts/{accountId}/events\n      description: Send custom events\n      operations:\n      - name: send-events\n        method: POST\n\
  \        description: Sends one or more custom events to a New Relic account.\n        inputParameters:\n        - name: accountId\n          in: path\n          type: integer\n          required: true\n          description: The New Relic account ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: '{{tools.events}}'\n  - type: http\n    namespace: log-api\n    baseUri: https://log-api.newrelic.com\n    description: New Relic Log API for ingesting log data.\n    authentication:\n      type: apikey\n      key: Api-Key\n      value: '{{NEW_RELIC_INSERT_KEY}}'\n      placement: header\n    resources:\n    - name: logs\n      path: /log/v1\n      description: Send log data\n      operations:\n      - name: send-logs\n        method: POST\n        description: Sends one or more log records to New Relic.\n        inputParameters: []\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: '{{tools.log_data}}'\n  - type: http\n    namespace: metric-api\n    baseUri: https://metric-api.newrelic.com\n    description: New Relic Metric API for ingesting dimensional metric data.\n    authentication:\n      type: apikey\n      key: Api-Key\n      value: '{{NEW_RELIC_INSERT_KEY}}'\n      placement: header\n    resources:\n    - name: metrics\n      path: /metric/v1\n      description: Send metric data\n      operations:\n      - name: send-metrics\n        method: POST\n        description: Sends metric data points to New Relic.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: '{{tools.metric_data}}'\n  - type: http\n    namespace: trace-api\n    baseUri: https://trace-api.newrelic.com\n\
  \    description: New Relic Trace API for ingesting distributed trace spans.\n    authentication:\n      type: apikey\n      key: Api-Key\n      value: '{{NEW_RELIC_INSERT_KEY}}'\n      placement: header\n    resources:\n    - name: traces\n      path: /trace/v1\n      description: Send trace spans\n      operations:\n      - name: send-traces\n        method: POST\n        description: Sends distributed trace spans to New Relic.\n        inputParameters:\n        - name: Data-Format\n          in: header\n          type: string\n          required: true\n          description: The format of the trace data (newrelic or zipkin).\n        - name: Data-Format-Version\n          in: header\n          type: string\n          required: false\n          description: Version of the data format.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: '{{tools.trace_data}}'\n\
  \  exposes:\n  - type: rest\n    port: 8081\n    namespace: telemetry-ingestion-api\n    description: Unified REST API for New Relic telemetry data ingestion.\n    resources:\n    - path: /v1/events/{accountId}\n      name: events\n      description: Send custom events\n      operations:\n      - method: POST\n        name: send-events\n        description: Send custom events to New Relic\n        call: event-api.send-events\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/logs\n      name: logs\n      description: Send log data\n      operations:\n      - method: POST\n        name: send-logs\n        description: Send log records to New Relic\n        call: log-api.send-logs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics\n      name: metrics\n      description: Send metric data\n      operations:\n      - method: POST\n        name: send-metrics\n\
  \        description: Send metric data to New Relic\n        call: metric-api.send-metrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/traces\n      name: traces\n      description: Send trace spans\n      operations:\n      - method: POST\n        name: send-traces\n        description: Send distributed trace spans to New Relic\n        call: trace-api.send-traces\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: telemetry-ingestion-mcp\n    transport: http\n    description: MCP server for AI-assisted New Relic telemetry data ingestion.\n    tools:\n    - name: send-events\n      description: Send custom events to a New Relic account\n      hints:\n        readOnly: false\n        openWorld: true\n      call: event-api.send-events\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-logs\n\
  \      description: Send log records to New Relic\n      hints:\n        readOnly: false\n        openWorld: true\n      call: log-api.send-logs\n      with:\n        log_data: tools.log_data\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-metrics\n      description: Send dimensional metric data to New Relic\n      hints:\n        readOnly: false\n        openWorld: true\n      call: metric-api.send-metrics\n      with:\n        metric_data: tools.metric_data\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-traces\n      description: Send distributed trace spans to New Relic\n      hints:\n        readOnly: false\n        openWorld: true\n      call: trace-api.send-traces\n      with:\n        trace_data: tools.trace_data\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
