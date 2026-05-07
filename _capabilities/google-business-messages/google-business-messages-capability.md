---
categories: []
consumed_apis: []
description: The Google Business Messages API enables agents to send messages, create events, and manage customer satisfaction surveys within conversations. Allows businesses to communicate with customers directly through Google entry points.
layout: capability
name: Google Business Messages API
operations:
- description: Google Business Messages Create Message
  method: POST
  name: createmessage
  path: /conversations/{conversationId}/messages
- description: Google Business Messages Update Message Receipt
  method: PATCH
  name: updatereceipt
  path: /conversations/{conversationId}/messages/{messageId}:receiptUpdate
- description: Google Business Messages Create Event
  method: POST
  name: createevent
  path: /conversations/{conversationId}/events
- description: Google Business Messages Create Survey
  method: POST
  name: createsurvey
  path: /conversations/{conversationId}/surveys
personas: []
provider_name: Google Business Messages
provider_slug: google-business-messages
search_terms:
- createsurvey
- google business messages update message receipt
- business communications
- conversations
- google business messages create survey
- customer support
- google
- google business messages create event
- business
- messaging
- messages
- google business messages create message
- api
- createevent
- updatereceipt
- createmessage
slug: google-business-messages-capability
source_filename: google-business-messages-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Business Messages API\n  description: The Google Business Messages API enables agents to send messages, create events, and manage customer satisfaction\n    surveys within conversations. Allows businesses to communicate with customers directly through Google entry points.\n  tags:\n  - Google\n  - Business\n  - Messages\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-business-messages\n    baseUri: https://businessmessages.googleapis.com/v1\n    description: Google Business Messages API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_BUSINESS_MESSAGES_TOKEN}}'\n    resources:\n    - name: conversations-conversationid-messages\n      path: /conversations/{conversationId}/messages\n      operations:\n      - name: createmessage\n        method: POST\n        description: Google Business Messages Create Message\n        inputParameters:\n\
  \        - name: conversationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conversations-conversationid-messages-messageid-\n      path: /conversations/{conversationId}/messages/{messageId}:receiptUpdate\n      operations:\n      - name: updatereceipt\n        method: PATCH\n        description: Google Business Messages Update Message Receipt\n        inputParameters:\n        - name: conversationId\n          in: path\n          type: string\n          required: true\n        - name: messageId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conversations-conversationid-events\n      path: /conversations/{conversationId}/events\n      operations:\n      - name: createevent\n\
  \        method: POST\n        description: Google Business Messages Create Event\n        inputParameters:\n        - name: conversationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conversations-conversationid-surveys\n      path: /conversations/{conversationId}/surveys\n      operations:\n      - name: createsurvey\n        method: POST\n        description: Google Business Messages Create Survey\n        inputParameters:\n        - name: conversationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-business-messages-rest\n    description: REST adapter for Google Business Messages API.\n    resources:\n  \
  \  - path: /conversations/{conversationId}/messages\n      name: createmessage\n      operations:\n      - method: POST\n        name: createmessage\n        description: Google Business Messages Create Message\n        call: google-business-messages.createmessage\n        with:\n          conversationId: rest.conversationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /conversations/{conversationId}/messages/{messageId}:receiptUpdate\n      name: updatereceipt\n      operations:\n      - method: PATCH\n        name: updatereceipt\n        description: Google Business Messages Update Message Receipt\n        call: google-business-messages.updatereceipt\n        with:\n          conversationId: rest.conversationId\n          messageId: rest.messageId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /conversations/{conversationId}/events\n      name: createevent\n      operations:\n      - method: POST\n    \
  \    name: createevent\n        description: Google Business Messages Create Event\n        call: google-business-messages.createevent\n        with:\n          conversationId: rest.conversationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /conversations/{conversationId}/surveys\n      name: createsurvey\n      operations:\n      - method: POST\n        name: createsurvey\n        description: Google Business Messages Create Survey\n        call: google-business-messages.createsurvey\n        with:\n          conversationId: rest.conversationId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-business-messages-mcp\n    transport: http\n    description: MCP adapter for Google Business Messages API for AI agent use.\n    tools:\n    - name: createmessage\n      description: Google Business Messages Create Message\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: google-business-messages.createmessage\n      with:\n        conversationId: tools.conversationId\n      inputParameters:\n      - name: conversationId\n        type: string\n        description: conversationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatereceipt\n      description: Google Business Messages Update Message Receipt\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-business-messages.updatereceipt\n      with:\n        conversationId: tools.conversationId\n        messageId: tools.messageId\n      inputParameters:\n      - name: conversationId\n        type: string\n        description: conversationId\n        required: true\n      - name: messageId\n        type: string\n        description: messageId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n   \
  \ - name: createevent\n      description: Google Business Messages Create Event\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-business-messages.createevent\n      with:\n        conversationId: tools.conversationId\n      inputParameters:\n      - name: conversationId\n        type: string\n        description: conversationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsurvey\n      description: Google Business Messages Create Survey\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-business-messages.createsurvey\n      with:\n        conversationId: tools.conversationId\n      inputParameters:\n      - name: conversationId\n        type: string\n        description: conversationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace:\
  \ env\n  keys:\n    GOOGLE_BUSINESS_MESSAGES_TOKEN: GOOGLE_BUSINESS_MESSAGES_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-business-messages/refs/heads/main/capabilities/google-business-messages-capability.yaml
tags:
- Google
- Business
- Messages
- API
tools:
- description: Google Business Messages Create Message
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmessage
- description: Google Business Messages Update Message Receipt
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatereceipt
- description: Google Business Messages Create Event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createevent
- description: Google Business Messages Create Survey
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsurvey
---
