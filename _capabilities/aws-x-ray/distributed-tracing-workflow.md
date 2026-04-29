---
categories:
- monitoring
consumed_apis:
- x-ray
description: Workflow capability for collecting, analyzing, and visualizing distributed traces with AWS X-Ray.
layout: capability
name: AWS X-Ray Distributed Tracing Workflow
operations: []
personas: []
provider_name: AWS X-Ray
provider_slug: aws-x-ray
search_terms:
- batch_get_traces
- get active sampling rules controlling trace collection
- performance
- aws
- retrieve full trace details by trace ids
- list x-ray groups for filtering traces
- microservices
- create_group
- create a new x-ray group with a filter expression
- get_groups
- distributed tracing
- get a service graph showing service dependencies and health
- get_sampling_rules
- observability
- get_trace_summaries
- get summaries of x-ray traces for a time period
- get_service_graph
- debugging
slug: distributed-tracing-workflow
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: AWS X-Ray Distributed Tracing Workflow\n  description: Workflow capability for collecting, analyzing, and visualizing distributed traces with AWS X-Ray.\n  tags:\n    - Observability\n    - Distributed Tracing\n    - Debugging\n    - Performance\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n    - import: x-ray\n      location: ./shared/x-ray.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: workflow-api\n      resources:\n        - label: Submit Trace Segments\n          method: POST\n          path: /traces\n        - label: Get Trace Summaries\n          method: GET\n          path: /traces\n        - label: Get Service Graph\n          method: GET\n          path: /service-graph\n        - label: Get Groups\n \
  \         method: GET\n          path: /groups\n        - label: Create Group\n          method: POST\n          path: /groups\n        - label: Get Sampling Rules\n          method: GET\n          path: /sampling-rules\n    - type: mcp\n      port: 9090\n      namespace: workflow-mcp\n      transport: http\n      tools:\n        - name: get_trace_summaries\n          description: Get summaries of X-Ray traces for a time period\n        - name: get_service_graph\n          description: Get a service graph showing service dependencies and health\n        - name: batch_get_traces\n          description: Retrieve full trace details by trace IDs\n        - name: get_groups\n          description: List X-Ray groups for filtering traces\n        - name: create_group\n          description: Create a new X-Ray group with a filter expression\n        - name: get_sampling_rules\n          description: Get active sampling rules controlling trace collection\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/aws-x-ray/refs/heads/main/capabilities/distributed-tracing-workflow.yaml
tags:
- Observability
- Distributed Tracing
- Debugging
- Performance
tools:
- description: Get summaries of X-Ray traces for a time period
  hints: {}
  name: get_trace_summaries
- description: Get a service graph showing service dependencies and health
  hints: {}
  name: get_service_graph
- description: Retrieve full trace details by trace IDs
  hints: {}
  name: batch_get_traces
- description: List X-Ray groups for filtering traces
  hints: {}
  name: get_groups
- description: Create a new X-Ray group with a filter expression
  hints: {}
  name: create_group
- description: Get active sampling rules controlling trace collection
  hints: {}
  name: get_sampling_rules
---
