---
categories: []
consumed_apis:
- vector-api
description: Workflow capability for DevOps engineers monitoring Vector observability pipeline health. Provides health check access for integration with load balancers, Kubernetes probes, and monitoring systems.
layout: capability
name: Vector Pipeline Monitoring
operations:
- description: Check if the Vector pipeline is running and healthy.
  method: GET
  name: get-health
  path: /v1/health
personas: []
provider_name: Vector
provider_slug: vector
search_terms:
- traces
- get vector health
- open source
- rust
- observability
- collecting, transforming, and routing logs, metrics, and traces.
- engineer responsible for operating and monitoring observability data pipelines.
- DevOps Engineer
- vector pipeline health status.
- vector
- devops
- health monitoring workflow for vector pipeline instances.
- check the health status of a running vector observability pipeline instance. returns ok:true when healthy.
- monitoring
- logs
- metrics
- check if the vector pipeline is running and healthy.
- get health
- data pipeline
slug: pipeline-monitoring
source_filename: pipeline-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Vector Pipeline Monitoring\"\n  description: \"Workflow capability for DevOps engineers monitoring Vector observability pipeline health. Provides health check access for integration with load balancers, Kubernetes probes, and monitoring systems.\"\n  tags:\n    - Vector\n    - Observability\n    - Data Pipeline\n    - DevOps\n    - Monitoring\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VECTOR_API_ADDR: VECTOR_API_ADDR\n\ncapability:\n  consumes:\n    - import: vector-api\n      location: ./shared/observability-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: vector-pipeline-api\n      description: \"Unified REST API for Vector pipeline monitoring.\"\n      resources:\n        - path: /v1/health\n          name: health\n          description: \"Vector pipeline health status.\"\n          operations:\n            - method: GET\n              name:\
  \ get-health\n              description: \"Check if the Vector pipeline is running and healthy.\"\n              call: \"vector-api.get-health\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: vector-pipeline-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Vector pipeline monitoring.\"\n      tools:\n        - name: get-vector-health\n          description: \"Check the health status of a running Vector observability pipeline instance. Returns ok:true when healthy.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"vector-api.get-health\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vector/refs/heads/main/capabilities/pipeline-monitoring.yaml
tags:
- Vector
- Observability
- Data Pipeline
- DevOps
- Monitoring
tools:
- description: Check the health status of a running Vector observability pipeline instance. Returns ok:true when healthy.
  hints:
    openWorld: true
    readOnly: true
  name: get-vector-health
---
