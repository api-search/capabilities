---
categories: []
consumed_apis:
- axon-server
description: Workflow capability for managing Axon Server applications, contexts, and event streaming.
layout: capability
name: Axon Framework Event-Driven Workflow
operations: []
personas: []
provider_name: Axon Framework
provider_slug: axon-framework
search_terms:
- event sourcing
- create_application
- list_applications
- list_contexts
- java
- delete an axon application registration
- delete_application
- messaging
- list all registered axon applications
- create a new axon application registration
- event-driven
- get_metrics
- create_context
- create a new axon context
- list all axon contexts
- cqrs
- get axon server metrics and health information
- microservices
slug: event-driven-workflow
source_filename: event-driven-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: Axon Framework Event-Driven Workflow\n  description: Workflow capability for managing Axon Server applications, contexts, and event streaming.\n  tags:\n    - CQRS\n    - Event Sourcing\n    - Event-Driven\n    - Microservices\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      AXON_SERVER_URL: AXON_SERVER_URL\n      AXON_TOKEN: AXON_TOKEN\ncapability:\n  consumes:\n    - import: axon-server\n      location: ./shared/axon-server.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: workflow-api\n      resources:\n        - label: List Applications\n          method: GET\n          path: /applications\n        - label: Create Application\n          method: POST\n          path: /applications\n        - label: Delete Application\n          method: DELETE\n          path: /applications/{name}\n        - label: List Contexts\n          method: GET\n          path: /contexts\n\
  \        - label: Create Context\n          method: POST\n          path: /contexts\n        - label: Get Metrics\n          method: GET\n          path: /metrics\n    - type: mcp\n      port: 9090\n      namespace: workflow-mcp\n      transport: http\n      tools:\n        - name: list_applications\n          description: List all registered Axon applications\n        - name: create_application\n          description: Create a new Axon application registration\n        - name: delete_application\n          description: Delete an Axon application registration\n        - name: list_contexts\n          description: List all Axon contexts\n        - name: create_context\n          description: Create a new Axon context\n        - name: get_metrics\n          description: Get Axon Server metrics and health information\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/axon-framework/refs/heads/main/capabilities/event-driven-workflow.yaml
tags:
- CQRS
- Event Sourcing
- Event-Driven
- Microservices
tools:
- description: List all registered Axon applications
  hints: {}
  name: list_applications
- description: Create a new Axon application registration
  hints: {}
  name: create_application
- description: Delete an Axon application registration
  hints: {}
  name: delete_application
- description: List all Axon contexts
  hints: {}
  name: list_contexts
- description: Create a new Axon context
  hints: {}
  name: create_context
- description: Get Axon Server metrics and health information
  hints: {}
  name: get_metrics
---
