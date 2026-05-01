---
api_specs:
- filename: azure-functions-openapi.yaml
  format: yaml
  label: azure-functions
  slug: azure-functions
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/azure-functions/refs/heads/main/openapi/azure-functions-openapi.yaml
categories: []
consumed_apis:
- azure-functions
description: Workflow capability for managing Azure Functions resources. Used by cloud engineers and DevOps teams.
layout: capability
name: Azure Functions Management
operations:
- description: List all resources
  method: GET
  name: list
  path: /v1/resources
personas: []
provider_name: Azure Functions
provider_slug: azure-functions
search_terms:
- list all resources
- list function apps
- compute
- list bindings
- cloud
- list binding resources
- list
- resource management
- list functions
- list triggers
- list trigger resources
- azure resource management
- list function resources
- functions
- azure
- event-driven
- list functionapp resources
- serverless
- management
slug: azure-functions-management
source_filename: azure-functions-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Azure Functions Management\"\n  description: \"Workflow capability for managing Azure Functions resources. Used by cloud engineers and DevOps teams.\"\n  tags:\n    - Azure\n    - Cloud\n    - Management\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AZURE_SUBSCRIPTION_ID: AZURE_SUBSCRIPTION_ID\n      AZURE_ACCESS_TOKEN: AZURE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: azure-functions\n      location: ./shared/azure-functions.yaml\n\n  exposes:\n    - type: rest\n      port: 8085\n      namespace: azure-functions-management-api\n      description: \"Unified REST API for Azure Functions management.\"\n      resources:\n        - path: /v1/resources\n          name: resources\n          description: \"Resource management\"\n          operations:\n            - method: GET\n              name: list\n              description: \"List all resources\"\n            \
  \  call: \"azure-functions.list-function-apps\"\n              with:\n                subscriptionId: \"rest.subscriptionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9095\n      namespace: azure-functions-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Azure Functions management.\"\n      tools:\n        - name: list-function-apps\n          description: \"List FunctionApp resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-functions.list-function-apps\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-functions\n          description: \"List Function resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-functions.list-functions\"\
  \n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-triggers\n          description: \"List Trigger resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-functions.list-triggers\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-bindings\n          description: \"List Binding resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-functions.list-bindings\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/azure-functions/refs/heads/main/capabilities/azure-functions-management.yaml
tags:
- Azure
- Cloud
- Management
tools:
- description: List FunctionApp resources
  hints:
    openWorld: true
    readOnly: true
  name: list-function-apps
- description: List Function resources
  hints:
    openWorld: true
    readOnly: true
  name: list-functions
- description: List Trigger resources
  hints:
    openWorld: true
    readOnly: true
  name: list-triggers
- description: List Binding resources
  hints:
    openWorld: true
    readOnly: true
  name: list-bindings
---
