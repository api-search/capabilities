---
categories: []
consumed_apis: []
description: A capability composing ESB / iPaaS endpoints (MuleSoft, Boomi) into a unified integration context for enterprise agents.
layout: capability
name: Enterprise Integration Context Composition
operations:
- description: ''
  method: GET
  name: list-integrations
  path: /integrations
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- naftiko
- list integrations
- mulesoft
- mcp
- integration
- api integration
- governance
- spec-driven integration
- ai
- get integration
- boomi
- capabilities
slug: enterprise-integration-context-composition
source_filename: enterprise-integration-context-composition.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Enterprise Integration Context Composition\n  description: A capability composing ESB / iPaaS endpoints (MuleSoft, Boomi) into a unified integration context for enterprise agents.\n  tags: [Naftiko, MuleSoft, Boomi, Integration]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: mulesoft-env\n  keys: {MULESOFT_TOKEN: MULESOFT_TOKEN}\ncapability:\n  consumes:\n  - namespace: mulesoft\n    type: http\n    baseUri: https://anypoint.mulesoft.com\n    authentication: {type: bearer, token: '{{MULESOFT_TOKEN}}'}\n    resources:\n    - {name: applications, path: /cloudhub/api/v2/applications, operations: [{name: list-applications, method: GET}]}\n    - name: application\n      path: /cloudhub/api/v2/applications/{{domain}}\n      operations:\n      - {name: get-application, method: GET, inputParameters: [{name: domain, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: enterprise-integration-context-composition-rest\n\
  \    description: REST surface for integration context.\n    resources:\n    - {name: integrations, path: /integrations, operations: [{method: GET, name: list-integrations, call: mulesoft.list-applications}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: enterprise-integration-context-composition-mcp\n    description: MCP for integration context.\n    tools:\n    - {name: list-integrations, hints: {readOnly: true}, call: mulesoft.list-applications}\n    - name: get-integration\n      hints: {readOnly: true}\n      inputParameters: [{name: domain, type: string, required: true}]\n      call: mulesoft.get-application\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: enterprise-integration-context-composition-skills\n    description: Skill for enterprise integration context.\n    skills:\n    - name: enterprise-integration-context-composition\n      description: Enterprise integration context.\n      location: file:///opt/naftiko/skills/enterprise-integration-context-composition\n\
  \      allowed-tools: list-integrations,get-integration\n      tools:\n      - {name: list-integrations, from: {sourceNamespace: enterprise-integration-context-composition-mcp, action: list-integrations}}\n      - {name: get-integration, from: {sourceNamespace: enterprise-integration-context-composition-mcp, action: get-integration}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/enterprise-integration-context-composition.yaml
tags:
- Naftiko
- MuleSoft
- Boomi
- Integration
tools:
- description: ''
  hints:
    readOnly: true
  name: list-integrations
- description: ''
  hints:
    readOnly: true
  name: get-integration
---
