---
categories: []
consumed_apis: []
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
- get scheduler workload recommendations
- disable a scheduler
- enable a scheduler
- list map projects
- get map project
- list products in a map project
- get workload summary
- get workload recommendations
- optimization
- get map migration project details
- trigger scheduler
- create scheduler
- disable scheduler
- enable scheduler
- get utilization recommendations
- map migration projects
- get utilization summary
- manually trigger a scheduler
- cloud costs
- create a scheduler
- list resources in a map project
- get scheduler workload summary
- nops
- list map products
- list map migration projects
- costs
- finops
slug: cloud-cost-optimization
source_filename: cloud-cost-optimization.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: nOps Cloud Cost Optimization\n  description: Unified cloud cost optimization capability combining MAP migration tracking, scheduler automation, and cost\n    recommendations. Used by FinOps teams and cloud operations engineers.\n  tags:\n  - nOps\n  - FinOps\n  - Cloud Costs\n  - Optimization\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    NOPS_API_KEY: NOPS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: nops\n    baseUri: https://app.nops.io\n    description: nOps public API for MAP migration and scheduler operations.\n    authentication:\n      type: apikey\n      key: X-Nops-Api-Key\n      value: '{{NOPS_API_KEY}}'\n      placement: header\n    resources:\n    - name: map-migration\n      path: /c/v3/map-migration\n      description: MAP Migration operations\n      operations:\n      - name: list-map-projects\n        method: GET\n        description: List MAP migration projects\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-map-project\n        method: GET\n        description: Get MAP migration project details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-map-products\n        method: GET\n        description: List products in a MAP project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-map-resources\n        method: GET\n        description: List resources in a MAP project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scheduler\n      path: /svc\n      description: Essentials scheduler operations\n      operations:\n      - name: get-workload-recommendations\n        method:\
  \ GET\n        description: Get scheduler workload recommendations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-workload-summary\n        method: GET\n        description: Get scheduler workload summary\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-utilization-recommendations\n        method: GET\n        description: Get utilization recommendations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-utilization-summary\n        method: GET\n        description: Get utilization summary\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-scheduler\n        method: POST\n        description: Create a scheduler\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: trigger-scheduler\n        method: POST\n        description: Manually trigger a scheduler\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: enable-scheduler\n        method: POST\n        description: Enable a scheduler\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: disable-scheduler\n        method: POST\n        description: Disable a scheduler\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: cloud-cost-optimization-api\n    description: Unified REST API for nOps cloud cost optimization.\n    resources:\n    - path: /v1/map-projects\n\
  \      name: map-projects\n      description: MAP migration projects\n      operations:\n      - method: GET\n        name: list-map-projects\n        description: List MAP migration projects\n        call: nops.list-map-projects\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: cloud-cost-optimization-mcp\n    transport: http\n    description: MCP server for AI-assisted cloud cost optimization.\n    tools:\n    - name: list-map-projects\n      description: List MAP migration projects\n      hints:\n        readOnly: true\n      call: nops.list-map-projects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-map-project\n      description: Get MAP migration project details\n      hints:\n        readOnly: true\n      call: nops.get-map-project\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-map-products\n      description: List products in a MAP\
  \ project\n      hints:\n        readOnly: true\n      call: nops.list-map-products\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-map-resources\n      description: List resources in a MAP project\n      hints:\n        readOnly: true\n      call: nops.list-map-resources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-workload-recommendations\n      description: Get scheduler workload recommendations\n      hints:\n        readOnly: true\n      call: nops.get-workload-recommendations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-workload-summary\n      description: Get scheduler workload summary\n      hints:\n        readOnly: true\n      call: nops.get-workload-summary\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-utilization-recommendations\n      description: Get utilization recommendations\n      hints:\n        readOnly: true\n\
  \      call: nops.get-utilization-recommendations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-utilization-summary\n      description: Get utilization summary\n      hints:\n        readOnly: true\n      call: nops.get-utilization-summary\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-scheduler\n      description: Create a scheduler\n      call: nops.create-scheduler\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: trigger-scheduler\n      description: Manually trigger a scheduler\n      call: nops.trigger-scheduler\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: enable-scheduler\n      description: Enable a scheduler\n      call: nops.enable-scheduler\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: disable-scheduler\n      description: Disable a scheduler\n      call: nops.disable-scheduler\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n"
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
