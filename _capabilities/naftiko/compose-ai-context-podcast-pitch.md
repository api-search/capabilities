---
categories: []
consumed_apis: []
description: A capability composing CRM contact context + recent content into an AI context for podcast-pitch outreach.
layout: capability
name: Compose Ai Context Podcast Pitch
operations:
- description: ''
  method: GET
  name: get-pitch-context
  path: /pitch-context/{{contact_id}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- podcast
- pitch
- spec-driven integration
- mcp
- capabilities
- ai context
- naftiko
- api integration
- get pitch context
- governance
- ai
slug: compose-ai-context-podcast-pitch
source_filename: compose-ai-context-podcast-pitch.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Compose Ai Context Podcast Pitch\n  description: A capability composing CRM contact context + recent content into an AI context for podcast-pitch outreach.\n  tags: [Naftiko, Podcast, Pitch, AI Context]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: hubspot-env\n  keys: {HUBSPOT_TOKEN: HUBSPOT_TOKEN}\ncapability:\n  consumes:\n  - namespace: hubspot\n    type: http\n    baseUri: https://api.hubapi.com\n    authentication: {type: bearer, token: '{{HUBSPOT_TOKEN}}'}\n    resources:\n    - name: contact\n      path: '/crm/v3/objects/contacts/{{contact_id}}'\n      operations:\n      - {name: get-contact, method: GET, inputParameters: [{name: contact_id, in: path}]}\n    - {name: contacts-search, path: /crm/v3/objects/contacts/search, operations: [{name: search-contacts, method: POST}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: compose-ai-context-podcast-pitch-rest\n    description:\
  \ REST surface for podcast pitch AI context.\n    resources:\n    - {name: pitch-context, path: '/pitch-context/{{contact_id}}', operations: [{method: GET, name: get-pitch-context, inputParameters: [{name: contact_id, in: path, type: string}], call: hubspot.get-contact}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: compose-ai-context-podcast-pitch-mcp\n    description: MCP for podcast pitch context.\n    tools:\n    - name: get-pitch-context\n      hints: {readOnly: true}\n      inputParameters: [{name: contact_id, type: string, required: true}]\n      call: hubspot.get-contact\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: compose-ai-context-podcast-pitch-skills\n    description: Skill for podcast pitch context.\n    skills:\n    - name: compose-ai-context-podcast-pitch\n      description: Podcast pitch AI context.\n      location: file:///opt/naftiko/skills/compose-ai-context-podcast-pitch\n      allowed-tools: get-pitch-context\n    \
  \  tools:\n      - {name: get-pitch-context, from: {sourceNamespace: compose-ai-context-podcast-pitch-mcp, action: get-pitch-context}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/compose-ai-context-podcast-pitch.yaml
tags:
- Naftiko
- Podcast
- Pitch
- AI Context
tools:
- description: ''
  hints:
    readOnly: true
  name: get-pitch-context
---
