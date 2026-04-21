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
- list triggers
- cloud native
- delete action
- event driven
- manages serverless deployments and ci/cd pipelines
- serverless function actions
- Platform Administrator
- list all action packages
- action packages
- list all actions
- event-driven
- Backend Developer
- event triggers
- delete a serverless action
- functions as a service
- get details of a specific activation
- builds event-driven applications using serverless functions
- fire trigger
- invoke an action
- list rules
- get activation
- list actions
- DevOps Engineer
- faas
- list all trigger-to-action rules
- create a new serverless action
- create action
- serverless
- fire an event trigger
- invoke a serverless action/function
- list all event triggers
- activation history
- functions
- list all serverless functions/actions
- list packages
- manages namespaces, limits, and platform configuration
- apache
- invoke action
- apache openwhisk
- serverless computing
- open source
- list activations
- list activation history
- event-driven architecture
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
