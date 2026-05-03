---
api_specs:
- filename: azure-container-apps-openapi.yml
  format: yaml
  label: azure-container-apps
  slug: azure-container-apps
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/azure-container-apps/refs/heads/main/openapi/azure-container-apps-openapi.yml
categories:
- container-orchestration
consumed_apis:
- azure-container-apps
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
- Platform Engineer
- list all azure container apps in a subscription
- container app deployment and management
- serverless compute and job execution
- create container app
- list all container apps
- create or update an azure container app
- manage containerized applications, environments, and jobs
- managed environment management
- azure
- container app job management
- manages the container infrastructure and environments
- kubernetes
- delete an azure container app
- list jobs
- list all managed container app environments
- deploys and manages containerized application workloads
- delete container app
- list all managed environments
- containers
- list environments
- dapr
- microservices
- list container apps
- list all container app jobs
- container app management
- serverless
- devops
- DevOps Engineer
slug: container-apps-management
source_filename: container-apps-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Azure Container Apps Management\"\n  description: \"Workflow capability for managing containerized applications, environments, and jobs in Azure Container Apps. Used by platform engineers and DevOps teams.\"\n  tags:\n    - Azure\n    - Containers\n    - Microservices\n    - Serverless\n    - DevOps\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AZURE_SUBSCRIPTION_ID: AZURE_SUBSCRIPTION_ID\n      AZURE_ACCESS_TOKEN: AZURE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: azure-container-apps\n      location: ./shared/azure-container-apps.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: container-apps-management-api\n      description: \"Unified REST API for Azure Container Apps management.\"\n      resources:\n        - path: /v1/container-apps\n          name: container-apps\n          description: \"Container app management\"\n          operations:\n\
  \            - method: GET\n              name: list-container-apps\n              description: \"List all container apps\"\n              call: \"azure-container-apps.list-container-apps\"\n              with:\n                subscriptionId: \"rest.subscriptionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/environments\n          name: environments\n          description: \"Managed environment management\"\n          operations:\n            - method: GET\n              name: list-environments\n              description: \"List all managed environments\"\n              call: \"azure-container-apps.list-environments\"\n              with:\n                subscriptionId: \"rest.subscriptionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/jobs\n          name: jobs\n          description: \"Container app job management\"\n         \
  \ operations:\n            - method: GET\n              name: list-jobs\n              description: \"List all container app jobs\"\n              call: \"azure-container-apps.list-jobs\"\n              with:\n                subscriptionId: \"rest.subscriptionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: container-apps-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Azure Container Apps management.\"\n      tools:\n        - name: list-container-apps\n          description: \"List all Azure Container Apps in a subscription\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-container-apps.list-container-apps\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-container-app\n\
  \          description: \"Create or update an Azure Container App\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"azure-container-apps.create-container-app\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n            resourceGroupName: \"tools.resourceGroupName\"\n            containerAppName: \"tools.containerAppName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-container-app\n          description: \"Delete an Azure Container App\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"azure-container-apps.delete-container-app\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n            resourceGroupName: \"tools.resourceGroupName\"\n            containerAppName: \"tools.containerAppName\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: list-environments\n          description: \"List all managed container app environments\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-container-apps.list-environments\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-jobs\n          description: \"List all container app jobs\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"azure-container-apps.list-jobs\"\n          with:\n            subscriptionId: \"tools.subscriptionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
