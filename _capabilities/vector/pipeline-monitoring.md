---
categories: []
consumed_apis: []
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
- get vector health
- DevOps Engineer
- devops
- data pipeline
- metrics
- logs
- monitoring
- health monitoring workflow for vector pipeline instances.
- vector pipeline health status.
- open source
- observability
- vector
- check the health status of a running vector observability pipeline instance. returns ok:true when healthy.
- rust
- check if the vector pipeline is running and healthy.
- traces
- engineer responsible for operating and monitoring observability data pipelines.
- get health
- collecting, transforming, and routing logs, metrics, and traces.
slug: pipeline-monitoring
source_filename: pipeline-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Vector Pipeline Monitoring\n  description: Workflow capability for DevOps engineers monitoring Vector observability pipeline health. Provides health check\n    access for integration with load balancers, Kubernetes probes, and monitoring systems.\n  tags:\n  - Vector\n  - Observability\n  - Data Pipeline\n  - DevOps\n  - Monitoring\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VECTOR_API_ADDR: VECTOR_API_ADDR\ncapability:\n  consumes:\n  - type: http\n    namespace: vector-api\n    baseUri: http://127.0.0.1:8686\n    description: Vector Observability HTTP API.\n    resources:\n    - name: health\n      path: /health\n      description: Vector instance health status.\n      operations:\n      - name: get-health\n        method: GET\n        description: Check if Vector is running normally.\n        outputRawFormat: json\n        outputParameters:\n        - name: ok\n          type: boolean\n\
  \          value: $.ok\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: vector-pipeline-api\n    description: Unified REST API for Vector pipeline monitoring.\n    resources:\n    - path: /v1/health\n      name: health\n      description: Vector pipeline health status.\n      operations:\n      - method: GET\n        name: get-health\n        description: Check if the Vector pipeline is running and healthy.\n        call: vector-api.get-health\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: vector-pipeline-mcp\n    transport: http\n    description: MCP server for AI-assisted Vector pipeline monitoring.\n    tools:\n    - name: get-vector-health\n      description: Check the health status of a running Vector observability pipeline instance. Returns ok:true when healthy.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: vector-api.get-health\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n"
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
