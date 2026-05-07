---
categories: []
consumed_apis: []
description: The Jaeger Query API provides HTTP endpoints for retrieving trace data, service information, operations, and dependency graphs from the Jaeger distributed tracing backend. This API is exposed by the jaeger-query component and is used by the Jaeger UI and other clients to search and retrieve distributed traces collected across microservices.
layout: capability
name: Jaeger Query API
operations:
- description: Search traces
  method: GET
  name: searchtraces
  path: /api/traces
- description: Get a trace by ID
  method: GET
  name: gettrace
  path: /api/traces/{traceID}
- description: Get all services
  method: GET
  name: getservices
  path: /api/services
- description: Get operations for a service
  method: GET
  name: getoperations
  path: /api/services/{service}/operations
- description: Get service dependency graph
  method: GET
  name: getdependencies
  path: /api/dependencies
- description: Get latency metrics
  method: GET
  name: getlatencymetrics
  path: /api/metrics/latencies
- description: Get call rate metrics
  method: GET
  name: getcallmetrics
  path: /api/metrics/calls
- description: Get error rate metrics
  method: GET
  name: geterrormetrics
  path: /api/metrics/errors
- description: Get minimum step duration
  method: GET
  name: getminstep
  path: /api/metrics/minstep
personas: []
provider_name: Jaeger
provider_slug: jaeger
search_terms:
- get all services
- distributed tracing
- search traces
- getdependencies
- api
- getminstep
- geterrormetrics
- monitoring
- jaeger
- getcallmetrics
- get call rate metrics
- observability
- searchtraces
- get operations for a service
- get a trace by id
- get minimum step duration
- gettrace
- get service dependency graph
- getlatencymetrics
- getoperations
- getservices
- get error rate metrics
- microservices
- get latency metrics
slug: jaeger-capability
source_filename: jaeger-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Jaeger Query API\n  description: The Jaeger Query API provides HTTP endpoints for retrieving trace data, service information, operations, and\n    dependency graphs from the Jaeger distributed tracing backend. This API is exposed by the jaeger-query component and is\n    used by the Jaeger UI and other clients to search and retrieve distributed traces collected across microservices.\n  tags:\n  - Jaeger\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: jaeger\n    baseUri: http://localhost:16686\n    description: Jaeger Query API HTTP API.\n    resources:\n    - name: api-traces\n      path: /api/traces\n      operations:\n      - name: searchtraces\n        method: GET\n        description: Search traces\n        inputParameters:\n        - name: service\n          in: query\n          type: string\n          required: true\n          description: The service name to\
  \ filter traces by.\n        - name: operation\n          in: query\n          type: string\n          description: The operation name to filter traces by.\n        - name: tags\n          in: query\n          type: string\n          description: Tags to filter by in JSON format, e.g. {\"http.status_code\":\"200\"}.\n        - name: start\n          in: query\n          type: integer\n          description: Start time as Unix microseconds.\n        - name: end\n          in: query\n          type: integer\n          description: End time as Unix microseconds.\n        - name: minDuration\n          in: query\n          type: string\n          description: Minimum trace duration filter, specified as a duration string (e.g. 1.2s, 100ms, 500us).\n        - name: maxDuration\n          in: query\n          type: string\n          description: Maximum trace duration filter, specified as a duration string (e.g. 1.2s, 100ms, 500us).\n        - name: limit\n          in: query\n          type:\
  \ integer\n          description: Maximum number of traces to return.\n        - name: lookback\n          in: query\n          type: string\n          description: How far back to search for traces, specified as a duration string (e.g. 1h, 2d). Only used if start\n            and end are not set.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-traces-traceid\n      path: /api/traces/{traceID}\n      operations:\n      - name: gettrace\n        method: GET\n        description: Get a trace by ID\n        inputParameters:\n        - name: traceID\n          in: path\n          type: string\n          required: true\n          description: The trace ID in hexadecimal format (16 or 32 hex characters).\n        - name: raw\n          in: query\n          type: boolean\n          description: Return raw trace data without post-processing.\n        - name: prettyPrint\n          in: query\n      \
  \    type: boolean\n          description: Pretty-print the JSON response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-services\n      path: /api/services\n      operations:\n      - name: getservices\n        method: GET\n        description: Get all services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-services-service-operations\n      path: /api/services/{service}/operations\n      operations:\n      - name: getoperations\n        method: GET\n        description: Get operations for a service\n        inputParameters:\n        - name: service\n          in: path\n          type: string\n          required: true\n          description: The service name.\n        - name: spanKind\n          in: query\n          type: string\n          description: Filter operations by span kind (e.g. server,\
  \ client, producer, consumer).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-dependencies\n      path: /api/dependencies\n      operations:\n      - name: getdependencies\n        method: GET\n        description: Get service dependency graph\n        inputParameters:\n        - name: endTs\n          in: query\n          type: integer\n          required: true\n          description: End timestamp in Unix milliseconds.\n        - name: lookback\n          in: query\n          type: integer\n          required: true\n          description: Duration to look back from endTs in milliseconds.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-metrics-latencies\n      path: /api/metrics/latencies\n      operations:\n      - name: getlatencymetrics\n        method: GET\n        description: Get latency metrics\n\
  \        inputParameters:\n        - name: service\n          in: query\n          type: string\n          required: true\n          description: The service name.\n        - name: quantile\n          in: query\n          type: number\n          required: true\n          description: The quantile to retrieve (e.g. 0.5, 0.75, 0.95, 0.99).\n        - name: endTs\n          in: query\n          type: integer\n          description: End timestamp in Unix milliseconds.\n        - name: lookback\n          in: query\n          type: integer\n          description: Duration to look back in milliseconds.\n        - name: step\n          in: query\n          type: integer\n          description: Step duration for bucketing in milliseconds.\n        - name: ratePer\n          in: query\n          type: integer\n          description: Rate normalization duration in milliseconds.\n        - name: spanKind\n          in: query\n          type: string\n          description: Filter by span kind.\n \
  \       outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-metrics-calls\n      path: /api/metrics/calls\n      operations:\n      - name: getcallmetrics\n        method: GET\n        description: Get call rate metrics\n        inputParameters:\n        - name: service\n          in: query\n          type: string\n          required: true\n          description: The service name.\n        - name: endTs\n          in: query\n          type: integer\n          description: End timestamp in Unix milliseconds.\n        - name: lookback\n          in: query\n          type: integer\n          description: Duration to look back in milliseconds.\n        - name: step\n          in: query\n          type: integer\n          description: Step duration for bucketing in milliseconds.\n        - name: ratePer\n          in: query\n          type: integer\n          description: Rate normalization duration in milliseconds.\n\
  \        - name: spanKind\n          in: query\n          type: string\n          description: Filter by span kind.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-metrics-errors\n      path: /api/metrics/errors\n      operations:\n      - name: geterrormetrics\n        method: GET\n        description: Get error rate metrics\n        inputParameters:\n        - name: service\n          in: query\n          type: string\n          required: true\n          description: The service name.\n        - name: endTs\n          in: query\n          type: integer\n          description: End timestamp in Unix milliseconds.\n        - name: lookback\n          in: query\n          type: integer\n          description: Duration to look back in milliseconds.\n        - name: step\n          in: query\n          type: integer\n          description: Step duration for bucketing in milliseconds.\n        -\
  \ name: ratePer\n          in: query\n          type: integer\n          description: Rate normalization duration in milliseconds.\n        - name: spanKind\n          in: query\n          type: string\n          description: Filter by span kind.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-metrics-minstep\n      path: /api/metrics/minstep\n      operations:\n      - name: getminstep\n        method: GET\n        description: Get minimum step duration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: jaeger-rest\n    description: REST adapter for Jaeger Query API.\n    resources:\n    - path: /api/traces\n      name: searchtraces\n      operations:\n      - method: GET\n        name: searchtraces\n        description: Search traces\n        call: jaeger.searchtraces\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/traces/{traceID}\n      name: gettrace\n      operations:\n      - method: GET\n        name: gettrace\n        description: Get a trace by ID\n        call: jaeger.gettrace\n        with:\n          traceID: rest.traceID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/services\n      name: getservices\n      operations:\n      - method: GET\n        name: getservices\n        description: Get all services\n        call: jaeger.getservices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/services/{service}/operations\n      name: getoperations\n      operations:\n      - method: GET\n        name: getoperations\n        description: Get operations for a service\n        call: jaeger.getoperations\n        with:\n          service: rest.service\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /api/dependencies\n      name: getdependencies\n      operations:\n      - method: GET\n        name: getdependencies\n        description: Get service dependency graph\n        call: jaeger.getdependencies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/metrics/latencies\n      name: getlatencymetrics\n      operations:\n      - method: GET\n        name: getlatencymetrics\n        description: Get latency metrics\n        call: jaeger.getlatencymetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/metrics/calls\n      name: getcallmetrics\n      operations:\n      - method: GET\n        name: getcallmetrics\n        description: Get call rate metrics\n        call: jaeger.getcallmetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/metrics/errors\n      name: geterrormetrics\n      operations:\n      - method: GET\n        name: geterrormetrics\n\
  \        description: Get error rate metrics\n        call: jaeger.geterrormetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/metrics/minstep\n      name: getminstep\n      operations:\n      - method: GET\n        name: getminstep\n        description: Get minimum step duration\n        call: jaeger.getminstep\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: jaeger-mcp\n    transport: http\n    description: MCP adapter for Jaeger Query API for AI agent use.\n    tools:\n    - name: searchtraces\n      description: Search traces\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jaeger.searchtraces\n      with:\n        service: tools.service\n        operation: tools.operation\n        tags: tools.tags\n        start: tools.start\n        end: tools.end\n        minDuration: tools.minDuration\n        maxDuration:\
  \ tools.maxDuration\n        limit: tools.limit\n        lookback: tools.lookback\n      inputParameters:\n      - name: service\n        type: string\n        description: The service name to filter traces by.\n        required: true\n      - name: operation\n        type: string\n        description: The operation name to filter traces by.\n      - name: tags\n        type: string\n        description: Tags to filter by in JSON format, e.g. {\"http.status_code\":\"200\"}.\n      - name: start\n        type: integer\n        description: Start time as Unix microseconds.\n      - name: end\n        type: integer\n        description: End time as Unix microseconds.\n      - name: minDuration\n        type: string\n        description: Minimum trace duration filter, specified as a duration string (e.g. 1.2s, 100ms, 500us).\n      - name: maxDuration\n        type: string\n        description: Maximum trace duration filter, specified as a duration string (e.g. 1.2s, 100ms, 500us).\n     \
  \ - name: limit\n        type: integer\n        description: Maximum number of traces to return.\n      - name: lookback\n        type: string\n        description: How far back to search for traces, specified as a duration string (e.g. 1h, 2d). Only used if start and\n          end are not set.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettrace\n      description: Get a trace by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jaeger.gettrace\n      with:\n        traceID: tools.traceID\n        raw: tools.raw\n        prettyPrint: tools.prettyPrint\n      inputParameters:\n      - name: traceID\n        type: string\n        description: The trace ID in hexadecimal format (16 or 32 hex characters).\n        required: true\n      - name: raw\n        type: boolean\n        description: Return raw trace data without post-processing.\n      - name: prettyPrint\n        type: boolean\n     \
  \   description: Pretty-print the JSON response.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getservices\n      description: Get all services\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jaeger.getservices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getoperations\n      description: Get operations for a service\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jaeger.getoperations\n      with:\n        service: tools.service\n        spanKind: tools.spanKind\n      inputParameters:\n      - name: service\n        type: string\n        description: The service name.\n        required: true\n      - name: spanKind\n        type: string\n        description: Filter operations by span kind (e.g. server, client, producer, consumer).\n      outputParameters:\n      - type: object\n        mapping: $.\n   \
  \ - name: getdependencies\n      description: Get service dependency graph\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jaeger.getdependencies\n      with:\n        endTs: tools.endTs\n        lookback: tools.lookback\n      inputParameters:\n      - name: endTs\n        type: integer\n        description: End timestamp in Unix milliseconds.\n        required: true\n      - name: lookback\n        type: integer\n        description: Duration to look back from endTs in milliseconds.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlatencymetrics\n      description: Get latency metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jaeger.getlatencymetrics\n      with:\n        service: tools.service\n        quantile: tools.quantile\n        endTs: tools.endTs\n        lookback: tools.lookback\n        step: tools.step\n\
  \        ratePer: tools.ratePer\n        spanKind: tools.spanKind\n      inputParameters:\n      - name: service\n        type: string\n        description: The service name.\n        required: true\n      - name: quantile\n        type: number\n        description: The quantile to retrieve (e.g. 0.5, 0.75, 0.95, 0.99).\n        required: true\n      - name: endTs\n        type: integer\n        description: End timestamp in Unix milliseconds.\n      - name: lookback\n        type: integer\n        description: Duration to look back in milliseconds.\n      - name: step\n        type: integer\n        description: Step duration for bucketing in milliseconds.\n      - name: ratePer\n        type: integer\n        description: Rate normalization duration in milliseconds.\n      - name: spanKind\n        type: string\n        description: Filter by span kind.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcallmetrics\n      description: Get call rate metrics\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jaeger.getcallmetrics\n      with:\n        service: tools.service\n        endTs: tools.endTs\n        lookback: tools.lookback\n        step: tools.step\n        ratePer: tools.ratePer\n        spanKind: tools.spanKind\n      inputParameters:\n      - name: service\n        type: string\n        description: The service name.\n        required: true\n      - name: endTs\n        type: integer\n        description: End timestamp in Unix milliseconds.\n      - name: lookback\n        type: integer\n        description: Duration to look back in milliseconds.\n      - name: step\n        type: integer\n        description: Step duration for bucketing in milliseconds.\n      - name: ratePer\n        type: integer\n        description: Rate normalization duration in milliseconds.\n      - name: spanKind\n        type: string\n        description: Filter by span kind.\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: geterrormetrics\n      description: Get error rate metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jaeger.geterrormetrics\n      with:\n        service: tools.service\n        endTs: tools.endTs\n        lookback: tools.lookback\n        step: tools.step\n        ratePer: tools.ratePer\n        spanKind: tools.spanKind\n      inputParameters:\n      - name: service\n        type: string\n        description: The service name.\n        required: true\n      - name: endTs\n        type: integer\n        description: End timestamp in Unix milliseconds.\n      - name: lookback\n        type: integer\n        description: Duration to look back in milliseconds.\n      - name: step\n        type: integer\n        description: Step duration for bucketing in milliseconds.\n      - name: ratePer\n        type: integer\n        description: Rate normalization duration in milliseconds.\n\
  \      - name: spanKind\n        type: string\n        description: Filter by span kind.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getminstep\n      description: Get minimum step duration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jaeger.getminstep\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/jaeger/refs/heads/main/capabilities/jaeger-capability.yaml
tags:
- Jaeger
- API
tools:
- description: Search traces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchtraces
- description: Get a trace by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettrace
- description: Get all services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getservices
- description: Get operations for a service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getoperations
- description: Get service dependency graph
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdependencies
- description: Get latency metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlatencymetrics
- description: Get call rate metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcallmetrics
- description: Get error rate metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: geterrormetrics
- description: Get minimum step duration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getminstep
---
