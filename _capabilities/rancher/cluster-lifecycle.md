---
api_specs:
- filename: rancher-management-api-openapi.yml
  format: yaml
  label: rancher
  slug: rancher
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/rancher/refs/heads/main/openapi/rancher-management-api-openapi.yml
categories: []
consumed_apis:
- rancher
description: 'Workflow capability for managing the full lifecycle of Kubernetes clusters through Rancher: provisioning new clusters, inspecting cluster health and node status, managing projects and namespaces, and decommissioning clusters. Designed for platform engineers and DevOps teams automating multi-cluster infrastructure.'
layout: capability
name: Rancher Cluster Lifecycle Management
operations:
- description: List all clusters.
  method: GET
  name: list-clusters
  path: /v1/clusters
- description: Provision a new cluster.
  method: POST
  name: create-cluster
  path: /v1/clusters
- description: Get cluster details.
  method: GET
  name: get-cluster
  path: /v1/clusters/{id}
- description: Remove a cluster from Rancher.
  method: DELETE
  name: delete-cluster
  path: /v1/clusters/{id}
- description: List all nodes across clusters.
  method: GET
  name: list-nodes
  path: /v1/nodes
- description: List all projects.
  method: GET
  name: list-projects
  path: /v1/projects
- description: Create a new project.
  method: POST
  name: create-project
  path: /v1/projects
personas: []
provider_name: Rancher
provider_slug: rancher
search_terms:
- infrastructure
- create a new project.
- cluster management
- create cluster
- create project
- list clusters
- open source
- list all nodes across clusters.
- platform engineering
- kubernetes
- list projects
- provision a new kubernetes cluster through rancher. specify name, provider, and kubernetes version.
- suse
- single cluster.
- create a new rancher project within a cluster to organize namespaces.
- list all kubernetes clusters managed by rancher, including their state, provider, and kubernetes version.
- retrieve details for a specific rancher-managed cluster by id.
- containers
- kubernetes clusters managed by rancher.
- list all nodes across rancher-managed clusters, including hostname, state, and roles.
- multi-cluster
- get cluster details.
- get cluster
- cluster nodes.
- list all clusters.
- list all projects.
- remove a cluster from rancher.
- provision a new cluster.
- rancher
- remove a cluster from rancher management. this deregisters or destroys the cluster.
- delete cluster
- list all rancher projects, which group namespaces within clusters for tenancy and policy.
- list nodes
- rancher projects.
slug: cluster-lifecycle
source_filename: cluster-lifecycle.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Rancher Cluster Lifecycle Management\"\n  description: >-\n    Workflow capability for managing the full lifecycle of Kubernetes clusters through\n    Rancher: provisioning new clusters, inspecting cluster health and node status,\n    managing projects and namespaces, and decommissioning clusters. Designed for\n    platform engineers and DevOps teams automating multi-cluster infrastructure.\n  tags:\n    - Cluster Management\n    - Kubernetes\n    - Multi-Cluster\n    - Platform Engineering\n    - Infrastructure\n    - Rancher\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      RANCHER_BEARER_TOKEN: RANCHER_BEARER_TOKEN\n      RANCHER_HOST: RANCHER_HOST\n\ncapability:\n  consumes:\n    - import: rancher\n      location: ./shared/rancher-management-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: rancher-cluster-lifecycle-api\n      description: \"Unified\
  \ REST API for Rancher cluster lifecycle management.\"\n      resources:\n        - path: /v1/clusters\n          name: clusters\n          description: \"Kubernetes clusters managed by Rancher.\"\n          operations:\n            - method: GET\n              name: list-clusters\n              description: \"List all clusters.\"\n              call: \"rancher.list-clusters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-cluster\n              description: \"Provision a new cluster.\"\n              call: \"rancher.create-cluster\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/clusters/{id}\n          name: cluster\n          description: \"Single cluster.\"\n          operations:\n            - method: GET\n              name: get-cluster\n              description: \"Get cluster details.\"\n       \
  \       call: \"rancher.get-cluster\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-cluster\n              description: \"Remove a cluster from Rancher.\"\n              call: \"rancher.delete-cluster\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/nodes\n          name: nodes\n          description: \"Cluster nodes.\"\n          operations:\n            - method: GET\n              name: list-nodes\n              description: \"List all nodes across clusters.\"\n              call: \"rancher.list-nodes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects\n          name: projects\n          description: \"Rancher\
  \ projects.\"\n          operations:\n            - method: GET\n              name: list-projects\n              description: \"List all projects.\"\n              call: \"rancher.list-projects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-project\n              description: \"Create a new project.\"\n              call: \"rancher.create-project\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: rancher-cluster-lifecycle-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Kubernetes cluster lifecycle management via Rancher.\"\n      tools:\n        - name: list-clusters\n          description: \"List all Kubernetes clusters managed by Rancher, including their state, provider, and Kubernetes version.\"\n          hints:\n            readOnly: true\n\
  \            openWorld: true\n          call: \"rancher.list-clusters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-cluster\n          description: \"Retrieve details for a specific Rancher-managed cluster by ID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"rancher.get-cluster\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-cluster\n          description: \"Provision a new Kubernetes cluster through Rancher. Specify name, provider, and Kubernetes version.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"rancher.create-cluster\"\n          with:\n            name: \"tools.name\"\n            description: \"tools.description\"\n            kubernetesVersion: \"tools.kubernetesVersion\"\n            provider:\
  \ \"tools.provider\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-cluster\n          description: \"Remove a cluster from Rancher management. This deregisters or destroys the cluster.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"rancher.delete-cluster\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-nodes\n          description: \"List all nodes across Rancher-managed clusters, including hostname, state, and roles.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rancher.list-nodes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-projects\n          description: \"List all Rancher projects, which group namespaces within\
  \ clusters for tenancy and policy.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rancher.list-projects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-project\n          description: \"Create a new Rancher project within a cluster to organize namespaces.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"rancher.create-project\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rancher/refs/heads/main/capabilities/cluster-lifecycle.yaml
tags:
- Cluster Management
- Kubernetes
- Multi-Cluster
- Platform Engineering
- Infrastructure
- Rancher
tools:
- description: List all Kubernetes clusters managed by Rancher, including their state, provider, and Kubernetes version.
  hints:
    openWorld: true
    readOnly: true
  name: list-clusters
- description: Retrieve details for a specific Rancher-managed cluster by ID.
  hints:
    idempotent: true
    readOnly: true
  name: get-cluster
- description: Provision a new Kubernetes cluster through Rancher. Specify name, provider, and Kubernetes version.
  hints:
    destructive: false
    readOnly: false
  name: create-cluster
- description: Remove a cluster from Rancher management. This deregisters or destroys the cluster.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-cluster
- description: List all nodes across Rancher-managed clusters, including hostname, state, and roles.
  hints:
    openWorld: true
    readOnly: true
  name: list-nodes
- description: List all Rancher projects, which group namespaces within clusters for tenancy and policy.
  hints:
    openWorld: true
    readOnly: true
  name: list-projects
- description: Create a new Rancher project within a cluster to organize namespaces.
  hints:
    destructive: false
    readOnly: false
  name: create-project
---
