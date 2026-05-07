---
categories:
- monitoring
consumed_apis: []
description: Capability for monitoring Apache Flume log collection agents — tracking source throughput, channel fill levels, and sink drain rates. Designed for data engineers and platform operators managing log aggregation pipelines.
layout: capability
name: Apache Flume Log Collection
operations:
- description: Get all component metrics for a Flume agent
  method: GET
  name: get-agent-metrics
  path: /v1/metrics
personas: []
provider_name: Apache Flume
provider_slug: apache-flume
search_terms:
- streaming
- Platform Operator
- collecting, aggregating, and moving log and event data
- data engineering
- apache flume
- operators monitoring flume agent health and throughput
- data collection
- monitoring
- open source
- monitor flume agent metrics for log collection pipelines
- engineers configuring and monitoring flume log collection pipelines
- get all metrics for apache flume agent components (sources, channels, sinks)
- flume agent component metrics
- get flume agent metrics
- apache
- agent component metrics and health monitoring
- Data Engineer
- get all component metrics for a flume agent
- etl
- log aggregation
- get agent metrics
slug: flume-log-collection
source_filename: flume-log-collection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apache Flume Log Collection\n  description: Capability for monitoring Apache Flume log collection agents — tracking source throughput, channel fill levels,\n    and sink drain rates. Designed for data engineers and platform operators managing log aggregation pipelines.\n  tags:\n  - Apache Flume\n  - Log Aggregation\n  - Data Collection\n  - Monitoring\n  - Data Engineering\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    FLUME_AGENT_URL: FLUME_AGENT_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: flume-monitoring\n    baseUri: http://localhost:41414\n    description: Apache Flume Agent Monitoring REST API\n    resources:\n    - name: metrics\n      path: /metrics\n      description: Agent component metrics\n      operations:\n      - name: get-metrics\n        method: GET\n        description: Retrieve all component metrics for the running Flume agent\n        inputParameters: []\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: flume-collection-api\n    description: Unified REST API for Apache Flume log collection monitoring.\n    resources:\n    - path: /v1/metrics\n      name: metrics\n      description: Flume agent component metrics\n      operations:\n      - method: GET\n        name: get-agent-metrics\n        description: Get all component metrics for a Flume agent\n        call: flume-monitoring.get-metrics\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: flume-collection-mcp\n    transport: http\n    description: MCP server for AI-assisted Apache Flume log collection monitoring.\n    tools:\n    - name: get-flume-agent-metrics\n      description: Get all metrics for Apache Flume agent components (sources, channels, sinks)\n      hints:\n        readOnly:\
  \ true\n        openWorld: true\n      call: flume-monitoring.get-metrics\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-flume/refs/heads/main/capabilities/flume-log-collection.yaml
tags:
- Apache Flume
- Log Aggregation
- Data Collection
- Monitoring
- Data Engineering
tools:
- description: Get all metrics for Apache Flume agent components (sources, channels, sinks)
  hints:
    openWorld: true
    readOnly: true
  name: get-flume-agent-metrics
---
