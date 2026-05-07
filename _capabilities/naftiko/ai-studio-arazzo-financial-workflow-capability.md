---
categories: []
consumed_apis: []
description: A capability that ingests an Arazzo workflow from AI Studio and exposes the workflow as a single composed MCP tool — the apidays NYC co-branded financial-services artifact.
layout: capability
name: Ai Studio Arazzo Financial Workflow Capability
operations:
- description: Execute the financial-services Arazzo workflow as one composed call.
  method: POST
  name: run-financial-workflow
  path: /run/{{workflow_id}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- get workflow
- ai studio
- financial
- governance
- execute the financial-services arazzo workflow as one composed call.
- run financial workflow
- execute the financial-services arazzo workflow end-to-end.
- inspect the underlying arazzo workflow definition.
- ai
- capabilities
- spec-driven integration
- api integration
- arazzo
- mcp
- naftiko
slug: ai-studio-arazzo-financial-workflow-capability
source_filename: ai-studio-arazzo-financial-workflow-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Ai Studio Arazzo Financial Workflow Capability\n  description: A capability that ingests an Arazzo workflow from AI Studio and exposes the workflow as a single composed MCP tool — the apidays NYC co-branded financial-services artifact.\n  tags: [Naftiko, Arazzo, AI Studio, Financial]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: aistudio-env\n  description: Speakeasy AI Studio API key.\n  keys: {AI_STUDIO_API_KEY: AI_STUDIO_API_KEY}\ncapability:\n  consumes:\n  - namespace: aistudio\n    type: http\n    baseUri: https://api.aistudio.speakeasy.com\n    authentication: {type: bearer, token: '{{AI_STUDIO_API_KEY}}'}\n    resources:\n    - name: workflow\n      path: /v1/workflows/{{workflow_id}}\n      operations:\n      - name: get-arazzo-workflow\n        method: GET\n        description: Fetch an Arazzo (1.0) workflow document.\n        inputParameters: [{name: workflow_id, in: path}]\n    - name: workflow-execute\n\
  \      path: /v1/workflows/{{workflow_id}}/executions\n      operations:\n      - name: execute-workflow\n        method: POST\n        description: Execute an Arazzo workflow with input parameters.\n        inputParameters: [{name: workflow_id, in: path}]\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: ai-studio-arazzo-financial-workflow-capability-rest\n    description: REST surface that exposes a composed financial-services Arazzo workflow.\n    resources:\n    - name: run\n      path: /run/{{workflow_id}}\n      operations:\n      - method: POST\n        name: run-financial-workflow\n        description: Execute the financial-services Arazzo workflow as one composed call.\n        inputParameters: [{name: workflow_id, in: path, type: string}]\n        call: aistudio.execute-workflow\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: ai-studio-arazzo-financial-workflow-capability-mcp\n    description: MCP server collapsing the Arazzo\
  \ workflow to a single agent tool.\n    tools:\n    - name: run-financial-workflow\n      description: Execute the financial-services Arazzo workflow end-to-end.\n      inputParameters: [{name: workflow_id, type: string, required: true}]\n      call: aistudio.execute-workflow\n    - name: get-workflow\n      description: Inspect the underlying Arazzo workflow definition.\n      hints: {readOnly: true}\n      inputParameters: [{name: workflow_id, type: string, required: true}]\n      call: aistudio.get-arazzo-workflow\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: ai-studio-arazzo-financial-workflow-capability-skills\n    description: Skill bundle wrapping the financial workflow.\n    skills:\n    - name: ai-studio-arazzo-financial-workflow-capability\n      description: Run a financial-services Arazzo workflow as a single agent tool.\n      location: file:///opt/naftiko/skills/ai-studio-arazzo-financial-workflow-capability\n      allowed-tools: run-financial-workflow,get-workflow\n\
  \      tools:\n      - {name: run-financial-workflow, from: {sourceNamespace: ai-studio-arazzo-financial-workflow-capability-mcp, action: run-financial-workflow}}\n      - {name: get-workflow, from: {sourceNamespace: ai-studio-arazzo-financial-workflow-capability-mcp, action: get-workflow}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/ai-studio-arazzo-financial-workflow-capability.yaml
tags:
- Naftiko
- Arazzo
- AI Studio
- Financial
tools:
- description: Execute the financial-services Arazzo workflow end-to-end.
  hints: {}
  name: run-financial-workflow
- description: Inspect the underlying Arazzo workflow definition.
  hints:
    readOnly: true
  name: get-workflow
---
