---
categories: []
consumed_apis: []
description: A primer capability used to onboard Avenga consultants to Naftiko — wraps a representative HR/People-Ops API as a capability.
layout: capability
name: Avenga Introduction Primer Capability
operations:
- description: ''
  method: GET
  name: list-employees
  path: /employees
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- governance
- spec-driven integration
- get employee
- list employees
- primer
- avenga
- ai
- api integration
- capabilities
- mcp
- naftiko
slug: avenga-introduction-primer-capability
source_filename: avenga-introduction-primer-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Avenga Introduction Primer Capability\n  description: A primer capability used to onboard Avenga consultants to Naftiko — wraps a representative HR/People-Ops API as a capability.\n  tags: [Naftiko, Avenga, Primer]\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: bamboohr-env\n  keys: {BAMBOOHR_SUBDOMAIN: BAMBOOHR_SUBDOMAIN, BAMBOOHR_TOKEN: BAMBOOHR_TOKEN}\ncapability:\n  consumes:\n  - namespace: bamboohr\n    type: http\n    baseUri: https://api.bamboohr.com\n    authentication: {type: bearer, token: '{{BAMBOOHR_TOKEN}}'}\n    resources:\n    - {name: employees, path: '/api/gateway.php/{{BAMBOOHR_SUBDOMAIN}}/v1/employees/directory', operations: [{name: list-employees, method: GET}]}\n    - name: employee\n      path: '/api/gateway.php/{{BAMBOOHR_SUBDOMAIN}}/v1/employees/{{employee_id}}'\n      operations:\n      - {name: get-employee, method: GET, inputParameters: [{name: employee_id, in: path}]}\n  exposes:\n\
  \  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: avenga-introduction-primer-capability-rest\n    description: REST surface for the Avenga primer.\n    resources:\n    - {name: employees, path: /employees, operations: [{method: GET, name: list-employees, call: bamboohr.list-employees}]}\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: avenga-introduction-primer-capability-mcp\n    description: MCP for the primer demo.\n    tools:\n    - {name: list-employees, hints: {readOnly: true}, call: bamboohr.list-employees}\n    - name: get-employee\n      hints: {readOnly: true}\n      inputParameters: [{name: employee_id, type: string, required: true}]\n      call: bamboohr.get-employee\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: avenga-introduction-primer-capability-skills\n    description: Skill bundle for the primer.\n    skills:\n    - name: avenga-introduction-primer-capability\n      description: Avenga onboarding primer.\n\
  \      location: file:///opt/naftiko/skills/avenga-introduction-primer-capability\n      allowed-tools: list-employees,get-employee\n      tools:\n      - {name: list-employees, from: {sourceNamespace: avenga-introduction-primer-capability-mcp, action: list-employees}}\n      - {name: get-employee, from: {sourceNamespace: avenga-introduction-primer-capability-mcp, action: get-employee}}\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/avenga-introduction-primer-capability.yaml
tags:
- Naftiko
- Avenga
- Primer
tools:
- description: ''
  hints:
    readOnly: true
  name: list-employees
- description: ''
  hints:
    readOnly: true
  name: get-employee
---
