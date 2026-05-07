---
categories: []
consumed_apis: []
description: The Global Relay Conversation Archiving API provides a RESTful interface to seamlessly integrate messaging platforms with the Global Relay Archive. It enables secure capture and preservation of one-to-one or multi-party conversations, including text messages, file attachments, reactions, edits, and deletions. The API supports all conversation events and provides guardrails and flexibility to efficiently automate the archiving process and meet compliance requirements. Authentication uses the Client Credentials OAuth 2.0 grant type with Bearer tokens.
layout: capability
name: Global Relay Conversation Archiving API
operations:
- description: Global Relay Archive a conversation
  method: POST
  name: archiveconversation
  path: /conversations
- description: Global Relay Upload a file attachment
  method: POST
  name: uploadfile
  path: /files
personas: []
provider_name: Global Relay
provider_slug: global-relay
search_terms:
- archiveconversation
- relay
- global
- compliance
- global relay upload a file attachment
- email security
- global relay archive a conversation
- uploadfile
- archiving
- data retention
- api
- regulatory compliance
slug: global-relay-capability
source_filename: global-relay-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Global Relay Conversation Archiving API\n  description: The Global Relay Conversation Archiving API provides a RESTful interface to seamlessly integrate messaging\n    platforms with the Global Relay Archive. It enables secure capture and preservation of one-to-one or multi-party conversations,\n    including text messages, file attachments, reactions, edits, and deletions. The API supports all conversation events and\n    provides guardrails and flexibility to efficiently automate the archiving process and meet compliance requirements. Authentication\n    uses the Client Credentials OAuth 2.0 grant type with Bearer tokens.\n  tags:\n  - Global\n  - Relay\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: global-relay\n    baseUri: https://conversations.api.globalrelay.com/v2\n    description: Global Relay Conversation Archiving API HTTP API.\n    authentication:\n    \
  \  type: bearer\n      token: '{{GLOBAL_RELAY_TOKEN}}'\n    resources:\n    - name: conversations\n      path: /conversations\n      operations:\n      - name: archiveconversation\n        method: POST\n        description: Global Relay Archive a conversation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: files\n      path: /files\n      operations:\n      - name: uploadfile\n        method: POST\n        description: Global Relay Upload a file attachment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: global-relay-rest\n    description: REST adapter for Global Relay Conversation Archiving API.\n    resources:\n    - path: /conversations\n      name: archiveconversation\n      operations:\n      - method: POST\n        name: archiveconversation\n        description:\
  \ Global Relay Archive a conversation\n        call: global-relay.archiveconversation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /files\n      name: uploadfile\n      operations:\n      - method: POST\n        name: uploadfile\n        description: Global Relay Upload a file attachment\n        call: global-relay.uploadfile\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: global-relay-mcp\n    transport: http\n    description: MCP adapter for Global Relay Conversation Archiving API for AI agent use.\n    tools:\n    - name: archiveconversation\n      description: Global Relay Archive a conversation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: global-relay.archiveconversation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: uploadfile\n      description: Global Relay Upload a file\
  \ attachment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: global-relay.uploadfile\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GLOBAL_RELAY_TOKEN: GLOBAL_RELAY_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/global-relay/refs/heads/main/capabilities/global-relay-capability.yaml
tags:
- Global
- Relay
- API
tools:
- description: Global Relay Archive a conversation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: archiveconversation
- description: Global Relay Upload a file attachment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploadfile
---
