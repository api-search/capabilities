---
categories: []
consumed_apis: []
description: Workflow capability for managing Azure Container Instances resources. Used by cloud engineers and DevOps teams.
layout: capability
name: Azure Container Instances Management
operations:
- description: List all resources
  method: GET
  name: list
  path: /v1/resources
personas: []
provider_name: Azure Container Instances
provider_slug: azure-container-instances
search_terms:
- azure
- management
- list all resources
- list containergroup resources
- cloud
- list container resources
- serverless
- azure resource management
- container instances
- list containergroupusage resources
- containers
- list
- resource management
- list container groups
- list containers
- list container group usages
- microsoft
slug: azure-container-instances-management
source_filename: azure-container-instances-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure Container Instances Management\n  description: Workflow capability for managing Azure Container Instances resources. Used by cloud engineers and DevOps teams.\n  tags:\n  - Azure\n  - Cloud\n  - Management\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AZURE_SUBSCRIPTION_ID: AZURE_SUBSCRIPTION_ID\n    AZURE_ACCESS_TOKEN: AZURE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: azure-container-instances\n    baseUri: https://management.azure.com\n    description: Azure Container Instances REST API\n    authentication:\n      type: bearer\n      token: '{{AZURE_ACCESS_TOKEN}}'\n    resources:\n    - name: container-group\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.ContainerGroup/ContainerGroups\n      description: Manage ContainerGroup resources\n      operations:\n      - name: list-container-groups\n        method: GET\n        description: List\
  \ all ContainerGroup resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Container/Containers\n      description: Manage Container resources\n      operations:\n      - name: list-containers\n        method: GET\n        description: List all Container resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: container-group-usage\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.ContainerGroupUsage/ContainerGroupUsages\n\
  \      description: Manage ContainerGroupUsage resources\n      operations:\n      - name: list-container-group-usages\n        method: GET\n        description: List all ContainerGroupUsage resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8084\n    namespace: azure-container-instances-management-api\n    description: Unified REST API for Azure Container Instances management.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Resource management\n      operations:\n      - method: GET\n        name: list\n        description: List all resources\n        call: azure-container-instances.list-container-groups\n        with:\n          subscriptionId: rest.subscriptionId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9094\n    namespace: azure-container-instances-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Azure Container Instances management.\n    tools:\n    - name: list-container-groups\n      description: List ContainerGroup resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-container-instances.list-container-groups\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-containers\n      description: List Container resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-container-instances.list-containers\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-container-group-usages\n      description: List ContainerGroupUsage\
  \ resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-container-instances.list-container-group-usages\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/azure-container-instances/refs/heads/main/capabilities/azure-container-instances-management.yaml
tags:
- Azure
- Cloud
- Management
tools:
- description: List ContainerGroup resources
  hints:
    openWorld: true
    readOnly: true
  name: list-container-groups
- description: List Container resources
  hints:
    openWorld: true
    readOnly: true
  name: list-containers
- description: List ContainerGroupUsage resources
  hints:
    openWorld: true
    readOnly: true
  name: list-container-group-usages
---
