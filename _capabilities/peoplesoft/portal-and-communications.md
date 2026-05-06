---
categories:
- messaging
consumed_apis: []
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
- portal
- supply chain management
- portal content items
- branding themes
- peopletools platform services.
- list notifications
- peoplesoft
- chatbot intents
- retrieve available chatbot intents.
- campus solutions.
- fulfill intent
- financial and supply chain management.
- content management
- list intents
- human capital management.
- chatbot
- erp
- send notification
- financial management
- crm
- retrieve portal content items.
- list themes
- notification management
- hcm
- retrieve notifications for the current user.
- notifications
- list content
- campus solutions
- enterprise software
- create content
- process a chatbot intent fulfillment request.
- chatbot intent fulfillments
- retrieve available branding themes.
- send a notification via email, text, or in-app channels.
- create a new portal content item.
- communications
slug: portal-and-communications
source_filename: portal-and-communications.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: PeopleSoft Portal And Communications\n  description: Unified workflow for content managers combining portal content management, branding, chatbot integration, and\n    notification services across PeopleSoft Interaction Hub, Chatbot Integration, and Notification Framework APIs.\n  tags:\n  - PeopleSoft\n  - Portal\n  - Content Management\n  - Communications\n  - Notifications\n  - Chatbot\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    PEOPLESOFT_USERNAME: PEOPLESOFT_USERNAME\n    PEOPLESOFT_PASSWORD: PEOPLESOFT_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: interaction-hub\n    baseUri: https://${PEOPLESOFT_HOST}:${PEOPLESOFT_PORT}/psft/api/hub/v1\n    description: PeopleSoft Interaction Hub API\n    authentication:\n      type: basic\n      username: '{{PEOPLESOFT_USERNAME}}'\n      password: '{{PEOPLESOFT_PASSWORD}}'\n    resources:\n    - name: content\n      path: /content\n\
  \      description: Content management operations\n      operations:\n      - name: list-content\n        method: GET\n        description: Retrieve portal content items.\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Content category filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-content\n        method: POST\n        description: Create a new portal content item.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            body: '{{tools.body}}'\n            category: '{{tools.category}}'\n    - name: branding\n      path: /branding\n      description: Branding and theme operations\n      operations:\n      -\
  \ name: list-themes\n        method: GET\n        description: Retrieve available branding themes.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: notification-framework\n    baseUri: https://${PEOPLESOFT_HOST}:${PEOPLESOFT_PORT}/psft/api/notifications/v1\n    description: PeopleSoft Notification Framework API\n    authentication:\n      type: basic\n      username: '{{PEOPLESOFT_USERNAME}}'\n      password: '{{PEOPLESOFT_PASSWORD}}'\n    resources:\n    - name: notifications\n      path: /notifications\n      description: Notification management operations\n      operations:\n      - name: list-notifications\n        method: GET\n        description: Retrieve a list of notifications for the current user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: send-notification\n        method:\
  \ POST\n        description: Send a notification via email, text, or in-app channels.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            channel: '{{tools.channel}}'\n            recipients: '{{tools.recipients}}'\n            message: '{{tools.message}}'\n  - type: http\n    namespace: chatbot\n    baseUri: https://${PEOPLESOFT_HOST}:${PEOPLESOFT_PORT}/psft/api/chatbot/v1\n    description: PeopleSoft Chatbot Integration Framework API\n    authentication:\n      type: basic\n      username: '{{PEOPLESOFT_USERNAME}}'\n      password: '{{PEOPLESOFT_PASSWORD}}'\n    resources:\n    - name: intents\n      path: /\n      description: Chatbot integration operations\n      operations:\n      - name: list-intents\n        method: GET\n        description: Retrieve available chatbot intents and their configurations.\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: fulfill-intent\n        method: POST\n        description: Process a chatbot intent fulfillment request from Oracle Digital Assistant.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            intent: '{{tools.intent}}'\n            parameters: '{{tools.parameters}}'\n            userId: '{{tools.userId}}'\n  exposes:\n  - type: rest\n    port: 8087\n    namespace: portal-api\n    description: Unified REST API for PeopleSoft portal and communications workflows.\n    resources:\n    - path: /v1/content\n      name: content\n      description: Portal content items\n      operations:\n      - method: GET\n        name: list-content\n        description: Retrieve portal content items.\n        call: interaction-hub.list-content\n        with:\n       \
  \   category: rest.category\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-content\n        description: Create a new portal content item.\n        call: interaction-hub.create-content\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/themes\n      name: themes\n      description: Branding themes\n      operations:\n      - method: GET\n        name: list-themes\n        description: Retrieve available branding themes.\n        call: interaction-hub.list-themes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/notifications\n      name: notifications\n      description: Notification management\n      operations:\n      - method: GET\n        name: list-notifications\n        description: Retrieve notifications for the current user.\n        call: notification-framework.list-notifications\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n      - method: POST\n        name: send-notification\n        description: Send a notification via email, text, or in-app channels.\n        call: notification-framework.send-notification\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/intents\n      name: intents\n      description: Chatbot intents\n      operations:\n      - method: GET\n        name: list-intents\n        description: Retrieve available chatbot intents.\n        call: chatbot.list-intents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/intent-fulfillments\n      name: fulfillments\n      description: Chatbot intent fulfillments\n      operations:\n      - method: POST\n        name: fulfill-intent\n        description: Process a chatbot intent fulfillment request.\n        call: chatbot.fulfill-intent\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9097\n\
  \    namespace: portal-mcp\n    transport: http\n    description: MCP server for AI-assisted PeopleSoft portal and communications workflows.\n    tools:\n    - name: list-content\n      description: Retrieve portal content items.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: interaction-hub.list-content\n      with:\n        category: tools.category\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-content\n      description: Create a new portal content item.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: interaction-hub.create-content\n      with:\n        title: tools.title\n        body: tools.body\n        category: tools.category\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-themes\n      description: Retrieve available branding themes.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: interaction-hub.list-themes\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-notifications\n      description: Retrieve notifications for the current user.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: notification-framework.list-notifications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-notification\n      description: Send a notification via email, text, or in-app channels.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: notification-framework.send-notification\n      with:\n        channel: tools.channel\n        recipients: tools.recipients\n        message: tools.message\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-intents\n      description: Retrieve available chatbot intents.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: chatbot.list-intents\n      outputParameters:\n    \
  \  - type: object\n        mapping: $.\n    - name: fulfill-intent\n      description: Process a chatbot intent fulfillment request.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: chatbot.fulfill-intent\n      with:\n        intent: tools.intent\n        parameters: tools.parameters\n        userId: tools.userId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
