---
categories: []
consumed_apis: []
description: SEMrush is an all-in-one digital marketing tool that helps businesses improve their online visibility and attract more customers. This powerful software provides a range of tools and features for keyword research, website analysis, competitive analysis, and more. With SEMrush, businesses can track their online rankings, discover new keywords to target, analyze their competitors' strategies, and optimize their website for better search engine performance. Overall, SEMrush is a essential tool for any business looking to succeed in the competitive world of online marketing.
layout: capability
name: Semrush
operations:
- description: Semrush Request API access token
  method: POST
  name: post-app-center-api-v2-jwt-token
  path: /app-center-api/v2/jwt-token/
- description: Semrush User status
  method: POST
  name: post-apis-v4-app-center-v2-partner-viewer-status
  path: /apis/v4/app-center/v2/partner/viewer-status
- description: Semrush Get available subscriptions
  method: GET
  name: get-apis-v4-hermes-v0-subscriptions
  path: /apis/v4/hermes/v0/subscriptions
- description: Semrush Get user's subscription status
  method: GET
  name: get-apis-v4-hermes-v0-user-user-id-subscription-
  path: /apis/v4/hermes/v0/user/{user_id}/subscription/{id}
- description: Semrush Send notification
  method: POST
  name: post-apis-v4-hermes-v0-event
  path: /apis/v4/hermes/v0/event
- description: Semrush Get event status
  method: GET
  name: get-apis-v4-hermes-v0-event-id
  path: /apis/v4/hermes/v0/event/{id}
personas: []
provider_name: Semrush
provider_slug: semrush
search_terms:
- api
- semrush user status
- semrush send notification
- post apis v4 app center v2 partner viewer status
- semrush get available subscriptions
- get apis v4 hermes v0 user user id subscription
- post apis v4 hermes v0 event
- data
- search engines
- semrush
- semrush get user's subscription status
- semrush request api access token
- get apis v4 hermes v0 subscriptions
- get apis v4 hermes v0 event id
- semrush get event status
- post app center api v2 jwt token
slug: semrush-capability
source_filename: semrush-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Semrush\n  description: SEMrush is an all-in-one digital marketing tool that helps businesses improve their online visibility and attract\n    more customers. This powerful software provides a range of tools and features for keyword research, website analysis,\n    competitive analysis, and more. With SEMrush, businesses can track their online rankings, discover new keywords to target,\n    analyze their competitors' strategies, and optimize their website for better search engine performance. Overall, SEMrush\n    is a essential tool for any business looking to succeed in the competitive world of online marketing.\n  tags:\n  - Semrush\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: semrush\n    baseUri: https://api.semrush.com\n    description: Semrush HTTP API.\n    authentication:\n      type: bearer\n      token: '{{SEMRUSH_TOKEN}}'\n    resources:\n    - name: app-center-api-v2-jwt-token\n\
  \      path: /app-center-api/v2/jwt-token/\n      operations:\n      - name: post-app-center-api-v2-jwt-token\n        method: POST\n        description: Semrush Request API access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-v4-app-center-v2-partner-viewer-status\n      path: /apis/v4/app-center/v2/partner/viewer-status\n      operations:\n      - name: post-apis-v4-app-center-v2-partner-viewer-status\n        method: POST\n        description: Semrush User status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-v4-hermes-v0-subscriptions\n      path: /apis/v4/hermes/v0/subscriptions\n      operations:\n      - name: get-apis-v4-hermes-v0-subscriptions\n        method: GET\n        description: Semrush Get available subscriptions\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: apis-v4-hermes-v0-user-user-id-subscription-id\n      path: /apis/v4/hermes/v0/user/{user_id}/subscription/{id}\n      operations:\n      - name: get-apis-v4-hermes-v0-user-user-id-subscription-\n        method: GET\n        description: Semrush Get user's subscription status\n        inputParameters:\n        - name: user_id\n          in: path\n          type: integer\n          required: true\n          description: User id\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Subscription id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-v4-hermes-v0-event\n      path: /apis/v4/hermes/v0/event\n      operations:\n      - name: post-apis-v4-hermes-v0-event\n        method: POST\n        description: Semrush Send notification\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-v4-hermes-v0-event-id\n      path: /apis/v4/hermes/v0/event/{id}\n      operations:\n      - name: get-apis-v4-hermes-v0-event-id\n        method: GET\n        description: Semrush Get event status\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Subscription id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: semrush-rest\n    description: REST adapter for Semrush.\n    resources:\n    - path: /app-center-api/v2/jwt-token/\n      name: post-app-center-api-v2-jwt-token\n      operations:\n      - method: POST\n        name: post-app-center-api-v2-jwt-token\n        description: Semrush Request API access token\n        call: semrush.post-app-center-api-v2-jwt-token\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/v4/app-center/v2/partner/viewer-status\n      name: post-apis-v4-app-center-v2-partner-viewer-status\n      operations:\n      - method: POST\n        name: post-apis-v4-app-center-v2-partner-viewer-status\n        description: Semrush User status\n        call: semrush.post-apis-v4-app-center-v2-partner-viewer-status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/v4/hermes/v0/subscriptions\n      name: get-apis-v4-hermes-v0-subscriptions\n      operations:\n      - method: GET\n        name: get-apis-v4-hermes-v0-subscriptions\n        description: Semrush Get available subscriptions\n        call: semrush.get-apis-v4-hermes-v0-subscriptions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/v4/hermes/v0/user/{user_id}/subscription/{id}\n      name: get-apis-v4-hermes-v0-user-user-id-subscription\n      operations:\n\
  \      - method: GET\n        name: get-apis-v4-hermes-v0-user-user-id-subscription-\n        description: Semrush Get user's subscription status\n        call: semrush.get-apis-v4-hermes-v0-user-user-id-subscription-\n        with:\n          user_id: rest.user_id\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/v4/hermes/v0/event\n      name: post-apis-v4-hermes-v0-event\n      operations:\n      - method: POST\n        name: post-apis-v4-hermes-v0-event\n        description: Semrush Send notification\n        call: semrush.post-apis-v4-hermes-v0-event\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/v4/hermes/v0/event/{id}\n      name: get-apis-v4-hermes-v0-event-id\n      operations:\n      - method: GET\n        name: get-apis-v4-hermes-v0-event-id\n        description: Semrush Get event status\n        call: semrush.get-apis-v4-hermes-v0-event-id\n        with:\n       \
  \   id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: semrush-mcp\n    transport: http\n    description: MCP adapter for Semrush for AI agent use.\n    tools:\n    - name: post-app-center-api-v2-jwt-token\n      description: Semrush Request API access token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: semrush.post-app-center-api-v2-jwt-token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-apis-v4-app-center-v2-partner-viewer-status\n      description: Semrush User status\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: semrush.post-apis-v4-app-center-v2-partner-viewer-status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-apis-v4-hermes-v0-subscriptions\n      description: Semrush Get available subscriptions\n  \
  \    hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: semrush.get-apis-v4-hermes-v0-subscriptions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-apis-v4-hermes-v0-user-user-id-subscription-\n      description: Semrush Get user's subscription status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: semrush.get-apis-v4-hermes-v0-user-user-id-subscription-\n      with:\n        user_id: tools.user_id\n        id: tools.id\n      inputParameters:\n      - name: user_id\n        type: integer\n        description: User id\n        required: true\n      - name: id\n        type: integer\n        description: Subscription id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-apis-v4-hermes-v0-event\n      description: Semrush Send notification\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: semrush.post-apis-v4-hermes-v0-event\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-apis-v4-hermes-v0-event-id\n      description: Semrush Get event status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: semrush.get-apis-v4-hermes-v0-event-id\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: Subscription id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    SEMRUSH_TOKEN: SEMRUSH_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/semrush/refs/heads/main/capabilities/semrush-capability.yaml
tags:
- Semrush
- API
tools:
- description: Semrush Request API access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-app-center-api-v2-jwt-token
- description: Semrush User status
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-apis-v4-app-center-v2-partner-viewer-status
- description: Semrush Get available subscriptions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-apis-v4-hermes-v0-subscriptions
- description: Semrush Get user's subscription status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-apis-v4-hermes-v0-user-user-id-subscription-
- description: Semrush Send notification
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-apis-v4-hermes-v0-event
- description: Semrush Get event status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-apis-v4-hermes-v0-event-id
---
