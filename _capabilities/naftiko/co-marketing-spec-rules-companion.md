---
categories: []
consumed_apis: []
description: A companion capability that runs Spectral rules co-developed with co-marketing partners against a target OpenAPI spec.
layout: capability
name: Co Marketing Spec Rules Companion
operations:
- description: ''
  method: POST
  name: lint-spec
  path: /lint
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- governance
- get ruleset
- ai
- capabilities
- spec-driven integration
- spectral
- api integration
- lint spec
- mcp
- naftiko
- co-marketing
slug: co-marketing-spec-rules-companion
source_filename: co-marketing-spec-rules-companion.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Co Marketing Spec Rules Companion\n  description: A companion capability that runs Spectral rules co-developed with co-marketing partners against a target OpenAPI spec.\n  tags: [Naftiko, Spectral, Co-Marketing]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: stoplight-env\n  keys: {STOPLIGHT_TOKEN: STOPLIGHT_TOKEN}\ncapability:\n  consumes:\n  - namespace: stoplight\n    type: http\n    baseUri: https://api.stoplight.io\n    authentication: {type: bearer, token: '{{STOPLIGHT_TOKEN}}'}\n    resources:\n    - {name: lint, path: '/v1/projects/{{project_id}}/lint', operations: [{name: lint-spec, method: POST, inputParameters: [{name: project_id, in: path}]}]}\n    - name: ruleset\n      path: '/v1/rulesets/{{ruleset_id}}'\n      operations:\n      - {name: get-ruleset, method: GET, inputParameters: [{name: ruleset_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: co-marketing-spec-rules-companion-rest\n\
  \    description: REST surface for running co-marketing Spectral rules.\n    resources:\n    - {name: lint, path: /lint, operations: [{method: POST, name: lint-spec, call: stoplight.lint-spec}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: co-marketing-spec-rules-companion-mcp\n    description: MCP for running co-marketing rules.\n    tools:\n    - {name: lint-spec, call: stoplight.lint-spec}\n    - name: get-ruleset\n      hints: {readOnly: true}\n      inputParameters: [{name: ruleset_id, type: string, required: true}]\n      call: stoplight.get-ruleset\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: co-marketing-spec-rules-companion-skills\n    description: Skill for co-marketing rules.\n    skills:\n    - name: co-marketing-spec-rules-companion\n      description: Co-marketing Spectral rules companion.\n      location: file:///opt/naftiko/skills/co-marketing-spec-rules-companion\n      allowed-tools: lint-spec,get-ruleset\n      tools:\n\
  \      - {name: lint-spec, from: {sourceNamespace: co-marketing-spec-rules-companion-mcp, action: lint-spec}}\n      - {name: get-ruleset, from: {sourceNamespace: co-marketing-spec-rules-companion-mcp, action: get-ruleset}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/co-marketing-spec-rules-companion.yaml
tags:
- Naftiko
- Spectral
- Co-Marketing
tools:
- description: ''
  hints: {}
  name: lint-spec
- description: ''
  hints:
    readOnly: true
  name: get-ruleset
---
