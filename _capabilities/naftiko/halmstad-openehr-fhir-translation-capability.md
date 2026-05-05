---
categories: []
consumed_apis: []
description: A capability translating between openEHR archetypes and FHIR resources for the Halmstad health-data project, exposing both surfaces from one capability.
layout: capability
name: Halmstad Openehr Fhir Translation Capability
operations:
- description: ''
  method: GET
  name: translate-openehr-to-fhir
  path: /translate/openehr-to-fhir/{{composition_id}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- fhir
- get fhir observation
- spec-driven integration
- translation
- mcp
- translate openehr to fhir
- capabilities
- openehr
- naftiko
- api integration
- governance
- ai
slug: halmstad-openehr-fhir-translation-capability
source_filename: halmstad-openehr-fhir-translation-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Halmstad Openehr Fhir Translation Capability\n  description: A capability translating between openEHR archetypes and FHIR resources for the Halmstad health-data project, exposing both surfaces from one capability.\n  tags: [Naftiko, openEHR, FHIR, Translation]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: openehr-env\n  keys: {OPENEHR_HOST: OPENEHR_HOST, OPENEHR_TOKEN: OPENEHR_TOKEN}\n- namespace: fhir-env\n  keys: {FHIR_HOST: FHIR_HOST, FHIR_TOKEN: FHIR_TOKEN}\ncapability:\n  consumes:\n  - namespace: openehr\n    type: http\n    baseUri: https://{{OPENEHR_HOST}}\n    authentication: {type: bearer, token: '{{OPENEHR_TOKEN}}'}\n    resources:\n    - name: composition\n      path: '/rest/v1/composition/{{composition_id}}'\n      operations:\n      - {name: get-openehr-composition, method: GET, inputParameters: [{name: composition_id, in: path}]}\n  - namespace: fhir\n    type: http\n    baseUri: https://{{FHIR_HOST}}\n\
  \    authentication: {type: bearer, token: '{{FHIR_TOKEN}}'}\n    resources:\n    - name: observation\n      path: '/Observation/{{id}}'\n      operations:\n      - {name: get-fhir-observation, method: GET, inputParameters: [{name: id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: halmstad-openehr-fhir-translation-capability-rest\n    description: REST surface for openEHR↔FHIR translation.\n    resources:\n    - {name: translate, path: '/translate/openehr-to-fhir/{{composition_id}}', operations: [{method: GET, name: translate-openehr-to-fhir, inputParameters: [{name: composition_id, in: path, type: string}], call: openehr.get-openehr-composition}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: halmstad-openehr-fhir-translation-capability-mcp\n    description: MCP for openEHR↔FHIR translation.\n    tools:\n    - name: translate-openehr-to-fhir\n      hints: {readOnly: true}\n      inputParameters: [{name: composition_id,\
  \ type: string, required: true}]\n      call: openehr.get-openehr-composition\n    - name: get-fhir-observation\n      hints: {readOnly: true}\n      inputParameters: [{name: id, type: string, required: true}]\n      call: fhir.get-fhir-observation\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: halmstad-openehr-fhir-translation-capability-skills\n    description: Skill for openEHR↔FHIR translation.\n    skills:\n    - name: halmstad-openehr-fhir-translation-capability\n      description: openEHR↔FHIR translation.\n      location: file:///opt/naftiko/skills/halmstad-openehr-fhir-translation-capability\n      allowed-tools: translate-openehr-to-fhir,get-fhir-observation\n      tools:\n      - {name: translate-openehr-to-fhir, from: {sourceNamespace: halmstad-openehr-fhir-translation-capability-mcp, action: translate-openehr-to-fhir}}\n      - {name: get-fhir-observation, from: {sourceNamespace: halmstad-openehr-fhir-translation-capability-mcp, action: get-fhir-observation}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/halmstad-openehr-fhir-translation-capability.yaml
tags:
- Naftiko
- openEHR
- FHIR
- Translation
tools:
- description: ''
  hints:
    readOnly: true
  name: translate-openehr-to-fhir
- description: ''
  hints:
    readOnly: true
  name: get-fhir-observation
---
