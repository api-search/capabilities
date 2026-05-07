---
categories: []
consumed_apis: []
description: A bridge capability for BNP Paribas joining SimCorp Dimension and Bloomberg AIM into one deterministic portfolio object.
layout: capability
name: Bnp Simcorp Bloomberg Portfolio Deterministic Bridge
operations:
- description: ''
  method: GET
  name: get-bridged-portfolio
  path: /portfolios/{{portfolio_id}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- governance
- bloomberg
- spec-driven integration
- get bridged portfolio
- ai
- capabilities
- bnp
- api integration
- mcp
- simcorp
- naftiko
slug: bnp-simcorp-bloomberg-portfolio-deterministic-bridge
source_filename: bnp-simcorp-bloomberg-portfolio-deterministic-bridge.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Bnp Simcorp Bloomberg Portfolio Deterministic Bridge\n  description: A bridge capability for BNP Paribas joining SimCorp Dimension and Bloomberg AIM into one deterministic portfolio object.\n  tags: [Naftiko, BNP, SimCorp, Bloomberg]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: simcorp-env\n  keys: {SIMCORP_HOST: SIMCORP_HOST, SIMCORP_TOKEN: SIMCORP_TOKEN}\n- namespace: bloomberg-env\n  keys: {BLOOMBERG_TOKEN: BLOOMBERG_TOKEN}\ncapability:\n  consumes:\n  - namespace: simcorp\n    type: http\n    baseUri: https://{{SIMCORP_HOST}}\n    authentication: {type: bearer, token: '{{SIMCORP_TOKEN}}'}\n    resources:\n    - name: portfolio\n      path: /api/v1/portfolios/{{portfolio_id}}\n      operations:\n      - {name: get-simcorp-portfolio, method: GET, inputParameters: [{name: portfolio_id, in: path}]}\n  - namespace: aim\n    type: http\n    baseUri: https://api.bloomberg.com\n    authentication: {type: bearer,\
  \ token: '{{BLOOMBERG_TOKEN}}'}\n    resources:\n    - name: aim-portfolio\n      path: /eap/aim/v1/portfolios/{{portfolio_id}}\n      operations:\n      - {name: get-aim-portfolio, method: GET, inputParameters: [{name: portfolio_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: bnp-simcorp-bloomberg-portfolio-deterministic-bridge-rest\n    description: REST surface for SimCorp+AIM bridge.\n    resources:\n    - name: portfolio\n      path: /portfolios/{{portfolio_id}}\n      operations:\n      - {method: GET, name: get-bridged-portfolio, inputParameters: [{name: portfolio_id, in: path, type: string}], call: simcorp.get-simcorp-portfolio}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: bnp-simcorp-bloomberg-portfolio-deterministic-bridge-mcp\n    description: MCP for SimCorp+AIM bridge.\n    tools:\n    - name: get-bridged-portfolio\n      hints: {readOnly: true}\n      inputParameters: [{name: portfolio_id, type: string,\
  \ required: true}]\n      call: simcorp.get-simcorp-portfolio\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: bnp-simcorp-bloomberg-portfolio-deterministic-bridge-skills\n    description: Skill for SimCorp+AIM bridge.\n    skills:\n    - name: bnp-simcorp-bloomberg-portfolio-deterministic-bridge\n      description: SimCorp + Bloomberg AIM bridged portfolio.\n      location: file:///opt/naftiko/skills/bnp-simcorp-bloomberg-portfolio-deterministic-bridge\n      allowed-tools: get-bridged-portfolio\n      tools:\n      - {name: get-bridged-portfolio, from: {sourceNamespace: bnp-simcorp-bloomberg-portfolio-deterministic-bridge-mcp, action: get-bridged-portfolio}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/bnp-simcorp-bloomberg-portfolio-deterministic-bridge.yaml
tags:
- Naftiko
- BNP
- SimCorp
- Bloomberg
tools:
- description: ''
  hints:
    readOnly: true
  name: get-bridged-portfolio
---
