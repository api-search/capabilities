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
- invoke an action
- list all trigger-to-action rules
- get activation
- builds event-driven applications using serverless functions
- list all serverless functions/actions
- create action
- create a new serverless action
- action packages
- list packages
- get details of a specific activation
- activation history
- fire an event trigger
- Backend Developer
- open source
- cloud native
- event triggers
- invoke a serverless action/function
- apache openwhisk
- list actions
- apache
- event-driven architecture
- event driven
- list triggers
- list all event triggers
- delete action
- invoke action
- serverless
- list activation history
- event-driven
- list all actions
- manages namespaces, limits, and platform configuration
- list rules
- manages serverless deployments and ci/cd pipelines
- serverless computing
- functions
- Platform Administrator
- fire trigger
- functions as a service
- delete a serverless action
- DevOps Engineer
- faas
- list all action packages
- list activations
- serverless function actions
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
