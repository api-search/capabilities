---
categories: []
consumed_apis: []
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
- list binding resources
- list all resources
- compute
- azure
- list function apps
- serverless
- cloud
- list triggers
- list functionapp resources
- functions
- azure resource management
- list
- event-driven
- list functions
- list function resources
- list bindings
- management
- resource management
- list trigger resources
slug: azure-functions-management
source_filename: azure-functions-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure Functions Management\n  description: Workflow capability for managing Azure Functions resources. Used by cloud engineers and DevOps teams.\n  tags:\n  - Azure\n  - Cloud\n  - Management\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AZURE_SUBSCRIPTION_ID: AZURE_SUBSCRIPTION_ID\n    AZURE_ACCESS_TOKEN: AZURE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: azure-functions\n    baseUri: https://management.azure.com\n    description: Azure Functions REST API\n    authentication:\n      type: bearer\n      token: '{{AZURE_ACCESS_TOKEN}}'\n    resources:\n    - name: function-app\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.FunctionApp/FunctionApps\n      description: Manage FunctionApp resources\n      operations:\n      - name: list-function-apps\n        method: GET\n        description: List all FunctionApp resources\n        inputParameters:\n \
  \       - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: function\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Function/Functions\n      description: Manage Function resources\n      operations:\n      - name: list-functions\n        method: GET\n        description: List all Function resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: trigger\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Trigger/Triggers\n      description: Manage Trigger resources\n   \
  \   operations:\n      - name: list-triggers\n        method: GET\n        description: List all Trigger resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: binding\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Binding/Bindings\n      description: Manage Binding resources\n      operations:\n      - name: list-bindings\n        method: GET\n        description: List all Binding resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  -\
  \ type: rest\n    port: 8085\n    namespace: azure-functions-management-api\n    description: Unified REST API for Azure Functions management.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Resource management\n      operations:\n      - method: GET\n        name: list\n        description: List all resources\n        call: azure-functions.list-function-apps\n        with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9095\n    namespace: azure-functions-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Azure Functions management.\n    tools:\n    - name: list-function-apps\n      description: List FunctionApp resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-functions.list-function-apps\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n    \
  \  - type: object\n        mapping: $.\n    - name: list-functions\n      description: List Function resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-functions.list-functions\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-triggers\n      description: List Trigger resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-functions.list-triggers\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-bindings\n      description: List Binding resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-functions.list-bindings\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
