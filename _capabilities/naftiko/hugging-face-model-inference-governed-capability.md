---
categories: []
consumed_apis: []
description: A governed capability over Hugging Face Inference API — every inference call passes through Naftiko governance with usage and audit logged.
layout: capability
name: Hugging Face Model Inference Governed Capability
operations:
- description: ''
  method: POST
  name: run-governed-inference
  path: /infer/{{model_id}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- governance
- api integration
- inference
- hugging face
- ai
- capabilities
- spec-driven integration
- run governed inference
- mcp
- naftiko
slug: hugging-face-model-inference-governed-capability
source_filename: hugging-face-model-inference-governed-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Hugging Face Model Inference Governed Capability\n  description: A governed capability over Hugging Face Inference API — every inference call passes through Naftiko governance with usage and audit logged.\n  tags: [Naftiko, Hugging Face, Inference]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: huggingface-env\n  keys: {HF_TOKEN: HF_TOKEN}\ncapability:\n  consumes:\n  - namespace: huggingface\n    type: http\n    baseUri: https://api-inference.huggingface.co\n    authentication: {type: bearer, token: '{{HF_TOKEN}}'}\n    resources:\n    - name: model-inference\n      path: '/models/{{model_id}}'\n      operations:\n      - {name: run-inference, method: POST, inputParameters: [{name: model_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: hugging-face-model-inference-governed-capability-rest\n    description: Governed Hugging Face inference surface.\n    resources:\n\
  \    - {name: infer, path: '/infer/{{model_id}}', operations: [{method: POST, name: run-governed-inference, inputParameters: [{name: model_id, in: path, type: string}], call: huggingface.run-inference}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: hugging-face-model-inference-governed-capability-mcp\n    description: MCP for governed HF inference.\n    tools:\n    - name: run-governed-inference\n      inputParameters: [{name: model_id, type: string, required: true}]\n      call: huggingface.run-inference\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: hugging-face-model-inference-governed-capability-skills\n    description: Skill for governed HF inference.\n    skills:\n    - name: hugging-face-model-inference-governed-capability\n      description: Governed Hugging Face inference.\n      location: file:///opt/naftiko/skills/hugging-face-model-inference-governed-capability\n      allowed-tools: run-governed-inference\n      tools:\n     \
  \ - {name: run-governed-inference, from: {sourceNamespace: hugging-face-model-inference-governed-capability-mcp, action: run-governed-inference}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/hugging-face-model-inference-governed-capability.yaml
tags:
- Naftiko
- Hugging Face
- Inference
tools:
- description: ''
  hints: {}
  name: run-governed-inference
---
