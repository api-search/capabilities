---
categories: []
consumed_apis:
- azure
description: Workflow capability for managing Microsoft Azure resources. Used by cloud engineers and DevOps teams.
layout: capability
name: Microsoft Azure Management
operations:
- description: List all resources
  method: GET
  name: list
  path: /v1/resources
personas: []
provider_name: Microsoft Azure
provider_slug: azure
search_terms:
- networking
- databases
- list providers
- list provider resources
- management
- storage
- list resourcegroup resources
- infrastructure
- azure
- machine learning
- platform as a service
- azure resource management
- list
- list all resources
- cloud computing
- resource management
- cloud
- list resource resources
- list subscription resources
- list resource groups
- list resources
- list subscriptions
slug: azure-management
source_filename: azure-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Microsoft Azure Management\"\n  description: \"Workflow capability for managing Microsoft Azure resources. Used by cloud engineers and DevOps teams.\"\n  tags:\n    - Azure\n    - Cloud\n    - Management\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AZURE_SUBSCRIPTION_ID: AZURE_SUBSCRIPTION_ID\n      AZURE_ACCESS_TOKEN: AZURE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: azure\n      location: ./shared/azure.yaml\n\n  exposes:\n    - type: rest\n      port: 8084\n      namespace: azure-management-api\n      description: \"Unified REST API for Microsoft Azure management.\"\n      resources:\n        - path: /v1/resources\n          name: resources\n          description: \"Resource management\"\n          operations:\n            - method: GET\n              name: list\n              description: \"List all resources\"\n              call: \"azure.list-subscriptions\"\
  \n              with:\n                subscriptionId: \"rest.subscriptionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9094\n      namespace: azure-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Microsoft Azure management.\"\n      tools:\n        - name: list-subscriptions\n          description: \"List Subscription resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure.list-subscriptions\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-resource-groups\n          description: \"List ResourceGroup resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure.list-resource-groups\"\n          with:\n            subscriptionId:\
  \ \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-resources\n          description: \"List Resource resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure.list-resources\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-providers\n          description: \"List Provider resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure.list-providers\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/azure/refs/heads/main/capabilities/azure-management.yaml
tags:
- Azure
- Cloud
- Management
tools:
- description: List Subscription resources
  hints:
    openWorld: true
    readOnly: true
  name: list-subscriptions
- description: List ResourceGroup resources
  hints:
    openWorld: true
    readOnly: true
  name: list-resource-groups
- description: List Resource resources
  hints:
    openWorld: true
    readOnly: true
  name: list-resources
- description: List Provider resources
  hints:
    openWorld: true
    readOnly: true
  name: list-providers
---
