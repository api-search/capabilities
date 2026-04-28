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
- open a view.
- list workflows
- api test
- messaging
- team communication
- workflow management.
- complete function
- connect to real-time messaging.
- get bot info
- app development
- list apps.
- slack
- manage workflows
- open dialog
- manage calls
- app management.
- manage voice/video calls.
- productivity
- manage ai assistant threads.
- complete a workflow function.
- manage assistant
- bots
- open a dialog.
- rtm connect
- get bot information.
- collaboration
- list apps
- manage workflows.
- view management.
- test api connectivity.
- t1
- open view
- platform
- list workflows.
- list installed apps.
- chat
- automation
- open a modal view.
slug: app-platform
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
