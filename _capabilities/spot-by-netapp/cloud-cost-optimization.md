---
categories: []
consumed_apis: []
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
- elastigroup cost analysis
- get ocean cluster aws
- aws
- delete an aws elastigroup and terminate associated instances.
- list ocean clusters aws
- cost management
- get elastigroup instance status
- spot account management
- list all spot accounts associated with the organization.
- finops
- scale up elastigroup
- spot elastigroup intelligent auto-scaling groups
- retrieve audit log events recording api and console activity for compliance and troubleshooting.
- scale down an aws elastigroup by removing a specified number of instances.
- account activity audit log
- delete ocean cluster
- ocean kubernetes clusters
- azure
- get rightsizing
- create a new aws elastigroup with spot instance optimization for a workload.
- get cost analysis and savings data for an aws elastigroup over a time period.
- gcp
- overall cloud cost savings summary
- get ocean cluster
- spot instances
- get cost breakdown and savings for an ocean kubernetes cluster.
- get ocean costs
- list ocean clusters
- get ocean cluster details including auto-scaler config and capacity.
- ocean cluster cost analysis
- get details for a specific aws elastigroup including capacity, strategy, and instance type configuration.
- get elastigroup status
- create elastigroup aws
- auto scaling
- individual elastigroup
- kubernetes
- list all aws elastigroups
- get elastigroup cost and savings
- get cost summary
- cloud optimization
- update an aws elastigroup's configuration including capacity, instance types, or strategy.
- list elastigroups aws
- get elastigroup
- cost optimization
- get audit log
- get cloud cost savings summary
- elastigroup instance status
- list all aws elastigroup intelligent auto-scaling groups. each elastigroup uses spot instances to reduce compute costs 60-90%.
- get ocean cluster costs
- get ocean cluster details
- get elastigroup costs
- delete elastigroup aws
- scale up an aws elastigroup by adding a specified number of instances.
- get container rightsizing recommendations
- scale down elastigroup
- update elastigroup aws
- create ocean cluster aws
- get audit log events
- container rightsizing recommendations
- get elastigroup aws
- list all ocean kubernetes clusters on aws for container cost optimization.
- create a new ocean cluster for kubernetes cost optimization on aws.
- get overall cloud cost savings summary showing actual vs. potential spend and total savings percentage from spot optimization.
- list accounts
- list spot accounts
- get ocean cluster cost breakdown and savings
- list all ocean clusters on aws
- get current instance status and health for an aws elastigroup.
- get rightsizing suggestions
- list elastigroups
- individual ocean cluster
- get container rightsizing recommendations to eliminate over-provisioning and reduce costs.
- delete elastigroup
- get elastigroup details
slug: cloud-cost-optimization
source_filename: cloud-cost-optimization.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Spot by NetApp Cloud Cost Optimization\n  description: Unified cloud infrastructure cost optimization capability composing Spot by NetApp APIs for Elastigroup management,\n    Ocean Kubernetes optimization, rightsizing analysis, cost reporting, and account administration across AWS, Azure, and\n    GCP.\n  tags:\n  - Cloud Optimization\n  - FinOps\n  - Kubernetes\n  - AWS\n  - Cost Management\n  - Auto Scaling\n  - Spot Instances\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPOT_API_TOKEN: SPOT_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: spot\n    baseUri: https://api.spotinst.io\n    description: Spot by NetApp REST API for cloud optimization\n    authentication:\n      type: bearer\n      token: '{{SPOT_API_TOKEN}}'\n    resources:\n    - name: elastigroup-aws\n      path: /aws/ec2/group\n      description: AWS Elastigroup management\n      operations:\n      - name:\
  \ list-elastigroups-aws\n        method: GET\n        description: List all AWS Elastigroups\n        inputParameters:\n        - name: accountId\n          in: query\n          type: string\n          required: false\n          description: Spot account ID filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-elastigroup-aws\n        method: POST\n        description: Create a new AWS Elastigroup with Spot optimization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            group: '{{tools.group}}'\n    - name: elastigroup-aws-by-id\n      path: /aws/ec2/group/{groupId}\n      description: Individual AWS Elastigroup operations\n      operations:\n      - name: get-elastigroup-aws\n        method: GET\n        description: Get AWS Elastigroup by ID\n\
  \        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Elastigroup ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-elastigroup-aws\n        method: PUT\n        description: Update AWS Elastigroup configuration\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Elastigroup ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-elastigroup-aws\n        method: DELETE\n        description: Delete an AWS Elastigroup\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Elastigroup ID\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: elastigroup-aws-status\n      path: /aws/ec2/group/{groupId}/status\n      description: AWS Elastigroup instance status\n      operations:\n      - name: get-elastigroup-status\n        method: GET\n        description: Get instance status for an Elastigroup\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Elastigroup ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: elastigroup-aws-costs\n      path: /aws/ec2/group/{groupId}/costs\n      description: AWS Elastigroup cost analysis\n      operations:\n      - name: get-elastigroup-costs\n        method: GET\n        description: Get cost and savings analysis for an Elastigroup\n        inputParameters:\n        - name: groupId\n          in: path\n\
  \          type: string\n          required: true\n          description: Elastigroup ID\n        - name: fromDate\n          in: query\n          type: string\n          required: false\n          description: Start date (ISO 8601)\n        - name: toDate\n          in: query\n          type: string\n          required: false\n          description: End date (ISO 8601)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: elastigroup-aws-scale-up\n      path: /aws/ec2/group/{groupId}/scale/up\n      description: Scale up an AWS Elastigroup\n      operations:\n      - name: scale-up-elastigroup\n        method: PUT\n        description: Add capacity to an AWS Elastigroup\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Elastigroup ID\n        - name: adjustment\n          in: query\n          type: integer\n\
  \          required: true\n          description: Number of instances to add\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: elastigroup-aws-scale-down\n      path: /aws/ec2/group/{groupId}/scale/down\n      description: Scale down an AWS Elastigroup\n      operations:\n      - name: scale-down-elastigroup\n        method: PUT\n        description: Remove capacity from an AWS Elastigroup\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: Elastigroup ID\n        - name: adjustment\n          in: query\n          type: integer\n          required: true\n          description: Number of instances to remove\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ocean-aws-cluster\n      path: /ocean/aws/k8s/cluster\n      description:\
  \ Ocean Kubernetes cluster management on AWS\n      operations:\n      - name: list-ocean-clusters-aws\n        method: GET\n        description: List all Ocean clusters on AWS\n        inputParameters:\n        - name: accountId\n          in: query\n          type: string\n          required: false\n          description: Spot account ID filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-ocean-cluster-aws\n        method: POST\n        description: Create an Ocean Kubernetes cluster on AWS\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            cluster: '{{tools.cluster}}'\n    - name: ocean-aws-cluster-by-id\n      path: /ocean/aws/k8s/cluster/{clusterId}\n      description: Individual Ocean cluster operations\n      operations:\n      - name:\
  \ get-ocean-cluster-aws\n        method: GET\n        description: Get Ocean cluster details\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n          description: Ocean cluster ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-ocean-cluster-aws\n        method: PUT\n        description: Update Ocean cluster configuration\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n          description: Ocean cluster ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-ocean-cluster-aws\n        method: DELETE\n        description: Delete an Ocean cluster\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n\
  \          required: true\n          description: Ocean cluster ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ocean-cluster-costs\n      path: /ocean/aws/k8s/cluster/{clusterId}/costs\n      description: Ocean cluster cost and savings data\n      operations:\n      - name: get-ocean-cluster-costs\n        method: GET\n        description: Get cost breakdown and savings for an Ocean cluster\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n          description: Ocean cluster ID\n        - name: startTime\n          in: query\n          type: string\n          required: false\n          description: Start time (ISO 8601)\n        - name: endTime\n          in: query\n          type: string\n          required: false\n          description: End time (ISO 8601)\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: rightsizing\n      path: /ocean/aws/k8s/cluster/{clusterId}/rightSizing/suggestions\n      description: Container rightsizing recommendations\n      operations:\n      - name: get-rightsizing-suggestions\n        method: GET\n        description: Get container rightsizing recommendations to reduce waste and cost\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n          description: Ocean cluster ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts\n      path: /setup/account\n      description: Spot account management\n      operations:\n      - name: list-accounts\n        method: GET\n        description: List all Spot accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: create-account\n        method: POST\n        description: Create a new Spot account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            account: '{{tools.account}}'\n    - name: audit-log\n      path: /audit/log\n      description: Audit log for account activity\n      operations:\n      - name: get-audit-log\n        method: GET\n        description: Retrieve audit log events for account activity\n        inputParameters:\n        - name: accountId\n          in: query\n          type: string\n          required: false\n          description: Account ID filter\n        - name: fromDate\n          in: query\n          type: string\n          required: false\n          description: Start date filter\n        - name: toDate\n          in: query\n          type: string\n          required: false\n          description:\
  \ End date filter\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: insights\n      path: /insights/summary\n      description: Cloud cost savings insights\n      operations:\n      - name: get-cost-summary\n        method: GET\n        description: Get cloud cost savings summary from Spot optimization\n        inputParameters:\n        - name: accountId\n          in: query\n          type: string\n          required: false\n          description: Account ID filter\n        - name: fromDate\n          in: query\n          type: string\n          required: false\n          description: Start date\n        - name: toDate\n          in: query\n          type: string\n          required: false\n          description: End date\n        outputRawFormat: json\n  \
  \      outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: cloud-cost-optimization-api\n    description: Unified REST API for cloud cost optimization via Spot by NetApp.\n    resources:\n    - path: /v1/elastigroups\n      name: elastigroups\n      description: Spot Elastigroup intelligent auto-scaling groups\n      operations:\n      - method: GET\n        name: list-elastigroups\n        description: List all AWS Elastigroups\n        call: spot.list-elastigroups-aws\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/elastigroups/{groupId}\n      name: elastigroup\n      description: Individual Elastigroup\n      operations:\n      - method: GET\n        name: get-elastigroup\n        description: Get Elastigroup details\n        call: spot.get-elastigroup-aws\n        with:\n          groupId: rest.groupId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-elastigroup\n        description: Delete Elastigroup\n        call: spot.delete-elastigroup-aws\n        with:\n          groupId: rest.groupId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/elastigroups/{groupId}/status\n      name: elastigroup-status\n      description: Elastigroup instance status\n      operations:\n      - method: GET\n        name: get-elastigroup-status\n        description: Get Elastigroup instance status\n        call: spot.get-elastigroup-status\n        with:\n          groupId: rest.groupId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/elastigroups/{groupId}/costs\n      name: elastigroup-costs\n      description: Elastigroup cost analysis\n      operations:\n      - method: GET\n        name: get-elastigroup-costs\n        description: Get Elastigroup\
  \ cost and savings\n        call: spot.get-elastigroup-costs\n        with:\n          groupId: rest.groupId\n          fromDate: rest.fromDate\n          toDate: rest.toDate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ocean-clusters\n      name: ocean-clusters\n      description: Ocean Kubernetes clusters\n      operations:\n      - method: GET\n        name: list-ocean-clusters\n        description: List all Ocean clusters on AWS\n        call: spot.list-ocean-clusters-aws\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ocean-clusters/{clusterId}\n      name: ocean-cluster\n      description: Individual Ocean cluster\n      operations:\n      - method: GET\n        name: get-ocean-cluster\n        description: Get Ocean cluster details\n        call: spot.get-ocean-cluster-aws\n        with:\n          clusterId: rest.clusterId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-ocean-cluster\n        description: Delete Ocean cluster\n        call: spot.delete-ocean-cluster-aws\n        with:\n          clusterId: rest.clusterId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ocean-clusters/{clusterId}/costs\n      name: ocean-cluster-costs\n      description: Ocean cluster cost analysis\n      operations:\n      - method: GET\n        name: get-ocean-costs\n        description: Get Ocean cluster cost breakdown and savings\n        call: spot.get-ocean-cluster-costs\n        with:\n          clusterId: rest.clusterId\n          startTime: rest.startTime\n          endTime: rest.endTime\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ocean-clusters/{clusterId}/rightsizing\n      name: rightsizing\n      description: Container rightsizing recommendations\n      operations:\n      - method:\
  \ GET\n        name: get-rightsizing\n        description: Get container rightsizing recommendations\n        call: spot.get-rightsizing-suggestions\n        with:\n          clusterId: rest.clusterId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cost-summary\n      name: cost-summary\n      description: Overall cloud cost savings summary\n      operations:\n      - method: GET\n        name: get-cost-summary\n        description: Get cloud cost savings summary\n        call: spot.get-cost-summary\n        with:\n          accountId: rest.accountId\n          fromDate: rest.fromDate\n          toDate: rest.toDate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/audit-log\n      name: audit-log\n      description: Account activity audit log\n      operations:\n      - method: GET\n        name: get-audit-log\n        description: Get audit log events\n        call: spot.get-audit-log\n        with:\n\
  \          accountId: rest.accountId\n          fromDate: rest.fromDate\n          toDate: rest.toDate\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/accounts\n      name: accounts\n      description: Spot account management\n      operations:\n      - method: GET\n        name: list-accounts\n        description: List Spot accounts\n        call: spot.list-accounts\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9082\n    namespace: cloud-cost-optimization-mcp\n    transport: http\n    description: MCP server for AI-assisted cloud cost optimization and FinOps with Spot by NetApp.\n    tools:\n    - name: list-elastigroups-aws\n      description: List all AWS Elastigroup intelligent auto-scaling groups. Each Elastigroup uses Spot instances to reduce\n        compute costs 60-90%.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spot.list-elastigroups-aws\n\
  \      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-elastigroup-aws\n      description: Get details for a specific AWS Elastigroup including capacity, strategy, and instance type configuration.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spot.get-elastigroup-aws\n      with:\n        groupId: tools.groupId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-elastigroup-aws\n      description: Create a new AWS Elastigroup with Spot instance optimization for a workload.\n      hints:\n        readOnly: false\n        destructive: false\n      call: spot.create-elastigroup-aws\n      with:\n        group: tools.group\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-elastigroup-aws\n      description: Update an AWS Elastigroup's configuration including capacity, instance types, or strategy.\n      hints:\n\
  \        readOnly: false\n        idempotent: true\n      call: spot.update-elastigroup-aws\n      with:\n        groupId: tools.groupId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-elastigroup-aws\n      description: Delete an AWS Elastigroup and terminate associated instances.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: spot.delete-elastigroup-aws\n      with:\n        groupId: tools.groupId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-elastigroup-status\n      description: Get current instance status and health for an AWS Elastigroup.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spot.get-elastigroup-status\n      with:\n        groupId: tools.groupId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-elastigroup-costs\n      description: Get cost analysis and savings data for\
  \ an AWS Elastigroup over a time period.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spot.get-elastigroup-costs\n      with:\n        groupId: tools.groupId\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: scale-up-elastigroup\n      description: Scale up an AWS Elastigroup by adding a specified number of instances.\n      hints:\n        readOnly: false\n        destructive: false\n      call: spot.scale-up-elastigroup\n      with:\n        groupId: tools.groupId\n        adjustment: tools.adjustment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: scale-down-elastigroup\n      description: Scale down an AWS Elastigroup by removing a specified number of instances.\n      hints:\n        readOnly: false\n        destructive: false\n      call: spot.scale-down-elastigroup\n      with:\n        groupId: tools.groupId\n        adjustment:\
  \ tools.adjustment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-ocean-clusters-aws\n      description: List all Ocean Kubernetes clusters on AWS for container cost optimization.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spot.list-ocean-clusters-aws\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-ocean-cluster-aws\n      description: Get Ocean cluster details including auto-scaler config and capacity.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spot.get-ocean-cluster-aws\n      with:\n        clusterId: tools.clusterId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-ocean-cluster-aws\n      description: Create a new Ocean cluster for Kubernetes cost optimization on AWS.\n      hints:\n        readOnly: false\n        destructive: false\n      call: spot.create-ocean-cluster-aws\n\
  \      with:\n        cluster: tools.cluster\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-ocean-cluster-costs\n      description: Get cost breakdown and savings for an Ocean Kubernetes cluster.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spot.get-ocean-cluster-costs\n      with:\n        clusterId: tools.clusterId\n        startTime: tools.startTime\n        endTime: tools.endTime\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-rightsizing-suggestions\n      description: Get container rightsizing recommendations to eliminate over-provisioning and reduce costs.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spot.get-rightsizing-suggestions\n      with:\n        clusterId: tools.clusterId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cost-summary\n      description: Get overall cloud cost savings summary showing\
  \ actual vs. potential spend and total savings percentage\n        from Spot optimization.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spot.get-cost-summary\n      with:\n        accountId: tools.accountId\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-audit-log\n      description: Retrieve audit log events recording API and console activity for compliance and troubleshooting.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: spot.get-audit-log\n      with:\n        accountId: tools.accountId\n        fromDate: tools.fromDate\n        toDate: tools.toDate\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-accounts\n      description: List all Spot accounts associated with the organization.\n      hints:\n        readOnly: true\n        openWorld: false\n      call:\
  \ spot.list-accounts\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
