---
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
- enterprise
- acr list tags
- list clusters
- aks list clusters
- get repository attributes
- platform as a service
- api management
- aks cluster management
- azure
- cloud
- infrastructure as a service
- t1
- list aks managed clusters
- aks get cluster
- get agent pool details
- get aks cluster details
- container repositories
- list repositories
- containers
- list tags for a repository
- acr list manifests
- aks get agent pool
- acr list repositories
- acr get repository
- container registry
- cloud computing
- list container repositories
- get cluster admin credentials
- list aks clusters
- kubernetes
- aks get admin credentials
- list manifests for a repository
- aks list agent pools
- list cluster agent pools
slug: container-platform
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
