---
categories:
- container-orchestration
consumed_apis:
- spot-elastigroup
- spot-ocean
description: Unified workflow for managing cloud compute optimization across Elastigroup and Ocean, combining instance management, autoscaling, and Kubernetes infrastructure automation. Used by DevOps engineers and cloud infrastructure teams.
layout: capability
name: Spot Compute Optimization
operations:
- description: List AWS Elastigroups
  method: GET
  name: list-elastigroups
  path: /v1/elastigroups
- description: List AWS Ocean clusters
  method: GET
  name: list-ocean-clusters
  path: /v1/ocean-clusters
- description: List virtual node groups
  method: GET
  name: list-virtual-node-groups
  path: /v1/virtual-node-groups
personas: []
provider_name: Spot
provider_slug: spot
search_terms:
- get elastigroup instance status
- cost optimization
- get an aws elastigroup by id
- elastigroup list groups aws
- autoscaling
- elastigroup scale up aws
- compute
- list aws ocean clusters
- finops
- kubernetes
- spot
- ocean list clusters aws
- ocean list clusters aks
- elastigroup get costs
- elastigroup list azure
- list ocean spark clusters
- ocean virtual node groups
- ocean list clusters gke
- scale up an aws elastigroup
- ocean kubernetes clusters
- ocean list virtual node groups
- ocean get right sizing
- cloud infrastructure
- list aks ocean clusters
- list ocean virtual node groups
- list aws elastigroups
- containers
- list azure elastigroups
- ocean list spark clusters
- scale down an aws elastigroup
- list virtual node groups
- get elastigroup activity logs
- elastigroup get group aws
- elastigroup list gcp
- get an aws ocean cluster
- get elastigroup cost data
- ocean get cluster aws
- elastigroup get logs
- list gcp elastigroups
- list ocean clusters
- list elastigroups
- spot instances
- elastigroup compute groups
- list all aws elastigroups
- get right-sizing suggestions for an ocean cluster
- elastigroup get status aws
- list gke ocean clusters
- elastigroup scale down aws
slug: compute-optimization
tags:
- Spot
- Compute
- Autoscaling
- Kubernetes
tools:
- description: List all AWS Elastigroups
  hints:
    openWorld: true
    readOnly: true
  name: elastigroup-list-groups-aws
- description: Get an AWS Elastigroup by ID
  hints:
    readOnly: true
  name: elastigroup-get-group-aws
- description: Get Elastigroup instance status
  hints:
    readOnly: true
  name: elastigroup-get-status-aws
- description: Get Elastigroup cost data
  hints:
    readOnly: true
  name: elastigroup-get-costs
- description: Get Elastigroup activity logs
  hints:
    readOnly: true
  name: elastigroup-get-logs
- description: Scale up an AWS Elastigroup
  hints:
    readOnly: false
  name: elastigroup-scale-up-aws
- description: Scale down an AWS Elastigroup
  hints:
    readOnly: false
  name: elastigroup-scale-down-aws
- description: List Azure Elastigroups
  hints:
    readOnly: true
  name: elastigroup-list-azure
- description: List GCP Elastigroups
  hints:
    readOnly: true
  name: elastigroup-list-gcp
- description: List AWS Ocean clusters
  hints:
    openWorld: true
    readOnly: true
  name: ocean-list-clusters-aws
- description: Get an AWS Ocean cluster
  hints:
    readOnly: true
  name: ocean-get-cluster-aws
- description: Get right-sizing suggestions for an Ocean cluster
  hints:
    readOnly: true
  name: ocean-get-right-sizing
- description: List Ocean virtual node groups
  hints:
    readOnly: true
  name: ocean-list-virtual-node-groups
- description: List AKS Ocean clusters
  hints:
    readOnly: true
  name: ocean-list-clusters-aks
- description: List GKE Ocean clusters
  hints:
    readOnly: true
  name: ocean-list-clusters-gke
- description: List Ocean Spark clusters
  hints:
    readOnly: true
  name: ocean-list-spark-clusters
---
