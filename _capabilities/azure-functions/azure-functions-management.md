---
consumed_apis:
- azure-functions
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
- list
- list bindings
- list functions
- azure
- cloud
- list all resources
- azure resource management
- management
- list trigger resources
- list functionapp resources
- list triggers
- serverless
- list binding resources
- event-driven
- list function apps
- functions
- list function resources
- compute
- resource management
slug: azure-functions-management
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
