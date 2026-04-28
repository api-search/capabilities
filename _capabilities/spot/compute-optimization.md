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
- list ocean virtual node groups
- elastigroup get costs
- get elastigroup cost data
- containers
- get an aws elastigroup by id
- ocean list clusters gke
- elastigroup get logs
- kubernetes
- get an aws ocean cluster
- list aks ocean clusters
- list elastigroups
- list azure elastigroups
- elastigroup get status aws
- ocean list clusters aks
- elastigroup list gcp
- scale down an aws elastigroup
- list virtual node groups
- ocean list clusters aws
- compute
- list gcp elastigroups
- list aws ocean clusters
- spot instances
- list aws elastigroups
- ocean kubernetes clusters
- ocean list spark clusters
- ocean list virtual node groups
- elastigroup list groups aws
- list gke ocean clusters
- spot
- get right-sizing suggestions for an ocean cluster
- elastigroup scale down aws
- elastigroup list azure
- ocean get right sizing
- list ocean spark clusters
- ocean virtual node groups
- scale up an aws elastigroup
- elastigroup get group aws
- elastigroup compute groups
- ocean get cluster aws
- list all aws elastigroups
- finops
- get elastigroup instance status
- get elastigroup activity logs
- cost optimization
- elastigroup scale up aws
- cloud infrastructure
- autoscaling
- list ocean clusters
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
