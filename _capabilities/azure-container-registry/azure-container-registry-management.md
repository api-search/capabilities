---
api_specs:
- filename: azure-container-registry-openapi.yaml
  format: yaml
  label: azure-container-registry
  slug: azure-container-registry
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/azure-container-registry/refs/heads/main/openapi/azure-container-registry-openapi.yaml
categories: []
consumed_apis:
- azure-container-registry
description: Workflow capability for managing Azure Container Registry resources. Used by cloud engineers and DevOps teams.
layout: capability
name: Azure Container Registry Management
operations:
- description: List all resources
  method: GET
  name: list
  path: /v1/resources
personas: []
provider_name: Azure Container Registry
provider_slug: azure-container-registry
search_terms:
- resource management
- list webhooks
- containers
- list all resources
- docker
- azure resource management
- list registry resources
- azure
- list registrys
- container images
- list
- list webhook resources
- list replication resources
- list replications
- list tasks
- cloud
- list task resources
- registry
- management
slug: azure-container-registry-management
source_filename: azure-container-registry-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Azure Container Registry Management\"\n  description: \"Workflow capability for managing Azure Container Registry resources. Used by cloud engineers and DevOps teams.\"\n  tags:\n    - Azure\n    - Cloud\n    - Management\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AZURE_SUBSCRIPTION_ID: AZURE_SUBSCRIPTION_ID\n      AZURE_ACCESS_TOKEN: AZURE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: azure-container-registry\n      location: ./shared/azure-container-registry.yaml\n\n  exposes:\n    - type: rest\n      port: 8089\n      namespace: azure-container-registry-management-api\n      description: \"Unified REST API for Azure Container Registry management.\"\n      resources:\n        - path: /v1/resources\n          name: resources\n          description: \"Resource management\"\n          operations:\n            - method: GET\n              name: list\n         \
  \     description: \"List all resources\"\n              call: \"azure-container-registry.list-registrys\"\n              with:\n                subscriptionId: \"rest.subscriptionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9099\n      namespace: azure-container-registry-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Azure Container Registry management.\"\n      tools:\n        - name: list-registrys\n          description: \"List Registry resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-container-registry.list-registrys\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-replications\n          description: \"List Replication resources\"\n          hints:\n      \
  \      readOnly: true\n            openWorld: true\n          call: \"azure-container-registry.list-replications\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-webhooks\n          description: \"List Webhook resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-container-registry.list-webhooks\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tasks\n          description: \"List Task resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-container-registry.list-tasks\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n            \
  \  mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/azure-container-registry/refs/heads/main/capabilities/azure-container-registry-management.yaml
tags:
- Azure
- Cloud
- Management
tools:
- description: List Registry resources
  hints:
    openWorld: true
    readOnly: true
  name: list-registrys
- description: List Replication resources
  hints:
    openWorld: true
    readOnly: true
  name: list-replications
- description: List Webhook resources
  hints:
    openWorld: true
    readOnly: true
  name: list-webhooks
- description: List Task resources
  hints:
    openWorld: true
    readOnly: true
  name: list-tasks
---
