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
- get elastigroup activity logs
- get right-sizing suggestions for an ocean cluster
- ocean list clusters aks
- ocean list spark clusters
- cost optimization
- elastigroup get status aws
- list ocean virtual node groups
- ocean get right sizing
- list azure elastigroups
- elastigroup list groups aws
- ocean list clusters aws
- list aks ocean clusters
- spot instances
- list virtual node groups
- list gke ocean clusters
- containers
- list ocean spark clusters
- get elastigroup cost data
- scale up an aws elastigroup
- ocean get cluster aws
- get an aws elastigroup by id
- get elastigroup instance status
- compute
- elastigroup list gcp
- elastigroup compute groups
- ocean virtual node groups
- list aws elastigroups
- get an aws ocean cluster
- kubernetes
- list elastigroups
- list all aws elastigroups
- ocean list clusters gke
- ocean list virtual node groups
- elastigroup list azure
- elastigroup scale up aws
- elastigroup get costs
- ocean kubernetes clusters
- elastigroup get logs
- spot
- list gcp elastigroups
- scale down an aws elastigroup
- cloud infrastructure
- list ocean clusters
- elastigroup scale down aws
- finops
- elastigroup get group aws
- list aws ocean clusters
- autoscaling
slug: compute-optimization
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Spot Compute Optimization\"\n  description: \"Unified workflow for managing cloud compute optimization across Elastigroup and Ocean, combining instance management, autoscaling, and Kubernetes infrastructure automation. Used by DevOps engineers and cloud infrastructure teams.\"\n  tags:\n    - Spot\n    - Compute\n    - Autoscaling\n    - Kubernetes\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SPOT_API_TOKEN: SPOT_API_TOKEN\n\ncapability:\n  consumes:\n    - import: spot-elastigroup\n      location: ./shared/elastigroup.yaml\n    - import: spot-ocean\n      location: ./shared/ocean.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: spot-compute-api\n      description: \"Unified REST API for Spot compute optimization.\"\n      resources:\n        - path: /v1/elastigroups\n          name: elastigroups\n          description: \"Elastigroup compute groups\"\
  \n          operations:\n            - method: GET\n              name: list-elastigroups\n              description: \"List AWS Elastigroups\"\n              call: \"spot-elastigroup.list-elastigroups-aws\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ocean-clusters\n          name: ocean-clusters\n          description: \"Ocean Kubernetes clusters\"\n          operations:\n            - method: GET\n              name: list-ocean-clusters\n              description: \"List AWS Ocean clusters\"\n              call: \"spot-ocean.list-ocean-clusters-aws\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/virtual-node-groups\n          name: virtual-node-groups\n          description: \"Ocean virtual node groups\"\n          operations:\n            - method: GET\n              name: list-virtual-node-groups\n              description: \"List\
  \ virtual node groups\"\n              call: \"spot-ocean.list-virtual-node-groups-aws\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: spot-compute-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Spot compute optimization.\"\n      tools:\n        - name: elastigroup-list-groups-aws\n          description: \"List all AWS Elastigroups\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spot-elastigroup.list-elastigroups-aws\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: elastigroup-get-group-aws\n          description: \"Get an AWS Elastigroup by ID\"\n          hints:\n            readOnly: true\n          call: \"spot-elastigroup.get-elastigroup-aws\"\n          with:\n            groupId: \"tools.groupId\"\n          outputParameters:\n          \
  \  - type: object\n              mapping: \"$.\"\n        - name: elastigroup-get-status-aws\n          description: \"Get Elastigroup instance status\"\n          hints:\n            readOnly: true\n          call: \"spot-elastigroup.get-elastigroup-status-aws\"\n          with:\n            groupId: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: elastigroup-get-costs\n          description: \"Get Elastigroup cost data\"\n          hints:\n            readOnly: true\n          call: \"spot-elastigroup.get-elastigroup-costs\"\n          with:\n            groupId: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: elastigroup-get-logs\n          description: \"Get Elastigroup activity logs\"\n          hints:\n            readOnly: true\n          call: \"spot-elastigroup.get-elastigroup-logs\"\n          with:\n            groupId: \"tools.groupId\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: elastigroup-scale-up-aws\n          description: \"Scale up an AWS Elastigroup\"\n          hints:\n            readOnly: false\n          call: \"spot-elastigroup.scale-up-elastigroup-aws\"\n          with:\n            groupId: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: elastigroup-scale-down-aws\n          description: \"Scale down an AWS Elastigroup\"\n          hints:\n            readOnly: false\n          call: \"spot-elastigroup.scale-down-elastigroup-aws\"\n          with:\n            groupId: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: elastigroup-list-azure\n          description: \"List Azure Elastigroups\"\n          hints:\n            readOnly: true\n          call: \"spot-elastigroup.list-elastigroups-azure\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: elastigroup-list-gcp\n          description: \"List GCP Elastigroups\"\n          hints:\n            readOnly: true\n          call: \"spot-elastigroup.list-elastigroups-gcp\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ocean-list-clusters-aws\n          description: \"List AWS Ocean clusters\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spot-ocean.list-ocean-clusters-aws\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ocean-get-cluster-aws\n          description: \"Get an AWS Ocean cluster\"\n          hints:\n            readOnly: true\n          call: \"spot-ocean.get-ocean-cluster-aws\"\n          with:\n            oceanId: \"tools.oceanId\"\n          outputParameters:\n            - type: object\n         \
  \     mapping: \"$.\"\n        - name: ocean-get-right-sizing\n          description: \"Get right-sizing suggestions for an Ocean cluster\"\n          hints:\n            readOnly: true\n          call: \"spot-ocean.get-right-sizing-suggestions\"\n          with:\n            oceanId: \"tools.oceanId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ocean-list-virtual-node-groups\n          description: \"List Ocean virtual node groups\"\n          hints:\n            readOnly: true\n          call: \"spot-ocean.list-virtual-node-groups-aws\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ocean-list-clusters-aks\n          description: \"List AKS Ocean clusters\"\n          hints:\n            readOnly: true\n          call: \"spot-ocean.list-ocean-clusters-aks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ocean-list-clusters-gke\n\
  \          description: \"List GKE Ocean clusters\"\n          hints:\n            readOnly: true\n          call: \"spot-ocean.list-ocean-clusters-gke\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ocean-list-spark-clusters\n          description: \"List Ocean Spark clusters\"\n          hints:\n            readOnly: true\n          call: \"spot-ocean.list-ocean-spark-clusters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spot/refs/heads/main/capabilities/compute-optimization.yaml
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
