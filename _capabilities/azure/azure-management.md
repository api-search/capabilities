---
categories: []
consumed_apis: []
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
- list all resources
- list provider resources
- list subscription resources
- databases
- storage
- platform as a service
- infrastructure
- list resource groups
- azure
- cloud
- list resource resources
- cloud computing
- list subscriptions
- list resources
- machine learning
- list providers
- azure resource management
- list
- management
- resource management
- list resourcegroup resources
slug: azure-management
source_filename: azure-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Microsoft Azure Management\n  description: Workflow capability for managing Microsoft Azure resources. Used by cloud engineers and DevOps teams.\n  tags:\n  - Azure\n  - Cloud\n  - Management\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AZURE_SUBSCRIPTION_ID: AZURE_SUBSCRIPTION_ID\n    AZURE_ACCESS_TOKEN: AZURE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: azure\n    baseUri: https://management.azure.com\n    description: Microsoft Azure REST API\n    authentication:\n      type: bearer\n      token: '{{AZURE_ACCESS_TOKEN}}'\n    resources:\n    - name: subscription\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Subscription/Subscriptions\n      description: Manage Subscription resources\n      operations:\n      - name: list-subscriptions\n        method: GET\n        description: List all Subscription resources\n        inputParameters:\n       \
  \ - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resource-group\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.ResourceGroup/ResourceGroups\n      description: Manage ResourceGroup resources\n      operations:\n      - name: list-resource-groups\n        method: GET\n        description: List all ResourceGroup resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resource\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Resource/Resources\n      description: Manage\
  \ Resource resources\n      operations:\n      - name: list-resources\n        method: GET\n        description: List all Resource resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: provider\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Provider/Providers\n      description: Manage Provider resources\n      operations:\n      - name: list-providers\n        method: GET\n        description: List all Provider resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n  exposes:\n  - type: rest\n    port: 8084\n    namespace: azure-management-api\n    description: Unified REST API for Microsoft Azure management.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Resource management\n      operations:\n      - method: GET\n        name: list\n        description: List all resources\n        call: azure.list-subscriptions\n        with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9094\n    namespace: azure-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Microsoft Azure management.\n    tools:\n    - name: list-subscriptions\n      description: List Subscription resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure.list-subscriptions\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: list-resource-groups\n      description: List ResourceGroup resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure.list-resource-groups\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-resources\n      description: List Resource resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure.list-resources\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-providers\n      description: List Provider resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure.list-providers\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
