---
api_specs:
- filename: salesloft-openapi.yml
  format: yaml
  label: salesloft
  slug: salesloft
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/salesloft/refs/heads/main/openapi/salesloft-openapi.yml
categories: []
consumed_apis:
- salesloft
description: Revenue intelligence workflow combining calls, conversations, signals, and opportunities to provide pipeline visibility and AI-driven coaching insights. Used by sales managers and revenue leaders to monitor deal health and rep performance.
layout: capability
name: Salesloft Revenue Intelligence
operations:
- description: List all calls
  method: GET
  name: list-calls
  path: /v1/calls
- description: List all opportunities
  method: GET
  name: list-opportunities
  path: /v1/opportunities
- description: Get opportunity by ID
  method: GET
  name: fetch-opportunity
  path: /v1/opportunities/{id}
- description: Submit a buyer signal to Rhythm
  method: POST
  name: create-signal
  path: /v1/signals
- description: List all emails
  method: GET
  name: list-emails
  path: /v1/emails
- description: List all tasks
  method: GET
  name: list-tasks
  path: /v1/tasks
- description: Create a follow-up task
  method: POST
  name: create-task
  path: /v1/tasks
- description: List all users
  method: GET
  name: list-users
  path: /v1/users
personas: []
provider_name: Salesloft
provider_slug: salesloft
search_terms:
- list sales team members in salesloft
- signals
- list webhook subscriptions for salesloft event notifications
- list all calls
- list pending sales tasks and follow-ups
- revenue intelligence
- list all opportunities
- list users
- salesloft
- fetch opportunity
- call recordings and outcomes
- list sales opportunities and pipeline in salesloft
- create a webhook subscription to receive salesloft events
- create signal
- create task
- ai
- list emails sent through salesloft for activity tracking
- analytics
- list all tasks
- opportunities
- submit a buyer intent signal to salesloft rhythm to prioritize follow-up
- revenue
- sales opportunities and pipeline
- create a follow-up task
- list calls
- list call recordings and outcomes from salesloft
- list all emails
- submit a buyer signal to rhythm
- list emails
- get details for a specific opportunity
- list webhook subscriptions
- list all users
- sales team users
- conversations
- create a follow-up task for a sales rep
- crm
- email activity tracking
- get opportunity by id
- single opportunity
- tasks and follow-ups
- sales
- submit buyer signal
- automation
- list tasks
- create webhook subscription
- list opportunities
- buyer intent signals for rhythm
slug: revenue-intelligence
source_filename: revenue-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Salesloft Revenue Intelligence\"\n  description: >-\n    Revenue intelligence workflow combining calls, conversations, signals, and\n    opportunities to provide pipeline visibility and AI-driven coaching insights.\n    Used by sales managers and revenue leaders to monitor deal health and rep performance.\n  tags:\n    - Revenue Intelligence\n    - Conversations\n    - Opportunities\n    - Signals\n    - Analytics\n    - Salesloft\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SALESLOFT_API_KEY: SALESLOFT_API_KEY\n\ncapability:\n  consumes:\n    - import: salesloft\n      location: ./shared/salesloft.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: revenue-intelligence-api\n      description: \"Unified REST API for Salesloft revenue intelligence and pipeline management.\"\n      resources:\n        - path: /v1/calls\n          name: calls\n        \
  \  description: \"Call recordings and outcomes\"\n          operations:\n            - method: GET\n              name: list-calls\n              description: \"List all calls\"\n              call: \"salesloft.list-calls\"\n              with:\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/opportunities\n          name: opportunities\n          description: \"Sales opportunities and pipeline\"\n          operations:\n            - method: GET\n              name: list-opportunities\n              description: \"List all opportunities\"\n              call: \"salesloft.list-opportunities\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/opportunities/{id}\n          name: opportunity-by-id\n          description: \"Single opportunity\"\n          operations:\n            - method: GET\n              name:\
  \ fetch-opportunity\n              description: \"Get opportunity by ID\"\n              call: \"salesloft.fetch-opportunity\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/signals\n          name: signals\n          description: \"Buyer intent signals for Rhythm\"\n          operations:\n            - method: POST\n              name: create-signal\n              description: \"Submit a buyer signal to Rhythm\"\n              call: \"salesloft.create-signal\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/emails\n          name: emails\n          description: \"Email activity tracking\"\n          operations:\n            - method: GET\n              name: list-emails\n              description: \"List all emails\"\n              call: \"salesloft.list-emails\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tasks\n          name: tasks\n          description: \"Tasks and follow-ups\"\n          operations:\n            - method: GET\n              name: list-tasks\n              description: \"List all tasks\"\n              call: \"salesloft.list-tasks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-task\n              description: \"Create a follow-up task\"\n              call: \"salesloft.create-task\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/users\n          name: users\n          description: \"Sales team users\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List all users\"\n              call: \"salesloft.list-users\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: revenue-intelligence-mcp\n      transport: http\n      description: \"MCP server for AI-assisted revenue intelligence and pipeline management.\"\n      tools:\n        - name: list-calls\n          description: \"List call recordings and outcomes from Salesloft\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesloft.list-calls\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-opportunities\n          description: \"List sales opportunities and pipeline in Salesloft\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesloft.list-opportunities\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: fetch-opportunity\n          description: \"Get details for\
  \ a specific opportunity\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesloft.fetch-opportunity\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: submit-buyer-signal\n          description: \"Submit a buyer intent signal to Salesloft Rhythm to prioritize follow-up\"\n          hints:\n            readOnly: false\n          call: \"salesloft.create-signal\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-emails\n          description: \"List emails sent through Salesloft for activity tracking\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesloft.list-emails\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-tasks\n          description: \"List pending sales\
  \ tasks and follow-ups\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesloft.list-tasks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-task\n          description: \"Create a follow-up task for a sales rep\"\n          hints:\n            readOnly: false\n          call: \"salesloft.create-task\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-users\n          description: \"List sales team members in Salesloft\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesloft.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-webhook-subscriptions\n          description: \"List webhook subscriptions for Salesloft event notifications\"\n          hints:\n            readOnly: true\n        \
  \    idempotent: true\n          call: \"salesloft.list-webhook-subscriptions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-webhook-subscription\n          description: \"Create a webhook subscription to receive Salesloft events\"\n          hints:\n            readOnly: false\n          call: \"salesloft.create-webhook-subscription\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/salesloft/refs/heads/main/capabilities/revenue-intelligence.yaml
tags:
- Revenue Intelligence
- Conversations
- Opportunities
- Signals
- Analytics
- Salesloft
tools:
- description: List call recordings and outcomes from Salesloft
  hints:
    idempotent: true
    readOnly: true
  name: list-calls
- description: List sales opportunities and pipeline in Salesloft
  hints:
    idempotent: true
    readOnly: true
  name: list-opportunities
- description: Get details for a specific opportunity
  hints:
    idempotent: true
    readOnly: true
  name: fetch-opportunity
- description: Submit a buyer intent signal to Salesloft Rhythm to prioritize follow-up
  hints:
    readOnly: false
  name: submit-buyer-signal
- description: List emails sent through Salesloft for activity tracking
  hints:
    idempotent: true
    readOnly: true
  name: list-emails
- description: List pending sales tasks and follow-ups
  hints:
    idempotent: true
    readOnly: true
  name: list-tasks
- description: Create a follow-up task for a sales rep
  hints:
    readOnly: false
  name: create-task
- description: List sales team members in Salesloft
  hints:
    idempotent: true
    readOnly: true
  name: list-users
- description: List webhook subscriptions for Salesloft event notifications
  hints:
    idempotent: true
    readOnly: true
  name: list-webhook-subscriptions
- description: Create a webhook subscription to receive Salesloft events
  hints:
    readOnly: false
  name: create-webhook-subscription
---
