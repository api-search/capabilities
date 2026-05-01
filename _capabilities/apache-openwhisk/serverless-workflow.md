---
categories:
- serverless
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
- create a new serverless action
- event triggers
- serverless
- serverless computing
- invoke an action
- Platform Administrator
- get details of a specific activation
- manages serverless deployments and ci/cd pipelines
- activation history
- delete a serverless action
- Backend Developer
- get activation
- DevOps Engineer
- event driven
- manages namespaces, limits, and platform configuration
- list all trigger-to-action rules
- action packages
- functions
- list activations
- serverless function actions
- list all actions
- faas
- fire an event trigger
- list all serverless functions/actions
- cloud native
- list triggers
- delete action
- builds event-driven applications using serverless functions
- apache
- invoke a serverless action/function
- list activation history
- list all event triggers
- list rules
- event-driven
- functions as a service
- open source
- list all action packages
- list actions
- event-driven architecture
- list packages
- apache openwhisk
- create action
- invoke action
- fire trigger
slug: serverless-workflow
source_filename: serverless-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Apache OpenWhisk Serverless Workflow\"\n  description: \"Unified workflow capability for deploying and managing serverless functions, event triggers, rules, and activations in Apache OpenWhisk.\"\n  tags:\n    - Apache OpenWhisk\n    - Serverless\n    - Functions As A Service\n    - Event Driven\n    - Cloud Native\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      OPENWHISK_AUTH_USER: OPENWHISK_AUTH_USER\n      OPENWHISK_AUTH_PASS: OPENWHISK_AUTH_PASS\n\ncapability:\n  consumes:\n    - import: openwhisk\n      location: ./shared/openwhisk-rest-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: serverless-api\n      description: \"Unified REST API for OpenWhisk serverless management.\"\n      resources:\n        - path: /v1/actions\n          name: actions\n          description: \"Serverless function actions\"\n          operations:\n            - method:\
  \ GET\n              name: list-actions\n              description: \"List all actions\"\n              call: \"openwhisk.listActions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: invoke-action\n              description: \"Invoke an action\"\n              call: \"openwhisk.invokeAction\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/triggers\n          name: triggers\n          description: \"Event triggers\"\n          operations:\n            - method: GET\n              name: list-triggers\n              description: \"List triggers\"\n              call: \"openwhisk.listTriggers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/activations\n          name: activations\n          description: \"Activation history\"\n          operations:\n\
  \            - method: GET\n              name: list-activations\n              description: \"List activations\"\n              call: \"openwhisk.listActivations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/packages\n          name: packages\n          description: \"Action packages\"\n          operations:\n            - method: GET\n              name: list-packages\n              description: \"List packages\"\n              call: \"openwhisk.listPackages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: serverless-mcp\n      transport: http\n      description: \"MCP server for AI-assisted serverless function management.\"\n      tools:\n        - name: list-actions\n          description: \"List all serverless functions/actions\"\n          hints:\n            readOnly: true\n          call: \"openwhisk.listActions\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: invoke-action\n          description: \"Invoke a serverless action/function\"\n          hints:\n            readOnly: false\n          call: \"openwhisk.invokeAction\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-action\n          description: \"Create a new serverless action\"\n          hints:\n            readOnly: false\n          call: \"openwhisk.createOrUpdateAction\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-action\n          description: \"Delete a serverless action\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"openwhisk.deleteAction\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-triggers\n          description: \"List all\
  \ event triggers\"\n          hints:\n            readOnly: true\n          call: \"openwhisk.listTriggers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: fire-trigger\n          description: \"Fire an event trigger\"\n          hints:\n            readOnly: false\n          call: \"openwhisk.fireTrigger\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-rules\n          description: \"List all trigger-to-action rules\"\n          hints:\n            readOnly: true\n          call: \"openwhisk.listRules\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-packages\n          description: \"List all action packages\"\n          hints:\n            readOnly: true\n          call: \"openwhisk.listPackages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-activations\n\
  \          description: \"List activation history\"\n          hints:\n            readOnly: true\n          call: \"openwhisk.listActivations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-activation\n          description: \"Get details of a specific activation\"\n          hints:\n            readOnly: true\n          call: \"openwhisk.getActivation\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-openwhisk/refs/heads/main/capabilities/serverless-workflow.yaml
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
