---
categories: []
consumed_apis: []
description: A bridge capability joining Bloomberg AIM/BVAL with Tradeweb liquidity into one deterministic cross-source object for portfolio/risk agents.
layout: capability
name: Bloomberg Tradeweb Cross Source Deterministic Bridge
operations:
- description: ''
  method: GET
  name: get-cross-source
  path: /securities/{{security_id}}/cross-source
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- tradeweb
- mcp
- bloomberg
- get cross source
- api integration
- governance
- spec-driven integration
- get liquidity
- ai
- bridge
- capabilities
- get valuations
slug: bloomberg-tradeweb-cross-source-deterministic-bridge
source_filename: bloomberg-tradeweb-cross-source-deterministic-bridge.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Bloomberg Tradeweb Cross Source Deterministic Bridge\n  description: A bridge capability joining Bloomberg AIM/BVAL with Tradeweb liquidity into one deterministic cross-source object for portfolio/risk agents.\n  tags: [Naftiko, Bloomberg, Tradeweb, Bridge]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: bloomberg-env\n  keys: {BLOOMBERG_TOKEN: BLOOMBERG_TOKEN}\n- namespace: tradeweb-env\n  keys: {TRADEWEB_TOKEN: TRADEWEB_TOKEN}\ncapability:\n  consumes:\n  - namespace: bval\n    type: http\n    baseUri: https://api.bloomberg.com\n    authentication: {type: bearer, token: '{{BLOOMBERG_TOKEN}}'}\n    resources:\n    - {name: valuations, path: /eap/bval/v1/valuations, operations: [{name: get-valuations, method: POST}]}\n  - namespace: tradeweb\n    type: http\n    baseUri: https://api.tradeweb.com\n    authentication: {type: bearer, token: '{{TRADEWEB_TOKEN}}'}\n    resources:\n    - name: liquidity\n      path:\
  \ /v1/liquidity/{{security_id}}\n      operations:\n      - {name: get-liquidity, method: GET, inputParameters: [{name: security_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: bloomberg-tradeweb-cross-source-deterministic-bridge-rest\n    description: REST surface for cross-source valuation+liquidity.\n    resources:\n    - name: cross-source\n      path: /securities/{{security_id}}/cross-source\n      operations:\n      - {method: GET, name: get-cross-source, inputParameters: [{name: security_id, in: path, type: string}], call: bval.get-valuations}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: bloomberg-tradeweb-cross-source-deterministic-bridge-mcp\n    description: MCP for cross-source bridge.\n    tools:\n    - {name: get-valuations, hints: {readOnly: true}, call: bval.get-valuations}\n    - name: get-liquidity\n      hints: {readOnly: true}\n      inputParameters: [{name: security_id, type: string, required:\
  \ true}]\n      call: tradeweb.get-liquidity\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: bloomberg-tradeweb-cross-source-deterministic-bridge-skills\n    description: Skill for cross-source bridge.\n    skills:\n    - name: bloomberg-tradeweb-cross-source-deterministic-bridge\n      description: Cross-source valuation + liquidity.\n      location: file:///opt/naftiko/skills/bloomberg-tradeweb-cross-source-deterministic-bridge\n      allowed-tools: get-valuations,get-liquidity\n      tools:\n      - {name: get-valuations, from: {sourceNamespace: bloomberg-tradeweb-cross-source-deterministic-bridge-mcp, action: get-valuations}}\n      - {name: get-liquidity, from: {sourceNamespace: bloomberg-tradeweb-cross-source-deterministic-bridge-mcp, action: get-liquidity}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/bloomberg-tradeweb-cross-source-deterministic-bridge.yaml
tags:
- Naftiko
- Bloomberg
- Tradeweb
- Bridge
tools:
- description: ''
  hints:
    readOnly: true
  name: get-valuations
- description: ''
  hints:
    readOnly: true
  name: get-liquidity
---
