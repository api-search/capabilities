---
categories: []
consumed_apis: []
description: Unified metrics and observability capability for SRE, platform engineers, and monitoring teams. Composes Thanos Query API to provide PromQL-based metric queries, long-term trend analysis, alert monitoring, and store health inspection across distributed Prometheus deployments.
layout: capability
name: Thanos Metrics and Observability
operations:
- description: Execute an instant PromQL query for current metric values
  method: GET
  name: instant-query
  path: /v1/query
- description: Execute a PromQL range query for historical metric data
  method: GET
  name: range-query
  path: /v1/query-range
- description: Find time series matching label selectors
  method: GET
  name: get-series
  path: /v1/series
- description: Get all available metric label names
  method: GET
  name: get-labels
  path: /v1/labels
- description: Get all currently active alerts
  method: GET
  name: get-alerts
  path: /v1/alerts
- description: Get alerting and recording rules
  method: GET
  name: get-rules
  path: /v1/rules
- description: Get connected Thanos store information and health
  method: GET
  name: get-stores
  path: /v1/stores
personas: []
provider_name: Thanos
provider_slug: thanos
search_terms:
- alerting and recording rules
- thanos
- get alerts
- execute an instant promql query for current metric values
- get rules
- find time series in thanos matching label selectors for service discovery
- execute a promql range query for historical metric data
- get labels
- promql
- monitoring
- instant promql metric queries
- range query
- get all available metric label names
- time series discovery
- get connected thanos store information and health
- get alerting and recording rules configured in thanos ruler
- find series
- inspect connected thanos store endpoints, health status, and data time ranges
- prometheus
- get stores
- get active alerts
- observability
- get all currently firing and pending alerts from thanos
- sre
- get series
- time series database
- list labels
- execute a promql range query to analyze metric trends over time in thanos
- instant query
- get alerting and recording rules
- get all currently active alerts
- inspect stores
- label name discovery
- metrics
- range promql metric queries over time
- list all available metric label names across thanos stores
- execute an instant promql query to get current metric values from thanos
- store endpoint health
- active alert monitoring
- find time series matching label selectors
slug: metrics-observability
source_filename: metrics-observability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Thanos Metrics and Observability\n  description: Unified metrics and observability capability for SRE, platform engineers, and monitoring teams. Composes Thanos\n    Query API to provide PromQL-based metric queries, long-term trend analysis, alert monitoring, and store health inspection\n    across distributed Prometheus deployments.\n  tags:\n  - Thanos\n  - Observability\n  - Metrics\n  - Prometheus\n  - SRE\n  - Monitoring\n  - PromQL\n  created: '2026-05-03'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: thanos-query\n    baseUri: http://localhost:9090\n    description: Thanos Query HTTP API — Prometheus-compatible query interface\n    resources:\n    - name: instant-query\n      path: /api/v1/query\n      description: Instant PromQL queries\n      operations:\n      - name: instant-query\n        method: GET\n        description: Evaluate a PromQL expression at a single point in time\n        inputParameters:\n\
  \        - name: query\n          in: query\n          type: string\n          required: true\n          description: PromQL query expression\n        - name: time\n          in: query\n          type: string\n          required: false\n          description: Evaluation timestamp (RFC3339 or Unix)\n        - name: dedup\n          in: query\n          type: boolean\n          required: false\n          description: 'Enable deduplication (default: true)'\n        - name: partial_response\n          in: query\n          type: boolean\n          required: false\n          description: 'Enable partial response (default: false)'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: range-query\n      path: /api/v1/query_range\n      description: Range PromQL queries\n      operations:\n      - name: range-query\n        method: GET\n        description: Evaluate a PromQL expression over a time range\n    \
  \    inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: PromQL query expression\n        - name: start\n          in: query\n          type: string\n          required: true\n          description: Start timestamp\n        - name: end\n          in: query\n          type: string\n          required: true\n          description: End timestamp\n        - name: step\n          in: query\n          type: string\n          required: true\n          description: Step interval (e.g., 60s, 5m)\n        - name: dedup\n          in: query\n          type: boolean\n          required: false\n          description: Enable deduplication\n        - name: max_source_resolution\n          in: query\n          type: string\n          required: false\n          description: 'Max resolution: 0s, 5m, or 1h'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n    - name: series\n      path: /api/v1/series\n      description: Series discovery\n      operations:\n      - name: get-series\n        method: GET\n        description: Find time series by label matchers\n        inputParameters:\n        - name: match[]\n          in: query\n          type: array\n          required: true\n          description: Label matchers\n        - name: start\n          in: query\n          type: string\n          required: false\n          description: Start timestamp\n        - name: end\n          in: query\n          type: string\n          required: false\n          description: End timestamp\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: labels\n      path: /api/v1/labels\n      description: Label name discovery\n      operations:\n      - name: get-labels\n        method: GET\n        description: Get all label names\n        inputParameters:\n  \
  \      - name: start\n          in: query\n          type: string\n          required: false\n        - name: end\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stores\n      path: /api/v1/stores\n      description: Connected store information\n      operations:\n      - name: get-stores\n        method: GET\n        description: Get information about connected Thanos store endpoints\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alerts\n      path: /api/v1/alerts\n      description: Active alerts\n      operations:\n      - name: get-alerts\n        method: GET\n        description: Get all active alerts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: rules\n      path: /api/v1/rules\n      description: Alerting and recording rules\n      operations:\n      - name: get-rules\n        method: GET\n        description: Get alerting and recording rules\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: 'Filter by rule type: alert or record'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: thanos-observability-api\n    description: Unified REST API for Thanos metrics and observability.\n    resources:\n    - path: /v1/query\n      name: instant-query\n      description: Instant PromQL metric queries\n      operations:\n      - method: GET\n        name: instant-query\n        description: Execute an instant PromQL query for current metric values\n        call: thanos-query.instant-query\n        with:\n\
  \          query: rest.query\n          time: rest.time\n          dedup: rest.dedup\n          partial_response: rest.partial_response\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/query-range\n      name: range-query\n      description: Range PromQL metric queries over time\n      operations:\n      - method: GET\n        name: range-query\n        description: Execute a PromQL range query for historical metric data\n        call: thanos-query.range-query\n        with:\n          query: rest.query\n          start: rest.start\n          end: rest.end\n          step: rest.step\n          dedup: rest.dedup\n          max_source_resolution: rest.max_source_resolution\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/series\n      name: series\n      description: Time series discovery\n      operations:\n      - method: GET\n        name: get-series\n        description: Find time series matching label\
  \ selectors\n        call: thanos-query.get-series\n        with:\n          match[]: rest.matchers\n          start: rest.start\n          end: rest.end\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/labels\n      name: labels\n      description: Label name discovery\n      operations:\n      - method: GET\n        name: get-labels\n        description: Get all available metric label names\n        call: thanos-query.get-labels\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/alerts\n      name: alerts\n      description: Active alert monitoring\n      operations:\n      - method: GET\n        name: get-alerts\n        description: Get all currently active alerts\n        call: thanos-query.get-alerts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rules\n      name: rules\n      description: Alerting and recording rules\n      operations:\n      - method: GET\n\
  \        name: get-rules\n        description: Get alerting and recording rules\n        call: thanos-query.get-rules\n        with:\n          type: rest.type\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stores\n      name: stores\n      description: Store endpoint health\n      operations:\n      - method: GET\n        name: get-stores\n        description: Get connected Thanos store information and health\n        call: thanos-query.get-stores\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: thanos-observability-mcp\n    transport: http\n    description: MCP server for AI-assisted Thanos metrics analysis and observability.\n    tools:\n    - name: instant-query\n      description: Execute an instant PromQL query to get current metric values from Thanos\n      hints:\n        readOnly: true\n        openWorld: false\n        idempotent: true\n      call: thanos-query.instant-query\n\
  \      with:\n        query: tools.query\n        time: tools.time\n        dedup: tools.dedup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: range-query\n      description: Execute a PromQL range query to analyze metric trends over time in Thanos\n      hints:\n        readOnly: true\n        openWorld: false\n        idempotent: true\n      call: thanos-query.range-query\n      with:\n        query: tools.query\n        start: tools.start\n        end: tools.end\n        step: tools.step\n        dedup: tools.dedup\n        max_source_resolution: tools.max_source_resolution\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-series\n      description: Find time series in Thanos matching label selectors for service discovery\n      hints:\n        readOnly: true\n        openWorld: false\n        idempotent: true\n      call: thanos-query.get-series\n      with:\n        match[]: tools.matchers\n        start: tools.start\n\
  \        end: tools.end\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-labels\n      description: List all available metric label names across Thanos stores\n      hints:\n        readOnly: true\n        openWorld: true\n        idempotent: true\n      call: thanos-query.get-labels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-active-alerts\n      description: Get all currently firing and pending alerts from Thanos\n      hints:\n        readOnly: true\n        openWorld: false\n        idempotent: true\n      call: thanos-query.get-alerts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-rules\n      description: Get alerting and recording rules configured in Thanos Ruler\n      hints:\n        readOnly: true\n        openWorld: false\n        idempotent: true\n      call: thanos-query.get-rules\n      with:\n        type: tools.type\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: inspect-stores\n      description: Inspect connected Thanos store endpoints, health status, and data time ranges\n      hints:\n        readOnly: true\n        openWorld: false\n        idempotent: true\n      call: thanos-query.get-stores\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/thanos/refs/heads/main/capabilities/metrics-observability.yaml
tags:
- Thanos
- Observability
- Metrics
- Prometheus
- SRE
- Monitoring
- PromQL
tools:
- description: Execute an instant PromQL query to get current metric values from Thanos
  hints:
    idempotent: true
    openWorld: false
    readOnly: true
  name: instant-query
- description: Execute a PromQL range query to analyze metric trends over time in Thanos
  hints:
    idempotent: true
    openWorld: false
    readOnly: true
  name: range-query
- description: Find time series in Thanos matching label selectors for service discovery
  hints:
    idempotent: true
    openWorld: false
    readOnly: true
  name: find-series
- description: List all available metric label names across Thanos stores
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-labels
- description: Get all currently firing and pending alerts from Thanos
  hints:
    idempotent: true
    openWorld: false
    readOnly: true
  name: get-active-alerts
- description: Get alerting and recording rules configured in Thanos Ruler
  hints:
    idempotent: true
    openWorld: false
    readOnly: true
  name: get-rules
- description: Inspect connected Thanos store endpoints, health status, and data time ranges
  hints:
    idempotent: true
    openWorld: false
    readOnly: true
  name: inspect-stores
---
