---
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
- get agent metrics
- open source
- Platform Operator
- flume agent component metrics
- get flume agent metrics
- apache
- etl
- Data Engineer
- agent component metrics and health monitoring
- monitor flume agent metrics for log collection pipelines
- streaming
- get all metrics for apache flume agent components (sources, channels, sinks)
- monitoring
- data collection
- apache flume
- log aggregation
- engineers configuring and monitoring flume log collection pipelines
- operators monitoring flume agent health and throughput
- collecting, aggregating, and moving log and event data
- get all component metrics for a flume agent
- data engineering
slug: flume-log-collection
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
