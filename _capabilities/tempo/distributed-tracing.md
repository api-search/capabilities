---
api_specs:
- filename: tempo-openapi.yml
  format: yaml
  label: tempo
  slug: tempo
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/tempo/refs/heads/main/openapi/tempo-openapi.yml
categories: []
consumed_apis:
- tempo
description: Distributed tracing workflow using the Grafana Tempo API for trace retrieval, TraceQL search, tag discovery, and trace-based metrics generation. Used by SREs, platform engineers, and developers to investigate performance issues and service dependencies.
layout: capability
name: Grafana Tempo Distributed Tracing
operations:
- description: Get a complete distributed trace by its trace ID
  method: GET
  name: get-trace
  path: /v1/traces/{traceID}
- description: Search traces with TraceQL query
  method: GET
  name: search-traces
  path: /v1/search
- description: List all tag keys present in trace data
  method: GET
  name: list-tag-keys
  path: /v1/tags
- description: List distinct values for a tag key
  method: GET
  name: list-tag-values
  path: /v1/tags/{tagName}/values
- description: Generate time-series metrics from trace data
  method: GET
  name: query-metrics
  path: /v1/metrics
personas: []
provider_name: Tempo
provider_slug: tempo
search_terms:
- trace search using traceql
- get a complete distributed trace by its trace id
- debugging
- search traces
- trace-based metrics
- tag key discovery
- grafana
- list tag values
- tag value discovery
- retrieve a complete distributed trace to see all service calls and latencies
- find traces exceeding a minimum duration threshold
- observability
- generate error rate metrics for a service over time
- performance
- opentelemetry
- trace retrieval by id
- query error rate
- find slow traces
- list all tag keys present in trace data
- search for traces matching a traceql query (e.g. find slow requests, errors)
- list distinct values for a tag key
- distributed tracing
- query metrics
- list all values for a trace attribute (e.g. all service names)
- discover all available trace attribute keys for building queries
- monitoring
- generate time-series metrics from trace data
- find error traces
- list tag keys
- find traces with errors in a time window
- search traces with traceql query
- get trace
slug: distributed-tracing
source_filename: distributed-tracing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Grafana Tempo Distributed Tracing\"\n  description: \"Distributed tracing workflow using the Grafana Tempo API for trace retrieval, TraceQL search, tag discovery, and trace-based metrics generation. Used by SREs, platform engineers, and developers to investigate performance issues and service dependencies.\"\n  tags:\n    - Distributed Tracing\n    - Observability\n    - OpenTelemetry\n    - Performance\n    - Debugging\n    - Grafana\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TEMPO_BASE_URL: TEMPO_BASE_URL\n\ncapability:\n  consumes:\n    - import: tempo\n      location: ./shared/tempo.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: distributed-tracing-api\n      description: \"Unified REST API for Grafana Tempo distributed tracing operations.\"\n      resources:\n        - path: /v1/traces/{traceID}\n          name: traces\n          description:\
  \ \"Trace retrieval by ID\"\n          operations:\n            - method: GET\n              name: get-trace\n              description: \"Get a complete distributed trace by its trace ID\"\n              call: \"tempo.get-trace\"\n              with:\n                traceID: \"rest.traceID\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/search\n          name: search\n          description: \"Trace search using TraceQL\"\n          operations:\n            - method: GET\n              name: search-traces\n              description: \"Search traces with TraceQL query\"\n              call: \"tempo.search-traces\"\n              with:\n                q: \"rest.q\"\n                start: \"rest.start\"\n                end: \"rest.end\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tags\n      \
  \    name: tag-keys\n          description: \"Tag key discovery\"\n          operations:\n            - method: GET\n              name: list-tag-keys\n              description: \"List all tag keys present in trace data\"\n              call: \"tempo.list-tag-keys\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tags/{tagName}/values\n          name: tag-values\n          description: \"Tag value discovery\"\n          operations:\n            - method: GET\n              name: list-tag-values\n              description: \"List distinct values for a tag key\"\n              call: \"tempo.list-tag-values\"\n              with:\n                tagName: \"rest.tagName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/metrics\n          name: metrics\n          description: \"Trace-based metrics\"\n          operations:\n            - method:\
  \ GET\n              name: query-metrics\n              description: \"Generate time-series metrics from trace data\"\n              call: \"tempo.query-metrics-range\"\n              with:\n                q: \"rest.q\"\n                start: \"rest.start\"\n                end: \"rest.end\"\n                step: \"rest.step\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: distributed-tracing-mcp\n      transport: http\n      description: \"MCP server for AI-assisted distributed tracing investigation and performance analysis.\"\n      tools:\n        - name: get-trace\n          description: \"Retrieve a complete distributed trace to see all service calls and latencies\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tempo.get-trace\"\n          with:\n            traceID: \"tools.traceID\"\n          outputParameters:\n        \
  \    - type: object\n              mapping: \"$.\"\n        - name: search-traces\n          description: \"Search for traces matching a TraceQL query (e.g. find slow requests, errors)\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tempo.search-traces\"\n          with:\n            q: \"tools.q\"\n            start: \"tools.start\"\n            end: \"tools.end\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: find-error-traces\n          description: \"Find traces with errors in a time window\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tempo.search-traces\"\n          with:\n            q: \"{status=error}\"\n            start: \"tools.start\"\n            end: \"tools.end\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: find-slow-traces\n\
  \          description: \"Find traces exceeding a minimum duration threshold\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tempo.search-traces\"\n          with:\n            minDuration: \"tools.minDuration\"\n            start: \"tools.start\"\n            end: \"tools.end\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tag-keys\n          description: \"Discover all available trace attribute keys for building queries\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tempo.list-tag-keys\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tag-values\n          description: \"List all values for a trace attribute (e.g. all service names)\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"tempo.list-tag-values\"\n         \
  \ with:\n            tagName: \"tools.tagName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-error-rate\n          description: \"Generate error rate metrics for a service over time\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tempo.query-metrics-range\"\n          with:\n            q: \"tools.metricsQuery\"\n            start: \"tools.start\"\n            end: \"tools.end\"\n            step: \"tools.step\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tempo/refs/heads/main/capabilities/distributed-tracing.yaml
tags:
- Distributed Tracing
- Observability
- OpenTelemetry
- Performance
- Debugging
- Grafana
tools:
- description: Retrieve a complete distributed trace to see all service calls and latencies
  hints:
    openWorld: false
    readOnly: true
  name: get-trace
- description: Search for traces matching a TraceQL query (e.g. find slow requests, errors)
  hints:
    openWorld: false
    readOnly: true
  name: search-traces
- description: Find traces with errors in a time window
  hints:
    openWorld: false
    readOnly: true
  name: find-error-traces
- description: Find traces exceeding a minimum duration threshold
  hints:
    openWorld: false
    readOnly: true
  name: find-slow-traces
- description: Discover all available trace attribute keys for building queries
  hints:
    openWorld: false
    readOnly: true
  name: list-tag-keys
- description: List all values for a trace attribute (e.g. all service names)
  hints:
    openWorld: false
    readOnly: true
  name: list-tag-values
- description: Generate error rate metrics for a service over time
  hints:
    openWorld: true
    readOnly: true
  name: query-error-rate
---
