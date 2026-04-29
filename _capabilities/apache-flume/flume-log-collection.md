---
categories:
- monitoring
consumed_apis:
- flume-monitoring
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
- data engineering
- log aggregation
- get flume agent metrics
- Platform Operator
- get all metrics for apache flume agent components (sources, channels, sinks)
- flume agent component metrics
- data collection
- operators monitoring flume agent health and throughput
- monitor flume agent metrics for log collection pipelines
- get all component metrics for a flume agent
- streaming
- engineers configuring and monitoring flume log collection pipelines
- Data Engineer
- collecting, aggregating, and moving log and event data
- apache flume
- etl
- apache
- get agent metrics
- monitoring
- open source
- agent component metrics and health monitoring
slug: flume-log-collection
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: \"Apache Flume Log Collection\"\n  description: \"Capability for monitoring Apache Flume log collection agents — tracking source throughput, channel fill levels, and sink drain rates. Designed for data engineers and platform operators managing log aggregation pipelines.\"\n  tags:\n    - Apache Flume\n    - Log Aggregation\n    - Data Collection\n    - Monitoring\n    - Data Engineering\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      FLUME_AGENT_URL: FLUME_AGENT_URL\ncapability:\n  consumes:\n    - import: flume-monitoring\n      location: ./shared/flume-monitoring.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: flume-collection-api\n      description: \"Unified REST API for Apache Flume log collection monitoring.\"\n      resources:\n        - path: /v1/metrics\n          name: metrics\n          description: Flume agent component metrics\n          operations:\n\
  \            - method: GET\n              name: get-agent-metrics\n              description: Get all component metrics for a Flume agent\n              call: \"flume-monitoring.get-metrics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9090\n      namespace: flume-collection-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Apache Flume log collection monitoring.\"\n      tools:\n        - name: get-flume-agent-metrics\n          description: Get all metrics for Apache Flume agent components (sources, channels, sinks)\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"flume-monitoring.get-metrics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
