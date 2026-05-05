---
categories: []
consumed_apis: []
description: A sandbox capability for the Halmstad/Mölnlycke/Avenga wound-care collaboration — wraps wound-imaging API plus a clinical decision-support call.
layout: capability
name: Halmstad Molnlycke Avenga Wound Care Sandbox
operations:
- description: ''
  method: GET
  name: get-wound-assessment
  path: /assessments/{{image_id}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- healthcare
- wound care
- spec-driven integration
- sandbox
- get wound assessment
- mcp
- capabilities
- naftiko
- upload wound image
- api integration
- governance
- ai
slug: halmstad-molnlycke-avenga-wound-care-sandbox
source_filename: halmstad-molnlycke-avenga-wound-care-sandbox.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Halmstad Molnlycke Avenga Wound Care Sandbox\n  description: A sandbox capability for the Halmstad/Mölnlycke/Avenga wound-care collaboration — wraps wound-imaging API plus a clinical decision-support call.\n  tags: [Naftiko, Healthcare, Wound Care, Sandbox]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: molnlycke-env\n  keys: {MOLNLYCKE_HOST: MOLNLYCKE_HOST, MOLNLYCKE_TOKEN: MOLNLYCKE_TOKEN}\ncapability:\n  consumes:\n  - namespace: molnlycke\n    type: http\n    baseUri: https://{{MOLNLYCKE_HOST}}\n    authentication: {type: bearer, token: '{{MOLNLYCKE_TOKEN}}'}\n    resources:\n    - {name: wound-images, path: /api/v1/wound-images, operations: [{name: upload-wound-image, method: POST}]}\n    - name: wound-assessment\n      path: '/api/v1/wound-images/{{image_id}}/assessment'\n      operations:\n      - {name: get-wound-assessment, method: GET, inputParameters: [{name: image_id, in: path}]}\n  exposes:\n  - type:\
  \ rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: halmstad-molnlycke-avenga-wound-care-sandbox-rest\n    description: Sandbox REST surface for wound-care.\n    resources:\n    - {name: assessments, path: '/assessments/{{image_id}}', operations: [{method: GET, name: get-wound-assessment, inputParameters: [{name: image_id, in: path, type: string}], call: molnlycke.get-wound-assessment}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: halmstad-molnlycke-avenga-wound-care-sandbox-mcp\n    description: MCP for wound-care sandbox.\n    tools:\n    - name: get-wound-assessment\n      hints: {readOnly: true}\n      inputParameters: [{name: image_id, type: string, required: true}]\n      call: molnlycke.get-wound-assessment\n    - name: upload-wound-image\n      call: molnlycke.upload-wound-image\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: halmstad-molnlycke-avenga-wound-care-sandbox-skills\n    description: Skill for wound-care sandbox.\n\
  \    skills:\n    - name: halmstad-molnlycke-avenga-wound-care-sandbox\n      description: Wound-care sandbox.\n      location: file:///opt/naftiko/skills/halmstad-molnlycke-avenga-wound-care-sandbox\n      allowed-tools: get-wound-assessment,upload-wound-image\n      tools:\n      - {name: get-wound-assessment, from: {sourceNamespace: halmstad-molnlycke-avenga-wound-care-sandbox-mcp, action: get-wound-assessment}}\n      - {name: upload-wound-image, from: {sourceNamespace: halmstad-molnlycke-avenga-wound-care-sandbox-mcp, action: upload-wound-image}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/halmstad-molnlycke-avenga-wound-care-sandbox.yaml
tags:
- Naftiko
- Healthcare
- Wound Care
- Sandbox
tools:
- description: ''
  hints:
    readOnly: true
  name: get-wound-assessment
- description: ''
  hints: {}
  name: upload-wound-image
---
