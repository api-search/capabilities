---
categories: []
consumed_apis: []
description: The Allocation API retrieves cost allocation information for any Kubernetes concept, such as cost by namespace, label, deployment, service, and more. It is directly integrated with the Kubecost ETL caching layer and CSV pipeline so it can scale for large clusters.
layout: capability
name: Kubecost Allocation API
operations:
- description: Kubecost Query allocation cost data
  method: GET
  name: getallocation
  path: /model/allocation
- description: Kubecost Query total allocation costs
  method: GET
  name: getallocationtotals
  path: /model/allocation/totals
personas: []
provider_name: Kubecost
provider_slug: kubecost
search_terms:
- kubecost
- cloud cost
- api
- getallocationtotals
- spending
- kubecost query total allocation costs
- kubecost query allocation cost data
- optimization
- kubernetes
- getallocation
- cost monitoring
slug: kubecost-capability
source_filename: kubecost-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Kubecost Allocation API\n  description: The Allocation API retrieves cost allocation information for any Kubernetes concept, such as cost by namespace,\n    label, deployment, service, and more. It is directly integrated with the Kubecost ETL caching layer and CSV pipeline so\n    it can scale for large clusters.\n  tags:\n  - Kubecost\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: kubecost\n    baseUri: http://localhost:9090\n    description: Kubecost Allocation API HTTP API.\n    resources:\n    - name: model-allocation\n      path: /model/allocation\n      operations:\n      - name: getallocation\n        method: GET\n        description: Kubecost Query allocation cost data\n        inputParameters:\n        - name: window\n          in: query\n          type: string\n          required: true\n          description: Duration of time over which to query. Accepts units\
  \ of time (e.g. 3d, 24h, 7d), relative time (e.g.\n            yesterday, lastweek, lastmonth), or RFC3339 date pairs.\n        - name: aggregate\n          in: query\n          type: string\n          description: 'Field by which to aggregate results. Supported values include cluster, namespace, controllerKind,\n            controller, service, deployment, statefulset, daemonset, job, '\n        - name: step\n          in: query\n          type: string\n          description: Duration of a single allocation set. If unspecified, this defaults to the window, so that you receive\n            exactly one set for the entire window.\n        - name: accumulate\n          in: query\n          type: boolean\n          description: If true, sum the entire range of sets into a single set.\n        - name: idle\n          in: query\n          type: boolean\n          description: Whether to return idle cost. If true, idle allocations are returned.\n        - name: external\n          in: query\n\
  \          type: boolean\n          description: Whether to include external (out-of-cluster) costs.\n        - name: filterClusters\n          in: query\n          type: string\n          description: Filter results by cluster name (comma-separated).\n        - name: filterNamespaces\n          in: query\n          type: string\n          description: Filter results by namespace (comma-separated).\n        - name: filterControllerKinds\n          in: query\n          type: string\n          description: Filter results by controller kind (comma-separated).\n        - name: filterControllers\n          in: query\n          type: string\n          description: Filter results by controller name (comma-separated).\n        - name: filterLabels\n          in: query\n          type: string\n          description: Filter results by label in the format label:value (comma-separated).\n        - name: filterAnnotations\n          in: query\n          type: string\n          description: Filter results\
  \ by annotation in the format annotation:value (comma-separated).\n        - name: filterServices\n          in: query\n          type: string\n          description: Filter results by service (comma-separated).\n        - name: shareIdle\n          in: query\n          type: boolean\n          description: If true, idle cost is allocated proportionally across tenants.\n        - name: splitIdle\n          in: query\n          type: boolean\n          description: If true, idle cost is split into separate allocations by cluster and node.\n        - name: idleByNode\n          in: query\n          type: boolean\n          description: If true, idle allocations are created on a per-node basis.\n        - name: format\n          in: query\n          type: string\n          description: Output format. Supports csv and json.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: model-allocation-totals\n  \
  \    path: /model/allocation/totals\n      operations:\n      - name: getallocationtotals\n        method: GET\n        description: Kubecost Query total allocation costs\n        inputParameters:\n        - name: window\n          in: query\n          type: string\n          required: true\n          description: Duration of time over which to query.\n        - name: aggregate\n          in: query\n          type: string\n          description: Field by which to aggregate results.\n        - name: filterClusters\n          in: query\n          type: string\n        - name: filterNamespaces\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: kubecost-rest\n    description: REST adapter for Kubecost Allocation API.\n    resources:\n    - path: /model/allocation\n      name: getallocation\n      operations:\n \
  \     - method: GET\n        name: getallocation\n        description: Kubecost Query allocation cost data\n        call: kubecost.getallocation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /model/allocation/totals\n      name: getallocationtotals\n      operations:\n      - method: GET\n        name: getallocationtotals\n        description: Kubecost Query total allocation costs\n        call: kubecost.getallocationtotals\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: kubecost-mcp\n    transport: http\n    description: MCP adapter for Kubecost Allocation API for AI agent use.\n    tools:\n    - name: getallocation\n      description: Kubecost Query allocation cost data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kubecost.getallocation\n      with:\n        window: tools.window\n        aggregate: tools.aggregate\n\
  \        step: tools.step\n        accumulate: tools.accumulate\n        idle: tools.idle\n        external: tools.external\n        filterClusters: tools.filterClusters\n        filterNamespaces: tools.filterNamespaces\n        filterControllerKinds: tools.filterControllerKinds\n        filterControllers: tools.filterControllers\n        filterLabels: tools.filterLabels\n        filterAnnotations: tools.filterAnnotations\n        filterServices: tools.filterServices\n        shareIdle: tools.shareIdle\n        splitIdle: tools.splitIdle\n        idleByNode: tools.idleByNode\n        format: tools.format\n      inputParameters:\n      - name: window\n        type: string\n        description: Duration of time over which to query. Accepts units of time (e.g. 3d, 24h, 7d), relative time (e.g. yesterday,\n          lastweek, lastmonth), or RFC3339 date pairs.\n        required: true\n      - name: aggregate\n        type: string\n        description: 'Field by which to aggregate results.\
  \ Supported values include cluster, namespace, controllerKind, controller,\n          service, deployment, statefulset, daemonset, job, '\n      - name: step\n        type: string\n        description: Duration of a single allocation set. If unspecified, this defaults to the window, so that you receive\n          exactly one set for the entire window.\n      - name: accumulate\n        type: boolean\n        description: If true, sum the entire range of sets into a single set.\n      - name: idle\n        type: boolean\n        description: Whether to return idle cost. If true, idle allocations are returned.\n      - name: external\n        type: boolean\n        description: Whether to include external (out-of-cluster) costs.\n      - name: filterClusters\n        type: string\n        description: Filter results by cluster name (comma-separated).\n      - name: filterNamespaces\n        type: string\n        description: Filter results by namespace (comma-separated).\n      - name: filterControllerKinds\n\
  \        type: string\n        description: Filter results by controller kind (comma-separated).\n      - name: filterControllers\n        type: string\n        description: Filter results by controller name (comma-separated).\n      - name: filterLabels\n        type: string\n        description: Filter results by label in the format label:value (comma-separated).\n      - name: filterAnnotations\n        type: string\n        description: Filter results by annotation in the format annotation:value (comma-separated).\n      - name: filterServices\n        type: string\n        description: Filter results by service (comma-separated).\n      - name: shareIdle\n        type: boolean\n        description: If true, idle cost is allocated proportionally across tenants.\n      - name: splitIdle\n        type: boolean\n        description: If true, idle cost is split into separate allocations by cluster and node.\n      - name: idleByNode\n        type: boolean\n        description: If true,\
  \ idle allocations are created on a per-node basis.\n      - name: format\n        type: string\n        description: Output format. Supports csv and json.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getallocationtotals\n      description: Kubecost Query total allocation costs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: kubecost.getallocationtotals\n      with:\n        window: tools.window\n        aggregate: tools.aggregate\n        filterClusters: tools.filterClusters\n        filterNamespaces: tools.filterNamespaces\n      inputParameters:\n      - name: window\n        type: string\n        description: Duration of time over which to query.\n        required: true\n      - name: aggregate\n        type: string\n        description: Field by which to aggregate results.\n      - name: filterClusters\n        type: string\n        description: filterClusters\n      - name: filterNamespaces\n\
  \        type: string\n        description: filterNamespaces\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/kubecost/refs/heads/main/capabilities/kubecost-capability.yaml
tags:
- Kubecost
- API
tools:
- description: Kubecost Query allocation cost data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getallocation
- description: Kubecost Query total allocation costs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getallocationtotals
---
