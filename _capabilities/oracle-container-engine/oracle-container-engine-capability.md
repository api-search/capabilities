---
categories: []
consumed_apis: []
description: Oracle Container Engine for Kubernetes (OKE) is a managed Kubernetes service on Oracle Cloud Infrastructure. The API exposes endpoints for managing Kubernetes clusters, node pools, virtual node pools, add-ons, work requests, and cluster credentials within OCI compartments.
layout: capability
name: Oracle Container Engine for Kubernetes (OKE) API
operations:
- description: List clusters
  method: GET
  name: listclusters
  path: /clusters
- description: Create a cluster
  method: POST
  name: createcluster
  path: /clusters
- description: Get a cluster
  method: GET
  name: getcluster
  path: /clusters/{clusterId}
- description: Update a cluster
  method: PUT
  name: updatecluster
  path: /clusters/{clusterId}
- description: Delete a cluster
  method: DELETE
  name: deletecluster
  path: /clusters/{clusterId}
- description: Create kubeconfig content
  method: POST
  name: createkubeconfig
  path: /clusters/{clusterId}/kubeconfig/content
- description: List node pools
  method: GET
  name: listnodepools
  path: /nodePools
- description: Create a node pool
  method: POST
  name: createnodepool
  path: /nodePools
- description: Get a node pool
  method: GET
  name: getnodepool
  path: /nodePools/{nodePoolId}
- description: Delete a node pool
  method: DELETE
  name: deletenodepool
  path: /nodePools/{nodePoolId}
- description: List virtual node pools
  method: GET
  name: listvirtualnodepools
  path: /virtualNodePools
- description: List add-ons installed on a cluster
  method: GET
  name: listaddons
  path: /clusters/{clusterId}/addons
- description: Install a cluster add-on
  method: POST
  name: installaddon
  path: /clusters/{clusterId}/addons
- description: List work requests
  method: GET
  name: listworkrequests
  path: /workRequests
- description: Get a work request
  method: GET
  name: getworkrequest
  path: /workRequests/{workRequestId}
personas: []
provider_name: Oracle Container Engine for Kubernetes
provider_slug: oracle-container-engine
search_terms:
- getnodepool
- list work requests
- containers
- list virtual node pools
- listnodepools
- deletecluster
- createkubeconfig
- getcluster
- list node pools
- api
- listaddons
- createcluster
- create a node pool
- installaddon
- get a cluster
- orchestration
- delete a node pool
- delete a cluster
- listclusters
- get a work request
- list clusters
- updatecluster
- getworkrequest
- kubernetes
- container
- create a cluster
- listworkrequests
- create kubeconfig content
- update a cluster
- install a cluster add-on
- cloud
- engine
- get a node pool
- createnodepool
- listvirtualnodepools
- deletenodepool
- list add-ons installed on a cluster
- oracle
slug: oracle-container-engine-capability
source_filename: oracle-container-engine-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Oracle Container Engine for Kubernetes (OKE) API\n  description: Oracle Container Engine for Kubernetes (OKE) is a managed Kubernetes service on Oracle Cloud Infrastructure.\n    The API exposes endpoints for managing Kubernetes clusters, node pools, virtual node pools, add-ons, work requests, and\n    cluster credentials within OCI compartments.\n  tags:\n  - Oracle\n  - Container\n  - Engine\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: oracle-container-engine\n    baseUri: https://containerengine.us-ashburn-1.oci.oraclecloud.com/20180222\n    description: Oracle Container Engine for Kubernetes (OKE) API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{ORACLE_CONTAINER_ENGINE_TOKEN}}'\n    resources:\n    - name: clusters\n      path: /clusters\n      operations:\n      - name: listclusters\n       \
  \ method: GET\n        description: List clusters\n        inputParameters:\n        - name: lifecycleState\n          in: query\n          type: array\n        - name: name\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcluster\n        method: POST\n        description: Create a cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clusters-clusterid\n      path: /clusters/{clusterId}\n      operations:\n      - name: getcluster\n        method: GET\n        description: Get a cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecluster\n        method: PUT\n        description: Update a cluster\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: deletecluster\n        method: DELETE\n        description: Delete a cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clusters-clusterid-kubeconfig-content\n      path: /clusters/{clusterId}/kubeconfig/content\n      operations:\n      - name: createkubeconfig\n        method: POST\n        description: Create kubeconfig content\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nodepools\n      path: /nodePools\n      operations:\n      - name: listnodepools\n        method: GET\n        description: List node pools\n        inputParameters:\n        - name: clusterId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: createnodepool\n        method: POST\n        description: Create a node pool\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nodepools-nodepoolid\n      path: /nodePools/{nodePoolId}\n      operations:\n      - name: getnodepool\n        method: GET\n        description: Get a node pool\n        inputParameters:\n        - name: nodePoolId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletenodepool\n        method: DELETE\n        description: Delete a node pool\n        inputParameters:\n        - name: nodePoolId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n    - name: virtualnodepools\n      path: /virtualNodePools\n      operations:\n      - name: listvirtualnodepools\n        method: GET\n        description: List virtual node pools\n        inputParameters:\n        - name: clusterId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clusters-clusterid-addons\n      path: /clusters/{clusterId}/addons\n      operations:\n      - name: listaddons\n        method: GET\n        description: List add-ons installed on a cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: installaddon\n        method: POST\n        description: Install a cluster add-on\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workrequests\n\
  \      path: /workRequests\n      operations:\n      - name: listworkrequests\n        method: GET\n        description: List work requests\n        inputParameters:\n        - name: resourceId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workrequests-workrequestid\n      path: /workRequests/{workRequestId}\n      operations:\n      - name: getworkrequest\n        method: GET\n        description: Get a work request\n        inputParameters:\n        - name: workRequestId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: oracle-container-engine-rest\n    description: REST adapter for Oracle Container Engine for Kubernetes (OKE) API.\n    resources:\n\
  \    - path: /clusters\n      name: listclusters\n      operations:\n      - method: GET\n        name: listclusters\n        description: List clusters\n        call: oracle-container-engine.listclusters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /clusters\n      name: createcluster\n      operations:\n      - method: POST\n        name: createcluster\n        description: Create a cluster\n        call: oracle-container-engine.createcluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /clusters/{clusterId}\n      name: getcluster\n      operations:\n      - method: GET\n        name: getcluster\n        description: Get a cluster\n        call: oracle-container-engine.getcluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /clusters/{clusterId}\n      name: updatecluster\n      operations:\n      - method: PUT\n        name: updatecluster\n        description:\
  \ Update a cluster\n        call: oracle-container-engine.updatecluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /clusters/{clusterId}\n      name: deletecluster\n      operations:\n      - method: DELETE\n        name: deletecluster\n        description: Delete a cluster\n        call: oracle-container-engine.deletecluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /clusters/{clusterId}/kubeconfig/content\n      name: createkubeconfig\n      operations:\n      - method: POST\n        name: createkubeconfig\n        description: Create kubeconfig content\n        call: oracle-container-engine.createkubeconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nodePools\n      name: listnodepools\n      operations:\n      - method: GET\n        name: listnodepools\n        description: List node pools\n        call: oracle-container-engine.listnodepools\n      \
  \  outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nodePools\n      name: createnodepool\n      operations:\n      - method: POST\n        name: createnodepool\n        description: Create a node pool\n        call: oracle-container-engine.createnodepool\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nodePools/{nodePoolId}\n      name: getnodepool\n      operations:\n      - method: GET\n        name: getnodepool\n        description: Get a node pool\n        call: oracle-container-engine.getnodepool\n        with:\n          nodePoolId: rest.nodePoolId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nodePools/{nodePoolId}\n      name: deletenodepool\n      operations:\n      - method: DELETE\n        name: deletenodepool\n        description: Delete a node pool\n        call: oracle-container-engine.deletenodepool\n        with:\n          nodePoolId: rest.nodePoolId\n     \
  \   outputParameters:\n        - type: object\n          mapping: $.\n    - path: /virtualNodePools\n      name: listvirtualnodepools\n      operations:\n      - method: GET\n        name: listvirtualnodepools\n        description: List virtual node pools\n        call: oracle-container-engine.listvirtualnodepools\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /clusters/{clusterId}/addons\n      name: listaddons\n      operations:\n      - method: GET\n        name: listaddons\n        description: List add-ons installed on a cluster\n        call: oracle-container-engine.listaddons\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /clusters/{clusterId}/addons\n      name: installaddon\n      operations:\n      - method: POST\n        name: installaddon\n        description: Install a cluster add-on\n        call: oracle-container-engine.installaddon\n        outputParameters:\n        - type: object\n       \
  \   mapping: $.\n    - path: /workRequests\n      name: listworkrequests\n      operations:\n      - method: GET\n        name: listworkrequests\n        description: List work requests\n        call: oracle-container-engine.listworkrequests\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workRequests/{workRequestId}\n      name: getworkrequest\n      operations:\n      - method: GET\n        name: getworkrequest\n        description: Get a work request\n        call: oracle-container-engine.getworkrequest\n        with:\n          workRequestId: rest.workRequestId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: oracle-container-engine-mcp\n    transport: http\n    description: MCP adapter for Oracle Container Engine for Kubernetes (OKE) API for AI agent use.\n    tools:\n    - name: listclusters\n      description: List clusters\n      hints:\n        readOnly: true\n     \
  \   destructive: false\n        idempotent: true\n      call: oracle-container-engine.listclusters\n      with:\n        lifecycleState: tools.lifecycleState\n        name: tools.name\n      inputParameters:\n      - name: lifecycleState\n        type: array\n        description: lifecycleState\n      - name: name\n        type: string\n        description: name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcluster\n      description: Create a cluster\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-container-engine.createcluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcluster\n      description: Get a cluster\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-container-engine.getcluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecluster\n\
  \      description: Update a cluster\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: oracle-container-engine.updatecluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecluster\n      description: Delete a cluster\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: oracle-container-engine.deletecluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createkubeconfig\n      description: Create kubeconfig content\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-container-engine.createkubeconfig\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnodepools\n      description: List node pools\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-container-engine.listnodepools\n\
  \      with:\n        clusterId: tools.clusterId\n      inputParameters:\n      - name: clusterId\n        type: string\n        description: clusterId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnodepool\n      description: Create a node pool\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-container-engine.createnodepool\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnodepool\n      description: Get a node pool\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-container-engine.getnodepool\n      with:\n        nodePoolId: tools.nodePoolId\n      inputParameters:\n      - name: nodePoolId\n        type: string\n        description: nodePoolId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletenodepool\n      description: Delete\
  \ a node pool\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: oracle-container-engine.deletenodepool\n      with:\n        nodePoolId: tools.nodePoolId\n      inputParameters:\n      - name: nodePoolId\n        type: string\n        description: nodePoolId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listvirtualnodepools\n      description: List virtual node pools\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-container-engine.listvirtualnodepools\n      with:\n        clusterId: tools.clusterId\n      inputParameters:\n      - name: clusterId\n        type: string\n        description: clusterId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listaddons\n      description: List add-ons installed on a cluster\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: oracle-container-engine.listaddons\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: installaddon\n      description: Install a cluster add-on\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: oracle-container-engine.installaddon\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listworkrequests\n      description: List work requests\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: oracle-container-engine.listworkrequests\n      with:\n        resourceId: tools.resourceId\n      inputParameters:\n      - name: resourceId\n        type: string\n        description: resourceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getworkrequest\n      description: Get a work request\n      hints:\n        readOnly: true\n        destructive: false\n \
  \       idempotent: true\n      call: oracle-container-engine.getworkrequest\n      with:\n        workRequestId: tools.workRequestId\n      inputParameters:\n      - name: workRequestId\n        type: string\n        description: workRequestId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ORACLE_CONTAINER_ENGINE_TOKEN: ORACLE_CONTAINER_ENGINE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oracle-container-engine/refs/heads/main/capabilities/oracle-container-engine-capability.yaml
tags:
- Oracle
- Container
- Engine
- API
tools:
- description: List clusters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listclusters
- description: Create a cluster
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcluster
- description: Get a cluster
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcluster
- description: Update a cluster
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecluster
- description: Delete a cluster
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecluster
- description: Create kubeconfig content
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createkubeconfig
- description: List node pools
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnodepools
- description: Create a node pool
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnodepool
- description: Get a node pool
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnodepool
- description: Delete a node pool
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletenodepool
- description: List virtual node pools
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvirtualnodepools
- description: List add-ons installed on a cluster
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listaddons
- description: Install a cluster add-on
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: installaddon
- description: List work requests
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkrequests
- description: Get a work request
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkrequest
---
