---
categories: []
consumed_apis: []
description: The GKE On-Prem API provides programmatic access to manage the lifecycle of on-premises Kubernetes clusters running on VMware or bare metal infrastructure as part of Google Distributed Cloud. It enables creating, updating, deleting, and monitoring clusters, managing node pools, and handling enrollment and upgrades.
layout: capability
name: Google Anthos Google GKE On-Prem API
operations:
- description: Google Anthos List VMware clusters
  method: GET
  name: listvmwareclusters
  path: /projects/{projectId}/locations/{location}/vmwareClusters
- description: Google Anthos Create a VMware cluster
  method: POST
  name: createvmwarecluster
  path: /projects/{projectId}/locations/{location}/vmwareClusters
- description: Google Anthos Get a VMware cluster
  method: GET
  name: getvmwarecluster
  path: /projects/{projectId}/locations/{location}/vmwareClusters/{clusterId}
- description: Google Anthos Delete a VMware cluster
  method: DELETE
  name: deletevmwarecluster
  path: /projects/{projectId}/locations/{location}/vmwareClusters/{clusterId}
- description: Google Anthos List bare metal clusters
  method: GET
  name: listbaremetalclusters
  path: /projects/{projectId}/locations/{location}/bareMetalClusters
- description: Google Anthos Create a bare metal cluster
  method: POST
  name: createbaremetalcluster
  path: /projects/{projectId}/locations/{location}/bareMetalClusters
- description: Google Anthos List VMware node pools
  method: GET
  name: listvmwarenodepools
  path: /projects/{projectId}/locations/{location}/vmwareClusters/{clusterId}/vmwareNodePools
- description: Google Anthos Create a VMware node pool
  method: POST
  name: createvmwarenodepool
  path: /projects/{projectId}/locations/{location}/vmwareClusters/{clusterId}/vmwareNodePools
personas: []
provider_name: Google Anthos
provider_slug: google-anthos
search_terms:
- container platform
- listvmwarenodepools
- on-premises
- createbaremetalcluster
- api
- listvmwareclusters
- deletevmwarecluster
- service mesh
- google anthos create a vmware node pool
- google
- createvmwarecluster
- multi-cloud
- google anthos get a vmware cluster
- google anthos create a bare metal cluster
- getvmwarecluster
- kubernetes
- google anthos delete a vmware cluster
- createvmwarenodepool
- google anthos create a vmware cluster
- listbaremetalclusters
- hybrid cloud
- google anthos list vmware clusters
- google anthos list vmware node pools
- google anthos list bare metal clusters
- anthos
slug: google-anthos-capability
source_filename: google-anthos-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Anthos Google GKE On-Prem API\n  description: The GKE On-Prem API provides programmatic access to manage the lifecycle of on-premises Kubernetes clusters\n    running on VMware or bare metal infrastructure as part of Google Distributed Cloud. It enables creating, updating, deleting,\n    and monitoring clusters, managing node pools, and handling enrollment and upgrades.\n  tags:\n  - Google\n  - Anthos\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-anthos\n    baseUri: https://gkeonprem.googleapis.com/v1\n    description: Google Anthos Google GKE On-Prem API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_ANTHOS_TOKEN}}'\n    resources:\n    - name: projects-projectid-locations-location-vmwareclus\n      path: /projects/{projectId}/locations/{location}/vmwareClusters\n      operations:\n      - name: listvmwareclusters\n    \
  \    method: GET\n        description: Google Anthos List VMware clusters\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createvmwarecluster\n        method: POST\n        description: Google Anthos Create a VMware cluster\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: vmwareClusterId\n          in: query\n          type: string\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-vmwareclus\n      path: /projects/{projectId}/locations/{location}/vmwareClusters/{clusterId}\n      operations:\n      - name: getvmwarecluster\n        method: GET\n        description: Google Anthos Get a VMware cluster\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletevmwarecluster\n        method: DELETE\n        description: Google Anthos Delete a VMware cluster\n        inputParameters:\n        - name: projectId\n      \
  \    in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-baremetalc\n      path: /projects/{projectId}/locations/{location}/bareMetalClusters\n      operations:\n      - name: listbaremetalclusters\n        method: GET\n        description: Google Anthos List bare metal clusters\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n \
  \         type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createbaremetalcluster\n        method: POST\n        description: Google Anthos Create a bare metal cluster\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-vmwareclus\n      path: /projects/{projectId}/locations/{location}/vmwareClusters/{clusterId}/vmwareNodePools\n      operations:\n      - name: listvmwarenodepools\n        method: GET\n        description: Google Anthos List VMware node pools\n        inputParameters:\n        - name: projectId\n          in: path\n          type:\
  \ string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createvmwarenodepool\n        method: POST\n        description: Google Anthos Create a VMware node pool\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-anthos-rest\n \
  \   description: REST adapter for Google Anthos Google GKE On-Prem API.\n    resources:\n    - path: /projects/{projectId}/locations/{location}/vmwareClusters\n      name: listvmwareclusters\n      operations:\n      - method: GET\n        name: listvmwareclusters\n        description: Google Anthos List VMware clusters\n        call: google-anthos.listvmwareclusters\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/vmwareClusters\n      name: createvmwarecluster\n      operations:\n      - method: POST\n        name: createvmwarecluster\n        description: Google Anthos Create a VMware cluster\n        call: google-anthos.createvmwarecluster\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/vmwareClusters/{clusterId}\n\
  \      name: getvmwarecluster\n      operations:\n      - method: GET\n        name: getvmwarecluster\n        description: Google Anthos Get a VMware cluster\n        call: google-anthos.getvmwarecluster\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          clusterId: rest.clusterId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/vmwareClusters/{clusterId}\n      name: deletevmwarecluster\n      operations:\n      - method: DELETE\n        name: deletevmwarecluster\n        description: Google Anthos Delete a VMware cluster\n        call: google-anthos.deletevmwarecluster\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          clusterId: rest.clusterId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/bareMetalClusters\n      name: listbaremetalclusters\n\
  \      operations:\n      - method: GET\n        name: listbaremetalclusters\n        description: Google Anthos List bare metal clusters\n        call: google-anthos.listbaremetalclusters\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/bareMetalClusters\n      name: createbaremetalcluster\n      operations:\n      - method: POST\n        name: createbaremetalcluster\n        description: Google Anthos Create a bare metal cluster\n        call: google-anthos.createbaremetalcluster\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/vmwareClusters/{clusterId}/vmwareNodePools\n      name: listvmwarenodepools\n      operations:\n      - method: GET\n        name:\
  \ listvmwarenodepools\n        description: Google Anthos List VMware node pools\n        call: google-anthos.listvmwarenodepools\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          clusterId: rest.clusterId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/vmwareClusters/{clusterId}/vmwareNodePools\n      name: createvmwarenodepool\n      operations:\n      - method: POST\n        name: createvmwarenodepool\n        description: Google Anthos Create a VMware node pool\n        call: google-anthos.createvmwarenodepool\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          clusterId: rest.clusterId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-anthos-mcp\n    transport: http\n    description: MCP adapter for Google Anthos Google GKE On-Prem\
  \ API for AI agent use.\n    tools:\n    - name: listvmwareclusters\n      description: Google Anthos List VMware clusters\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-anthos.listvmwareclusters\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createvmwarecluster\n      description: Google Anthos Create a VMware cluster\n      hints:\n        readOnly: false\n \
  \       destructive: false\n        idempotent: false\n      call: google-anthos.createvmwarecluster\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        vmwareClusterId: tools.vmwareClusterId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: vmwareClusterId\n        type: string\n        description: vmwareClusterId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvmwarecluster\n      description: Google Anthos Get a VMware cluster\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-anthos.getvmwarecluster\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        clusterId: tools.clusterId\n      inputParameters:\n      - name: projectId\n\
  \        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: clusterId\n        type: string\n        description: clusterId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletevmwarecluster\n      description: Google Anthos Delete a VMware cluster\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-anthos.deletevmwarecluster\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        clusterId: tools.clusterId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: clusterId\n        type: string\n        description: clusterId\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbaremetalclusters\n      description: Google Anthos List bare metal clusters\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-anthos.listbaremetalclusters\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createbaremetalcluster\n      description: Google Anthos\
  \ Create a bare metal cluster\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-anthos.createbaremetalcluster\n      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listvmwarenodepools\n      description: Google Anthos List VMware node pools\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-anthos.listvmwarenodepools\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        clusterId: tools.clusterId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n\
  \        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: clusterId\n        type: string\n        description: clusterId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createvmwarenodepool\n      description: Google Anthos Create a VMware node pool\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-anthos.createvmwarenodepool\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        clusterId: tools.clusterId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: clusterId\n        type: string\n        description: clusterId\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_ANTHOS_TOKEN: GOOGLE_ANTHOS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-anthos/refs/heads/main/capabilities/google-anthos-capability.yaml
tags:
- Google
- Anthos
- API
tools:
- description: Google Anthos List VMware clusters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvmwareclusters
- description: Google Anthos Create a VMware cluster
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createvmwarecluster
- description: Google Anthos Get a VMware cluster
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvmwarecluster
- description: Google Anthos Delete a VMware cluster
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletevmwarecluster
- description: Google Anthos List bare metal clusters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbaremetalclusters
- description: Google Anthos Create a bare metal cluster
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbaremetalcluster
- description: Google Anthos List VMware node pools
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvmwarenodepools
- description: Google Anthos Create a VMware node pool
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createvmwarenodepool
---
