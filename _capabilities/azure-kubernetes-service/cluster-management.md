---
categories:
- container-orchestration
consumed_apis:
- aks-rest
description: Workflow for managing AKS clusters and agent pools including lifecycle operations, upgrades, scaling, and credentials. Used by DevOps engineers and platform administrators.
layout: capability
name: Azure Kubernetes Service Cluster Management
operations:
- description: List all managed clusters
  method: GET
  name: list-clusters
  path: /v1/clusters
- description: Get cluster details
  method: GET
  name: get-cluster
  path: /v1/clusters/{resourceName}
- description: Create or update a cluster
  method: PUT
  name: create-or-update-cluster
  path: /v1/clusters/{resourceName}
- description: Delete a cluster
  method: DELETE
  name: delete-cluster
  path: /v1/clusters/{resourceName}
- description: List agent pools in a cluster
  method: GET
  name: list-agent-pools
  path: /v1/clusters/{resourceName}/agent-pools
personas: []
provider_name: Azure Kubernetes Service
provider_slug: azure-kubernetes-service
search_terms:
- get details of an aks cluster
- get cluster
- orchestration
- get cluster details
- get agent pool details
- create or update agent pool
- delete cluster
- delete an aks managed cluster
- create or update cluster
- delete agent pool
- agent pool operations
- list clusters
- single cluster operations
- stop cluster
- cloud
- containers
- create or update an agent pool
- get upgrade profile
- create or update a cluster
- delete a cluster
- devops
- azure
- get agent pool
- list agent pools in a cluster
- stop a running aks cluster
- get the upgrade profile for a cluster
- cluster management
- kubernetes
- list agent pools
- cluster lifecycle operations
- list all managed clusters
- delete an agent pool from a cluster
- start a stopped aks cluster
- list all aks managed clusters in a subscription
- create or update an aks managed cluster
- start cluster
slug: cluster-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Azure Kubernetes Service Cluster Management\"\n  description: \"Workflow for managing AKS clusters and agent pools including lifecycle operations, upgrades, scaling, and credentials. Used by DevOps engineers and platform administrators.\"\n  tags:\n    - Azure\n    - Kubernetes\n    - Cluster Management\n    - DevOps\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      AZURE_BEARER_TOKEN: AZURE_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: aks-rest\n      location: ./shared/aks-rest.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: aks-cluster-api\n      description: \"Unified REST API for AKS cluster management.\"\n      resources:\n        - path: /v1/clusters\n          name: clusters\n          description: \"Cluster lifecycle operations\"\n          operations:\n            - method: GET\n              name: list-clusters\n              description:\
  \ \"List all managed clusters\"\n              call: \"aks-rest.list-clusters\"\n              with:\n                subscriptionId: \"rest.subscriptionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/clusters/{resourceName}\n          name: cluster\n          description: \"Single cluster operations\"\n          operations:\n            - method: GET\n              name: get-cluster\n              description: \"Get cluster details\"\n              call: \"aks-rest.get-cluster\"\n              with:\n                subscriptionId: \"rest.subscriptionId\"\n                resourceGroupName: \"rest.resourceGroupName\"\n                resourceName: \"rest.resourceName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: create-or-update-cluster\n              description: \"Create or update a cluster\"\n         \
  \     call: \"aks-rest.create-or-update-cluster\"\n              with:\n                subscriptionId: \"rest.subscriptionId\"\n                resourceGroupName: \"rest.resourceGroupName\"\n                resourceName: \"rest.resourceName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-cluster\n              description: \"Delete a cluster\"\n              call: \"aks-rest.delete-cluster\"\n              with:\n                subscriptionId: \"rest.subscriptionId\"\n                resourceGroupName: \"rest.resourceGroupName\"\n                resourceName: \"rest.resourceName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/clusters/{resourceName}/agent-pools\n          name: agent-pools\n          description: \"Agent pool operations\"\n          operations:\n            - method: GET\n          \
  \    name: list-agent-pools\n              description: \"List agent pools in a cluster\"\n              call: \"aks-rest.list-agent-pools\"\n              with:\n                subscriptionId: \"rest.subscriptionId\"\n                resourceGroupName: \"rest.resourceGroupName\"\n                resourceName: \"rest.resourceName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: aks-cluster-mcp\n      transport: http\n      description: \"MCP server for AI-assisted AKS cluster management.\"\n      tools:\n        - name: list-clusters\n          description: \"List all AKS managed clusters in a subscription\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"aks-rest.list-clusters\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n        - name: get-cluster\n          description: \"Get details of an AKS cluster\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"aks-rest.get-cluster\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n            resourceGroupName: \"tools.resourceGroupName\"\n            resourceName: \"tools.resourceName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-or-update-cluster\n          description: \"Create or update an AKS managed cluster\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"aks-rest.create-or-update-cluster\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n            resourceGroupName: \"tools.resourceGroupName\"\n            resourceName: \"tools.resourceName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        -\
  \ name: delete-cluster\n          description: \"Delete an AKS managed cluster\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"aks-rest.delete-cluster\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n            resourceGroupName: \"tools.resourceGroupName\"\n            resourceName: \"tools.resourceName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-upgrade-profile\n          description: \"Get the upgrade profile for a cluster\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"aks-rest.get-upgrade-profile\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n            resourceGroupName: \"tools.resourceGroupName\"\n            resourceName: \"tools.resourceName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n        - name: stop-cluster\n          description: \"Stop a running AKS cluster\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"aks-rest.stop-cluster\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n            resourceGroupName: \"tools.resourceGroupName\"\n            resourceName: \"tools.resourceName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-cluster\n          description: \"Start a stopped AKS cluster\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"aks-rest.start-cluster\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n            resourceGroupName: \"tools.resourceGroupName\"\n            resourceName: \"tools.resourceName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-agent-pools\n          description:\
  \ \"List agent pools in a cluster\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"aks-rest.list-agent-pools\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n            resourceGroupName: \"tools.resourceGroupName\"\n            resourceName: \"tools.resourceName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-agent-pool\n          description: \"Get agent pool details\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"aks-rest.get-agent-pool\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n            resourceGroupName: \"tools.resourceGroupName\"\n            resourceName: \"tools.resourceName\"\n            agentPoolName: \"tools.agentPoolName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-or-update-agent-pool\n\
  \          description: \"Create or update an agent pool\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"aks-rest.create-or-update-agent-pool\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n            resourceGroupName: \"tools.resourceGroupName\"\n            resourceName: \"tools.resourceName\"\n            agentPoolName: \"tools.agentPoolName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-agent-pool\n          description: \"Delete an agent pool from a cluster\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"aks-rest.delete-agent-pool\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n            resourceGroupName: \"tools.resourceGroupName\"\n            resourceName: \"tools.resourceName\"\n            agentPoolName: \"tools.agentPoolName\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/azure-kubernetes-service/refs/heads/main/capabilities/cluster-management.yaml
tags:
- Azure
- Kubernetes
- Cluster Management
- DevOps
tools:
- description: List all AKS managed clusters in a subscription
  hints:
    idempotent: true
    readOnly: true
  name: list-clusters
- description: Get details of an AKS cluster
  hints:
    idempotent: true
    readOnly: true
  name: get-cluster
- description: Create or update an AKS managed cluster
  hints:
    idempotent: true
    readOnly: false
  name: create-or-update-cluster
- description: Delete an AKS managed cluster
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-cluster
- description: Get the upgrade profile for a cluster
  hints:
    idempotent: true
    readOnly: true
  name: get-upgrade-profile
- description: Stop a running AKS cluster
  hints:
    idempotent: true
    readOnly: false
  name: stop-cluster
- description: Start a stopped AKS cluster
  hints:
    idempotent: true
    readOnly: false
  name: start-cluster
- description: List agent pools in a cluster
  hints:
    idempotent: true
    readOnly: true
  name: list-agent-pools
- description: Get agent pool details
  hints:
    idempotent: true
    readOnly: true
  name: get-agent-pool
- description: Create or update an agent pool
  hints:
    idempotent: true
    readOnly: false
  name: create-or-update-agent-pool
- description: Delete an agent pool from a cluster
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-agent-pool
---
