---
api_specs:
- filename: interaction-hub.yml
  format: yaml
  label: interaction-hub
  slug: interaction-hub
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/openapi/interaction-hub.yml
- filename: notification-framework.yml
  format: yaml
  label: notification-framework
  slug: notification-framework
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/openapi/notification-framework.yml
- filename: chatbot-integration.yml
  format: yaml
  label: chatbot
  slug: chatbot
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/openapi/chatbot-integration.yml
categories:
- messaging
consumed_apis:
- interaction-hub
- notification-framework
- chatbot
description: Unified workflow for content managers combining portal content management, branding, chatbot integration, and notification services across PeopleSoft Interaction Hub, Chatbot Integration, and Notification Framework APIs.
layout: capability
name: PeopleSoft Portal And Communications
operations:
- description: Retrieve portal content items.
  method: GET
  name: list-content
  path: /v1/content
- description: Create a new portal content item.
  method: POST
  name: create-content
  path: /v1/content
- description: Retrieve available branding themes.
  method: GET
  name: list-themes
  path: /v1/themes
- description: Retrieve notifications for the current user.
  method: GET
  name: list-notifications
  path: /v1/notifications
- description: Send a notification via email, text, or in-app channels.
  method: POST
  name: send-notification
  path: /v1/notifications
- description: Retrieve available chatbot intents.
  method: GET
  name: list-intents
  path: /v1/intents
- description: Process a chatbot intent fulfillment request.
  method: POST
  name: fulfill-intent
  path: /v1/intent-fulfillments
personas: []
provider_name: PeopleSoft
provider_slug: peoplesoft
search_terms:
- notifications
- financial management
- create a new portal content item.
- list content
- branding themes
- list intents
- chatbot
- erp
- portal
- create content
- campus solutions
- enterprise software
- crm
- send a notification via email, text, or in-app channels.
- human capital management.
- send notification
- portal content items
- list themes
- supply chain management
- fulfill intent
- hcm
- campus solutions.
- retrieve notifications for the current user.
- peoplesoft
- retrieve available chatbot intents.
- content management
- list notifications
- chatbot intents
- communications
- retrieve available branding themes.
- chatbot intent fulfillments
- retrieve portal content items.
- financial and supply chain management.
- peopletools platform services.
- notification management
- process a chatbot intent fulfillment request.
slug: portal-and-communications
source_filename: portal-and-communications.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"PeopleSoft Portal And Communications\"\n  description: \"Unified workflow for content managers combining portal content management, branding, chatbot integration, and notification services across PeopleSoft Interaction Hub, Chatbot Integration, and Notification Framework APIs.\"\n  tags:\n    - PeopleSoft\n    - Portal\n    - Content Management\n    - Communications\n    - Notifications\n    - Chatbot\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      PEOPLESOFT_USERNAME: PEOPLESOFT_USERNAME\n      PEOPLESOFT_PASSWORD: PEOPLESOFT_PASSWORD\n\ncapability:\n  consumes:\n    - import: interaction-hub\n      location: ./shared/interaction-hub.yaml\n    - import: notification-framework\n      location: ./shared/notification-framework.yaml\n    - import: chatbot\n      location: ./shared/chatbot-integration.yaml\n\n  exposes:\n    - type: rest\n      port: 8087\n      namespace: portal-api\n\
  \      description: \"Unified REST API for PeopleSoft portal and communications workflows.\"\n      resources:\n        - path: /v1/content\n          name: content\n          description: \"Portal content items\"\n          operations:\n            - method: GET\n              name: list-content\n              description: \"Retrieve portal content items.\"\n              call: \"interaction-hub.list-content\"\n              with:\n                category: \"rest.category\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-content\n              description: \"Create a new portal content item.\"\n              call: \"interaction-hub.create-content\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/themes\n          name: themes\n          description: \"Branding themes\"\n          operations:\n            -\
  \ method: GET\n              name: list-themes\n              description: \"Retrieve available branding themes.\"\n              call: \"interaction-hub.list-themes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/notifications\n          name: notifications\n          description: \"Notification management\"\n          operations:\n            - method: GET\n              name: list-notifications\n              description: \"Retrieve notifications for the current user.\"\n              call: \"notification-framework.list-notifications\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: send-notification\n              description: \"Send a notification via email, text, or in-app channels.\"\n              call: \"notification-framework.send-notification\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n        - path: /v1/intents\n          name: intents\n          description: \"Chatbot intents\"\n          operations:\n            - method: GET\n              name: list-intents\n              description: \"Retrieve available chatbot intents.\"\n              call: \"chatbot.list-intents\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/intent-fulfillments\n          name: fulfillments\n          description: \"Chatbot intent fulfillments\"\n          operations:\n            - method: POST\n              name: fulfill-intent\n              description: \"Process a chatbot intent fulfillment request.\"\n              call: \"chatbot.fulfill-intent\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9097\n      namespace: portal-mcp\n      transport: http\n      description: \"MCP server\
  \ for AI-assisted PeopleSoft portal and communications workflows.\"\n      tools:\n        - name: list-content\n          description: \"Retrieve portal content items.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"interaction-hub.list-content\"\n          with:\n            category: \"tools.category\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-content\n          description: \"Create a new portal content item.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"interaction-hub.create-content\"\n          with:\n            title: \"tools.title\"\n            body: \"tools.body\"\n            category: \"tools.category\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-themes\n          description: \"Retrieve available branding themes.\"\
  \n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"interaction-hub.list-themes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-notifications\n          description: \"Retrieve notifications for the current user.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"notification-framework.list-notifications\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-notification\n          description: \"Send a notification via email, text, or in-app channels.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"notification-framework.send-notification\"\n          with:\n            channel: \"tools.channel\"\n            recipients: \"tools.recipients\"\n            message: \"tools.message\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: list-intents\n          description: \"Retrieve available chatbot intents.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"chatbot.list-intents\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: fulfill-intent\n          description: \"Process a chatbot intent fulfillment request.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"chatbot.fulfill-intent\"\n          with:\n            intent: \"tools.intent\"\n            parameters: \"tools.parameters\"\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/peoplesoft/refs/heads/main/capabilities/portal-and-communications.yaml
tags:
- PeopleSoft
- Portal
- Content Management
- Communications
- Notifications
- Chatbot
tools:
- description: Retrieve portal content items.
  hints:
    openWorld: true
    readOnly: true
  name: list-content
- description: Create a new portal content item.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-content
- description: Retrieve available branding themes.
  hints:
    openWorld: true
    readOnly: true
  name: list-themes
- description: Retrieve notifications for the current user.
  hints:
    openWorld: true
    readOnly: true
  name: list-notifications
- description: Send a notification via email, text, or in-app channels.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: send-notification
- description: Retrieve available chatbot intents.
  hints:
    openWorld: true
    readOnly: true
  name: list-intents
- description: Process a chatbot intent fulfillment request.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: fulfill-intent
---
