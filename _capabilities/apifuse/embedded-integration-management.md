---
categories: []
consumed_apis:
- apifuse
description: Unified workflow for managing embedded integrations within SaaS products - browsing connectors, building workflows, monitoring usage analytics, and managing user connections.
layout: capability
name: Apifuse Embedded Integration Management
operations:
- description: List all integrations.
  method: GET
  name: list-integrations
  path: /v1/integrations
- description: List all connectors.
  method: GET
  name: list-connectors
  path: /v1/connectors
- description: List workflows.
  method: GET
  name: list-workflows
  path: /v1/workflows
- description: Create a workflow.
  method: POST
  name: create-workflow
  path: /v1/workflows
- description: Get analytics data.
  method: GET
  name: get-analytics
  path: /v1/analytics
personas: []
provider_name: Apifuse
provider_slug: apifuse
search_terms:
- saas
- browse pre-built connectors.
- list all integrations.
- ipaas
- browse and manage integrations.
- create workflow
- Integration Developer
- create a new automation workflow connecting two or more integrated platforms.
- create a workflow.
- SaaS Product Manager
- list all connectors.
- list workflows.
- apifuse
- managing native integrations within saas products.
- embedded integrations
- product manager building native integrations into a saas product.
- list workflows
- retrieve integration usage analytics including total tasks, active integrations, and active users.
- list connectors
- manage workflows.
- get analytics
- integrations
- list integrations
- list all pre-built connectors available for embedding into your saas product.
- developer implementing and automating embedded integration workflows.
- integration analytics.
- browse all available embedded integrations, optionally filtered by category.
- get analytics data.
- list all integration workflows configured in the embedded marketplace.
- integration platform
- marketplace
- workflow automation
slug: embedded-integration-management
source_filename: embedded-integration-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Apifuse Embedded Integration Management\"\n  description: \"Unified workflow for managing embedded integrations within SaaS products - browsing connectors, building workflows, monitoring usage analytics, and managing user connections.\"\n  tags:\n    - Apifuse\n    - Embedded Integrations\n    - Workflow Automation\n    - SaaS\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      APIFUSE_API_KEY: APIFUSE_API_KEY\n\ncapability:\n  consumes:\n    - import: apifuse\n      location: ./shared/apifuse.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: apifuse-integration-api\n      description: \"Unified REST API for managing Apifuse embedded integrations.\"\n      resources:\n        - path: /v1/integrations\n          name: integrations\n          description: \"Browse and manage integrations.\"\n          operations:\n            - method: GET\n              name:\
  \ list-integrations\n              description: \"List all integrations.\"\n              call: \"apifuse.list-integrations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/connectors\n          name: connectors\n          description: \"Browse pre-built connectors.\"\n          operations:\n            - method: GET\n              name: list-connectors\n              description: \"List all connectors.\"\n              call: \"apifuse.list-connectors\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workflows\n          name: workflows\n          description: \"Manage workflows.\"\n          operations:\n            - method: GET\n              name: list-workflows\n              description: \"List workflows.\"\n              call: \"apifuse.list-workflows\"\n              outputParameters:\n                - type: object\n               \
  \   mapping: \"$.\"\n            - method: POST\n              name: create-workflow\n              description: \"Create a workflow.\"\n              call: \"apifuse.create-workflow\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/analytics\n          name: analytics\n          description: \"Integration analytics.\"\n          operations:\n            - method: GET\n              name: get-analytics\n              description: \"Get analytics data.\"\n              call: \"apifuse.get-analytics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: apifuse-integration-mcp\n      transport: http\n      description: \"MCP server for AI-assisted embedded integration management.\"\n      tools:\n        - name: list-integrations\n          description: \"Browse all available embedded integrations, optionally filtered\
  \ by category.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"apifuse.list-integrations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-connectors\n          description: \"List all pre-built connectors available for embedding into your SaaS product.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"apifuse.list-connectors\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-workflows\n          description: \"List all integration workflows configured in the embedded marketplace.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"apifuse.list-workflows\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: create-workflow\n          description: \"Create a new automation workflow connecting two or more integrated platforms.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"apifuse.create-workflow\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-analytics\n          description: \"Retrieve integration usage analytics including total tasks, active integrations, and active users.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"apifuse.get-analytics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apifuse/refs/heads/main/capabilities/embedded-integration-management.yaml
tags:
- Apifuse
- Embedded Integrations
- Workflow Automation
- SaaS
tools:
- description: Browse all available embedded integrations, optionally filtered by category.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-integrations
- description: List all pre-built connectors available for embedding into your SaaS product.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-connectors
- description: List all integration workflows configured in the embedded marketplace.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-workflows
- description: Create a new automation workflow connecting two or more integrated platforms.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-workflow
- description: Retrieve integration usage analytics including total tasks, active integrations, and active users.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-analytics
---
