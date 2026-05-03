---
categories: []
consumed_apis: []
description: A capability over a Hugging Face inference endpoint with PII detection + agent-safety tags + Datadog metrics — the ML-output-shaping podcast topic.
layout: capability
name: Hugging Face Model Inference Governed Capability
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- a capability over a hugging face inference endpoint with pii detection + agent-safety tags + datadog metrics — the ml-output-shaping podcast topic.
- example op
- example
- api integration
- spec-driven integration
- naftiko
- governance
- mcp
- capabilities
- ai
slug: hugging-face-model-inference-governed-capability
source_filename: hugging-face-model-inference-governed-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Hugging Face Model Inference Governed Capability\n  description: A capability over a Hugging Face inference endpoint with PII detection + agent-safety tags + Datadog metrics — the ML-output-shaping podcast topic.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: hugging-face-model-inference-governed-capability-rest\n    description: REST API for Hugging Face Model Inference Governed Capability.\n    resources:\n    -\
  \ name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: hugging-face-model-inference-governed-capability-mcp\n    description: MCP server exposing Hugging Face Model Inference Governed Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability over a Hugging Face inference endpoint with PII detection + agent-safety tags + Datadog metrics — the ML-output-shaping podcast topic.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: hugging-face-model-inference-governed-capability-skills\n    description: Agent Skill bundle for Hugging Face Model Inference Governed Capability.\n    skills:\n    - name: hugging-face-model-inference-governed-capability\n      description: A capability over a Hugging Face inference endpoint with\
  \ PII detection + agent-safety tags + Datadog metrics — the ML-output-shaping podcast topic.\n      location: file:///opt/naftiko/skills/hugging-face-model-inference-governed-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability over a Hugging Face inference endpoint with PII detection + agent-safety tags + Datadog metrics — the ML-output-shaping podcast topic.\n        from:\n          sourceNamespace: hugging-face-model-inference-governed-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/hugging-face-model-inference-governed-capability.yaml
tags:
- Naftiko
tools:
- description: A capability over a Hugging Face inference endpoint with PII detection + agent-safety tags + Datadog metrics — the ML-output-shaping podcast topic.
  hints:
    readOnly: true
  name: example
---
