---
categories:
- container-orchestration
consumed_apis:
- azure-aks
- azure-acr
description: Unified workflow for Azure container infrastructure combining AKS cluster management and Container Registry operations. Used by platform engineers, DevOps teams, and SREs managing containerized workloads.
layout: capability
name: Azure Container Platform
operations:
- description: List AKS clusters
  method: GET
  name: list-clusters
  path: /v1/clusters
- description: List container repositories
  method: GET
  name: list-repositories
  path: /v1/repositories
personas: []
provider_name: Microsoft Azure
provider_slug: microsoft-azure
search_terms:
- container registry
- get cluster admin credentials
- aks get agent pool
- get repository attributes
- get agent pool details
- list aks clusters
- enterprise
- acr list repositories
- aks get admin credentials
- aks get cluster
- aks cluster management
- aks list clusters
- list tags for a repository
- get aks cluster details
- azure
- infrastructure as a service
- container repositories
- containers
- aks list agent pools
- cloud computing
- kubernetes
- list container repositories
- list aks managed clusters
- acr get repository
- list manifests for a repository
- acr list manifests
- t1
- cloud
- list repositories
- acr list tags
- list cluster agent pools
- list clusters
- platform as a service
- api management
slug: container-platform
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Azure Container Platform\"\n  description: \"Unified workflow for Azure container infrastructure combining AKS cluster management and Container Registry operations. Used by platform engineers, DevOps teams, and SREs managing containerized workloads.\"\n  tags:\n    - Azure\n    - Kubernetes\n    - Containers\n    - Container Registry\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      AZURE_MANAGEMENT_TOKEN: AZURE_MANAGEMENT_TOKEN\n      AZURE_ACR_TOKEN: AZURE_ACR_TOKEN\n\ncapability:\n  consumes:\n    - import: azure-aks\n      location: ./shared/kubernetes-service.yaml\n    - import: azure-acr\n      location: ./shared/container-registry.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: azure-container-api\n      description: \"Unified REST API for Azure container platform.\"\n      resources:\n        - path: /v1/clusters\n          name: clusters\n  \
  \        description: \"AKS cluster management\"\n          operations:\n            - method: GET\n              name: list-clusters\n              description: \"List AKS clusters\"\n              call: \"azure-aks.list-clusters\"\n              with:\n                subscriptionId: \"rest.subscriptionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repositories\n          name: repositories\n          description: \"Container repositories\"\n          operations:\n            - method: GET\n              name: list-repositories\n              description: \"List container repositories\"\n              call: \"azure-acr.list-repositories\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: azure-container-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Azure container platform\
  \ management.\"\n      tools:\n        - name: aks-list-clusters\n          description: \"List AKS managed clusters\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-aks.list-clusters\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: aks-get-cluster\n          description: \"Get AKS cluster details\"\n          hints:\n            readOnly: true\n          call: \"azure-aks.get-cluster\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n            resourceGroupName: \"tools.resourceGroupName\"\n            resourceName: \"tools.resourceName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: aks-list-agent-pools\n          description: \"List cluster agent pools\"\n          hints:\n            readOnly: true\n          call: \"azure-aks.list-agent-pools\"\
  \n          with:\n            subscriptionId: \"tools.subscriptionId\"\n            resourceGroupName: \"tools.resourceGroupName\"\n            resourceName: \"tools.resourceName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: aks-get-agent-pool\n          description: \"Get agent pool details\"\n          hints:\n            readOnly: true\n          call: \"azure-aks.get-agent-pool\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n            resourceGroupName: \"tools.resourceGroupName\"\n            resourceName: \"tools.resourceName\"\n            agentPoolName: \"tools.agentPoolName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: aks-get-admin-credentials\n          description: \"Get cluster admin credentials\"\n          hints:\n            readOnly: true\n          call: \"azure-aks.get-admin-credentials\"\n          with:\n           \
  \ subscriptionId: \"tools.subscriptionId\"\n            resourceGroupName: \"tools.resourceGroupName\"\n            resourceName: \"tools.resourceName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: acr-list-repositories\n          description: \"List container repositories\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-acr.list-repositories\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: acr-get-repository\n          description: \"Get repository attributes\"\n          hints:\n            readOnly: true\n          call: \"azure-acr.get-repository\"\n          with:\n            repositoryName: \"tools.repositoryName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: acr-list-tags\n          description: \"List tags for a repository\"\n          hints:\n     \
  \       readOnly: true\n          call: \"azure-acr.list-tags\"\n          with:\n            repositoryName: \"tools.repositoryName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: acr-list-manifests\n          description: \"List manifests for a repository\"\n          hints:\n            readOnly: true\n          call: \"azure-acr.list-manifests\"\n          with:\n            repositoryName: \"tools.repositoryName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-azure/refs/heads/main/capabilities/container-platform.yaml
tags:
- Azure
- Kubernetes
- Containers
- Container Registry
tools:
- description: List AKS managed clusters
  hints:
    openWorld: true
    readOnly: true
  name: aks-list-clusters
- description: Get AKS cluster details
  hints:
    readOnly: true
  name: aks-get-cluster
- description: List cluster agent pools
  hints:
    readOnly: true
  name: aks-list-agent-pools
- description: Get agent pool details
  hints:
    readOnly: true
  name: aks-get-agent-pool
- description: Get cluster admin credentials
  hints:
    readOnly: true
  name: aks-get-admin-credentials
- description: List container repositories
  hints:
    openWorld: true
    readOnly: true
  name: acr-list-repositories
- description: Get repository attributes
  hints:
    readOnly: true
  name: acr-get-repository
- description: List tags for a repository
  hints:
    readOnly: true
  name: acr-list-tags
- description: List manifests for a repository
  hints:
    readOnly: true
  name: acr-list-manifests
---
