---
categories: []
consumed_apis: []
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
- list all resources
- list registrys
- list tasks
- container images
- list replication resources
- azure
- cloud
- list registry resources
- containers
- docker
- registry
- list webhook resources
- azure resource management
- list
- list task resources
- management
- resource management
- list webhooks
- list replications
slug: azure-container-registry-management
source_filename: azure-container-registry-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure Container Registry Management\n  description: Workflow capability for managing Azure Container Registry resources. Used by cloud engineers and DevOps teams.\n  tags:\n  - Azure\n  - Cloud\n  - Management\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AZURE_SUBSCRIPTION_ID: AZURE_SUBSCRIPTION_ID\n    AZURE_ACCESS_TOKEN: AZURE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: azure-container-registry\n    baseUri: https://management.azure.com\n    description: Azure Container Registry REST API\n    authentication:\n      type: bearer\n      token: '{{AZURE_ACCESS_TOKEN}}'\n    resources:\n    - name: registry\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Registry/Registrys\n      description: Manage Registry resources\n      operations:\n      - name: list-registrys\n        method: GET\n        description: List all Registry resources\n        inputParameters:\n\
  \        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: replication\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Replication/Replications\n      description: Manage Replication resources\n      operations:\n      - name: list-replications\n        method: GET\n        description: List all Replication resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhook\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Webhook/Webhooks\n      description: Manage Webhook\
  \ resources\n      operations:\n      - name: list-webhooks\n        method: GET\n        description: List all Webhook resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: task\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.Task/Tasks\n      description: Manage Task resources\n      operations:\n      - name: list-tasks\n        method: GET\n        description: List all Task resources\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type:\
  \ rest\n    port: 8089\n    namespace: azure-container-registry-management-api\n    description: Unified REST API for Azure Container Registry management.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Resource management\n      operations:\n      - method: GET\n        name: list\n        description: List all resources\n        call: azure-container-registry.list-registrys\n        with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9099\n    namespace: azure-container-registry-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Azure Container Registry management.\n    tools:\n    - name: list-registrys\n      description: List Registry resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-container-registry.list-registrys\n      with:\n        subscriptionId: tools.subscriptionId\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-replications\n      description: List Replication resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-container-registry.list-replications\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-webhooks\n      description: List Webhook resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-container-registry.list-webhooks\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tasks\n      description: List Task resources\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-container-registry.list-tasks\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n"
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
