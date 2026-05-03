---
categories: []
consumed_apis:
- spot
description: Unified cloud infrastructure cost optimization capability composing Spot by NetApp APIs for Elastigroup management, Ocean Kubernetes optimization, rightsizing analysis, cost reporting, and account administration across AWS, Azure, and GCP.
layout: capability
name: Spot by NetApp Cloud Cost Optimization
operations:
- description: List all AWS Elastigroups
  method: GET
  name: list-elastigroups
  path: /v1/elastigroups
- description: Get Elastigroup details
  method: GET
  name: get-elastigroup
  path: /v1/elastigroups/{groupId}
- description: Delete Elastigroup
  method: DELETE
  name: delete-elastigroup
  path: /v1/elastigroups/{groupId}
- description: Get Elastigroup instance status
  method: GET
  name: get-elastigroup-status
  path: /v1/elastigroups/{groupId}/status
- description: Get Elastigroup cost and savings
  method: GET
  name: get-elastigroup-costs
  path: /v1/elastigroups/{groupId}/costs
- description: List all Ocean clusters on AWS
  method: GET
  name: list-ocean-clusters
  path: /v1/ocean-clusters
- description: Get Ocean cluster details
  method: GET
  name: get-ocean-cluster
  path: /v1/ocean-clusters/{clusterId}
- description: Delete Ocean cluster
  method: DELETE
  name: delete-ocean-cluster
  path: /v1/ocean-clusters/{clusterId}
- description: Get Ocean cluster cost breakdown and savings
  method: GET
  name: get-ocean-costs
  path: /v1/ocean-clusters/{clusterId}/costs
- description: Get container rightsizing recommendations
  method: GET
  name: get-rightsizing
  path: /v1/ocean-clusters/{clusterId}/rightsizing
- description: Get cloud cost savings summary
  method: GET
  name: get-cost-summary
  path: /v1/cost-summary
- description: Get audit log events
  method: GET
  name: get-audit-log
  path: /v1/audit-log
- description: List Spot accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
personas: []
provider_name: Spot by NetApp
provider_slug: spot-by-netapp
search_terms:
- cost management
- spot elastigroup intelligent auto-scaling groups
- finops
- list elastigroups
- cost optimization
- list all spot accounts associated with the organization.
- get current instance status and health for an aws elastigroup.
- get ocean costs
- scale down an aws elastigroup by removing a specified number of instances.
- get container rightsizing recommendations
- get ocean cluster costs
- delete an aws elastigroup and terminate associated instances.
- create a new aws elastigroup with spot instance optimization for a workload.
- list all ocean kubernetes clusters on aws for container cost optimization.
- update an aws elastigroup's configuration including capacity, instance types, or strategy.
- spot account management
- create ocean cluster aws
- azure
- auto scaling
- get ocean cluster
- account activity audit log
- get elastigroup aws
- delete elastigroup aws
- ocean kubernetes clusters
- get cost breakdown and savings for an ocean kubernetes cluster.
- delete ocean cluster
- get elastigroup
- get ocean cluster details
- kubernetes
- list all ocean clusters on aws
- overall cloud cost savings summary
- get ocean cluster details including auto-scaler config and capacity.
- get elastigroup details
- aws
- container rightsizing recommendations
- get container rightsizing recommendations to eliminate over-provisioning and reduce costs.
- list all aws elastigroups
- gcp
- cloud optimization
- individual ocean cluster
- list all aws elastigroup intelligent auto-scaling groups. each elastigroup uses spot instances to reduce compute costs 60-90%.
- scale up elastigroup
- get rightsizing suggestions
- list elastigroups aws
- list accounts
- get elastigroup cost and savings
- get ocean cluster cost breakdown and savings
- get audit log events
- list ocean clusters
- scale down elastigroup
- list ocean clusters aws
- get elastigroup instance status
- get elastigroup status
- delete elastigroup
- ocean cluster cost analysis
- get cost analysis and savings data for an aws elastigroup over a time period.
- get cloud cost savings summary
- get ocean cluster aws
- retrieve audit log events recording api and console activity for compliance and troubleshooting.
- elastigroup cost analysis
- scale up an aws elastigroup by adding a specified number of instances.
- get audit log
- create a new ocean cluster for kubernetes cost optimization on aws.
- elastigroup instance status
- get rightsizing
- create elastigroup aws
- get cost summary
- list spot accounts
- get details for a specific aws elastigroup including capacity, strategy, and instance type configuration.
- spot instances
- individual elastigroup
- get elastigroup costs
- get overall cloud cost savings summary showing actual vs. potential spend and total savings percentage from spot optimization.
- update elastigroup aws
slug: cloud-cost-optimization
source_filename: cloud-cost-optimization.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Spot by NetApp Cloud Cost Optimization\"\n  description: >-\n    Unified cloud infrastructure cost optimization capability composing Spot by NetApp\n    APIs for Elastigroup management, Ocean Kubernetes optimization, rightsizing analysis,\n    cost reporting, and account administration across AWS, Azure, and GCP.\n  tags:\n    - Cloud Optimization\n    - FinOps\n    - Kubernetes\n    - AWS\n    - Cost Management\n    - Auto Scaling\n    - Spot Instances\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SPOT_API_TOKEN: SPOT_API_TOKEN\n\ncapability:\n  consumes:\n    - import: spot\n      location: ./shared/spot.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: cloud-cost-optimization-api\n      description: \"Unified REST API for cloud cost optimization via Spot by NetApp.\"\n      resources:\n        - path: /v1/elastigroups\n          name: elastigroups\n\
  \          description: \"Spot Elastigroup intelligent auto-scaling groups\"\n          operations:\n            - method: GET\n              name: list-elastigroups\n              description: \"List all AWS Elastigroups\"\n              call: \"spot.list-elastigroups-aws\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/elastigroups/{groupId}\n          name: elastigroup\n          description: \"Individual Elastigroup\"\n          operations:\n            - method: GET\n              name: get-elastigroup\n              description: \"Get Elastigroup details\"\n              call: \"spot.get-elastigroup-aws\"\n              with:\n                groupId: \"rest.groupId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-elastigroup\n   \
  \           description: \"Delete Elastigroup\"\n              call: \"spot.delete-elastigroup-aws\"\n              with:\n                groupId: \"rest.groupId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/elastigroups/{groupId}/status\n          name: elastigroup-status\n          description: \"Elastigroup instance status\"\n          operations:\n            - method: GET\n              name: get-elastigroup-status\n              description: \"Get Elastigroup instance status\"\n              call: \"spot.get-elastigroup-status\"\n              with:\n                groupId: \"rest.groupId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/elastigroups/{groupId}/costs\n          name: elastigroup-costs\n          description: \"Elastigroup cost analysis\"\n          operations:\n            - method: GET\n              name: get-elastigroup-costs\n\
  \              description: \"Get Elastigroup cost and savings\"\n              call: \"spot.get-elastigroup-costs\"\n              with:\n                groupId: \"rest.groupId\"\n                fromDate: \"rest.fromDate\"\n                toDate: \"rest.toDate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ocean-clusters\n          name: ocean-clusters\n          description: \"Ocean Kubernetes clusters\"\n          operations:\n            - method: GET\n              name: list-ocean-clusters\n              description: \"List all Ocean clusters on AWS\"\n              call: \"spot.list-ocean-clusters-aws\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ocean-clusters/{clusterId}\n          name: ocean-cluster\n          description: \"Individual Ocean cluster\"\n \
  \         operations:\n            - method: GET\n              name: get-ocean-cluster\n              description: \"Get Ocean cluster details\"\n              call: \"spot.get-ocean-cluster-aws\"\n              with:\n                clusterId: \"rest.clusterId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-ocean-cluster\n              description: \"Delete Ocean cluster\"\n              call: \"spot.delete-ocean-cluster-aws\"\n              with:\n                clusterId: \"rest.clusterId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ocean-clusters/{clusterId}/costs\n          name: ocean-cluster-costs\n          description: \"Ocean cluster cost analysis\"\n          operations:\n            - method: GET\n              name: get-ocean-costs\n              description: \"Get Ocean cluster cost\
  \ breakdown and savings\"\n              call: \"spot.get-ocean-cluster-costs\"\n              with:\n                clusterId: \"rest.clusterId\"\n                startTime: \"rest.startTime\"\n                endTime: \"rest.endTime\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ocean-clusters/{clusterId}/rightsizing\n          name: rightsizing\n          description: \"Container rightsizing recommendations\"\n          operations:\n            - method: GET\n              name: get-rightsizing\n              description: \"Get container rightsizing recommendations\"\n              call: \"spot.get-rightsizing-suggestions\"\n              with:\n                clusterId: \"rest.clusterId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cost-summary\n          name: cost-summary\n          description: \"Overall cloud cost savings summary\"\
  \n          operations:\n            - method: GET\n              name: get-cost-summary\n              description: \"Get cloud cost savings summary\"\n              call: \"spot.get-cost-summary\"\n              with:\n                accountId: \"rest.accountId\"\n                fromDate: \"rest.fromDate\"\n                toDate: \"rest.toDate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/audit-log\n          name: audit-log\n          description: \"Account activity audit log\"\n          operations:\n            - method: GET\n              name: get-audit-log\n              description: \"Get audit log events\"\n              call: \"spot.get-audit-log\"\n              with:\n                accountId: \"rest.accountId\"\n                fromDate: \"rest.fromDate\"\n                toDate: \"rest.toDate\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n        - path: /v1/accounts\n          name: accounts\n          description: \"Spot account management\"\n          operations:\n            - method: GET\n              name: list-accounts\n              description: \"List Spot accounts\"\n              call: \"spot.list-accounts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9082\n      namespace: cloud-cost-optimization-mcp\n      transport: http\n      description: \"MCP server for AI-assisted cloud cost optimization and FinOps with Spot by NetApp.\"\n      tools:\n        - name: list-elastigroups-aws\n          description: \"List all AWS Elastigroup intelligent auto-scaling groups. Each Elastigroup uses Spot instances to reduce compute costs 60-90%.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spot.list-elastigroups-aws\"\n          with:\n            accountId:\
  \ \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-elastigroup-aws\n          description: \"Get details for a specific AWS Elastigroup including capacity, strategy, and instance type configuration.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spot.get-elastigroup-aws\"\n          with:\n            groupId: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-elastigroup-aws\n          description: \"Create a new AWS Elastigroup with Spot instance optimization for a workload.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"spot.create-elastigroup-aws\"\n          with:\n            group: \"tools.group\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-elastigroup-aws\n\
  \          description: \"Update an AWS Elastigroup's configuration including capacity, instance types, or strategy.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"spot.update-elastigroup-aws\"\n          with:\n            groupId: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-elastigroup-aws\n          description: \"Delete an AWS Elastigroup and terminate associated instances.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"spot.delete-elastigroup-aws\"\n          with:\n            groupId: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-elastigroup-status\n          description: \"Get current instance status and health for an AWS Elastigroup.\"\n          hints:\n            readOnly: true\n\
  \            openWorld: false\n          call: \"spot.get-elastigroup-status\"\n          with:\n            groupId: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-elastigroup-costs\n          description: \"Get cost analysis and savings data for an AWS Elastigroup over a time period.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spot.get-elastigroup-costs\"\n          with:\n            groupId: \"tools.groupId\"\n            fromDate: \"tools.fromDate\"\n            toDate: \"tools.toDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: scale-up-elastigroup\n          description: \"Scale up an AWS Elastigroup by adding a specified number of instances.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"spot.scale-up-elastigroup\"\n          with:\n\
  \            groupId: \"tools.groupId\"\n            adjustment: \"tools.adjustment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: scale-down-elastigroup\n          description: \"Scale down an AWS Elastigroup by removing a specified number of instances.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"spot.scale-down-elastigroup\"\n          with:\n            groupId: \"tools.groupId\"\n            adjustment: \"tools.adjustment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-ocean-clusters-aws\n          description: \"List all Ocean Kubernetes clusters on AWS for container cost optimization.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spot.list-ocean-clusters-aws\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n  \
  \          - type: object\n              mapping: \"$.\"\n        - name: get-ocean-cluster-aws\n          description: \"Get Ocean cluster details including auto-scaler config and capacity.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spot.get-ocean-cluster-aws\"\n          with:\n            clusterId: \"tools.clusterId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-ocean-cluster-aws\n          description: \"Create a new Ocean cluster for Kubernetes cost optimization on AWS.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"spot.create-ocean-cluster-aws\"\n          with:\n            cluster: \"tools.cluster\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-ocean-cluster-costs\n          description: \"Get cost breakdown and savings for an Ocean Kubernetes\
  \ cluster.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spot.get-ocean-cluster-costs\"\n          with:\n            clusterId: \"tools.clusterId\"\n            startTime: \"tools.startTime\"\n            endTime: \"tools.endTime\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-rightsizing-suggestions\n          description: \"Get container rightsizing recommendations to eliminate over-provisioning and reduce costs.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spot.get-rightsizing-suggestions\"\n          with:\n            clusterId: \"tools.clusterId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-cost-summary\n          description: \"Get overall cloud cost savings summary showing actual vs. potential spend and total savings percentage from Spot optimization.\"\
  \n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spot.get-cost-summary\"\n          with:\n            accountId: \"tools.accountId\"\n            fromDate: \"tools.fromDate\"\n            toDate: \"tools.toDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-audit-log\n          description: \"Retrieve audit log events recording API and console activity for compliance and troubleshooting.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spot.get-audit-log\"\n          with:\n            accountId: \"tools.accountId\"\n            fromDate: \"tools.fromDate\"\n            toDate: \"tools.toDate\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-accounts\n          description: \"List all Spot accounts associated with the organization.\"\
  \n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spot.list-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spot-by-netapp/refs/heads/main/capabilities/cloud-cost-optimization.yaml
tags:
- Cloud Optimization
- FinOps
- Kubernetes
- Cost Management
- Auto Scaling
- Spot Instances
tools:
- description: List all AWS Elastigroup intelligent auto-scaling groups. Each Elastigroup uses Spot instances to reduce compute costs 60-90%.
  hints:
    openWorld: false
    readOnly: true
  name: list-elastigroups-aws
- description: Get details for a specific AWS Elastigroup including capacity, strategy, and instance type configuration.
  hints:
    openWorld: false
    readOnly: true
  name: get-elastigroup-aws
- description: Create a new AWS Elastigroup with Spot instance optimization for a workload.
  hints:
    destructive: false
    readOnly: false
  name: create-elastigroup-aws
- description: Update an AWS Elastigroup's configuration including capacity, instance types, or strategy.
  hints:
    idempotent: true
    readOnly: false
  name: update-elastigroup-aws
- description: Delete an AWS Elastigroup and terminate associated instances.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-elastigroup-aws
- description: Get current instance status and health for an AWS Elastigroup.
  hints:
    openWorld: false
    readOnly: true
  name: get-elastigroup-status
- description: Get cost analysis and savings data for an AWS Elastigroup over a time period.
  hints:
    openWorld: false
    readOnly: true
  name: get-elastigroup-costs
- description: Scale up an AWS Elastigroup by adding a specified number of instances.
  hints:
    destructive: false
    readOnly: false
  name: scale-up-elastigroup
- description: Scale down an AWS Elastigroup by removing a specified number of instances.
  hints:
    destructive: false
    readOnly: false
  name: scale-down-elastigroup
- description: List all Ocean Kubernetes clusters on AWS for container cost optimization.
  hints:
    openWorld: false
    readOnly: true
  name: list-ocean-clusters-aws
- description: Get Ocean cluster details including auto-scaler config and capacity.
  hints:
    openWorld: false
    readOnly: true
  name: get-ocean-cluster-aws
- description: Create a new Ocean cluster for Kubernetes cost optimization on AWS.
  hints:
    destructive: false
    readOnly: false
  name: create-ocean-cluster-aws
- description: Get cost breakdown and savings for an Ocean Kubernetes cluster.
  hints:
    openWorld: false
    readOnly: true
  name: get-ocean-cluster-costs
- description: Get container rightsizing recommendations to eliminate over-provisioning and reduce costs.
  hints:
    openWorld: false
    readOnly: true
  name: get-rightsizing-suggestions
- description: Get overall cloud cost savings summary showing actual vs. potential spend and total savings percentage from Spot optimization.
  hints:
    openWorld: false
    readOnly: true
  name: get-cost-summary
- description: Retrieve audit log events recording API and console activity for compliance and troubleshooting.
  hints:
    openWorld: false
    readOnly: true
  name: get-audit-log
- description: List all Spot accounts associated with the organization.
  hints:
    openWorld: false
    readOnly: true
  name: list-accounts
---
