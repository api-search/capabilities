---
categories: []
consumed_apis: []
description: A collection of CPaaS (communications platform) capabilities — SMS, voice, WhatsApp — exposed as MCP tools for agent flows.
layout: capability
name: Cpaas Mcp Collection
operations:
- description: ''
  method: POST
  name: send-sms
  path: /sms
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- governance
- list messages
- cpaas
- send sms
- twilio
- place call
- ai
- capabilities
- spec-driven integration
- api integration
- mcp
- naftiko
slug: cpaas-mcp-collection
source_filename: cpaas-mcp-collection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Cpaas Mcp Collection\n  description: A collection of CPaaS (communications platform) capabilities — SMS, voice, WhatsApp — exposed as MCP tools for agent flows.\n  tags: [Naftiko, CPaaS, Twilio]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: twilio-env\n  keys: {TWILIO_ACCOUNT_SID: TWILIO_ACCOUNT_SID, TWILIO_AUTH_TOKEN: TWILIO_AUTH_TOKEN}\ncapability:\n  consumes:\n  - namespace: twilio\n    type: http\n    baseUri: https://api.twilio.com\n    authentication: {type: basic, username: '{{TWILIO_ACCOUNT_SID}}', password: '{{TWILIO_AUTH_TOKEN}}'}\n    resources:\n    - {name: messages, path: '/2010-04-01/Accounts/{{TWILIO_ACCOUNT_SID}}/Messages.json', operations: [{name: send-sms, method: POST}, {name: list-messages, method: GET}]}\n    - {name: calls, path: '/2010-04-01/Accounts/{{TWILIO_ACCOUNT_SID}}/Calls.json', operations: [{name: place-call, method: POST}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n\
  \    port: 8080\n    namespace: cpaas-mcp-collection-rest\n    description: REST surface for CPaaS ops.\n    resources:\n    - {name: send-sms, path: /sms, operations: [{method: POST, name: send-sms, call: twilio.send-sms}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: cpaas-mcp-collection-mcp\n    description: MCP for CPaaS ops.\n    tools:\n    - {name: send-sms, call: twilio.send-sms}\n    - {name: place-call, call: twilio.place-call}\n    - {name: list-messages, hints: {readOnly: true}, call: twilio.list-messages}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: cpaas-mcp-collection-skills\n    description: Skill for CPaaS.\n    skills:\n    - name: cpaas-mcp-collection\n      description: CPaaS MCP collection (SMS, voice).\n      location: file:///opt/naftiko/skills/cpaas-mcp-collection\n      allowed-tools: send-sms,place-call,list-messages\n      tools:\n      - {name: send-sms, from: {sourceNamespace: cpaas-mcp-collection-mcp, action:\
  \ send-sms}}\n      - {name: place-call, from: {sourceNamespace: cpaas-mcp-collection-mcp, action: place-call}}\n      - {name: list-messages, from: {sourceNamespace: cpaas-mcp-collection-mcp, action: list-messages}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/cpaas-mcp-collection.yaml
tags:
- Naftiko
- CPaaS
- Twilio
tools:
- description: ''
  hints: {}
  name: send-sms
- description: ''
  hints: {}
  name: place-call
- description: ''
  hints:
    readOnly: true
  name: list-messages
---
