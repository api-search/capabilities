---
categories: []
consumed_apis: []
description: The OpenCost API provides real-time and historical reporting of Kubernetes workload costs and underlying cloud infrastructure spend. OpenCost is an open source CNCF specification and reference implementation for Kubernetes cost monitoring and FinOps.
layout: capability
name: OpenCost API
operations:
- description: Query Kubernetes workload cost allocations
  method: GET
  name: getallocation
  path: /allocation
- description: Query underlying cloud infrastructure asset costs
  method: GET
  name: getassets
  path: /assets
- description: Query cloud provider billing data
  method: GET
  name: getcloudcost
  path: /cloudCost
- description: Custom cost timeseries data
  method: GET
  name: getcustomcosttimeseries
  path: /customCost/timeseries
- description: Custom cost totals
  method: GET
  name: getcustomcosttotal
  path: /customCost/total
personas: []
provider_name: OpenCost
provider_slug: opencost
search_terms:
- custom cost timeseries data
- query underlying cloud infrastructure asset costs
- getcloudcost
- cloud cost management
- observability
- query kubernetes workload cost allocations
- getassets
- getcustomcosttotal
- finops
- getallocation
- getcustomcosttimeseries
- kubernetes
- custom cost totals
- cncf
- api
- opencost
- query cloud provider billing data
slug: opencost-capability
source_filename: opencost-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OpenCost API\n  description: The OpenCost API provides real-time and historical reporting of Kubernetes workload costs and underlying cloud\n    infrastructure spend. OpenCost is an open source CNCF specification and reference implementation for Kubernetes cost monitoring\n    and FinOps.\n  tags:\n  - Opencost\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: opencost\n    baseUri: http://localhost:9003\n    description: OpenCost API HTTP API.\n    resources:\n    - name: allocation\n      path: /allocation\n      operations:\n      - name: getallocation\n        method: GET\n        description: Query Kubernetes workload cost allocations\n        inputParameters:\n        - name: window\n          in: query\n          type: string\n          required: true\n          description: Duration of time over which to query.\n        - name: aggregate\n          in: query\n\
  \          type: string\n          description: Field by which to aggregate (namespace, controller, label:app, etc.).\n        - name: step\n          in: query\n          type: string\n          description: Duration of a single allocation set.\n        - name: accumulate\n          in: query\n          type: boolean\n        - name: resolution\n          in: query\n          type: string\n        - name: includeIdle\n          in: query\n          type: boolean\n        - name: shareIdle\n          in: query\n          type: boolean\n        - name: idleByNode\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets\n      path: /assets\n      operations:\n      - name: getassets\n        method: GET\n        description: Query underlying cloud infrastructure asset costs\n        inputParameters:\n        - name: window\n          in: query\n       \
  \   type: string\n          required: true\n        - name: aggregate\n          in: query\n          type: string\n        - name: accumulate\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloudcost\n      path: /cloudCost\n      operations:\n      - name: getcloudcost\n        method: GET\n        description: Query cloud provider billing data\n        inputParameters:\n        - name: window\n          in: query\n          type: string\n          required: true\n        - name: aggregate\n          in: query\n          type: string\n        - name: accumulate\n          in: query\n          type: string\n        - name: filter\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customcost-timeseries\n      path: /customCost/timeseries\n\
  \      operations:\n      - name: getcustomcosttimeseries\n        method: GET\n        description: Custom cost timeseries data\n        inputParameters:\n        - name: window\n          in: query\n          type: string\n          required: true\n        - name: aggregate\n          in: query\n          type: string\n        - name: accumulate\n          in: query\n          type: string\n        - name: filter\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customcost-total\n      path: /customCost/total\n      operations:\n      - name: getcustomcosttotal\n        method: GET\n        description: Custom cost totals\n        inputParameters:\n        - name: window\n          in: query\n          type: string\n          required: true\n        - name: aggregate\n          in: query\n          type: string\n        - name: accumulate\n          in:\
  \ query\n          type: string\n        - name: filter\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: opencost-rest\n    description: REST adapter for OpenCost API.\n    resources:\n    - path: /allocation\n      name: getallocation\n      operations:\n      - method: GET\n        name: getallocation\n        description: Query Kubernetes workload cost allocations\n        call: opencost.getallocation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /assets\n      name: getassets\n      operations:\n      - method: GET\n        name: getassets\n        description: Query underlying cloud infrastructure asset costs\n        call: opencost.getassets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cloudCost\n      name: getcloudcost\n\
  \      operations:\n      - method: GET\n        name: getcloudcost\n        description: Query cloud provider billing data\n        call: opencost.getcloudcost\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customCost/timeseries\n      name: getcustomcosttimeseries\n      operations:\n      - method: GET\n        name: getcustomcosttimeseries\n        description: Custom cost timeseries data\n        call: opencost.getcustomcosttimeseries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customCost/total\n      name: getcustomcosttotal\n      operations:\n      - method: GET\n        name: getcustomcosttotal\n        description: Custom cost totals\n        call: opencost.getcustomcosttotal\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: opencost-mcp\n    transport: http\n    description: MCP adapter for OpenCost API for AI agent use.\n\
  \    tools:\n    - name: getallocation\n      description: Query Kubernetes workload cost allocations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: opencost.getallocation\n      with:\n        window: tools.window\n        aggregate: tools.aggregate\n        step: tools.step\n        accumulate: tools.accumulate\n        resolution: tools.resolution\n        includeIdle: tools.includeIdle\n        shareIdle: tools.shareIdle\n        idleByNode: tools.idleByNode\n      inputParameters:\n      - name: window\n        type: string\n        description: Duration of time over which to query.\n        required: true\n      - name: aggregate\n        type: string\n        description: Field by which to aggregate (namespace, controller, label:app, etc.).\n      - name: step\n        type: string\n        description: Duration of a single allocation set.\n      - name: accumulate\n        type: boolean\n        description: accumulate\n\
  \      - name: resolution\n        type: string\n        description: resolution\n      - name: includeIdle\n        type: boolean\n        description: includeIdle\n      - name: shareIdle\n        type: boolean\n        description: shareIdle\n      - name: idleByNode\n        type: boolean\n        description: idleByNode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getassets\n      description: Query underlying cloud infrastructure asset costs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: opencost.getassets\n      with:\n        window: tools.window\n        aggregate: tools.aggregate\n        accumulate: tools.accumulate\n      inputParameters:\n      - name: window\n        type: string\n        description: window\n        required: true\n      - name: aggregate\n        type: string\n        description: aggregate\n      - name: accumulate\n        type: boolean\n        description:\
  \ accumulate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcloudcost\n      description: Query cloud provider billing data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: opencost.getcloudcost\n      with:\n        window: tools.window\n        aggregate: tools.aggregate\n        accumulate: tools.accumulate\n        filter: tools.filter\n      inputParameters:\n      - name: window\n        type: string\n        description: window\n        required: true\n      - name: aggregate\n        type: string\n        description: aggregate\n      - name: accumulate\n        type: string\n        description: accumulate\n      - name: filter\n        type: string\n        description: filter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcustomcosttimeseries\n      description: Custom cost timeseries data\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: opencost.getcustomcosttimeseries\n      with:\n        window: tools.window\n        aggregate: tools.aggregate\n        accumulate: tools.accumulate\n        filter: tools.filter\n      inputParameters:\n      - name: window\n        type: string\n        description: window\n        required: true\n      - name: aggregate\n        type: string\n        description: aggregate\n      - name: accumulate\n        type: string\n        description: accumulate\n      - name: filter\n        type: string\n        description: filter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcustomcosttotal\n      description: Custom cost totals\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: opencost.getcustomcosttotal\n      with:\n        window: tools.window\n        aggregate: tools.aggregate\n        accumulate: tools.accumulate\n        filter: tools.filter\n\
  \      inputParameters:\n      - name: window\n        type: string\n        description: window\n        required: true\n      - name: aggregate\n        type: string\n        description: aggregate\n      - name: accumulate\n        type: string\n        description: accumulate\n      - name: filter\n        type: string\n        description: filter\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/opencost/refs/heads/main/capabilities/opencost-capability.yaml
tags:
- Opencost
- API
tools:
- description: Query Kubernetes workload cost allocations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getallocation
- description: Query underlying cloud infrastructure asset costs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getassets
- description: Query cloud provider billing data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcloudcost
- description: Custom cost timeseries data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcustomcosttimeseries
- description: Custom cost totals
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcustomcosttotal
---
