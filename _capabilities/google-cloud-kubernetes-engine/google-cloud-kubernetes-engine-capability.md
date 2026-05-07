---
categories: []
consumed_apis: []
description: Builds and manages container-based applications, powered by the open source Kubernetes technology.
layout: capability
name: Google Cloud Kubernetes Engine Google Kubernetes Engine API
operations:
- description: Google Cloud Kubernetes Engine List Clusters
  method: GET
  name: listclusters
  path: /projects/{projectId}/locations/{location}/clusters
- description: Google Cloud Kubernetes Engine Create Cluster
  method: POST
  name: createcluster
  path: /projects/{projectId}/locations/{location}/clusters
- description: Google Cloud Kubernetes Engine Get Cluster
  method: GET
  name: getcluster
  path: /projects/{projectId}/locations/{location}/clusters/{clusterId}
- description: Google Cloud Kubernetes Engine Delete Cluster
  method: DELETE
  name: deletecluster
  path: /projects/{projectId}/locations/{location}/clusters/{clusterId}
- description: Google Cloud Kubernetes Engine List Node Pools
  method: GET
  name: listnodepools
  path: /projects/{projectId}/locations/{location}/clusters/{clusterId}/nodePools
- description: Google Cloud Kubernetes Engine Create Node Pool
  method: POST
  name: createnodepool
  path: /projects/{projectId}/locations/{location}/clusters/{clusterId}/nodePools
- description: Google Cloud Kubernetes Engine List Operations
  method: GET
  name: listoperations
  path: /projects/{projectId}/locations/{location}/operations
personas: []
provider_name: Google Cloud Kubernetes Engine
provider_slug: google-cloud-kubernetes-engine
search_terms:
- containers
- google cloud kubernetes engine list node pools
- listnodepools
- deletecluster
- listoperations
- getcluster
- api
- google cloud kubernetes engine delete cluster
- createcluster
- google cloud kubernetes engine get cluster
- google
- orchestration
- google cloud kubernetes engine create node pool
- listclusters
- kubernetes
- google cloud kubernetes engine create cluster
- gke
- google cloud kubernetes engine list clusters
- cloud
- engine
- compute
- createnodepool
- google cloud kubernetes engine list operations
- google cloud
slug: google-cloud-kubernetes-engine-capability
source_filename: google-cloud-kubernetes-engine-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Kubernetes Engine Google Kubernetes Engine API\n  description: Builds and manages container-based applications, powered by the open source Kubernetes technology.\n  tags:\n  - Google\n  - Cloud\n  - Kubernetes\n  - Engine\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-kubernetes-engine\n    baseUri: https://container.googleapis.com/v1\n    description: Google Cloud Kubernetes Engine Google Kubernetes Engine API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_KUBERNETES_ENGINE_TOKEN}}'\n    resources:\n    - name: projects-projectid-locations-location-clusters\n      path: /projects/{projectId}/locations/{location}/clusters\n      operations:\n      - name: listclusters\n        method: GET\n        description: Google Cloud Kubernetes Engine List Clusters\n        inputParameters:\n        - name: projectId\n\
  \          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcluster\n        method: POST\n        description: Google Cloud Kubernetes Engine Create Cluster\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-clusters-c\n      path: /projects/{projectId}/locations/{location}/clusters/{clusterId}\n      operations:\n      - name: getcluster\n        method: GET\n        description: Google Cloud Kubernetes\
  \ Engine Get Cluster\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecluster\n        method: DELETE\n        description: Google Cloud Kubernetes Engine Delete Cluster\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: projects-projectid-locations-location-clusters-c\n      path: /projects/{projectId}/locations/{location}/clusters/{clusterId}/nodePools\n      operations:\n      - name: listnodepools\n        method: GET\n        description: Google Cloud Kubernetes Engine List Node Pools\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnodepool\n        method: POST\n        description: Google Cloud Kubernetes Engine Create Node Pool\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required:\
  \ true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-operations\n      path: /projects/{projectId}/locations/{location}/operations\n      operations:\n      - name: listoperations\n        method: GET\n        description: Google Cloud Kubernetes Engine List Operations\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace:\
  \ google-cloud-kubernetes-engine-rest\n    description: REST adapter for Google Cloud Kubernetes Engine Google Kubernetes Engine API.\n    resources:\n    - path: /projects/{projectId}/locations/{location}/clusters\n      name: listclusters\n      operations:\n      - method: GET\n        name: listclusters\n        description: Google Cloud Kubernetes Engine List Clusters\n        call: google-cloud-kubernetes-engine.listclusters\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/clusters\n      name: createcluster\n      operations:\n      - method: POST\n        name: createcluster\n        description: Google Cloud Kubernetes Engine Create Cluster\n        call: google-cloud-kubernetes-engine.createcluster\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/clusters/{clusterId}\n      name: getcluster\n      operations:\n      - method: GET\n        name: getcluster\n        description: Google Cloud Kubernetes Engine Get Cluster\n        call: google-cloud-kubernetes-engine.getcluster\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          clusterId: rest.clusterId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/clusters/{clusterId}\n      name: deletecluster\n      operations:\n      - method: DELETE\n        name: deletecluster\n        description: Google Cloud Kubernetes Engine Delete Cluster\n        call: google-cloud-kubernetes-engine.deletecluster\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          clusterId: rest.clusterId\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/clusters/{clusterId}/nodePools\n      name: listnodepools\n      operations:\n      - method: GET\n        name: listnodepools\n        description: Google Cloud Kubernetes Engine List Node Pools\n        call: google-cloud-kubernetes-engine.listnodepools\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          clusterId: rest.clusterId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/clusters/{clusterId}/nodePools\n      name: createnodepool\n      operations:\n      - method: POST\n        name: createnodepool\n        description: Google Cloud Kubernetes Engine Create Node Pool\n        call: google-cloud-kubernetes-engine.createnodepool\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          clusterId: rest.clusterId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/operations\n      name: listoperations\n      operations:\n      - method: GET\n        name: listoperations\n        description: Google Cloud Kubernetes Engine List Operations\n        call: google-cloud-kubernetes-engine.listoperations\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-kubernetes-engine-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Kubernetes Engine Google Kubernetes Engine API for AI agent use.\n    tools:\n    - name: listclusters\n      description: Google Cloud Kubernetes Engine List Clusters\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-kubernetes-engine.listclusters\n      with:\n        projectId:\
  \ tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcluster\n      description: Google Cloud Kubernetes Engine Create Cluster\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-kubernetes-engine.createcluster\n      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcluster\n  \
  \    description: Google Cloud Kubernetes Engine Get Cluster\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-kubernetes-engine.getcluster\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        clusterId: tools.clusterId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: clusterId\n        type: string\n        description: clusterId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecluster\n      description: Google Cloud Kubernetes Engine Delete Cluster\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-kubernetes-engine.deletecluster\n      with:\n        projectId:\
  \ tools.projectId\n        location: tools.location\n        clusterId: tools.clusterId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: clusterId\n        type: string\n        description: clusterId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnodepools\n      description: Google Cloud Kubernetes Engine List Node Pools\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-kubernetes-engine.listnodepools\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        clusterId: tools.clusterId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n\
  \        type: string\n        description: location\n        required: true\n      - name: clusterId\n        type: string\n        description: clusterId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnodepool\n      description: Google Cloud Kubernetes Engine Create Node Pool\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-kubernetes-engine.createnodepool\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        clusterId: tools.clusterId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: clusterId\n        type: string\n        description: clusterId\n        required: true\n      outputParameters:\n      - type: object\n    \
  \    mapping: $.\n    - name: listoperations\n      description: Google Cloud Kubernetes Engine List Operations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-kubernetes-engine.listoperations\n      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_KUBERNETES_ENGINE_TOKEN: GOOGLE_CLOUD_KUBERNETES_ENGINE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-kubernetes-engine/refs/heads/main/capabilities/google-cloud-kubernetes-engine-capability.yaml
tags:
- Google
- Cloud
- Kubernetes
- Engine
- API
tools:
- description: Google Cloud Kubernetes Engine List Clusters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listclusters
- description: Google Cloud Kubernetes Engine Create Cluster
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcluster
- description: Google Cloud Kubernetes Engine Get Cluster
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcluster
- description: Google Cloud Kubernetes Engine Delete Cluster
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecluster
- description: Google Cloud Kubernetes Engine List Node Pools
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnodepools
- description: Google Cloud Kubernetes Engine Create Node Pool
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnodepool
- description: Google Cloud Kubernetes Engine List Operations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listoperations
---
