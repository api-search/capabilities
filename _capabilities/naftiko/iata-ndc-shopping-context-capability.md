---
categories: []
consumed_apis: []
description: A capability over the IATA NDC shopping flow — shape AirShopping/OfferPrice responses into a compact AI-friendly shopping context.
layout: capability
name: Iata Ndc Shopping Context Capability
operations:
- description: Run an NDC AirShopping query and return shaped offers.
  method: POST
  name: shop
  path: /shop
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- governance
- iata ndc
- shop
- price offer
- run an ndc airshopping query and return shaped offers.
- travel
- ai
- capabilities
- spec-driven integration
- api integration
- mcp
- naftiko
slug: iata-ndc-shopping-context-capability
source_filename: iata-ndc-shopping-context-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Iata Ndc Shopping Context Capability\n  description: A capability over the IATA NDC shopping flow — shape AirShopping/OfferPrice responses into a compact AI-friendly shopping context.\n  tags: [Naftiko, IATA NDC, Travel]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: ndc-env\n  keys: {NDC_HOST: NDC_HOST, NDC_TOKEN: NDC_TOKEN}\ncapability:\n  consumes:\n  - namespace: ndc\n    type: http\n    baseUri: https://{{NDC_HOST}}\n    authentication: {type: bearer, token: '{{NDC_TOKEN}}'}\n    resources:\n    - {name: air-shopping, path: /ndc/v21.3/AirShopping, operations: [{name: air-shopping, method: POST, description: NDC AirShopping request.}]}\n    - {name: offer-price, path: /ndc/v21.3/OfferPrice, operations: [{name: offer-price, method: POST}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: iata-ndc-shopping-context-capability-rest\n    description: REST surface for shaped NDC\
  \ shopping.\n    resources:\n    - {name: shop, path: /shop, operations: [{method: POST, name: shop, description: Run an NDC AirShopping query and return shaped offers., call: ndc.air-shopping}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: iata-ndc-shopping-context-capability-mcp\n    description: MCP for NDC shopping.\n    tools:\n    - {name: shop, call: ndc.air-shopping}\n    - {name: price-offer, call: ndc.offer-price}\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: iata-ndc-shopping-context-capability-skills\n    description: Skill for NDC shopping.\n    skills:\n    - name: iata-ndc-shopping-context-capability\n      description: IATA NDC shaped shopping context.\n      location: file:///opt/naftiko/skills/iata-ndc-shopping-context-capability\n      allowed-tools: shop,price-offer\n      tools:\n      - {name: shop, from: {sourceNamespace: iata-ndc-shopping-context-capability-mcp, action: shop}}\n      - {name: price-offer, from: {sourceNamespace:\
  \ iata-ndc-shopping-context-capability-mcp, action: price-offer}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/iata-ndc-shopping-context-capability.yaml
tags:
- Naftiko
- IATA NDC
- Travel
tools:
- description: ''
  hints: {}
  name: shop
- description: ''
  hints: {}
  name: price-offer
---
