---
categories:
- monitoring
consumed_apis: []
description: Unified workflow for developers and operations teams to analyze distributed traces, visualize service maps, manage sampling rules, and investigate application performance insights using Amazon X-Ray.
layout: capability
name: Amazon X-Ray Distributed Tracing
operations:
- description: Get trace summaries for a time range.
  method: GET
  name: get-trace-summaries
  path: /v1/traces
- description: Get the service map.
  method: GET
  name: get-service-graph
  path: /v1/service-map
- description: Get sampling rules.
  method: GET
  name: get-sampling-rules
  path: /v1/sampling-rules
- description: Get trace groups.
  method: GET
  name: get-groups
  path: /v1/groups
- description: Get insight summaries.
  method: GET
  name: get-insight-summaries
  path: /v1/insights
personas: []
provider_name: Amazon X-Ray
provider_slug: amazon-xray
search_terms:
- aws
- application performance
- service dependency visualization.
- get service graph
- application tracing and service map visualization
- get all trace sampling rules to understand data collection configuration.
- Developer
- get insight summaries
- get trace summaries for a time range.
- retrieve complete trace documents for specific trace ids.
- get x-ray groups used to filter and organize traces.
- trace data access and analysis.
- get trace groups.
- Site Reliability Engineer
- root cause analysis using distributed trace data
- get insight summaries.
- monitoring
- get summaries of distributed traces for a specified time range.
- workflow for developers and operations teams to analyze traces, service maps, sampling rules, groups, and performance insights.
- application performance insights.
- analyzes traces to debug application issues.
- monitors service health and performance using x-ray.
- get groups
- observability
- get trace summaries
- batch get traces
- trace filtering groups.
- get summaries of x-ray insights identifying anomalies and performance issues.
- get sampling rules.
- get the service map showing inter-service dependencies and request flow.
- get sampling rules
- get the service map.
- latency analysis and bottleneck identification
- distributed tracing
- trace sampling configuration.
- debugging
slug: distributed-tracing
source_filename: distributed-tracing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon X-Ray Distributed Tracing\n  description: Unified workflow for developers and operations teams to analyze distributed traces, visualize service maps,\n    manage sampling rules, and investigate application performance insights using Amazon X-Ray.\n  tags:\n  - AWS\n  - Distributed Tracing\n  - Observability\n  - Application Performance\n  - Debugging\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: xray\n    baseUri: https://xray.us-east-1.amazonaws.com\n    description: Amazon X-Ray REST API for distributed tracing.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: traces\n      path: /Traces\n      description:\
  \ Retrieve distributed trace data.\n      operations:\n      - name: batch-get-traces\n        method: POST\n        description: Retrieve trace documents for a list of trace IDs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            TraceIds: '{{tools.trace_ids}}'\n    - name: trace-summaries\n      path: /TraceSummaries\n      description: Get trace summaries for a time range.\n      operations:\n      - name: get-trace-summaries\n        method: POST\n        description: Retrieve trace summaries for a specified time range.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            StartTime: '{{tools.start_time}}'\n            EndTime: '{{tools.end_time}}'\n    - name: service-graph\n      path: /ServiceGraph\n\
  \      description: Get service map for distributed applications.\n      operations:\n      - name: get-service-graph\n        method: POST\n        description: Get a document that describes the services connected in a request call chain.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            StartTime: '{{tools.start_time}}'\n            EndTime: '{{tools.end_time}}'\n    - name: sampling-rules\n      path: /GetSamplingRules\n      description: Manage trace sampling rules.\n      operations:\n      - name: get-sampling-rules\n        method: POST\n        description: Retrieve all sampling rules.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /GetGroups\n      description: Manage X-Ray groups for filtering traces.\n      operations:\n \
  \     - name: get-groups\n        method: POST\n        description: Retrieve all groups.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights\n      path: /GetInsightSummaries\n      description: Get X-Ray insights about application anomalies.\n      operations:\n      - name: get-insight-summaries\n        method: POST\n        description: Retrieve summaries of X-Ray insights.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: distributed-tracing-api\n    description: Unified REST API for Amazon X-Ray distributed tracing analysis.\n    resources:\n    - path: /v1/traces\n      name: traces\n      description: Trace data access and analysis.\n      operations:\n      - method: GET\n        name: get-trace-summaries\n        description: Get trace summaries\
  \ for a time range.\n        call: xray.get-trace-summaries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/service-map\n      name: service-map\n      description: Service dependency visualization.\n      operations:\n      - method: GET\n        name: get-service-graph\n        description: Get the service map.\n        call: xray.get-service-graph\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sampling-rules\n      name: sampling-rules\n      description: Trace sampling configuration.\n      operations:\n      - method: GET\n        name: get-sampling-rules\n        description: Get sampling rules.\n        call: xray.get-sampling-rules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups\n      name: groups\n      description: Trace filtering groups.\n      operations:\n      - method: GET\n        name: get-groups\n        description: Get trace groups.\n\
  \        call: xray.get-groups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/insights\n      name: insights\n      description: Application performance insights.\n      operations:\n      - method: GET\n        name: get-insight-summaries\n        description: Get insight summaries.\n        call: xray.get-insight-summaries\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: distributed-tracing-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon X-Ray distributed tracing analysis.\n    tools:\n    - name: get-trace-summaries\n      description: Get summaries of distributed traces for a specified time range.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: xray.get-trace-summaries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batch-get-traces\n      description: Retrieve complete trace documents\
  \ for specific trace IDs.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: xray.batch-get-traces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-service-graph\n      description: Get the service map showing inter-service dependencies and request flow.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: xray.get-service-graph\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-sampling-rules\n      description: Get all trace sampling rules to understand data collection configuration.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: xray.get-sampling-rules\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-groups\n      description: Get X-Ray groups used to filter and organize traces.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: xray.get-groups\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: get-insight-summaries\n      description: Get summaries of X-Ray insights identifying anomalies and performance issues.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: xray.get-insight-summaries\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-xray/refs/heads/main/capabilities/distributed-tracing.yaml
tags:
- Distributed Tracing
- Observability
- Application Performance
- Debugging
tools:
- description: Get summaries of distributed traces for a specified time range.
  hints:
    openWorld: true
    readOnly: true
  name: get-trace-summaries
- description: Retrieve complete trace documents for specific trace IDs.
  hints:
    openWorld: false
    readOnly: true
  name: batch-get-traces
- description: Get the service map showing inter-service dependencies and request flow.
  hints:
    openWorld: true
    readOnly: true
  name: get-service-graph
- description: Get all trace sampling rules to understand data collection configuration.
  hints:
    openWorld: true
    readOnly: true
  name: get-sampling-rules
- description: Get X-Ray groups used to filter and organize traces.
  hints:
    openWorld: true
    readOnly: true
  name: get-groups
- description: Get summaries of X-Ray insights identifying anomalies and performance issues.
  hints:
    openWorld: true
    readOnly: true
  name: get-insight-summaries
---
