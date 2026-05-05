---
categories: []
consumed_apis: []
description: A deterministic capability for healthcare agentic flows — same patient/encounter inputs yield same shaped care-plan context for clinician agents.
layout: capability
name: Deterministic Agentic Care Capability
operations:
- description: ''
  method: GET
  name: get-care-context
  path: /patients/{{patient_id}}/care-context
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- healthcare
- spec-driven integration
- deterministic
- mcp
- capabilities
- agentic
- naftiko
- api integration
- governance
- ai
- get care context
slug: deterministic-agentic-care-capability
source_filename: deterministic-agentic-care-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Deterministic Agentic Care Capability\n  description: A deterministic capability for healthcare agentic flows — same patient/encounter inputs yield same shaped care-plan context for clinician agents.\n  tags: [Naftiko, Healthcare, Deterministic, Agentic]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: fhir-env\n  keys: {FHIR_HOST: FHIR_HOST, FHIR_TOKEN: FHIR_TOKEN}\ncapability:\n  consumes:\n  - namespace: fhir\n    type: http\n    baseUri: https://{{FHIR_HOST}}\n    authentication: {type: bearer, token: '{{FHIR_TOKEN}}'}\n    resources:\n    - name: patient\n      path: /Patient/{{patient_id}}\n      operations:\n      - {name: get-patient, method: GET, inputParameters: [{name: patient_id, in: path}]}\n    - name: care-plans\n      path: /CarePlan\n      operations: [{name: search-care-plans, method: GET}]\n    - name: encounters\n      path: /Encounter\n      operations: [{name: search-encounters, method: GET}]\n\
  \  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: deterministic-agentic-care-capability-rest\n    description: REST surface for deterministic care context.\n    resources:\n    - name: care-context\n      path: /patients/{{patient_id}}/care-context\n      operations:\n      - {method: GET, name: get-care-context, inputParameters: [{name: patient_id, in: path, type: string}], call: fhir.get-patient}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: deterministic-agentic-care-capability-mcp\n    description: MCP for deterministic care context.\n    tools:\n    - name: get-care-context\n      hints: {readOnly: true}\n      inputParameters: [{name: patient_id, type: string, required: true}]\n      call: fhir.get-patient\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: deterministic-agentic-care-capability-skills\n    description: Skill for deterministic care.\n    skills:\n    - name: deterministic-agentic-care-capability\n\
  \      description: Deterministic care context.\n      location: file:///opt/naftiko/skills/deterministic-agentic-care-capability\n      allowed-tools: get-care-context\n      tools:\n      - {name: get-care-context, from: {sourceNamespace: deterministic-agentic-care-capability-mcp, action: get-care-context}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/deterministic-agentic-care-capability.yaml
tags:
- Naftiko
- Healthcare
- Deterministic
- Agentic
tools:
- description: ''
  hints:
    readOnly: true
  name: get-care-context
---
