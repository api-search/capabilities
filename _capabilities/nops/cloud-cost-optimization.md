---
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
- list map resources
- create a scheduler
- create scheduler
- get map migration project details
- list resources in a map project
- get scheduler workload summary
- get workload summary
- costs
- finops
- list products in a map project
- list map projects
- cloud costs
- get workload recommendations
- optimization
- disable scheduler
- get scheduler workload recommendations
- list map migration projects
- enable a scheduler
- get utilization summary
- enable scheduler
- map migration projects
- get map project
- get utilization recommendations
- manually trigger a scheduler
- trigger scheduler
- nops
- disable a scheduler
- list map products
slug: cloud-cost-optimization
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
