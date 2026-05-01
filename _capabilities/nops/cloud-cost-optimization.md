---
categories: []
consumed_apis:
- nops
description: Unified cloud cost optimization capability combining MAP migration tracking, scheduler automation, and cost recommendations. Used by FinOps teams and cloud operations engineers.
layout: capability
name: nOps Cloud Cost Optimization
operations:
- description: List MAP migration projects
  method: GET
  name: list-map-projects
  path: /v1/map-projects
personas: []
provider_name: nOps
provider_slug: nops
search_terms:
- get scheduler workload recommendations
- optimization
- get scheduler workload summary
- list map resources
- list products in a map project
- get workload summary
- manually trigger a scheduler
- create a scheduler
- create scheduler
- get map project
- disable a scheduler
- list map products
- list map migration projects
- disable scheduler
- nops
- get workload recommendations
- trigger scheduler
- list resources in a map project
- get utilization summary
- enable scheduler
- get utilization recommendations
- costs
- enable a scheduler
- list map projects
- map migration projects
- get map migration project details
- finops
- cloud costs
slug: cloud-cost-optimization
source_filename: cloud-cost-optimization.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: \"nOps Cloud Cost Optimization\"\n  description: \"Unified cloud cost optimization capability combining MAP migration tracking, scheduler automation, and cost recommendations. Used by FinOps teams and cloud operations engineers.\"\n  tags: [nOps, FinOps, Cloud Costs, Optimization]\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\nbinds:\n  - namespace: env\n    keys:\n      NOPS_API_KEY: NOPS_API_KEY\ncapability:\n  consumes:\n    - import: nops\n      location: ./shared/nops.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: cloud-cost-optimization-api\n      description: \"Unified REST API for nOps cloud cost optimization.\"\n      resources:\n        - path: /v1/map-projects\n          name: map-projects\n          description: \"MAP migration projects\"\n          operations:\n            - { method: GET, name: list-map-projects, description: \"List MAP migration projects\", call: \"nops.list-map-projects\"\
  , outputParameters: [{ type: object, mapping: \"$.\" }] }\n    - type: mcp\n      port: 9090\n      namespace: cloud-cost-optimization-mcp\n      transport: http\n      description: \"MCP server for AI-assisted cloud cost optimization.\"\n      tools:\n        - { name: list-map-projects, description: \"List MAP migration projects\", hints: { readOnly: true }, call: \"nops.list-map-projects\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: get-map-project, description: \"Get MAP migration project details\", hints: { readOnly: true }, call: \"nops.get-map-project\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-map-products, description: \"List products in a MAP project\", hints: { readOnly: true }, call: \"nops.list-map-products\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: list-map-resources, description: \"List resources in a MAP project\", hints: { readOnly: true }, call: \"nops.list-map-resources\"\
  , outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: get-workload-recommendations, description: \"Get scheduler workload recommendations\", hints: { readOnly: true }, call: \"nops.get-workload-recommendations\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: get-workload-summary, description: \"Get scheduler workload summary\", hints: { readOnly: true }, call: \"nops.get-workload-summary\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: get-utilization-recommendations, description: \"Get utilization recommendations\", hints: { readOnly: true }, call: \"nops.get-utilization-recommendations\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: get-utilization-summary, description: \"Get utilization summary\", hints: { readOnly: true }, call: \"nops.get-utilization-summary\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: create-scheduler, description: \"Create\
  \ a scheduler\", call: \"nops.create-scheduler\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: trigger-scheduler, description: \"Manually trigger a scheduler\", call: \"nops.trigger-scheduler\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: enable-scheduler, description: \"Enable a scheduler\", call: \"nops.enable-scheduler\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n        - { name: disable-scheduler, description: \"Disable a scheduler\", call: \"nops.disable-scheduler\", outputParameters: [{ type: object, mapping: \"$.\" }] }\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/nops/refs/heads/main/capabilities/cloud-cost-optimization.yaml
tags:
- nOps
- FinOps
- Cloud Costs
- Optimization
tools:
- description: List MAP migration projects
  hints:
    readOnly: true
  name: list-map-projects
- description: Get MAP migration project details
  hints:
    readOnly: true
  name: get-map-project
- description: List products in a MAP project
  hints:
    readOnly: true
  name: list-map-products
- description: List resources in a MAP project
  hints:
    readOnly: true
  name: list-map-resources
- description: Get scheduler workload recommendations
  hints:
    readOnly: true
  name: get-workload-recommendations
- description: Get scheduler workload summary
  hints:
    readOnly: true
  name: get-workload-summary
- description: Get utilization recommendations
  hints:
    readOnly: true
  name: get-utilization-recommendations
- description: Get utilization summary
  hints:
    readOnly: true
  name: get-utilization-summary
- description: Create a scheduler
  hints: {}
  name: create-scheduler
- description: Manually trigger a scheduler
  hints: {}
  name: trigger-scheduler
- description: Enable a scheduler
  hints: {}
  name: enable-scheduler
- description: Disable a scheduler
  hints: {}
  name: disable-scheduler
---
