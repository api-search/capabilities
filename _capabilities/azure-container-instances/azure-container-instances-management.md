---
api_specs:
- filename: azure-container-instances-openapi.yaml
  format: yaml
  label: azure-container-instances
  slug: azure-container-instances
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/azure-container-instances/refs/heads/main/openapi/azure-container-instances-openapi.yaml
categories: []
consumed_apis:
- azure-container-instances
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
- container instances
- azure
- azure resource management
- resource management
- management
- list all resources
- list containers
- list container groups
- list containergroupusage resources
- containers
- serverless
- list containergroup resources
- list container resources
- cloud
- list
- microsoft
- list container group usages
slug: azure-container-instances-management
source_filename: azure-container-instances-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Azure Container Instances Management\"\n  description: \"Workflow capability for managing Azure Container Instances resources. Used by cloud engineers and DevOps teams.\"\n  tags:\n    - Azure\n    - Cloud\n    - Management\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AZURE_SUBSCRIPTION_ID: AZURE_SUBSCRIPTION_ID\n      AZURE_ACCESS_TOKEN: AZURE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: azure-container-instances\n      location: ./shared/azure-container-instances.yaml\n\n  exposes:\n    - type: rest\n      port: 8084\n      namespace: azure-container-instances-management-api\n      description: \"Unified REST API for Azure Container Instances management.\"\n      resources:\n        - path: /v1/resources\n          name: resources\n          description: \"Resource management\"\n          operations:\n            - method: GET\n              name: list\n   \
  \           description: \"List all resources\"\n              call: \"azure-container-instances.list-container-groups\"\n              with:\n                subscriptionId: \"rest.subscriptionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9094\n      namespace: azure-container-instances-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Azure Container Instances management.\"\n      tools:\n        - name: list-container-groups\n          description: \"List ContainerGroup resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-container-instances.list-container-groups\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-containers\n          description: \"List Container resources\"\
  \n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-container-instances.list-containers\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-container-group-usages\n          description: \"List ContainerGroupUsage resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-container-instances.list-container-group-usages\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
