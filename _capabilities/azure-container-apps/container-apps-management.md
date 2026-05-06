---
categories:
- container-orchestration
consumed_apis: []
description: Workflow capability for managing containerized applications, environments, and jobs in Azure Container Apps. Used by platform engineers and DevOps teams.
layout: capability
name: Azure Container Apps Management
operations:
- description: List all container apps
  method: GET
  name: list-container-apps
  path: /v1/container-apps
- description: List all managed environments
  method: GET
  name: list-environments
  path: /v1/environments
- description: List all container app jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
personas: []
provider_name: Azure Container Apps
provider_slug: azure-container-apps
search_terms:
- list jobs
- list environments
- dapr
- managed environment management
- deploys and manages containerized application workloads
- list all managed container app environments
- DevOps Engineer
- list container apps
- devops
- manages the container infrastructure and environments
- azure
- manage containerized applications, environments, and jobs
- serverless
- containers
- kubernetes
- list all container apps
- list all container app jobs
- create or update an azure container app
- container app deployment and management
- container app management
- serverless compute and job execution
- create container app
- container app job management
- delete container app
- Platform Engineer
- delete an azure container app
- microservices
- list all azure container apps in a subscription
- list all managed environments
slug: container-apps-management
source_filename: container-apps-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure Container Apps Management\n  description: Workflow capability for managing containerized applications, environments, and jobs in Azure Container Apps.\n    Used by platform engineers and DevOps teams.\n  tags:\n  - Azure\n  - Containers\n  - Microservices\n  - Serverless\n  - DevOps\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AZURE_SUBSCRIPTION_ID: AZURE_SUBSCRIPTION_ID\n    AZURE_ACCESS_TOKEN: AZURE_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: azure-container-apps\n    baseUri: https://management.azure.com\n    description: Azure Container Apps Resource Manager REST API\n    authentication:\n      type: bearer\n      token: '{{AZURE_ACCESS_TOKEN}}'\n    resources:\n    - name: container-apps\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.App/containerApps\n      description: Manage container apps\n      operations:\n      - name: list-container-apps\n\
  \        method: GET\n        description: List all container apps in subscription\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-container-app\n        method: PUT\n        description: Create or update a container app\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: Resource group name\n        - name: containerAppName\n         \
  \ in: path\n          type: string\n          required: true\n          description: Container app name\n        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            location: '{{tools.location}}'\n            properties:\n              environmentId: '{{tools.environmentId}}'\n      - name: delete-container-app\n        method: DELETE\n        description: Delete a container app\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: Resource group name\n        - name: containerAppName\n\
  \          in: path\n          type: string\n          required: true\n          description: Container app name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: managed-environments\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.App/managedEnvironments\n      description: Manage container app environments\n      operations:\n      - name: list-environments\n        method: GET\n        description: List all managed environments\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.App/jobs\n      description: Manage container app jobs\n      operations:\n\
  \      - name: list-jobs\n        method: GET\n        description: List all container app jobs\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: container-apps-management-api\n    description: Unified REST API for Azure Container Apps management.\n    resources:\n    - path: /v1/container-apps\n      name: container-apps\n      description: Container app management\n      operations:\n      - method: GET\n        name: list-container-apps\n        description: List all container apps\n        call: azure-container-apps.list-container-apps\n        with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /v1/environments\n      name: environments\n      description: Managed environment management\n      operations:\n      - method: GET\n        name: list-environments\n        description: List all managed environments\n        call: azure-container-apps.list-environments\n        with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs\n      name: jobs\n      description: Container app job management\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List all container app jobs\n        call: azure-container-apps.list-jobs\n        with:\n          subscriptionId: rest.subscriptionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: container-apps-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Azure Container Apps management.\n    tools:\n    - name:\
  \ list-container-apps\n      description: List all Azure Container Apps in a subscription\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-container-apps.list-container-apps\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-container-app\n      description: Create or update an Azure Container App\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: azure-container-apps.create-container-app\n      with:\n        subscriptionId: tools.subscriptionId\n        resourceGroupName: tools.resourceGroupName\n        containerAppName: tools.containerAppName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-container-app\n      description: Delete an Azure Container App\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: azure-container-apps.delete-container-app\n\
  \      with:\n        subscriptionId: tools.subscriptionId\n        resourceGroupName: tools.resourceGroupName\n        containerAppName: tools.containerAppName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-environments\n      description: List all managed container app environments\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-container-apps.list-environments\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-jobs\n      description: List all container app jobs\n      hints:\n        readOnly: true\n        openWorld: true\n      call: azure-container-apps.list-jobs\n      with:\n        subscriptionId: tools.subscriptionId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/azure-container-apps/refs/heads/main/capabilities/container-apps-management.yaml
tags:
- Azure
- Containers
- Microservices
- Serverless
- DevOps
tools:
- description: List all Azure Container Apps in a subscription
  hints:
    openWorld: true
    readOnly: true
  name: list-container-apps
- description: Create or update an Azure Container App
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: create-container-app
- description: Delete an Azure Container App
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-container-app
- description: List all managed container app environments
  hints:
    openWorld: true
    readOnly: true
  name: list-environments
- description: List all container app jobs
  hints:
    openWorld: true
    readOnly: true
  name: list-jobs
---
