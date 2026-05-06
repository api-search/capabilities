---
categories: []
consumed_apis: []
description: A workflow capability for an SRE investigating latency or errors in a distributed system. Combines Zipkin trace search, trace retrieval, and dependency analysis to surface root causes across microservices.
layout: capability
name: Distributed Tracing Investigation
operations: []
personas: []
provider_name: Zipkin
provider_slug: zipkin
search_terms:
- instruments services and consumes traces during development.
- sre investigation of latency or errors via traces and dependencies.
- operates the tracing infrastructure (zipkin server and storage).
- observability
- distributed tracing
- operates production systems and investigates incidents.
- microservices
- open source
slug: distributed-tracing-investigation
source_filename: distributed-tracing-investigation.yaml
source_heading: Capability Spec
source_yaml: "apiVersion: naftiko/v1\nkind: WorkflowCapability\nmetadata:\n  name: distributed-tracing-investigation\n  provider: zipkin\ninfo:\n  title: Distributed Tracing Investigation\n  description: >-\n    A workflow capability for an SRE investigating latency or errors in a\n    distributed system. Combines Zipkin trace search, trace retrieval, and\n    dependency analysis to surface root causes across microservices.\n  persona: Site Reliability Engineer\ncombines:\n  - api: zipkin-api-v2\n    capability: capabilities/shared/zipkin-api-v2.yaml\nmcp:\n  tools:\n    - name: list-services\n      description: List all services emitting spans into Zipkin.\n      operationId: getServices\n    - name: list-span-names\n      description: List span names for a given service.\n      operationId: getSpanNames\n    - name: search-traces\n      description: Search traces matching given query parameters.\n      operationId: getTraces\n    - name: get-trace\n      description: Retrieve a specific\
  \ trace by its ID.\n      operationId: getTrace\n    - name: get-dependencies\n      description: Retrieve service-to-service dependency links.\n      operationId: getDependencies\n    - name: health-check\n      description: Verify Zipkin server health.\n      operationId: getHealth\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/zipkin/refs/heads/main/capabilities/distributed-tracing-investigation.yaml
tags: []
tools: []
---
