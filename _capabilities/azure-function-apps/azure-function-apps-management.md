---
consumed_apis:
- azure-function-apps
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
- faas
- list function resources
- list configurations
- serverless
- management
- list configuration resources
- list all resources
- functions
- cloud
- azure
- list
- list functions
- list functionapp resources
- list deployment resources
- list function apps
- list deployments
- resource management
- compute
- azure resource management
slug: azure-function-apps-management
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
