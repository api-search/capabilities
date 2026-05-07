---
categories:
- serverless
consumed_apis: []
description: Workflow capability for managing Azure Function Apps resources. Used by cloud engineers and DevOps teams.
layout: capability
name: Azure Function Apps Management
operations:
- description: List all resources
  method: GET
  name: list
  path: /v1/resources
personas: []
provider_name: Azure Function Apps
provider_slug: azure-function-apps
search_terms:
- azure resource management
- resource management
- list
- list deployment resources
- serverless
- list deployments
- management
- list configurations
- list configuration resources
- list all resources
- cloud
- faas
- compute
- list function resources
- azure
- list function apps
- list functionapp resources
- list functions
- functions
slug: azure-function-apps-management
source_filename: azure-function-apps-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure Function Apps Management\n  description: Workflow capability for managing Azure Function Apps resources. Used by cloud engineers and DevOps teams.\n  tags:\n  - Azure\n  - Cloud\n  - Management\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AZURE_SUBSCRIPTION_ID: AZURE_SUBSCRIPTION_ID\n    AZURE_ACCESS_TOKEN: AZURE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: azure-function-apps\n    baseUri: https://management.azure.com\n    description: Azure Function Apps REST API\n    authentication:\n      type: bearer\n      token: '{{AZURE_ACCESS_TOKEN}}'\n    resources:\n    - name: function-app\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.FunctionApp/FunctionApps\n      description: Manage FunctionApp resources\n      operations:\n      - name: list-function-apps\n        method: GET\n        description: List all FunctionApp resources\n        inputParameters:\n\
  \        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: function\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Function/Functions\n      description: Manage Function resources\n      operations:\n      - name: list-functions\n        method: GET\n        description: List all Function resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployment\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Deployment/Deployments\n      description: Manage Deployment resources\n\
  \      operations:\n      - name: list-deployments\n        method: GET\n        description: List all Deployment resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: configuration\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Configuration/Configurations\n      description: Manage Configuration resources\n      operations:\n      - name: list-configurations\n        method: GET\n        description: List all Configuration resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8084\n    namespace: azure-function-apps-management-api\n    description: Unified REST API for Azure Function Apps management.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Resource management\n      operations:\n      - method: GET\n        name: list\n        description: List all resources\n        call: azure-function-apps.list-function-apps\n        with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9094\n    namespace: azure-function-apps-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Azure Function Apps management.\n    tools:\n    - name: list-function-apps\n      description: List FunctionApp resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-function-apps.list-function-apps\n      with:\n      \
  \  subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-functions\n      description: List Function resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-function-apps.list-functions\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-deployments\n      description: List Deployment resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-function-apps.list-deployments\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-configurations\n      description: List Configuration resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-function-apps.list-configurations\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/azure-function-apps/refs/heads/main/capabilities/azure-function-apps-management.yaml
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
- description: List Deployment resources
  hints:
    openWorld: true
    readOnly: true
  name: list-deployments
- description: List Configuration resources
  hints:
    openWorld: true
    readOnly: true
  name: list-configurations
---
