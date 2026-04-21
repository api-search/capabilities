---
consumed_apis:
- openwhisk
description: Unified workflow capability for deploying and managing serverless functions, event triggers, rules, and activations in Apache OpenWhisk.
layout: capability
name: Apache OpenWhisk Serverless Workflow
operations:
- description: List all actions
  method: GET
  name: list-actions
  path: /v1/actions
- description: Invoke an action
  method: POST
  name: invoke-action
  path: /v1/actions
- description: List triggers
  method: GET
  name: list-triggers
  path: /v1/triggers
- description: List activations
  method: GET
  name: list-activations
  path: /v1/activations
- description: List packages
  method: GET
  name: list-packages
  path: /v1/packages
personas: []
provider_name: Apache OpenWhisk
provider_slug: apache-openwhisk
search_terms:
- cloud native
- event-driven
- list packages
- faas
- open source
- list actions
- invoke a serverless action/function
- serverless
- serverless function actions
- create action
- list rules
- invoke action
- DevOps Engineer
- manages namespaces, limits, and platform configuration
- action packages
- create a new serverless action
- functions as a service
- apache
- serverless computing
- functions
- get details of a specific activation
- delete a serverless action
- list all trigger-to-action rules
- event triggers
- list activations
- fire trigger
- delete action
- list all actions
- list activation history
- Backend Developer
- manages serverless deployments and ci/cd pipelines
- list all serverless functions/actions
- event driven
- list triggers
- builds event-driven applications using serverless functions
- event-driven architecture
- get activation
- activation history
- Platform Administrator
- invoke an action
- list all event triggers
- apache openwhisk
- fire an event trigger
- list all action packages
slug: serverless-workflow
tags:
- Apache OpenWhisk
- Serverless
- Functions As A Service
- Event Driven
- Cloud Native
tools:
- description: List all serverless functions/actions
  hints:
    readOnly: true
  name: list-actions
- description: Invoke a serverless action/function
  hints:
    readOnly: false
  name: invoke-action
- description: Create a new serverless action
  hints:
    readOnly: false
  name: create-action
- description: Delete a serverless action
  hints:
    destructive: true
    readOnly: false
  name: delete-action
- description: List all event triggers
  hints:
    readOnly: true
  name: list-triggers
- description: Fire an event trigger
  hints:
    readOnly: false
  name: fire-trigger
- description: List all trigger-to-action rules
  hints:
    readOnly: true
  name: list-rules
- description: List all action packages
  hints:
    readOnly: true
  name: list-packages
- description: List activation history
  hints:
    readOnly: true
  name: list-activations
- description: Get details of a specific activation
  hints:
    readOnly: true
  name: get-activation
---
