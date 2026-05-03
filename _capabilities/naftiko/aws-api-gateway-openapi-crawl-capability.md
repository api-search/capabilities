---
categories: []
consumed_apis: []
description: A capability that pulls OpenAPI specs out of an AWS API Gateway account (and Kong + Apigee), normalizes them, and republishes the enriched specs back to a portal AND to MCP for IDE-injected developer tooling.
layout: capability
name: Aws Api Gateway Openapi Crawl Capability
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- example
- mcp
- ai
- naftiko
- api integration
- spec-driven integration
- capabilities
- a capability that pulls openapi specs out of an aws api gateway account (and kong + apigee), normalizes them, and republishes the enriched specs back to a portal and to mcp for ide-injected developer tooling.
- example op
- governance
slug: aws-api-gateway-openapi-crawl-capability
source_filename: aws-api-gateway-openapi-crawl-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Aws Api Gateway Openapi Crawl Capability\n  description: A capability that pulls OpenAPI specs out of an AWS API Gateway account (and Kong + Apigee), normalizes them, and republishes the enriched specs back to a portal AND to MCP for IDE-injected developer tooling.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: aws-api-gateway-openapi-crawl-capability-rest\n    description: REST API for Aws Api Gateway Openapi Crawl\
  \ Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: aws-api-gateway-openapi-crawl-capability-mcp\n    description: MCP server exposing Aws Api Gateway Openapi Crawl Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability that pulls OpenAPI specs out of an AWS API Gateway account (and Kong + Apigee), normalizes them, and republishes the enriched specs back to a portal AND to MCP for IDE-injected developer tooling.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: aws-api-gateway-openapi-crawl-capability-skills\n    description: Agent Skill bundle for Aws Api Gateway Openapi Crawl Capability.\n    skills:\n    - name: aws-api-gateway-openapi-crawl-capability\n      description:\
  \ A capability that pulls OpenAPI specs out of an AWS API Gateway account (and Kong + Apigee), normalizes them, and republishes the enriched specs back to a portal AND to MCP for IDE-injected developer tooling.\n      location: file:///opt/naftiko/skills/aws-api-gateway-openapi-crawl-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that pulls OpenAPI specs out of an AWS API Gateway account (and Kong + Apigee), normalizes them, and republishes the enriched specs back to a portal AND to MCP for IDE-injected developer tooling.\n        from:\n          sourceNamespace: aws-api-gateway-openapi-crawl-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/aws-api-gateway-openapi-crawl-capability.yaml
tags:
- Naftiko
tools:
- description: A capability that pulls OpenAPI specs out of an AWS API Gateway account (and Kong + Apigee), normalizes them, and republishes the enriched specs back to a portal AND to MCP for IDE-injected developer tooling.
  hints:
    readOnly: true
  name: example
---
