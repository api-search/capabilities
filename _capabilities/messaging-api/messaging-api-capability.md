---
categories: []
consumed_apis: []
description: This is a template APIs.json for a messages API, to be used in storytelling, training, and knowledge bases.
layout: capability
name: Messaging API Messages API
operations:
- description: Messaging API Retrieves Messages
  method: GET
  name: getmessages
  path: /messages
- description: Messaging API Create Message
  method: POST
  name: createmessage
  path: /messages
- description: Messaging API Retrieve Message
  method: GET
  name: getmessage
  path: /messages/{messageId}
- description: Messaging API Update Message
  method: PUT
  name: updatemessage
  path: /messages/{messageId}
- description: Messaging API Delete Message
  method: DELETE
  name: deletemessage
  path: /messages/{messageId}
- description: Messaging API Send Message
  method: PUT
  name: sendmessage
  path: /messages/{messageId}/send
personas: []
provider_name: Messaging API
provider_slug: messaging-api
search_terms:
- messaging api retrieve message
- template
- getmessages
- createmessage
- messaging
- getmessage
- messaging api update message
- updatemessage
- messaging api delete message
- messaging api send message
- api
- sendmessage
- messaging api retrieves messages
- deletemessage
- api pattern
- messaging api create message
slug: messaging-api-capability
source_filename: messaging-api-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Messaging API Messages API\n  description: This is a template APIs.json for a messages API, to be used in storytelling, training, and knowledge bases.\n  tags:\n  - Messaging\n  - Api\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: messaging-api\n    baseUri: https://api.example.com\n    description: Messaging API Messages API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: api-key\n      value: '{{MESSAGING_API_TOKEN}}'\n    resources:\n    - name: messages\n      path: /messages\n      operations:\n      - name: getmessages\n        method: GET\n        description: Messaging API Retrieves Messages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createmessage\n        method: POST\n        description: Messaging API Create Message\n      \
  \  outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: messages-messageid\n      path: /messages/{messageId}\n      operations:\n      - name: getmessage\n        method: GET\n        description: Messaging API Retrieve Message\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatemessage\n        method: PUT\n        description: Messaging API Update Message\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemessage\n        method: DELETE\n        description: Messaging API Delete Message\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: messages-messageid-send\n      path: /messages/{messageId}/send\n      operations:\n      - name:\
  \ sendmessage\n        method: PUT\n        description: Messaging API Send Message\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: messaging-api-rest\n    description: REST adapter for Messaging API Messages API.\n    resources:\n    - path: /messages\n      name: getmessages\n      operations:\n      - method: GET\n        name: getmessages\n        description: Messaging API Retrieves Messages\n        call: messaging-api.getmessages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /messages\n      name: createmessage\n      operations:\n      - method: POST\n        name: createmessage\n        description: Messaging API Create Message\n        call: messaging-api.createmessage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /messages/{messageId}\n      name: getmessage\n\
  \      operations:\n      - method: GET\n        name: getmessage\n        description: Messaging API Retrieve Message\n        call: messaging-api.getmessage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /messages/{messageId}\n      name: updatemessage\n      operations:\n      - method: PUT\n        name: updatemessage\n        description: Messaging API Update Message\n        call: messaging-api.updatemessage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /messages/{messageId}\n      name: deletemessage\n      operations:\n      - method: DELETE\n        name: deletemessage\n        description: Messaging API Delete Message\n        call: messaging-api.deletemessage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /messages/{messageId}/send\n      name: sendmessage\n      operations:\n      - method: PUT\n        name: sendmessage\n        description: Messaging API\
  \ Send Message\n        call: messaging-api.sendmessage\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: messaging-api-mcp\n    transport: http\n    description: MCP adapter for Messaging API Messages API for AI agent use.\n    tools:\n    - name: getmessages\n      description: Messaging API Retrieves Messages\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: messaging-api.getmessages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createmessage\n      description: Messaging API Create Message\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: messaging-api.createmessage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmessage\n      description: Messaging API Retrieve Message\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: messaging-api.getmessage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatemessage\n      description: Messaging API Update Message\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: messaging-api.updatemessage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletemessage\n      description: Messaging API Delete Message\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: messaging-api.deletemessage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sendmessage\n      description: Messaging API Send Message\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: messaging-api.sendmessage\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MESSAGING_API_TOKEN:\
  \ MESSAGING_API_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/messaging-api/refs/heads/main/capabilities/messaging-api-capability.yaml
tags:
- Messaging
- Api
- API
tools:
- description: Messaging API Retrieves Messages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmessages
- description: Messaging API Create Message
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmessage
- description: Messaging API Retrieve Message
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmessage
- description: Messaging API Update Message
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatemessage
- description: Messaging API Delete Message
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemessage
- description: Messaging API Send Message
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: sendmessage
---
