---
categories: []
consumed_apis: []
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
- azure resource management
- resource management
- list
- list workflowrun resources
- azure
- management
- list workflow runs
- list workflowtrigger resources
- list integrationaccount resources
- ipaas
- list workflows
- list integration accounts
- workflows
- list all resources
- list workflow triggers
- integration
- cloud
- list workflow resources
slug: azure-logic-apps-management
source_filename: azure-logic-apps-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure Logic Apps Management\n  description: Workflow capability for managing Azure Logic Apps resources. Used by cloud engineers and DevOps teams.\n  tags:\n  - Azure\n  - Cloud\n  - Management\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AZURE_SUBSCRIPTION_ID: AZURE_SUBSCRIPTION_ID\n    AZURE_ACCESS_TOKEN: AZURE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: azure-logic-apps\n    baseUri: https://management.azure.com\n    description: Azure Logic Apps REST API\n    authentication:\n      type: bearer\n      token: '{{AZURE_ACCESS_TOKEN}}'\n    resources:\n    - name: workflow\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Workflow/Workflows\n      description: Manage Workflow resources\n      operations:\n      - name: list-workflows\n        method: GET\n        description: List all Workflow resources\n        inputParameters:\n        - name: subscriptionId\n\
  \          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow-run\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.WorkflowRun/WorkflowRuns\n      description: Manage WorkflowRun resources\n      operations:\n      - name: list-workflow-runs\n        method: GET\n        description: List all WorkflowRun resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow-trigger\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.WorkflowTrigger/WorkflowTriggers\n      description: Manage WorkflowTrigger\
  \ resources\n      operations:\n      - name: list-workflow-triggers\n        method: GET\n        description: List all WorkflowTrigger resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: integration-account\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.IntegrationAccount/IntegrationAccounts\n      description: Manage IntegrationAccount resources\n      operations:\n      - name: list-integration-accounts\n        method: GET\n        description: List all IntegrationAccount resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: azure-logic-apps-management-api\n    description: Unified REST API for Azure Logic Apps management.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Resource management\n      operations:\n      - method: GET\n        name: list\n        description: List all resources\n        call: azure-logic-apps.list-workflows\n        with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: azure-logic-apps-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Azure Logic Apps management.\n    tools:\n    - name: list-workflows\n      description: List Workflow resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-logic-apps.list-workflows\n      with:\n\
  \        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workflow-runs\n      description: List WorkflowRun resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-logic-apps.list-workflow-runs\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workflow-triggers\n      description: List WorkflowTrigger resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-logic-apps.list-workflow-triggers\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-integration-accounts\n      description: List IntegrationAccount resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-logic-apps.list-integration-accounts\n      with:\n        subscriptionId:\
  \ tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
