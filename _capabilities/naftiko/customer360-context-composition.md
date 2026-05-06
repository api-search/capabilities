---
categories: []
consumed_apis: []
description: A capability composing CRM, support, and billing into a unified Customer 360 context.
layout: capability
name: Customer360 Context Composition
operations:
- description: ''
  method: GET
  name: get-customer-360
  path: /customers/{{contact_id}}/360
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- customer 360
- api integration
- governance
- spec-driven integration
- ai
- mcp
- capabilities
- composition
- get customer 360
slug: customer360-context-composition
source_filename: customer360-context-composition.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Customer360 Context Composition\n  description: A capability composing CRM, support, and billing into a unified Customer 360 context.\n  tags: [Naftiko, Customer 360, Composition]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: hubspot-env\n  keys: {HUBSPOT_TOKEN: HUBSPOT_TOKEN}\n- namespace: zendesk-env\n  keys: {ZENDESK_SUBDOMAIN: ZENDESK_SUBDOMAIN, ZENDESK_TOKEN: ZENDESK_TOKEN}\n- namespace: stripe-env\n  keys: {STRIPE_API_KEY: STRIPE_API_KEY}\ncapability:\n  consumes:\n  - namespace: hubspot\n    type: http\n    baseUri: https://api.hubapi.com\n    authentication: {type: bearer, token: '{{HUBSPOT_TOKEN}}'}\n    resources:\n    - name: contact\n      path: /crm/v3/objects/contacts/{{contact_id}}\n      operations:\n      - {name: get-contact, method: GET, inputParameters: [{name: contact_id, in: path}]}\n  - namespace: zendesk\n    type: http\n    baseUri: https://{{ZENDESK_SUBDOMAIN}}.zendesk.com\n    authentication:\
  \ {type: bearer, token: '{{ZENDESK_TOKEN}}'}\n    resources:\n    - {name: tickets, path: /api/v2/tickets, operations: [{name: list-tickets, method: GET}]}\n  - namespace: stripe\n    type: http\n    baseUri: https://api.stripe.com\n    authentication: {type: bearer, token: '{{STRIPE_API_KEY}}'}\n    resources:\n    - name: customer\n      path: /v1/customers/{{customer_id}}\n      operations:\n      - {name: get-stripe-customer, method: GET, inputParameters: [{name: customer_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: customer360-context-composition-rest\n    description: REST surface for Customer 360.\n    resources:\n    - name: customer-360\n      path: /customers/{{contact_id}}/360\n      operations:\n      - {method: GET, name: get-customer-360, inputParameters: [{name: contact_id, in: path, type: string}], call: hubspot.get-contact}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: customer360-context-composition-mcp\n\
  \    description: MCP for Customer 360.\n    tools:\n    - name: get-customer-360\n      hints: {readOnly: true}\n      inputParameters: [{name: contact_id, type: string, required: true}]\n      call: hubspot.get-contact\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: customer360-context-composition-skills\n    description: Skill for Customer 360.\n    skills:\n    - name: customer360-context-composition\n      description: Composed Customer 360 context.\n      location: file:///opt/naftiko/skills/customer360-context-composition\n      allowed-tools: get-customer-360\n      tools:\n      - {name: get-customer-360, from: {sourceNamespace: customer360-context-composition-mcp, action: get-customer-360}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/customer360-context-composition.yaml
tags:
- Naftiko
- Customer 360
- Composition
tools:
- description: ''
  hints:
    readOnly: true
  name: get-customer-360
---
