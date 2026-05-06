---
categories: []
consumed_apis: []
description: A Microsoft 365 capability over Microsoft Graph that exposes a shaped subset of M365 data for AI agents (Copilot, ADK).
layout: capability
name: M365 Sharepoint Document Rightsize Capability
operations:
- description: ''
  method: GET
  name: get-me
  path: /me
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- get me
- list events
- microsoft 365
- list messages
- graph
- api integration
- governance
- capabilities
- spec-driven integration
- ai
- list drive items
- mcp
- list chats
slug: m365-sharepoint-document-rightsize-capability
source_filename: m365-sharepoint-document-rightsize-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: M365 Sharepoint Document Rightsize Capability\n  description: A Microsoft 365 capability over Microsoft Graph that exposes a shaped subset of M365 data for AI agents (Copilot, ADK).\n  tags: [Naftiko, Microsoft 365, Graph]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: msgraph-env\n  description: Microsoft Graph OAuth bearer (delegated or app-only).\n  keys: {MSGRAPH_TOKEN: MSGRAPH_TOKEN}\ncapability:\n  consumes:\n  - namespace: msgraph\n    type: http\n    baseUri: https://graph.microsoft.com\n    authentication: {type: bearer, token: '{{MSGRAPH_TOKEN}}'}\n    resources:\n    - {name: me, path: /v1.0/me, operations: [{name: get-me, method: GET}]}\n    - {name: messages, path: /v1.0/me/messages, operations: [{name: list-messages, method: GET}]}\n    - {name: events, path: /v1.0/me/events, operations: [{name: list-events, method: GET}]}\n    - {name: chats, path: /v1.0/me/chats, operations: [{name: list-chats,\
  \ method: GET}]}\n    - {name: drive-items, path: /v1.0/me/drive/root/children, operations: [{name: list-drive-items, method: GET}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: m365-sharepoint-document-rightsize-capability-rest\n    description: REST surface over a shaped Microsoft Graph subset.\n    resources:\n    - {name: me, path: /me, operations: [{method: GET, name: get-me, call: msgraph.get-me}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: m365-sharepoint-document-rightsize-capability-mcp\n    description: MCP for shaped M365 access.\n    tools:\n    - {name: get-me, hints: {readOnly: true}, call: msgraph.get-me}\n    - {name: list-messages, hints: {readOnly: true}, call: msgraph.list-messages}\n    - {name: list-events, hints: {readOnly: true}, call: msgraph.list-events}\n    - {name: list-chats, hints: {readOnly: true}, call: msgraph.list-chats}\n    - {name: list-drive-items, hints: {readOnly: true}, call: msgraph.list-drive-items}\n\
  \  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: m365-sharepoint-document-rightsize-capability-skills\n    description: Skill bundle for shaped M365 access.\n    skills:\n    - name: m365-sharepoint-document-rightsize-capability\n      description: Shaped Microsoft Graph capability.\n      location: file:///opt/naftiko/skills/m365-sharepoint-document-rightsize-capability\n      allowed-tools: get-me,list-messages,list-events,list-chats,list-drive-items\n      tools:\n      - {name: get-me, from: {sourceNamespace: m365-sharepoint-document-rightsize-capability-mcp, action: get-me}}\n      - {name: list-messages, from: {sourceNamespace: m365-sharepoint-document-rightsize-capability-mcp, action: list-messages}}\n      - {name: list-events, from: {sourceNamespace: m365-sharepoint-document-rightsize-capability-mcp, action: list-events}}\n      - {name: list-chats, from: {sourceNamespace: m365-sharepoint-document-rightsize-capability-mcp, action: list-chats}}\n      - {name:\
  \ list-drive-items, from: {sourceNamespace: m365-sharepoint-document-rightsize-capability-mcp, action: list-drive-items}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/m365-sharepoint-document-rightsize-capability.yaml
tags:
- Naftiko
- Microsoft 365
- Graph
tools:
- description: ''
  hints:
    readOnly: true
  name: get-me
- description: ''
  hints:
    readOnly: true
  name: list-messages
- description: ''
  hints:
    readOnly: true
  name: list-events
- description: ''
  hints:
    readOnly: true
  name: list-chats
- description: ''
  hints:
    readOnly: true
  name: list-drive-items
---
