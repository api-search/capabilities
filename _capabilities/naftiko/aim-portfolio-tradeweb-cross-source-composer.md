---
categories: []
consumed_apis: []
description: A composite capability that joins AIM + Valuation Service (BVAL) + Tradeweb into one shaped portfolio-context object.
layout: capability
name: Aim Portfolio Tradeweb Cross Source Composer
operations:
- description: Return a single shaped object joining AIM positions, BVAL valuations, and Tradeweb liquidity.
  method: GET
  name: get-portfolio-context
  path: /portfolios/{{portfolio_id}}/context
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- spec-driven integration
- return a single shaped object joining aim positions, bval valuations, and tradeweb liquidity.
- tradeweb
- portfolio
- one-call composed portfolio context across aim, bval, and tradeweb.
- mcp
- get portfolio context
- capabilities
- bloomberg
- naftiko
- api integration
- governance
- ai
slug: aim-portfolio-tradeweb-cross-source-composer
source_filename: aim-portfolio-tradeweb-cross-source-composer.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Aim Portfolio Tradeweb Cross Source Composer\n  description: A composite capability that joins AIM + Valuation Service (BVAL) + Tradeweb into one shaped portfolio-context object.\n  tags: [Naftiko, Bloomberg, Tradeweb, Portfolio]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: bloomberg-env\n  description: Bloomberg AIM and BVAL API credentials.\n  keys: {BLOOMBERG_TOKEN: BLOOMBERG_TOKEN}\n- namespace: tradeweb-env\n  description: Tradeweb Connect API credentials.\n  keys: {TRADEWEB_TOKEN: TRADEWEB_TOKEN}\ncapability:\n  consumes:\n  - namespace: aim\n    type: http\n    baseUri: https://api.bloomberg.com\n    authentication: {type: bearer, token: '{{BLOOMBERG_TOKEN}}'}\n    resources:\n    - name: portfolio\n      path: /eap/aim/v1/portfolios/{{portfolio_id}}\n      operations:\n      - {name: get-aim-portfolio, method: GET, inputParameters: [{name: portfolio_id, in: path}]}\n  - namespace: bval\n    type: http\n\
  \    baseUri: https://api.bloomberg.com\n    authentication: {type: bearer, token: '{{BLOOMBERG_TOKEN}}'}\n    resources:\n    - name: valuations\n      path: /eap/bval/v1/valuations\n      operations:\n      - {name: get-bval-valuations, method: POST, description: Get valuations for a list of identifiers.}\n  - namespace: tradeweb\n    type: http\n    baseUri: https://api.tradeweb.com\n    authentication: {type: bearer, token: '{{TRADEWEB_TOKEN}}'}\n    resources:\n    - name: liquidity\n      path: /v1/liquidity/{{security_id}}\n      operations:\n      - {name: get-tradeweb-liquidity, method: GET, inputParameters: [{name: security_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: aim-portfolio-tradeweb-cross-source-composer-rest\n    description: Composed portfolio context spanning AIM positions, BVAL valuations, and Tradeweb liquidity.\n    resources:\n    - name: portfolio-context\n      path: /portfolios/{{portfolio_id}}/context\n \
  \     operations:\n      - method: GET\n        name: get-portfolio-context\n        description: Return a single shaped object joining AIM positions, BVAL valuations, and Tradeweb liquidity.\n        inputParameters: [{name: portfolio_id, in: path, type: string}]\n        call: aim.get-aim-portfolio\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: aim-portfolio-tradeweb-cross-source-composer-mcp\n    description: MCP server exposing the composed portfolio context as one tool.\n    tools:\n    - name: get-portfolio-context\n      description: One-call composed portfolio context across AIM, BVAL, and Tradeweb.\n      hints: {readOnly: true}\n      inputParameters: [{name: portfolio_id, type: string, required: true}]\n      call: aim.get-aim-portfolio\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: aim-portfolio-tradeweb-cross-source-composer-skills\n    description: Skill bundle for composed portfolio context.\n    skills:\n    - name: aim-portfolio-tradeweb-cross-source-composer\n\
  \      description: Composed portfolio context across AIM + BVAL + Tradeweb.\n      location: file:///opt/naftiko/skills/aim-portfolio-tradeweb-cross-source-composer\n      allowed-tools: get-portfolio-context\n      tools:\n      - {name: get-portfolio-context, from: {sourceNamespace: aim-portfolio-tradeweb-cross-source-composer-mcp, action: get-portfolio-context}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/aim-portfolio-tradeweb-cross-source-composer.yaml
tags:
- Naftiko
- Bloomberg
- Tradeweb
- Portfolio
tools:
- description: One-call composed portfolio context across AIM, BVAL, and Tradeweb.
  hints:
    readOnly: true
  name: get-portfolio-context
---
