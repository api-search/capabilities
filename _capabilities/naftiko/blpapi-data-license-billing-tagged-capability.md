---
categories: []
consumed_apis: []
description: A capability over BLPAPI Data License that tags every read with billing metadata so per-team attribution is automatic.
layout: capability
name: Blpapi Data License Billing Tagged Capability
operations:
- description: Submit a billing-tagged BLPAPI request.
  method: POST
  name: query-tagged
  path: /query
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- query tagged
- blpapi
- bloomberg
- governance
- spec-driven integration
- submit a billing-tagged blpapi request.
- ai
- capabilities
- billing
- api integration
- get response
- mcp
- naftiko
slug: blpapi-data-license-billing-tagged-capability
source_filename: blpapi-data-license-billing-tagged-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Blpapi Data License Billing Tagged Capability\n  description: A capability over BLPAPI Data License that tags every read with billing metadata so per-team attribution is automatic.\n  tags: [Naftiko, Bloomberg, BLPAPI, Billing]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: bloomberg-env\n  keys: {BLOOMBERG_TOKEN: BLOOMBERG_TOKEN}\ncapability:\n  consumes:\n  - namespace: blpapi\n    type: http\n    baseUri: https://api.bloomberg.com\n    authentication: {type: bearer, token: '{{BLOOMBERG_TOKEN}}'}\n    resources:\n    - {name: requests, path: /eap/dl/v1/requests, operations: [{name: create-data-request, method: POST}]}\n    - name: request\n      path: /eap/dl/v1/requests/{{request_id}}\n      operations:\n      - {name: get-request, method: GET, inputParameters: [{name: request_id, in: path}]}\n    - name: responses\n      path: /eap/dl/v1/responses/{{response_id}}\n      operations:\n      - {name: get-response,\
  \ method: GET, inputParameters: [{name: response_id, in: path}]}\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: blpapi-data-license-billing-tagged-capability-rest\n    description: REST surface for billing-tagged BLPAPI data reads.\n    resources:\n    - {name: query, path: /query, operations: [{method: POST, name: query-tagged, description: Submit a billing-tagged BLPAPI request., call: blpapi.create-data-request}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: blpapi-data-license-billing-tagged-capability-mcp\n    description: MCP for tagged BLPAPI reads.\n    tools:\n    - {name: query-tagged, call: blpapi.create-data-request}\n    - name: get-response\n      hints: {readOnly: true}\n      inputParameters: [{name: response_id, type: string, required: true}]\n      call: blpapi.get-response\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: blpapi-data-license-billing-tagged-capability-skills\n    description:\
  \ Skill for billing-tagged BLPAPI.\n    skills:\n    - name: blpapi-data-license-billing-tagged-capability\n      description: Billing-tagged BLPAPI Data License reads.\n      location: file:///opt/naftiko/skills/blpapi-data-license-billing-tagged-capability\n      allowed-tools: query-tagged,get-response\n      tools:\n      - {name: query-tagged, from: {sourceNamespace: blpapi-data-license-billing-tagged-capability-mcp, action: query-tagged}}\n      - {name: get-response, from: {sourceNamespace: blpapi-data-license-billing-tagged-capability-mcp, action: get-response}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/blpapi-data-license-billing-tagged-capability.yaml
tags:
- Naftiko
- Bloomberg
- BLPAPI
- Billing
tools:
- description: ''
  hints: {}
  name: query-tagged
- description: ''
  hints:
    readOnly: true
  name: get-response
---
