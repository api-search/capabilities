---
api_specs:
- filename: azure-dev-ops-openapi.yaml
  format: yaml
  label: azure-dev-ops
  slug: azure-dev-ops
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/azure-dev-ops/refs/heads/main/openapi/azure-dev-ops-openapi.yaml
categories: []
consumed_apis:
- azure-dev-ops
description: Workflow capability for managing Azure DevOps resources. Used by cloud engineers and DevOps teams.
layout: capability
name: Azure DevOps Management
operations:
- description: List all resources
  method: GET
  name: list
  path: /v1/resources
personas: []
provider_name: Azure DevOps
provider_slug: azure-dev-ops
search_terms:
- azure resource management
- management
- list projects
- list repositorys
- list pipelines
- list project resources
- azure
- list all resources
- project management
- list
- cloud
- list organization resources
- list pipeline resources
- resource management
- list organizations
- ci/cd
- devops
- list repository resources
- version control
slug: azure-dev-ops-management
source_filename: azure-dev-ops-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Azure DevOps Management\"\n  description: \"Workflow capability for managing Azure DevOps resources. Used by cloud engineers and DevOps teams.\"\n  tags:\n    - Azure\n    - Cloud\n    - Management\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AZURE_SUBSCRIPTION_ID: AZURE_SUBSCRIPTION_ID\n      AZURE_ACCESS_TOKEN: AZURE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: azure-dev-ops\n      location: ./shared/azure-dev-ops.yaml\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace: azure-dev-ops-management-api\n      description: \"Unified REST API for Azure DevOps management.\"\n      resources:\n        - path: /v1/resources\n          name: resources\n          description: \"Resource management\"\n          operations:\n            - method: GET\n              name: list\n              description: \"List all resources\"\n              call: \"azure-dev-ops.list-pipelines\"\
  \n              with:\n                subscriptionId: \"rest.subscriptionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9093\n      namespace: azure-dev-ops-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Azure DevOps management.\"\n      tools:\n        - name: list-pipelines\n          description: \"List Pipeline resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-dev-ops.list-pipelines\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-projects\n          description: \"List Project resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-dev-ops.list-projects\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-organizations\n          description: \"List Organization resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-dev-ops.list-organizations\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-repositorys\n          description: \"List Repository resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-dev-ops.list-repositorys\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/azure-dev-ops/refs/heads/main/capabilities/azure-dev-ops-management.yaml
tags:
- Azure
- Cloud
- Management
tools:
- description: List Pipeline resources
  hints:
    openWorld: true
    readOnly: true
  name: list-pipelines
- description: List Project resources
  hints:
    openWorld: true
    readOnly: true
  name: list-projects
- description: List Organization resources
  hints:
    openWorld: true
    readOnly: true
  name: list-organizations
- description: List Repository resources
  hints:
    openWorld: true
    readOnly: true
  name: list-repositorys
---
