---
categories: []
consumed_apis: []
description: A payer-grade compliance capability over healthcare APIs that enforces HIPAA-aligned policies (audit, minimum necessary, BAA boundary) on every call.
layout: capability
name: Compliance Payer Grade Capability
operations:
- description: ''
  method: GET
  name: get-governed-patient
  path: /patients/{{patient_id}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- healthcare
- spec-driven integration
- compliance
- hipaa
- get patient
- search claims
- mcp
- capabilities
- naftiko
- api integration
- governance
- ai
- get governed patient
slug: compliance-payer-grade-capability
source_filename: compliance-payer-grade-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Compliance Payer Grade Capability\n  description: A payer-grade compliance capability over healthcare APIs that enforces HIPAA-aligned policies (audit, minimum necessary, BAA boundary) on every call.\n  tags: [Naftiko, Healthcare, HIPAA, Compliance]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: fhir-env\n  keys: {FHIR_HOST: FHIR_HOST, FHIR_TOKEN: FHIR_TOKEN}\ncapability:\n  consumes:\n  - namespace: fhir\n    type: http\n    baseUri: https://{{FHIR_HOST}}\n    authentication: {type: bearer, token: '{{FHIR_TOKEN}}'}\n    resources:\n    - name: patient\n      path: /Patient/{{patient_id}}\n      operations:\n      - {name: get-patient, method: GET, inputParameters: [{name: patient_id, in: path}]}\n    - name: claim\n      path: /Claim/{{claim_id}}\n      operations:\n      - {name: get-claim, method: GET, inputParameters: [{name: claim_id, in: path}]}\n    - {name: claims, path: /Claim, operations: [{name: search-claims,\
  \ method: GET}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: compliance-payer-grade-capability-rest\n    description: HIPAA-policy-gated FHIR surface.\n    resources:\n    - name: patient\n      path: /patients/{{patient_id}}\n      operations:\n      - {method: GET, name: get-governed-patient, inputParameters: [{name: patient_id, in: path, type: string}], call: fhir.get-patient}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: compliance-payer-grade-capability-mcp\n    description: MCP for HIPAA-policy-gated FHIR ops.\n    tools:\n    - name: get-patient\n      hints: {readOnly: true}\n      inputParameters: [{name: patient_id, type: string, required: true}]\n      call: fhir.get-patient\n    - name: search-claims\n      hints: {readOnly: true}\n      call: fhir.search-claims\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: compliance-payer-grade-capability-skills\n    description: Skill for payer-grade compliance.\n\
  \    skills:\n    - name: compliance-payer-grade-capability\n      description: Payer-grade FHIR governance.\n      location: file:///opt/naftiko/skills/compliance-payer-grade-capability\n      allowed-tools: get-patient,search-claims\n      tools:\n      - {name: get-patient, from: {sourceNamespace: compliance-payer-grade-capability-mcp, action: get-patient}}\n      - {name: search-claims, from: {sourceNamespace: compliance-payer-grade-capability-mcp, action: search-claims}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/compliance-payer-grade-capability.yaml
tags:
- Naftiko
- Healthcare
- HIPAA
- Compliance
tools:
- description: ''
  hints:
    readOnly: true
  name: get-patient
- description: ''
  hints:
    readOnly: true
  name: search-claims
---
