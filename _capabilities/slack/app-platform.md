---
categories: []
consumed_apis:
- slack-apps
- slack-views
- slack-dialog
- slack-bots
- slack-functions
- slack-workflows
- slack-calls
- slack-rtm
- slack-assistant
- slack-tests
description: Unified workflow for building Slack apps including app management, interactive views, dialogs, bots, workflow functions, calls, and real-time messaging. Used by platform developers building Slack integrations.
layout: capability
name: Slack App Platform
operations:
- description: List apps.
  method: GET
  name: list-apps
  path: /v1/apps
- description: Open a view.
  method: POST
  name: open-view
  path: /v1/views
- description: List workflows.
  method: GET
  name: list-workflows
  path: /v1/workflows
personas: []
provider_name: Slack
provider_slug: slack
search_terms:
- app development
- list apps.
- complete function
- workflow management.
- list installed apps.
- t1
- automation
- get bot information.
- collaboration
- list workflows.
- app management.
- rtm connect
- connect to real-time messaging.
- manage workflows.
- team communication
- chat
- list workflows
- api test
- open view
- test api connectivity.
- manage calls
- manage voice/video calls.
- complete a workflow function.
- view management.
- open a modal view.
- platform
- open dialog
- manage assistant
- get bot info
- slack
- open a view.
- productivity
- list apps
- open a dialog.
- manage ai assistant threads.
- manage workflows
- bots
- messaging
slug: app-platform
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Slack App Platform\"\n  description: \"Unified workflow for building Slack apps including app management, interactive views, dialogs, bots, workflow functions, calls, and real-time messaging. Used by platform developers building Slack integrations.\"\n  tags:\n    - Slack\n    - App Development\n    - Platform\n    - Automation\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SLACK_BOT_TOKEN: SLACK_BOT_TOKEN\n\ncapability:\n  consumes:\n    - import: slack-apps\n      location: ./shared/apps.yaml\n    - import: slack-views\n      location: ./shared/views.yaml\n    - import: slack-dialog\n      location: ./shared/dialog.yaml\n    - import: slack-bots\n      location: ./shared/bots.yaml\n    - import: slack-functions\n      location: ./shared/functions.yaml\n    - import: slack-workflows\n      location: ./shared/workflows.yaml\n    - import: slack-calls\n      location: ./shared/calls.yaml\n\
  \    - import: slack-rtm\n      location: ./shared/rtm.yaml\n    - import: slack-assistant\n      location: ./shared/assistant.yaml\n    - import: slack-tests\n      location: ./shared/test-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: app-platform-api\n      description: \"Unified REST API for Slack app platform.\"\n      resources:\n        - path: /v1/apps\n          name: apps\n          description: \"App management.\"\n          operations:\n            - method: GET\n              name: list-apps\n              description: \"List apps.\"\n              call: \"slack-apps.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/views\n          name: views\n          description: \"View management.\"\n          operations:\n            - method: POST\n              name: open-view\n              description: \"Open a view.\"\n              call: \"slack-views.list\"\n          \
  \    outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workflows\n          name: workflows\n          description: \"Workflow management.\"\n          operations:\n            - method: GET\n              name: list-workflows\n              description: \"List workflows.\"\n              call: \"slack-workflows.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9082\n      namespace: app-platform-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Slack app development.\"\n      tools:\n        - name: list-apps\n          description: \"List installed apps.\"\n          hints:\n            readOnly: true\n          call: \"slack-apps.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: open-view\n          description: \"Open a modal view.\"\n          hints:\n\
  \            readOnly: false\n          call: \"slack-views.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: open-dialog\n          description: \"Open a dialog.\"\n          hints:\n            readOnly: false\n          call: \"slack-dialog.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-bot-info\n          description: \"Get bot information.\"\n          hints:\n            readOnly: true\n          call: \"slack-bots.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: complete-function\n          description: \"Complete a workflow function.\"\n          hints:\n            readOnly: false\n          call: \"slack-functions.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: manage-workflows\n          description: \"Manage workflows.\"\
  \n          hints:\n            readOnly: false\n          call: \"slack-workflows.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: manage-calls\n          description: \"Manage voice/video calls.\"\n          hints:\n            readOnly: false\n          call: \"slack-calls.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: rtm-connect\n          description: \"Connect to Real-Time Messaging.\"\n          hints:\n            readOnly: true\n          call: \"slack-rtm.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: manage-assistant\n          description: \"Manage AI assistant threads.\"\n          hints:\n            readOnly: false\n          call: \"slack-assistant.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: api-test\n          description:\
  \ \"Test API connectivity.\"\n          hints:\n            readOnly: true\n          call: \"slack-tests.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/slack/refs/heads/main/capabilities/app-platform.yaml
tags:
- Slack
- App Development
- Platform
- Automation
tools:
- description: List installed apps.
  hints:
    readOnly: true
  name: list-apps
- description: Open a modal view.
  hints:
    readOnly: false
  name: open-view
- description: Open a dialog.
  hints:
    readOnly: false
  name: open-dialog
- description: Get bot information.
  hints:
    readOnly: true
  name: get-bot-info
- description: Complete a workflow function.
  hints:
    readOnly: false
  name: complete-function
- description: Manage workflows.
  hints:
    readOnly: false
  name: manage-workflows
- description: Manage voice/video calls.
  hints:
    readOnly: false
  name: manage-calls
- description: Connect to Real-Time Messaging.
  hints:
    readOnly: true
  name: rtm-connect
- description: Manage AI assistant threads.
  hints:
    readOnly: false
  name: manage-assistant
- description: Test API connectivity.
  hints:
    readOnly: true
  name: api-test
---
