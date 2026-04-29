---
api_specs:
- filename: azure-logic-apps-openapi.yaml
  format: yaml
  label: azure-logic-apps
  slug: azure-logic-apps
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/azure-logic-apps/refs/heads/main/openapi/azure-logic-apps-openapi.yaml
categories: []
consumed_apis:
- azure-logic-apps
description: Workflow capability for managing Azure Logic Apps resources. Used by cloud engineers and DevOps teams.
layout: capability
name: Azure Logic Apps Management
operations:
- description: List all resources
  method: GET
  name: list
  path: /v1/resources
personas: []
provider_name: Azure Logic Apps
provider_slug: azure-logic-apps
search_terms:
- list workflow resources
- list workflowtrigger resources
- azure
- list workflows
- azure resource management
- workflows
- resource management
- management
- list all resources
- list integrationaccount resources
- list workflow runs
- ipaas
- list workflow triggers
- integration
- list workflowrun resources
- list integration accounts
- cloud
- list
slug: azure-logic-apps-management
source_filename: azure-logic-apps-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Azure Logic Apps Management\"\n  description: \"Workflow capability for managing Azure Logic Apps resources. Used by cloud engineers and DevOps teams.\"\n  tags:\n    - Azure\n    - Cloud\n    - Management\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AZURE_SUBSCRIPTION_ID: AZURE_SUBSCRIPTION_ID\n      AZURE_ACCESS_TOKEN: AZURE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: azure-logic-apps\n      location: ./shared/azure-logic-apps.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: azure-logic-apps-management-api\n      description: \"Unified REST API for Azure Logic Apps management.\"\n      resources:\n        - path: /v1/resources\n          name: resources\n          description: \"Resource management\"\n          operations:\n            - method: GET\n              name: list\n              description: \"List all resources\"\n      \
  \        call: \"azure-logic-apps.list-workflows\"\n              with:\n                subscriptionId: \"rest.subscriptionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: azure-logic-apps-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Azure Logic Apps management.\"\n      tools:\n        - name: list-workflows\n          description: \"List Workflow resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-logic-apps.list-workflows\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-workflow-runs\n          description: \"List WorkflowRun resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-logic-apps.list-workflow-runs\"\
  \n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-workflow-triggers\n          description: \"List WorkflowTrigger resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-logic-apps.list-workflow-triggers\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-integration-accounts\n          description: \"List IntegrationAccount resources\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-logic-apps.list-integration-accounts\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/azure-logic-apps/refs/heads/main/capabilities/azure-logic-apps-management.yaml
tags:
- Azure
- Cloud
- Management
tools:
- description: List Workflow resources
  hints:
    openWorld: true
    readOnly: true
  name: list-workflows
- description: List WorkflowRun resources
  hints:
    openWorld: true
    readOnly: true
  name: list-workflow-runs
- description: List WorkflowTrigger resources
  hints:
    openWorld: true
    readOnly: true
  name: list-workflow-triggers
- description: List IntegrationAccount resources
  hints:
    openWorld: true
    readOnly: true
  name: list-integration-accounts
---
