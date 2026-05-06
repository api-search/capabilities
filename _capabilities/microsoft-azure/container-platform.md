---
categories:
- container-orchestration
consumed_apis: []
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
- list manifests for a repository
- acr list repositories
- get repository attributes
- aks get admin credentials
- acr get repository
- list tags for a repository
- platform as a service
- list repositories
- azure
- list aks clusters
- list aks managed clusters
- cloud
- containers
- enterprise
- aks list clusters
- aks list agent pools
- acr list manifests
- kubernetes
- cloud computing
- container registry
- list container repositories
- acr list tags
- t1
- container repositories
- infrastructure as a service
- aks cluster management
- api management
- aks get agent pool
- get cluster admin credentials
- aks get cluster
- list cluster agent pools
- list clusters
- get agent pool details
- get aks cluster details
slug: container-platform
source_filename: container-platform.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure Container Platform\n  description: Unified workflow for Azure container infrastructure combining AKS cluster management and Container Registry\n    operations. Used by platform engineers, DevOps teams, and SREs managing containerized workloads.\n  tags:\n  - Azure\n  - Kubernetes\n  - Containers\n  - Container Registry\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AZURE_MANAGEMENT_TOKEN: AZURE_MANAGEMENT_TOKEN\n    AZURE_ACR_TOKEN: AZURE_ACR_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: azure-aks\n    baseUri: https://management.azure.com\n    description: Azure Kubernetes Service API\n    authentication:\n      type: bearer\n      token: '{{AZURE_MANAGEMENT_TOKEN}}'\n    resources:\n    - name: managed-clusters\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.ContainerService/managedClusters\n      description: Managed cluster operations\n      operations:\n\
  \      - name: list-clusters\n        method: GET\n        description: List all AKS clusters\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-cluster\n        method: GET\n        description: Get an AKS cluster\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: Resource group name\n        - name: resourceName\n          in: path\n          type: string\n          required: true\n          description: Cluster name\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n      - name: create-or-update-cluster\n        method: PUT\n        description: Create or update an AKS cluster\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: Resource group name\n        - name: resourceName\n          in: path\n          type: string\n          required: true\n          description: Cluster name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-cluster\n        method: DELETE\n        description: Delete an AKS cluster\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description:\
  \ Subscription ID\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: Resource group name\n        - name: resourceName\n          in: path\n          type: string\n          required: true\n          description: Cluster name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-admin-credentials\n        method: POST\n        description: Get cluster admin credentials\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: Resource group name\n        - name: resourceName\n          in: path\n          type: string\n          required: true\n          description: Cluster name\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: agent-pools\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ContainerService/managedClusters/{resourceName}/agentPools\n      description: Agent pool operations\n      operations:\n      - name: list-agent-pools\n        method: GET\n        description: List agent pools\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: Resource group name\n        - name: resourceName\n          in: path\n          type: string\n          required: true\n          description: Cluster name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: get-agent-pool\n        method: GET\n        description: Get an agent pool\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Subscription ID\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: Resource group name\n        - name: resourceName\n          in: path\n          type: string\n          required: true\n          description: Cluster name\n        - name: agentPoolName\n          in: path\n          type: string\n          required: true\n          description: Agent pool name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: azure-acr\n    baseUri: https://{registryName}.azurecr.io\n    description: Azure Container Registry API\n   \
  \ authentication:\n      type: bearer\n      token: '{{AZURE_ACR_TOKEN}}'\n    resources:\n    - name: catalog\n      path: /acr/v1/_catalog\n      description: Registry catalog\n      operations:\n      - name: list-repositories\n        method: GET\n        description: List repositories in the registry\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repositories\n      path: /acr/v1/{repositoryName}\n      description: Repository operations\n      operations:\n      - name: get-repository\n        method: GET\n        description: Get repository attributes\n        inputParameters:\n        - name: repositoryName\n          in: path\n          type: string\n          required: true\n          description: Repository name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-repository\n\
  \        method: DELETE\n        description: Delete a repository\n        inputParameters:\n        - name: repositoryName\n          in: path\n          type: string\n          required: true\n          description: Repository name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags\n      path: /acr/v1/{repositoryName}/_tags\n      description: Tag operations\n      operations:\n      - name: list-tags\n        method: GET\n        description: List tags for a repository\n        inputParameters:\n        - name: repositoryName\n          in: path\n          type: string\n          required: true\n          description: Repository name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: manifests\n      path: /acr/v1/{repositoryName}/_manifests\n      description: Manifest operations\n      operations:\n\
  \      - name: list-manifests\n        method: GET\n        description: List manifests for a repository\n        inputParameters:\n        - name: repositoryName\n          in: path\n          type: string\n          required: true\n          description: Repository name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: azure-container-api\n    description: Unified REST API for Azure container platform.\n    resources:\n    - path: /v1/clusters\n      name: clusters\n      description: AKS cluster management\n      operations:\n      - method: GET\n        name: list-clusters\n        description: List AKS clusters\n        call: azure-aks.list-clusters\n        with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/repositories\n      name: repositories\n      description:\
  \ Container repositories\n      operations:\n      - method: GET\n        name: list-repositories\n        description: List container repositories\n        call: azure-acr.list-repositories\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: azure-container-mcp\n    transport: http\n    description: MCP server for AI-assisted Azure container platform management.\n    tools:\n    - name: aks-list-clusters\n      description: List AKS managed clusters\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-aks.list-clusters\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: aks-get-cluster\n      description: Get AKS cluster details\n      hints:\n        readOnly: true\n      call: azure-aks.get-cluster\n      with:\n        subscriptionId: tools.subscriptionId\n        resourceGroupName: tools.resourceGroupName\n\
  \        resourceName: tools.resourceName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: aks-list-agent-pools\n      description: List cluster agent pools\n      hints:\n        readOnly: true\n      call: azure-aks.list-agent-pools\n      with:\n        subscriptionId: tools.subscriptionId\n        resourceGroupName: tools.resourceGroupName\n        resourceName: tools.resourceName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: aks-get-agent-pool\n      description: Get agent pool details\n      hints:\n        readOnly: true\n      call: azure-aks.get-agent-pool\n      with:\n        subscriptionId: tools.subscriptionId\n        resourceGroupName: tools.resourceGroupName\n        resourceName: tools.resourceName\n        agentPoolName: tools.agentPoolName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: aks-get-admin-credentials\n      description: Get cluster admin credentials\n     \
  \ hints:\n        readOnly: true\n      call: azure-aks.get-admin-credentials\n      with:\n        subscriptionId: tools.subscriptionId\n        resourceGroupName: tools.resourceGroupName\n        resourceName: tools.resourceName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: acr-list-repositories\n      description: List container repositories\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-acr.list-repositories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: acr-get-repository\n      description: Get repository attributes\n      hints:\n        readOnly: true\n      call: azure-acr.get-repository\n      with:\n        repositoryName: tools.repositoryName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: acr-list-tags\n      description: List tags for a repository\n      hints:\n        readOnly: true\n      call: azure-acr.list-tags\n      with:\n     \
  \   repositoryName: tools.repositoryName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: acr-list-manifests\n      description: List manifests for a repository\n      hints:\n        readOnly: true\n      call: azure-acr.list-manifests\n      with:\n        repositoryName: tools.repositoryName\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
