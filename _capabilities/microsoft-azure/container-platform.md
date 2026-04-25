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
- aks list clusters
- get aks cluster details
- acr list repositories
- acr list manifests
- list repositories
- t1
- aks get admin credentials
- list container repositories
- containers
- aks get cluster
- aks list agent pools
- enterprise
- aks cluster management
- acr get repository
- get repository attributes
- list aks clusters
- platform as a service
- acr list tags
- get agent pool details
- list tags for a repository
- list manifests for a repository
- kubernetes
- get cluster admin credentials
- azure
- list aks managed clusters
- aks get agent pool
- list cluster agent pools
- api management
- container registry
- cloud
- infrastructure as a service
- cloud computing
- container repositories
- list clusters
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
