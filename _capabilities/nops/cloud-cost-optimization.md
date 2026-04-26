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
- list map migration projects
- optimization
- finops
- manually trigger a scheduler
- get scheduler workload summary
- enable scheduler
- disable a scheduler
- trigger scheduler
- list map products
- create a scheduler
- costs
- get utilization summary
- create scheduler
- enable a scheduler
- get workload recommendations
- get utilization recommendations
- get map migration project details
- get scheduler workload recommendations
- get workload summary
- list map resources
- nops
- list products in a map project
- disable scheduler
- list map projects
- list resources in a map project
- cloud costs
- get map project
- map migration projects
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
