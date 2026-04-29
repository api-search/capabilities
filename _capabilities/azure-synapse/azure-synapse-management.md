---
categories: []
consumed_apis:
- azure-synapse
description: Workflow capability for managing Azure Synapse Analytics resources. Used by cloud engineers and DevOps teams.
layout: capability
name: Azure Synapse Analytics Management
operations:
- description: List all resources
  method: GET
  name: list
  path: /v1/resources
personas: []
provider_name: Azure Synapse Analytics
provider_slug: azure-synapse
search_terms:
- list sqlpool resources
- list
- big data
- analytics
- list sql pools
- cloud
- list workspaces
- apache spark
- list pipeline resources
- sql
- list bigdatapool resources
- list big data pools
- data warehouse
- list all resources
- azure resource management
- azure
- list workspace resources
- etl
- resource management
- management
- list pipelines
slug: azure-synapse-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Azure Synapse Analytics Management\"\n  description: \"Workflow capability for managing Azure Synapse Analytics resources. Used by cloud engineers and DevOps teams.\"\n  tags:\n    - Azure\n    - Cloud\n    - Management\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AZURE_SUBSCRIPTION_ID: AZURE_SUBSCRIPTION_ID\n      AZURE_ACCESS_TOKEN: AZURE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: azure-synapse\n      location: ./shared/azure-synapse.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: azure-synapse-management-api\n      description: \"Unified REST API for Azure Synapse Analytics management.\"\n      resources:\n        - path: /v1/resources\n          name: resources\n          description: \"Resource management\"\n          operations:\n            - method: GET\n              name: list\n              description: \"List all resources\"\
  \n              call: \"azure-synapse.list-workspaces\"\n              with:\n                subscriptionId: \"rest.subscriptionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: azure-synapse-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Azure Synapse Analytics management.\"\n      tools:\n        - name: list-workspaces\n          description: \"List Workspace resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-synapse.list-workspaces\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-sql-pools\n          description: \"List SqlPool resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-synapse.list-sql-pools\"\
  \n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-big-data-pools\n          description: \"List BigDataPool resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-synapse.list-big-data-pools\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-pipelines\n          description: \"List Pipeline resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-synapse.list-pipelines\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/azure-synapse/refs/heads/main/capabilities/azure-synapse-management.yaml
tags:
- Azure
- Cloud
- Management
tools:
- description: List Workspace resources
  hints:
    openWorld: true
    readOnly: true
  name: list-workspaces
- description: List SqlPool resources
  hints:
    openWorld: true
    readOnly: true
  name: list-sql-pools
- description: List BigDataPool resources
  hints:
    openWorld: true
    readOnly: true
  name: list-big-data-pools
- description: List Pipeline resources
  hints:
    openWorld: true
    readOnly: true
  name: list-pipelines
---
