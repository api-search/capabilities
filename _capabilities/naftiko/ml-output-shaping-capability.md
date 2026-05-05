---
categories: []
consumed_apis: []
description: A capability that shapes ML model output (raw logits/probabilities) into typed business objects suitable for agent consumption.
layout: capability
name: Ml Output Shaping Capability
operations:
- description: ''
  method: POST
  name: predict-shaped
  path: /predict-shaped/{{model}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- spec-driven integration
- predict shaped
- output shaping
- ml
- mcp
- capabilities
- naftiko
- api integration
- governance
- ai
slug: ml-output-shaping-capability
source_filename: ml-output-shaping-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Ml Output Shaping Capability\n  description: A capability that shapes ML model output (raw logits/probabilities) into typed business objects suitable for agent consumption.\n  tags: [Naftiko, ML, Output Shaping]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: ml-env\n  keys: {ML_HOST: ML_HOST, ML_TOKEN: ML_TOKEN}\ncapability:\n  consumes:\n  - namespace: ml-serving\n    type: http\n    baseUri: https://{{ML_HOST}}\n    authentication: {type: bearer, token: '{{ML_TOKEN}}'}\n    resources:\n    - {name: predict, path: '/v1/models/{{model}}:predict', operations: [{name: predict, method: POST, inputParameters: [{name: model, in: path}]}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: ml-output-shaping-capability-rest\n    description: REST surface for shaped ML output.\n    resources:\n    - {name: predict-shaped, path: '/predict-shaped/{{model}}', operations: [{method: POST, name:\
  \ predict-shaped, inputParameters: [{name: model, in: path, type: string}], call: ml-serving.predict}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: ml-output-shaping-capability-mcp\n    description: MCP for shaped ML output.\n    tools:\n    - name: predict-shaped\n      inputParameters: [{name: model, type: string, required: true}]\n      call: ml-serving.predict\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: ml-output-shaping-capability-skills\n    description: Skill for shaped ML output.\n    skills:\n    - name: ml-output-shaping-capability\n      description: ML output shaping.\n      location: file:///opt/naftiko/skills/ml-output-shaping-capability\n      allowed-tools: predict-shaped\n      tools:\n      - {name: predict-shaped, from: {sourceNamespace: ml-output-shaping-capability-mcp, action: predict-shaped}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/ml-output-shaping-capability.yaml
tags:
- Naftiko
- ML
- Output Shaping
tools:
- description: ''
  hints: {}
  name: predict-shaped
---
