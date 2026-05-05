---
categories: []
consumed_apis: []
description: A capability over Bloomberg AIM that exposes deterministic portfolio reads (positions, attributions) as MCP tools — same inputs, same outputs, same hash.
layout: capability
name: Bloomberg Aim Deterministic Portfolio Mcp
operations:
- description: ''
  method: GET
  name: get-portfolio
  path: /portfolios/{{portfolio_id}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- spec-driven integration
- portfolio
- list attributions
- mcp
- get portfolio
- capabilities
- aim
- bloomberg
- naftiko
- list positions
- api integration
- governance
- ai
slug: bloomberg-aim-deterministic-portfolio-mcp
source_filename: bloomberg-aim-deterministic-portfolio-mcp.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Bloomberg Aim Deterministic Portfolio Mcp\n  description: A capability over Bloomberg AIM that exposes deterministic portfolio reads (positions, attributions) as MCP tools — same inputs, same outputs, same hash.\n  tags: [Naftiko, Bloomberg, AIM, Portfolio]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: bloomberg-env\n  keys: {BLOOMBERG_TOKEN: BLOOMBERG_TOKEN}\ncapability:\n  consumes:\n  - namespace: aim\n    type: http\n    baseUri: https://api.bloomberg.com\n    authentication: {type: bearer, token: '{{BLOOMBERG_TOKEN}}'}\n    resources:\n    - name: portfolio\n      path: /eap/aim/v1/portfolios/{{portfolio_id}}\n      operations:\n      - {name: get-portfolio, method: GET, inputParameters: [{name: portfolio_id, in: path}]}\n    - name: positions\n      path: /eap/aim/v1/portfolios/{{portfolio_id}}/positions\n      operations:\n      - {name: list-positions, method: GET, inputParameters: [{name: portfolio_id,\
  \ in: path}]}\n    - name: attributions\n      path: /eap/aim/v1/portfolios/{{portfolio_id}}/attributions\n      operations:\n      - {name: list-attributions, method: GET, inputParameters: [{name: portfolio_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: bloomberg-aim-deterministic-portfolio-mcp-rest\n    description: REST surface for deterministic AIM portfolio reads.\n    resources:\n    - name: portfolio\n      path: /portfolios/{{portfolio_id}}\n      operations:\n      - {method: GET, name: get-portfolio, inputParameters: [{name: portfolio_id, in: path, type: string}], call: aim.get-portfolio}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: bloomberg-aim-deterministic-portfolio-mcp-mcp\n    description: MCP exposing AIM portfolio reads.\n    tools:\n    - name: get-portfolio\n      hints: {readOnly: true}\n      inputParameters: [{name: portfolio_id, type: string, required: true}]\n      call: aim.get-portfolio\n\
  \    - name: list-positions\n      hints: {readOnly: true}\n      inputParameters: [{name: portfolio_id, type: string, required: true}]\n      call: aim.list-positions\n    - name: list-attributions\n      hints: {readOnly: true}\n      inputParameters: [{name: portfolio_id, type: string, required: true}]\n      call: aim.list-attributions\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: bloomberg-aim-deterministic-portfolio-mcp-skills\n    description: Skill for AIM portfolio.\n    skills:\n    - name: bloomberg-aim-deterministic-portfolio-mcp\n      description: Deterministic AIM portfolio reads.\n      location: file:///opt/naftiko/skills/bloomberg-aim-deterministic-portfolio-mcp\n      allowed-tools: get-portfolio,list-positions,list-attributions\n      tools:\n      - {name: get-portfolio, from: {sourceNamespace: bloomberg-aim-deterministic-portfolio-mcp-mcp, action: get-portfolio}}\n      - {name: list-positions, from: {sourceNamespace: bloomberg-aim-deterministic-portfolio-mcp-mcp,\
  \ action: list-positions}}\n      - {name: list-attributions, from: {sourceNamespace: bloomberg-aim-deterministic-portfolio-mcp-mcp, action: list-attributions}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/bloomberg-aim-deterministic-portfolio-mcp.yaml
tags:
- Naftiko
- Bloomberg
- AIM
- Portfolio
tools:
- description: ''
  hints:
    readOnly: true
  name: get-portfolio
- description: ''
  hints:
    readOnly: true
  name: list-positions
- description: ''
  hints:
    readOnly: true
  name: list-attributions
---
