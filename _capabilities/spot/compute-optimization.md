---
categories:
- container-orchestration
consumed_apis: []
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
- compute
- ocean virtual node groups
- get elastigroup activity logs
- elastigroup get logs
- get elastigroup instance status
- get right-sizing suggestions for an ocean cluster
- finops
- scale down an aws elastigroup
- ocean kubernetes clusters
- list ocean virtual node groups
- ocean list clusters aks
- elastigroup get status aws
- get elastigroup cost data
- scale up an aws elastigroup
- spot instances
- cloud infrastructure
- list ocean clusters
- containers
- get an aws elastigroup by id
- elastigroup get costs
- list ocean spark clusters
- kubernetes
- elastigroup get group aws
- elastigroup list gcp
- list all aws elastigroups
- ocean list clusters aws
- list virtual node groups
- cost optimization
- list aks ocean clusters
- list aws ocean clusters
- get an aws ocean cluster
- elastigroup list azure
- list gcp elastigroups
- ocean list spark clusters
- elastigroup list groups aws
- ocean get cluster aws
- list azure elastigroups
- spot
- list aws elastigroups
- elastigroup compute groups
- ocean get right sizing
- list gke ocean clusters
- elastigroup scale down aws
- list elastigroups
- elastigroup scale up aws
- ocean list clusters gke
- autoscaling
- ocean list virtual node groups
slug: compute-optimization
source_filename: compute-optimization.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Spot Compute Optimization\n  description: Unified workflow for managing cloud compute optimization across Elastigroup and Ocean, combining instance management,\n    autoscaling, and Kubernetes infrastructure automation. Used by DevOps engineers and cloud infrastructure teams.\n  tags:\n  - Spot\n  - Compute\n  - Autoscaling\n  - Kubernetes\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPOT_API_TOKEN: SPOT_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: spot-elastigroup\n    baseUri: https://api.spotinst.io\n    description: Spot Elastigroup API\n    authentication:\n      type: bearer\n      token: '{{SPOT_API_TOKEN}}'\n    resources:\n    - name: elastigroup-aws\n      path: /aws/ec2/group\n      description: Manage AWS Elastigroups\n      operations:\n      - name: create-elastigroup-aws\n        method: POST\n        description: Create an AWS Elastigroup\n        inputParameters:\
  \ []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-elastigroups-aws\n        method: GET\n        description: List all AWS Elastigroups\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-elastigroup-aws\n        method: GET\n        description: Get an AWS Elastigroup\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Elastigroup ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-elastigroup-aws\n        method: PUT\n        description: Update an AWS Elastigroup\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required:\
  \ true\n          description: Elastigroup ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-elastigroup-aws\n        method: DELETE\n        description: Delete an AWS Elastigroup\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Elastigroup ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-elastigroup-status-aws\n        method: GET\n        description: Get Elastigroup instance status\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Elastigroup ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: scale-up-elastigroup-aws\n\
  \        method: PUT\n        description: Scale up an AWS Elastigroup\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Elastigroup ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: scale-down-elastigroup-aws\n        method: PUT\n        description: Scale down an AWS Elastigroup\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Elastigroup ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: roll-elastigroup-aws\n        method: PUT\n        description: Initiate a roll for an AWS Elastigroup\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n\
  \          description: Elastigroup ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-elastigroup-logs\n        method: GET\n        description: Get Elastigroup activity logs\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Elastigroup ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-elastigroup-costs\n        method: GET\n        description: Get Elastigroup cost data\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Elastigroup ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: elastigroup-azure\n      path: /azure/compute/group\n\
  \      description: Manage Azure Elastigroups\n      operations:\n      - name: create-elastigroup-azure\n        method: POST\n        description: Create an Azure Elastigroup\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-elastigroups-azure\n        method: GET\n        description: List all Azure Elastigroups\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: elastigroup-gcp\n      path: /gcp/compute/group\n      description: Manage GCP Elastigroups\n      operations:\n      - name: create-elastigroup-gcp\n        method: POST\n        description: Create a GCP Elastigroup\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ list-elastigroups-gcp\n        method: GET\n        description: List all GCP Elastigroups\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: emr\n      path: /aws/emr/mrScaler\n      description: Manage EMR clusters\n      operations:\n      - name: create-emr-cluster\n        method: POST\n        description: Create an EMR cluster\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-emr-clusters\n        method: GET\n        description: List EMR clusters\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: spot-ocean\n    baseUri: https://api.spotinst.io\n    description: Spot Ocean API\n    authentication:\n \
  \     type: bearer\n      token: '{{SPOT_API_TOKEN}}'\n    resources:\n    - name: ocean-aws\n      path: /ocean/aws/k8s/cluster\n      description: Manage AWS Ocean clusters\n      operations:\n      - name: create-ocean-cluster-aws\n        method: POST\n        description: Create an AWS Ocean cluster\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-ocean-clusters-aws\n        method: GET\n        description: List AWS Ocean clusters\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-ocean-cluster-aws\n        method: GET\n        description: Get an AWS Ocean cluster\n        inputParameters:\n        - name: oceanId\n          in: path\n          type: string\n          required: true\n          description: Ocean cluster ID\n       \
  \ outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-ocean-cluster-aws\n        method: PUT\n        description: Update an AWS Ocean cluster\n        inputParameters:\n        - name: oceanId\n          in: path\n          type: string\n          required: true\n          description: Ocean cluster ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-ocean-cluster-aws\n        method: DELETE\n        description: Delete an AWS Ocean cluster\n        inputParameters:\n        - name: oceanId\n          in: path\n          type: string\n          required: true\n          description: Ocean cluster ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: initiate-roll-aws\n        method: POST\n        description:\
  \ Initiate a cluster roll\n        inputParameters:\n        - name: oceanId\n          in: path\n          type: string\n          required: true\n          description: Ocean cluster ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-right-sizing-suggestions\n        method: GET\n        description: Get right-sizing recommendations\n        inputParameters:\n        - name: oceanId\n          in: path\n          type: string\n          required: true\n          description: Ocean cluster ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: virtual-node-groups\n      path: /ocean/aws/k8s/launchSpec\n      description: Manage virtual node groups\n      operations:\n      - name: create-virtual-node-group-aws\n        method: POST\n        description: Create a virtual node group\n        inputParameters:\
  \ []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-virtual-node-groups-aws\n        method: GET\n        description: List virtual node groups\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ocean-aks\n      path: /ocean/azure/k8s/cluster\n      description: Manage AKS Ocean clusters\n      operations:\n      - name: list-ocean-clusters-aks\n        method: GET\n        description: List AKS Ocean clusters\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ocean-gke\n      path: /ocean/gcp/k8s/cluster\n      description: Manage GKE Ocean clusters\n      operations:\n      - name: list-ocean-clusters-gke\n        method: GET\n        description: List GKE\
  \ Ocean clusters\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ocean-spark\n      path: /ocean/spark/cluster\n      description: Manage Ocean Spark clusters\n      operations:\n      - name: list-ocean-spark-clusters\n        method: GET\n        description: List Ocean Spark clusters\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: spot-compute-api\n    description: Unified REST API for Spot compute optimization.\n    resources:\n    - path: /v1/elastigroups\n      name: elastigroups\n      description: Elastigroup compute groups\n      operations:\n      - method: GET\n        name: list-elastigroups\n        description: List AWS Elastigroups\n        call: spot-elastigroup.list-elastigroups-aws\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ocean-clusters\n      name: ocean-clusters\n      description: Ocean Kubernetes clusters\n      operations:\n      - method: GET\n        name: list-ocean-clusters\n        description: List AWS Ocean clusters\n        call: spot-ocean.list-ocean-clusters-aws\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/virtual-node-groups\n      name: virtual-node-groups\n      description: Ocean virtual node groups\n      operations:\n      - method: GET\n        name: list-virtual-node-groups\n        description: List virtual node groups\n        call: spot-ocean.list-virtual-node-groups-aws\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: spot-compute-mcp\n    transport: http\n    description: MCP server for AI-assisted Spot compute optimization.\n    tools:\n    - name: elastigroup-list-groups-aws\n\
  \      description: List all AWS Elastigroups\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spot-elastigroup.list-elastigroups-aws\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: elastigroup-get-group-aws\n      description: Get an AWS Elastigroup by ID\n      hints:\n        readOnly: true\n      call: spot-elastigroup.get-elastigroup-aws\n      with:\n        groupId: tools.groupId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: elastigroup-get-status-aws\n      description: Get Elastigroup instance status\n      hints:\n        readOnly: true\n      call: spot-elastigroup.get-elastigroup-status-aws\n      with:\n        groupId: tools.groupId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: elastigroup-get-costs\n      description: Get Elastigroup cost data\n      hints:\n        readOnly: true\n      call: spot-elastigroup.get-elastigroup-costs\n      with:\n\
  \        groupId: tools.groupId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: elastigroup-get-logs\n      description: Get Elastigroup activity logs\n      hints:\n        readOnly: true\n      call: spot-elastigroup.get-elastigroup-logs\n      with:\n        groupId: tools.groupId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: elastigroup-scale-up-aws\n      description: Scale up an AWS Elastigroup\n      hints:\n        readOnly: false\n      call: spot-elastigroup.scale-up-elastigroup-aws\n      with:\n        groupId: tools.groupId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: elastigroup-scale-down-aws\n      description: Scale down an AWS Elastigroup\n      hints:\n        readOnly: false\n      call: spot-elastigroup.scale-down-elastigroup-aws\n      with:\n        groupId: tools.groupId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: elastigroup-list-azure\n\
  \      description: List Azure Elastigroups\n      hints:\n        readOnly: true\n      call: spot-elastigroup.list-elastigroups-azure\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: elastigroup-list-gcp\n      description: List GCP Elastigroups\n      hints:\n        readOnly: true\n      call: spot-elastigroup.list-elastigroups-gcp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ocean-list-clusters-aws\n      description: List AWS Ocean clusters\n      hints:\n        readOnly: true\n        openWorld: true\n      call: spot-ocean.list-ocean-clusters-aws\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ocean-get-cluster-aws\n      description: Get an AWS Ocean cluster\n      hints:\n        readOnly: true\n      call: spot-ocean.get-ocean-cluster-aws\n      with:\n        oceanId: tools.oceanId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ocean-get-right-sizing\n\
  \      description: Get right-sizing suggestions for an Ocean cluster\n      hints:\n        readOnly: true\n      call: spot-ocean.get-right-sizing-suggestions\n      with:\n        oceanId: tools.oceanId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ocean-list-virtual-node-groups\n      description: List Ocean virtual node groups\n      hints:\n        readOnly: true\n      call: spot-ocean.list-virtual-node-groups-aws\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ocean-list-clusters-aks\n      description: List AKS Ocean clusters\n      hints:\n        readOnly: true\n      call: spot-ocean.list-ocean-clusters-aks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ocean-list-clusters-gke\n      description: List GKE Ocean clusters\n      hints:\n        readOnly: true\n      call: spot-ocean.list-ocean-clusters-gke\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: ocean-list-spark-clusters\n      description: List Ocean Spark clusters\n      hints:\n        readOnly: true\n      call: spot-ocean.list-ocean-spark-clusters\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
