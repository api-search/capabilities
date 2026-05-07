---
categories: []
consumed_apis: []
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
- containers
- get cluster
- kubernetes clusters managed by rancher.
- multi-cluster
- list all nodes across clusters.
- list all kubernetes clusters managed by rancher, including their state, provider, and kubernetes version.
- suse
- open source
- provision a new kubernetes cluster through rancher. specify name, provider, and kubernetes version.
- provision a new cluster.
- list all clusters.
- create a new rancher project within a cluster to organize namespaces.
- delete cluster
- infrastructure
- remove a cluster from rancher.
- list clusters
- remove a cluster from rancher management. this deregisters or destroys the cluster.
- kubernetes
- list projects
- create project
- single cluster.
- create a new project.
- cluster management
- retrieve details for a specific rancher-managed cluster by id.
- cluster nodes.
- rancher projects.
- list all projects.
- create cluster
- list nodes
- list all rancher projects, which group namespaces within clusters for tenancy and policy.
- list all nodes across rancher-managed clusters, including hostname, state, and roles.
- rancher
- get cluster details.
- platform engineering
slug: cluster-lifecycle
source_filename: cluster-lifecycle.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Rancher Cluster Lifecycle Management\n  description: 'Workflow capability for managing the full lifecycle of Kubernetes clusters through Rancher: provisioning new\n    clusters, inspecting cluster health and node status, managing projects and namespaces, and decommissioning clusters. Designed\n    for platform engineers and DevOps teams automating multi-cluster infrastructure.'\n  tags:\n  - Cluster Management\n  - Kubernetes\n  - Multi-Cluster\n  - Platform Engineering\n  - Infrastructure\n  - Rancher\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    RANCHER_BEARER_TOKEN: RANCHER_BEARER_TOKEN\n    RANCHER_HOST: RANCHER_HOST\ncapability:\n  consumes:\n  - type: http\n    namespace: rancher\n    baseUri: https://{{RANCHER_HOST}}/v3\n    description: Rancher v3 Management API.\n    authentication:\n      type: bearer\n      token: '{{RANCHER_BEARER_TOKEN}}'\n    resources:\n    - name: clusters\n\
  \      path: /clusters\n      description: Downstream Kubernetes clusters managed by Rancher.\n      operations:\n      - name: list-clusters\n        method: GET\n        description: List all clusters managed by Rancher.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-cluster\n        method: POST\n        description: Provision a new cluster.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            kubernetesVersion: '{{tools.kubernetesVersion}}'\n            provider: '{{tools.provider}}'\n    - name: cluster\n      path: /clusters/{id}\n      description: Single cluster resource.\n      operations:\n      - name: get-cluster\n        method: GET\n        description:\
  \ Retrieve a single cluster by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Cluster identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-cluster\n        method: DELETE\n        description: Remove a cluster from Rancher management.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Cluster identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects\n      path: /projects\n      description: Rancher projects grouping namespaces.\n      operations:\n      - name: list-projects\n        method: GET\n        description: List all projects.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-project\n        method: POST\n        description: Create a new project.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nodes\n      path: /nodes\n      description: Cluster nodes.\n      operations:\n      - name: list-nodes\n        method: GET\n        description: List all nodes.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      description: Rancher users.\n      operations:\n      - name: list-users\n        method: GET\n        description: List all users.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tokens\n      path: /tokens\n      description: API tokens.\n      operations:\n    \
  \  - name: list-tokens\n        method: GET\n        description: List all API tokens.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-token\n        method: POST\n        description: Create a new API token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: catalogs\n      path: /catalogs\n      description: Helm chart catalogs.\n      operations:\n      - name: list-catalogs\n        method: GET\n        description: List registered Helm catalogs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps\n      path: /apps\n      description: Deployed Helm applications.\n      operations:\n      - name: list-apps\n        method: GET\n        description: List deployed apps.\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: role-templates\n      path: /roleTemplates\n      description: Role templates for RBAC.\n      operations:\n      - name: list-role-templates\n        method: GET\n        description: List all role templates.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: rancher-cluster-lifecycle-api\n    description: Unified REST API for Rancher cluster lifecycle management.\n    resources:\n    - path: /v1/clusters\n      name: clusters\n      description: Kubernetes clusters managed by Rancher.\n      operations:\n      - method: GET\n        name: list-clusters\n        description: List all clusters.\n        call: rancher.list-clusters\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-cluster\n\
  \        description: Provision a new cluster.\n        call: rancher.create-cluster\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/clusters/{id}\n      name: cluster\n      description: Single cluster.\n      operations:\n      - method: GET\n        name: get-cluster\n        description: Get cluster details.\n        call: rancher.get-cluster\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-cluster\n        description: Remove a cluster from Rancher.\n        call: rancher.delete-cluster\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/nodes\n      name: nodes\n      description: Cluster nodes.\n      operations:\n      - method: GET\n        name: list-nodes\n        description: List all nodes across clusters.\n        call: rancher.list-nodes\n      \
  \  outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects\n      name: projects\n      description: Rancher projects.\n      operations:\n      - method: GET\n        name: list-projects\n        description: List all projects.\n        call: rancher.list-projects\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-project\n        description: Create a new project.\n        call: rancher.create-project\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: rancher-cluster-lifecycle-mcp\n    transport: http\n    description: MCP server for AI-assisted Kubernetes cluster lifecycle management via Rancher.\n    tools:\n    - name: list-clusters\n      description: List all Kubernetes clusters managed by Rancher, including their state, provider, and Kubernetes version.\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: rancher.list-clusters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cluster\n      description: Retrieve details for a specific Rancher-managed cluster by ID.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: rancher.get-cluster\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-cluster\n      description: Provision a new Kubernetes cluster through Rancher. Specify name, provider, and Kubernetes version.\n      hints:\n        readOnly: false\n        destructive: false\n      call: rancher.create-cluster\n      with:\n        name: tools.name\n        description: tools.description\n        kubernetesVersion: tools.kubernetesVersion\n        provider: tools.provider\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-cluster\n      description: Remove a cluster from Rancher management. This deregisters\
  \ or destroys the cluster.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: rancher.delete-cluster\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-nodes\n      description: List all nodes across Rancher-managed clusters, including hostname, state, and roles.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rancher.list-nodes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-projects\n      description: List all Rancher projects, which group namespaces within clusters for tenancy and policy.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rancher.list-projects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-project\n      description: Create a new Rancher project within a cluster to organize namespaces.\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n      call: rancher.create-project\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
