---
categories: []
consumed_apis: []
description: A booth-companion capability for apidays NYC — captures lead-scan events into the Naftiko CRM hook and emits a per-scan acknowledgement.
layout: capability
name: Apidays Nyc Booth Capability
operations:
- description: Record a lead scan; creates a HubSpot contact.
  method: POST
  name: capture-scan
  path: /scan
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- apidays
- events
- spec-driven integration
- record a lead scan into crm.
- mcp
- capabilities
- naftiko
- api integration
- governance
- ai
- capture scan
- record a lead scan; creates a hubspot contact.
slug: apidays-nyc-booth-capability
source_filename: apidays-nyc-booth-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Apidays Nyc Booth Capability\n  description: A booth-companion capability for apidays NYC — captures lead-scan events into the Naftiko CRM hook and emits a per-scan acknowledgement.\n  tags: [Naftiko, apidays, Events]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: hubspot-env\n  description: HubSpot CRM private app token.\n  keys: {HUBSPOT_TOKEN: HUBSPOT_TOKEN}\ncapability:\n  consumes:\n  - namespace: hubspot\n    type: http\n    baseUri: https://api.hubapi.com\n    authentication: {type: bearer, token: '{{HUBSPOT_TOKEN}}'}\n    resources:\n    - {name: contacts, path: /crm/v3/objects/contacts, operations: [{name: create-contact, method: POST}]}\n    - name: contact\n      path: /crm/v3/objects/contacts/{{contact_id}}\n      operations:\n      - {name: get-contact, method: GET, inputParameters: [{name: contact_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: apidays-nyc-booth-capability-rest\n\
  \    description: REST surface capturing booth lead scans into HubSpot.\n    resources:\n    - name: scan\n      path: /scan\n      operations: [{method: POST, name: capture-scan, description: Record a lead scan; creates a HubSpot contact., call: hubspot.create-contact}]\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: apidays-nyc-booth-capability-mcp\n    description: MCP for booth scan capture.\n    tools:\n    - {name: capture-scan, description: Record a lead scan into CRM., call: hubspot.create-contact}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: apidays-nyc-booth-capability-skills\n    description: Skill bundle for booth use.\n    skills:\n    - name: apidays-nyc-booth-capability\n      description: Lead-scan capture for apidays booth.\n      location: file:///opt/naftiko/skills/apidays-nyc-booth-capability\n      allowed-tools: capture-scan\n      tools:\n      - {name: capture-scan, from: {sourceNamespace: apidays-nyc-booth-capability-mcp,\
  \ action: capture-scan}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/apidays-nyc-booth-capability.yaml
tags:
- Naftiko
- apidays
- Events
tools:
- description: Record a lead scan into CRM.
  hints: {}
  name: capture-scan
---
