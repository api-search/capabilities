---
categories: []
consumed_apis: []
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
- opentelemetry
- trace-based metrics
- list all values for a trace attribute (e.g. all service names)
- trace search using traceql
- generate error rate metrics for a service over time
- distributed tracing
- get a complete distributed trace by its trace id
- search traces
- discover all available trace attribute keys for building queries
- list all tag keys present in trace data
- monitoring
- search traces with traceql query
- find traces exceeding a minimum duration threshold
- grafana
- find slow traces
- retrieve a complete distributed trace to see all service calls and latencies
- find error traces
- find traces with errors in a time window
- observability
- list tag values
- get trace
- list distinct values for a tag key
- tag value discovery
- generate time-series metrics from trace data
- debugging
- list tag keys
- performance
- tag key discovery
- query metrics
- trace retrieval by id
- query error rate
- search for traces matching a traceql query (e.g. find slow requests, errors)
slug: distributed-tracing
source_filename: distributed-tracing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Grafana Tempo Distributed Tracing\n  description: Distributed tracing workflow using the Grafana Tempo API for trace retrieval, TraceQL search, tag discovery,\n    and trace-based metrics generation. Used by SREs, platform engineers, and developers to investigate performance issues\n    and service dependencies.\n  tags:\n  - Distributed Tracing\n  - Observability\n  - OpenTelemetry\n  - Performance\n  - Debugging\n  - Grafana\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TEMPO_BASE_URL: TEMPO_BASE_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: tempo\n    baseUri: '{{TEMPO_BASE_URL}}'\n    description: Grafana Tempo HTTP API\n    resources:\n    - name: traces\n      path: /api/traces/{traceID}\n      description: Retrieve traces by ID\n      operations:\n      - name: get-trace\n        method: GET\n        description: Get a complete trace by its trace ID\n        inputParameters:\n\
  \        - name: traceID\n          in: path\n          type: string\n          required: true\n          description: Hexadecimal trace identifier\n        - name: start\n          in: query\n          type: integer\n          required: false\n          description: Unix epoch start time (seconds)\n        - name: end\n          in: query\n          type: integer\n          required: false\n          description: Unix epoch end time (seconds)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /api/search\n      description: Search traces using TraceQL\n      operations:\n      - name: search-traces\n        method: GET\n        description: Search traces with TraceQL query\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: TraceQL query string\n        - name: minDuration\n          in: query\n\
  \          type: string\n          required: false\n          description: Minimum duration filter\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results\n        - name: start\n          in: query\n          type: integer\n          required: false\n          description: Start time (Unix epoch)\n        - name: end\n          in: query\n          type: integer\n          required: false\n          description: End time (Unix epoch)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tag-keys\n      path: /api/search/tags\n      description: List tag keys in trace data\n      operations:\n      - name: list-tag-keys\n        method: GET\n        description: List all tag keys present in trace data\n        inputParameters:\n        - name: scope\n          in: query\n          type: string\n          required: false\n\
  \          description: Attribute scope (span, resource, intrinsic)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tag-values\n      path: /api/search/tag/{tagName}/values\n      description: List values for a tag key\n      operations:\n      - name: list-tag-values\n        method: GET\n        description: List distinct values for a tag key\n        inputParameters:\n        - name: tagName\n          in: path\n          type: string\n          required: true\n          description: Tag key name\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: TraceQL context query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics\n      path: /api/metrics/query_range\n      description: Generate time-series metrics from trace data\n      operations:\n\
  \      - name: query-metrics-range\n        method: GET\n        description: Generate metrics from traces using TraceQL metrics\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: TraceQL metrics expression\n        - name: start\n          in: query\n          type: integer\n          required: true\n          description: Start time (Unix epoch)\n        - name: end\n          in: query\n          type: integer\n          required: true\n          description: End time (Unix epoch)\n        - name: step\n          in: query\n          type: string\n          required: false\n          description: Query step interval\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: distributed-tracing-api\n    description: Unified REST API for Grafana Tempo distributed tracing\
  \ operations.\n    resources:\n    - path: /v1/traces/{traceID}\n      name: traces\n      description: Trace retrieval by ID\n      operations:\n      - method: GET\n        name: get-trace\n        description: Get a complete distributed trace by its trace ID\n        call: tempo.get-trace\n        with:\n          traceID: rest.traceID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search\n      name: search\n      description: Trace search using TraceQL\n      operations:\n      - method: GET\n        name: search-traces\n        description: Search traces with TraceQL query\n        call: tempo.search-traces\n        with:\n          q: rest.q\n          start: rest.start\n          end: rest.end\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tags\n      name: tag-keys\n      description: Tag key discovery\n      operations:\n      - method: GET\n        name: list-tag-keys\n\
  \        description: List all tag keys present in trace data\n        call: tempo.list-tag-keys\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tags/{tagName}/values\n      name: tag-values\n      description: Tag value discovery\n      operations:\n      - method: GET\n        name: list-tag-values\n        description: List distinct values for a tag key\n        call: tempo.list-tag-values\n        with:\n          tagName: rest.tagName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics\n      name: metrics\n      description: Trace-based metrics\n      operations:\n      - method: GET\n        name: query-metrics\n        description: Generate time-series metrics from trace data\n        call: tempo.query-metrics-range\n        with:\n          q: rest.q\n          start: rest.start\n          end: rest.end\n          step: rest.step\n        outputParameters:\n        - type: object\n      \
  \    mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: distributed-tracing-mcp\n    transport: http\n    description: MCP server for AI-assisted distributed tracing investigation and performance analysis.\n    tools:\n    - name: get-trace\n      description: Retrieve a complete distributed trace to see all service calls and latencies\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tempo.get-trace\n      with:\n        traceID: tools.traceID\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-traces\n      description: Search for traces matching a TraceQL query (e.g. find slow requests, errors)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tempo.search-traces\n      with:\n        q: tools.q\n        start: tools.start\n        end: tools.end\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-error-traces\n      description:\
  \ Find traces with errors in a time window\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tempo.search-traces\n      with:\n        q: '{status=error}'\n        start: tools.start\n        end: tools.end\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-slow-traces\n      description: Find traces exceeding a minimum duration threshold\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tempo.search-traces\n      with:\n        minDuration: tools.minDuration\n        start: tools.start\n        end: tools.end\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tag-keys\n      description: Discover all available trace attribute keys for building queries\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tempo.list-tag-keys\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tag-values\n      description: List\
  \ all values for a trace attribute (e.g. all service names)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tempo.list-tag-values\n      with:\n        tagName: tools.tagName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-error-rate\n      description: Generate error rate metrics for a service over time\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tempo.query-metrics-range\n      with:\n        q: tools.metricsQuery\n        start: tools.start\n        end: tools.end\n        step: tools.step\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
