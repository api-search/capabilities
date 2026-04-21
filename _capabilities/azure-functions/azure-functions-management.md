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
- list triggers
- list bindings
- list trigger resources
- management
- azure resource management
- event-driven
- azure
- list binding resources
- resource management
- compute
- list functionapp resources
- list function resources
- list function apps
- serverless
- list functions
- functions
- list
- list all resources
- cloud
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
