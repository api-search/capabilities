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
- list all serverless functions/actions
- event-driven architecture
- event driven
- serverless
- functions as a service
- serverless function actions
- list activation history
- builds event-driven applications using serverless functions
- apache openwhisk
- list actions
- invoke a serverless action/function
- serverless computing
- get details of a specific activation
- fire an event trigger
- delete action
- manages namespaces, limits, and platform configuration
- list triggers
- manages serverless deployments and ci/cd pipelines
- apache
- faas
- list rules
- list packages
- list all event triggers
- Platform Administrator
- open source
- invoke an action
- create a new serverless action
- invoke action
- list all action packages
- list all trigger-to-action rules
- list activations
- event triggers
- fire trigger
- list all actions
- delete a serverless action
- action packages
- event-driven
- get activation
- create action
- activation history
- functions
- Backend Developer
- DevOps Engineer
- cloud native
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
