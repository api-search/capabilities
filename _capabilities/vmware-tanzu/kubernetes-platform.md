---
categories: []
consumed_apis:
- tanzu-tsm
description: Workflow capability for platform engineers managing VMware Tanzu Kubernetes infrastructure. Combines Tanzu Service Mesh management (cluster onboarding, global namespaces, resource groups) with Kubernetes cluster lifecycle operations. Targeted at platform ops teams managing multi-cluster Kubernetes environments across clouds and on-premises vSphere.
layout: capability
name: VMware Tanzu Kubernetes Platform Workflow
operations:
- description: List clusters onboarded to Tanzu Service Mesh.
  method: GET
  name: list-clusters
  path: /v1/clusters
- description: Get cluster details and status.
  method: GET
  name: get-cluster
  path: /v1/clusters/{cluster_name}
- description: Onboard a cluster to Tanzu Service Mesh.
  method: PUT
  name: onboard-cluster
  path: /v1/clusters/{cluster_name}
- description: Remove a cluster from TSM.
  method: DELETE
  name: remove-cluster
  path: /v1/clusters/{cluster_name}
- description: List global namespaces.
  method: GET
  name: list-global-namespaces
  path: /v1/global-namespaces
- description: Create a global namespace spanning clusters.
  method: POST
  name: create-global-namespace
  path: /v1/global-namespaces
- description: Get global namespace details.
  method: GET
  name: get-global-namespace
  path: /v1/global-namespaces/{namespace_id}
- description: Delete a global namespace.
  method: DELETE
  name: delete-global-namespace
  path: /v1/global-namespaces/{namespace_id}
- description: List resource groups.
  method: GET
  name: list-resource-groups
  path: /v1/resource-groups
- description: Create a resource group.
  method: POST
  name: create-resource-group
  path: /v1/resource-groups
personas: []
provider_name: VMware Tanzu
provider_slug: vmware-tanzu
search_terms:
- delete global namespace
- individual global namespace.
- vsphere
- resource groups for policy.
- individual cluster operations.
- list tanzu clusters
- get details for a specific global namespace, including cluster configurations and status.
- list all global namespaces in tanzu service mesh. global namespaces connect workloads across multiple clusters into a single virtual network.
- create resource group
- get tanzu cluster
- onboard a cluster to tanzu service mesh.
- onboard cluster
- list clusters onboarded to tanzu service mesh.
- vmware tanzu
- get global namespace
- create a resource group to enforce policies across a set of namespaces, services, or pods.
- list resource groups.
- get detailed status for a specific tanzu service mesh cluster, including phase, k8s version, and namespace count.
- cloud native
- remove a cluster from tsm.
- delete a global namespace.
- create a global namespace to connect workloads across multiple kubernetes clusters. enables consistent traffic routing and mtls security.
- global namespaces
- remove cluster
- kubernetes
- delete a global namespace from tanzu service mesh.
- remove kubernetes cluster
- kubernetes cluster management.
- remove a kubernetes cluster from tanzu service mesh management.
- onboard kubernetes cluster
- global namespace management.
- list resource groups used for policy enforcement and monitoring across clusters.
- onboard a kubernetes cluster to tanzu service mesh. installs the tsm agent and enables service mesh management.
- get global namespace details.
- service mesh
- create a resource group.
- list global namespaces
- multi-cloud
- enterprise
- list global namespaces.
- get cluster
- list all kubernetes clusters onboarded to tanzu service mesh. shows cluster state, cloud provider, region, and tsm agent version.
- create a global namespace spanning clusters.
- containers
- create global namespace
- clusters
- list clusters
- list resource groups
- get cluster details and status.
- vmware
slug: kubernetes-platform
source_filename: kubernetes-platform.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"VMware Tanzu Kubernetes Platform Workflow\"\n  description: >-\n    Workflow capability for platform engineers managing VMware Tanzu Kubernetes\n    infrastructure. Combines Tanzu Service Mesh management (cluster onboarding,\n    global namespaces, resource groups) with Kubernetes cluster lifecycle\n    operations. Targeted at platform ops teams managing multi-cluster\n    Kubernetes environments across clouds and on-premises vSphere.\n  tags:\n    - VMware Tanzu\n    - Cloud Native\n    - Clusters\n    - Containers\n    - Enterprise\n    - Global Namespaces\n    - Kubernetes\n    - Multi-Cloud\n    - Service Mesh\n    - vSphere\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TANZU_CSP_API_TOKEN: TANZU_CSP_API_TOKEN\n\ncapability:\n  consumes:\n    - import: tanzu-tsm\n      location: ./shared/tanzu-service-mesh.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n     \
  \ namespace: tanzu-platform-api\n      description: \"Unified REST API for VMware Tanzu Kubernetes platform management.\"\n      resources:\n        - path: /v1/clusters\n          name: clusters\n          description: \"Kubernetes cluster management.\"\n          operations:\n            - method: GET\n              name: list-clusters\n              description: \"List clusters onboarded to Tanzu Service Mesh.\"\n              call: \"tanzu-tsm.list-clusters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/clusters/{cluster_name}\n          name: cluster-detail\n          description: \"Individual cluster operations.\"\n          operations:\n            - method: GET\n              name: get-cluster\n              description: \"Get cluster details and status.\"\n              call: \"tanzu-tsm.get-cluster\"\n              with:\n                cluster_name: \"rest.cluster_name\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: onboard-cluster\n              description: \"Onboard a cluster to Tanzu Service Mesh.\"\n              call: \"tanzu-tsm.onboard-cluster\"\n              with:\n                cluster_name: \"rest.cluster_name\"\n                display_name: \"rest.display_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: remove-cluster\n              description: \"Remove a cluster from TSM.\"\n              call: \"tanzu-tsm.remove-cluster\"\n              with:\n                cluster_name: \"rest.cluster_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/global-namespaces\n          name: global-namespaces\n          description: \"Global namespace management.\"\n          operations:\n           \
  \ - method: GET\n              name: list-global-namespaces\n              description: \"List global namespaces.\"\n              call: \"tanzu-tsm.list-global-namespaces\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-global-namespace\n              description: \"Create a global namespace spanning clusters.\"\n              call: \"tanzu-tsm.create-global-namespace\"\n              with:\n                name: \"rest.name\"\n                domain_name: \"rest.domain_name\"\n                mtls_enforced: \"rest.mtls_enforced\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/global-namespaces/{namespace_id}\n          name: global-namespace-detail\n          description: \"Individual global namespace.\"\n          operations:\n            - method: GET\n              name: get-global-namespace\n     \
  \         description: \"Get global namespace details.\"\n              call: \"tanzu-tsm.get-global-namespace\"\n              with:\n                namespace_id: \"rest.namespace_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-global-namespace\n              description: \"Delete a global namespace.\"\n              call: \"tanzu-tsm.delete-global-namespace\"\n              with:\n                namespace_id: \"rest.namespace_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/resource-groups\n          name: resource-groups\n          description: \"Resource groups for policy.\"\n          operations:\n            - method: GET\n              name: list-resource-groups\n              description: \"List resource groups.\"\n              call: \"tanzu-tsm.list-resource-groups\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-resource-group\n              description: \"Create a resource group.\"\n              call: \"tanzu-tsm.create-resource-group\"\n              with:\n                name: \"rest.name\"\n                resource_type: \"rest.resource_type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: tanzu-platform-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Tanzu Kubernetes platform operations.\"\n      tools:\n        - name: list-tanzu-clusters\n          description: \"List all Kubernetes clusters onboarded to Tanzu Service Mesh. Shows cluster state, cloud provider, region, and TSM agent version.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tanzu-tsm.list-clusters\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: get-tanzu-cluster\n          description: \"Get detailed status for a specific Tanzu Service Mesh cluster, including phase, k8s version, and namespace count.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tanzu-tsm.get-cluster\"\n          with:\n            cluster_name: \"tools.cluster_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: onboard-kubernetes-cluster\n          description: \"Onboard a Kubernetes cluster to Tanzu Service Mesh. Installs the TSM agent and enables service mesh management.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"tanzu-tsm.onboard-cluster\"\n          with:\n            cluster_name: \"tools.cluster_name\"\n            display_name: \"tools.display_name\"\n            description: \"tools.description\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: remove-kubernetes-cluster\n          description: \"Remove a Kubernetes cluster from Tanzu Service Mesh management.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"tanzu-tsm.remove-cluster\"\n          with:\n            cluster_name: \"tools.cluster_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-global-namespaces\n          description: \"List all global namespaces in Tanzu Service Mesh. Global namespaces connect workloads across multiple clusters into a single virtual network.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tanzu-tsm.list-global-namespaces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-global-namespace\n          description:\
  \ \"Create a global namespace to connect workloads across multiple Kubernetes clusters. Enables consistent traffic routing and mTLS security.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"tanzu-tsm.create-global-namespace\"\n          with:\n            name: \"tools.name\"\n            domain_name: \"tools.domain_name\"\n            mtls_enforced: \"tools.mtls_enforced\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-global-namespace\n          description: \"Get details for a specific global namespace, including cluster configurations and status.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tanzu-tsm.get-global-namespace\"\n          with:\n            namespace_id: \"tools.namespace_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-global-namespace\n\
  \          description: \"Delete a global namespace from Tanzu Service Mesh.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"tanzu-tsm.delete-global-namespace\"\n          with:\n            namespace_id: \"tools.namespace_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-resource-groups\n          description: \"List resource groups used for policy enforcement and monitoring across clusters.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tanzu-tsm.list-resource-groups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-resource-group\n          description: \"Create a resource group to enforce policies across a set of namespaces, services, or pods.\"\n          hints:\n            readOnly: false\n            idempotent: false\n\
  \          call: \"tanzu-tsm.create-resource-group\"\n          with:\n            name: \"tools.name\"\n            resource_type: \"tools.resource_type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vmware-tanzu/refs/heads/main/capabilities/kubernetes-platform.yaml
tags:
- VMware Tanzu
- Cloud Native
- Clusters
- Containers
- Enterprise
- Global Namespaces
- Kubernetes
- Multi-Cloud
- Service Mesh
- vSphere
tools:
- description: List all Kubernetes clusters onboarded to Tanzu Service Mesh. Shows cluster state, cloud provider, region, and TSM agent version.
  hints:
    idempotent: true
    readOnly: true
  name: list-tanzu-clusters
- description: Get detailed status for a specific Tanzu Service Mesh cluster, including phase, k8s version, and namespace count.
  hints:
    idempotent: true
    readOnly: true
  name: get-tanzu-cluster
- description: Onboard a Kubernetes cluster to Tanzu Service Mesh. Installs the TSM agent and enables service mesh management.
  hints:
    idempotent: true
    readOnly: false
  name: onboard-kubernetes-cluster
- description: Remove a Kubernetes cluster from Tanzu Service Mesh management.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: remove-kubernetes-cluster
- description: List all global namespaces in Tanzu Service Mesh. Global namespaces connect workloads across multiple clusters into a single virtual network.
  hints:
    idempotent: true
    readOnly: true
  name: list-global-namespaces
- description: Create a global namespace to connect workloads across multiple Kubernetes clusters. Enables consistent traffic routing and mTLS security.
  hints:
    idempotent: false
    readOnly: false
  name: create-global-namespace
- description: Get details for a specific global namespace, including cluster configurations and status.
  hints:
    idempotent: true
    readOnly: true
  name: get-global-namespace
- description: Delete a global namespace from Tanzu Service Mesh.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-global-namespace
- description: List resource groups used for policy enforcement and monitoring across clusters.
  hints:
    idempotent: true
    readOnly: true
  name: list-resource-groups
- description: Create a resource group to enforce policies across a set of namespaces, services, or pods.
  hints:
    idempotent: false
    readOnly: false
  name: create-resource-group
---
