---
categories: []
consumed_apis: []
description: Observability workflow for platform operators to check KrakenD gateway health, inspect debug request flow, and pull extended runtime metrics from a running gateway instance.
layout: capability
name: KrakenD Gateway Observability
operations:
- description: Return the KrakenD gateway health status.
  method: GET
  name: get-health
  path: /v1/health
- description: Return request headers, query, method, and body.
  method: GET
  name: get-echo
  path: /v1/echo
- description: Return router, proxy, backend, and Go runtime metrics.
  method: GET
  name: get-stats
  path: /v1/stats
- description: GET against the KrakenD debug endpoint at a sub-path.
  method: GET
  name: debug-get
  path: /v1/debug
- description: POST against the KrakenD debug endpoint at a sub-path.
  method: POST
  name: debug-post
  path: /v1/debug
personas: []
provider_name: KrakenD
provider_slug: krakend
search_terms:
- issue a post against the krakend debug endpoint.
- post against the krakend debug endpoint at a sub-path.
- krakend
- issue a get against the krakend debug endpoint.
- debug get
- debug post
- get echo
- debug echo endpoint.
- return request headers, query, method, and body.
- return the krakend gateway health status.
- extended runtime metrics.
- open source
- gateway health.
- health
- observability
- get against the krakend debug endpoint at a sub-path.
- return router, proxy, backend, and go runtime metrics.
- echo endpoint for request inspection.
- api gateway
- go
- return request details from the krakend echo endpoint.
- return extended runtime metrics from krakend.
- aggregation
- get stats
- get health
slug: gateway-observability
source_filename: gateway-observability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: KrakenD Gateway Observability\n  description: Observability workflow for platform operators to check KrakenD gateway health, inspect debug request flow,\n    and pull extended runtime metrics from a running gateway instance.\n  tags:\n  - KrakenD\n  - API Gateway\n  - Observability\n  - Health\n  created: '2026-05-04'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    KRAKEND_GATEWAY_URL: KRAKEND_GATEWAY_URL\n    KRAKEND_METRICS_URL: KRAKEND_METRICS_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: krakend-service\n    baseUri: '{KRAKEND_GATEWAY_URL}'\n    description: KrakenD Service API for operational endpoints exposed by the gateway.\n    resources:\n    - name: health\n      path: /__health\n      description: Gateway health checks.\n      operations:\n      - name: get-health\n        method: GET\n        description: Return the health status of the KrakenD instance.\n        inputParameters: []\n     \
  \   outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: debug\n      path: /__debug/{path}\n      description: Echoing debug endpoint that logs request details.\n      operations:\n      - name: debug-get\n        method: GET\n        description: GET against the debug echo endpoint at the supplied sub-path.\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n          description: Arbitrary sub-path appended to /__debug.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: debug-post\n        method: POST\n        description: POST against the debug echo endpoint at the supplied sub-path.\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n          description: Arbitrary sub-path appended\
  \ to /__debug.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            payload: '{{tools.payload}}'\n    - name: echo\n      path: /__echo/\n      description: Echo endpoint returning request details.\n      operations:\n      - name: get-echo\n        method: GET\n        description: Return the headers, query string, method, path, and body of the request.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: krakend-metrics\n    baseUri: '{KRAKEND_METRICS_URL}'\n    description: KrakenD extended metrics endpoint exposed on a separate port.\n    resources:\n    - name: stats\n      path: /__stats/\n      description: Extended runtime metrics.\n      operations:\n      - name: get-stats\n        method: GET\n        description:\
  \ Return router, proxy, backend, and Go runtime statistics.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: krakend-observability-api\n    description: Unified REST API for KrakenD gateway operational checks.\n    resources:\n    - path: /v1/health\n      name: health\n      description: Gateway health.\n      operations:\n      - method: GET\n        name: get-health\n        description: Return the KrakenD gateway health status.\n        call: krakend-service.get-health\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/echo\n      name: echo\n      description: Echo endpoint for request inspection.\n      operations:\n      - method: GET\n        name: get-echo\n        description: Return request headers, query, method, and body.\n        call: krakend-service.get-echo\n      \
  \  outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stats\n      name: stats\n      description: Extended runtime metrics.\n      operations:\n      - method: GET\n        name: get-stats\n        description: Return router, proxy, backend, and Go runtime metrics.\n        call: krakend-metrics.get-stats\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/debug\n      name: debug\n      description: Debug echo endpoint.\n      operations:\n      - method: GET\n        name: debug-get\n        description: GET against the KrakenD debug endpoint at a sub-path.\n        call: krakend-service.debug-get\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: debug-post\n        description: POST against the KrakenD debug endpoint at a sub-path.\n        call: krakend-service.debug-post\n        with:\n          path: rest.path\n\
  \          payload: rest.payload\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: krakend-observability-mcp\n    transport: http\n    description: MCP server for AI-assisted KrakenD gateway operational checks.\n    tools:\n    - name: get-health\n      description: Return the KrakenD gateway health status.\n      hints:\n        readOnly: true\n      call: krakend-service.get-health\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-echo\n      description: Return request details from the KrakenD echo endpoint.\n      hints:\n        readOnly: true\n      call: krakend-service.get-echo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-stats\n      description: Return extended runtime metrics from KrakenD.\n      hints:\n        readOnly: true\n      call: krakend-metrics.get-stats\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: debug-get\n      description: Issue a GET against the KrakenD debug endpoint.\n      hints:\n        readOnly: true\n      call: krakend-service.debug-get\n      with:\n        path: tools.path\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: debug-post\n      description: Issue a POST against the KrakenD debug endpoint.\n      hints:\n        readOnly: false\n      call: krakend-service.debug-post\n      with:\n        path: tools.path\n        payload: tools.payload\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/krakend/refs/heads/main/capabilities/gateway-observability.yaml
tags:
- KrakenD
- API Gateway
- Observability
- Health
tools:
- description: Return the KrakenD gateway health status.
  hints:
    readOnly: true
  name: get-health
- description: Return request details from the KrakenD echo endpoint.
  hints:
    readOnly: true
  name: get-echo
- description: Return extended runtime metrics from KrakenD.
  hints:
    readOnly: true
  name: get-stats
- description: Issue a GET against the KrakenD debug endpoint.
  hints:
    readOnly: true
  name: debug-get
- description: Issue a POST against the KrakenD debug endpoint.
  hints:
    readOnly: false
  name: debug-post
---
