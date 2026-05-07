---
categories: []
consumed_apis: []
description: A capability over the European Health Data Space (EHDS) for cross-border care context — patient summaries shaped for clinician access across EU member states.
layout: capability
name: Halmstad Ehds Cross Border Care Context Capability
operations:
- description: ''
  method: GET
  name: get-care-context
  path: /patients/{{patient_id}}/care-context
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- get patient summary
- governance
- spec-driven integration
- cross-border
- ehds
- ai
- capabilities
- get care context
- api integration
- mcp
- naftiko
- halmstad
slug: halmstad-ehds-cross-border-care-context-capability
source_filename: halmstad-ehds-cross-border-care-context-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Halmstad Ehds Cross Border Care Context Capability\n  description: A capability over the European Health Data Space (EHDS) for cross-border care context — patient summaries shaped for clinician access across EU member states.\n  tags: [Naftiko, EHDS, Halmstad, Cross-Border]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: ehds-env\n  keys: {EHDS_HOST: EHDS_HOST, EHDS_TOKEN: EHDS_TOKEN}\ncapability:\n  consumes:\n  - namespace: ehds\n    type: http\n    baseUri: https://{{EHDS_HOST}}\n    authentication: {type: bearer, token: '{{EHDS_TOKEN}}'}\n    resources:\n    - name: patient-summary\n      path: /ehds/v1/patients/{{patient_id}}/summary\n      operations:\n      - {name: get-patient-summary, method: GET, inputParameters: [{name: patient_id, in: path}]}\n    - name: cross-border-record\n      path: /ehds/v1/patients/{{patient_id}}/cross-border-records\n      operations:\n      - {name: list-cross-border-records,\
  \ method: GET, inputParameters: [{name: patient_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: halmstad-ehds-cross-border-care-context-capability-rest\n    description: REST surface for cross-border care context.\n    resources:\n    - name: care-context\n      path: /patients/{{patient_id}}/care-context\n      operations:\n      - {method: GET, name: get-care-context, inputParameters: [{name: patient_id, in: path, type: string}], call: ehds.get-patient-summary}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: halmstad-ehds-cross-border-care-context-capability-mcp\n    description: MCP for cross-border care.\n    tools:\n    - name: get-patient-summary\n      hints: {readOnly: true}\n      inputParameters: [{name: patient_id, type: string, required: true}]\n      call: ehds.get-patient-summary\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: halmstad-ehds-cross-border-care-context-capability-skills\n\
  \    description: Skill for EHDS care context.\n    skills:\n    - name: halmstad-ehds-cross-border-care-context-capability\n      description: EHDS cross-border care context.\n      location: file:///opt/naftiko/skills/halmstad-ehds-cross-border-care-context-capability\n      allowed-tools: get-patient-summary\n      tools:\n      - {name: get-patient-summary, from: {sourceNamespace: halmstad-ehds-cross-border-care-context-capability-mcp, action: get-patient-summary}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/halmstad-ehds-cross-border-care-context-capability.yaml
tags:
- Naftiko
- EHDS
- Halmstad
- Cross-Border
tools:
- description: ''
  hints:
    readOnly: true
  name: get-patient-summary
---
