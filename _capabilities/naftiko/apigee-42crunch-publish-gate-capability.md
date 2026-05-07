---
categories: []
consumed_apis: []
description: A capability that wires the Apigee + 42 Crunch publish pipeline into the Naftiko capability publish flow, so capability YAMLs cannot reach production without passing both gates and emit a per-publish audit record back to API governance layer.
layout: capability
name: Apigee 42Crunch Publish Gate Capability
operations:
- description: Run the 42Crunch security audit and the Apigee deployment, returning pass/fail plus the audit record. Blocks if either gate fails.
  method: POST
  name: publish-with-gates
  path: /publish/{{capability_id}}
- description: Retrieve the most recent dual-gate audit record for a capability.
  method: GET
  name: get-audit-record
  path: /audit-record/{{capability_id}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- governance
- get 42crunch audit
- ai
- publish with gates
- mcp
- run the 42crunch security audit and the apigee deployment, returning pass/fail plus the audit record. blocks if either gate fails.
- naftiko
- retrieve the most recent dual-gate audit record for a capability.
- fetch the latest 42crunch security audit report for a registered api.
- list apigee proxies
- 42crunch
- spec-driven integration
- capabilities
- submit a capability for publishing through 42crunch (security audit) and apigee (deployment). returns pass/fail and the per-publish audit record.
- fetch the dual-gate audit record (42crunch audit score + conformance, apigee deployment status) for a capability.
- api integration
- apigee
- list api proxies in the configured apigee organization.
- get audit record
slug: apigee-42crunch-publish-gate-capability
source_filename: apigee-42crunch-publish-gate-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Apigee 42crunch Publish Gate Capability\n  description: A capability that wires the Apigee + 42 Crunch publish pipeline into the Naftiko capability publish flow, so capability YAMLs cannot reach production without passing both gates and emit a per-publish audit record back to API governance layer.\n  tags:\n  - Naftiko\n  - Apigee\n  - 42Crunch\n  - Governance\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: fortytwocrunch-env\n  description: 42Crunch platform API token with audit and conformance scopes.\n  keys:\n    FORTYTWOCRUNCH_TOKEN: FORTYTWOCRUNCH_TOKEN\n- namespace: apigee-env\n  description: Google Apigee credentials and target organization/environment.\n  keys:\n    APIGEE_TOKEN: APIGEE_TOKEN\n    APIGEE_ORG: APIGEE_ORG\n    APIGEE_ENV: APIGEE_ENV\ncapability:\n  consumes:\n  - namespace: fortytwocrunch\n    type: http\n    baseUri: https://platform.42crunch.com\n    authentication:\n      type: bearer\n\
  \      token: '{{FORTYTWOCRUNCH_TOKEN}}'\n    resources:\n    - name: api-audit\n      path: /api/v2/apis/{{api_id}}/assessmentreport\n      operations:\n      - name: get-audit-report\n        method: GET\n        inputParameters:\n        - name: api_id\n          in: path\n          description: 42Crunch API UUID.\n    - name: api-conformance\n      path: /api/v2/apis/{{api_id}}/scanreport\n      operations:\n      - name: get-conformance-report\n        method: GET\n        inputParameters:\n        - name: api_id\n          in: path\n    - name: apis\n      path: /api/v2/apis\n      operations:\n      - name: import-api\n        method: POST\n        description: Upload an OpenAPI spec to 42Crunch which triggers an automatic security audit.\n  - namespace: apigee\n    type: http\n    baseUri: https://apigee.googleapis.com\n    authentication:\n      type: bearer\n      token: '{{APIGEE_TOKEN}}'\n    resources:\n    - name: api-proxies\n      path: /v1/organizations/{{APIGEE_ORG}}/apis\n\
  \      operations:\n      - name: list-api-proxies\n        method: GET\n      - name: import-api-proxy\n        method: POST\n        description: Upload an API proxy bundle. Use action=import&name=<proxy-name>.\n        inputParameters:\n        - name: action\n          in: query\n        - name: name\n          in: query\n    - name: deployments\n      path: /v1/organizations/{{APIGEE_ORG}}/environments/{{APIGEE_ENV}}/apis/{{api_name}}/revisions/{{revision}}/deployments\n      operations:\n      - name: deploy-api-revision\n        method: POST\n        inputParameters:\n        - name: api_name\n          in: path\n        - name: revision\n          in: path\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: apigee-42crunch-publish-gate-capability-rest\n    description: REST API that runs the dual 42Crunch + Apigee publish gate and returns a unified audit record.\n    resources:\n    - name: publish\n      path: /publish/{{capability_id}}\n      operations:\n\
  \      - method: POST\n        name: publish-with-gates\n        description: Run the 42Crunch security audit and the Apigee deployment, returning pass/fail plus the audit record. Blocks if either gate fails.\n        inputParameters:\n        - name: capability_id\n          in: path\n          type: string\n          description: Capability identifier whose underlying OpenAPI spec is being published.\n        call: fortytwocrunch.import-api\n    - name: audit-record\n      path: /audit-record/{{capability_id}}\n      operations:\n      - method: GET\n        name: get-audit-record\n        description: Retrieve the most recent dual-gate audit record for a capability.\n        inputParameters:\n        - name: capability_id\n          in: path\n          type: string\n        call: fortytwocrunch.get-audit-report\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: apigee-42crunch-publish-gate-capability-mcp\n    description: MCP server letting governance agents run and\
  \ query the dual publish gate.\n    tools:\n    - name: publish-with-gates\n      description: Submit a capability for publishing through 42Crunch (security audit) and Apigee (deployment). Returns pass/fail and the per-publish audit record.\n      hints:\n        readOnly: false\n      inputParameters:\n      - name: capability_id\n        type: string\n        required: true\n      call: fortytwocrunch.import-api\n    - name: get-audit-record\n      description: Fetch the dual-gate audit record (42Crunch audit score + conformance, Apigee deployment status) for a capability.\n      hints:\n        readOnly: true\n      inputParameters:\n      - name: capability_id\n        type: string\n        required: true\n      call: fortytwocrunch.get-audit-report\n    - name: get-42crunch-audit\n      description: Fetch the latest 42Crunch security audit report for a registered API.\n      hints:\n        readOnly: true\n      inputParameters:\n      - name: api_id\n        type: string\n      \
  \  required: true\n      call: fortytwocrunch.get-audit-report\n    - name: list-apigee-proxies\n      description: List API proxies in the configured Apigee organization.\n      hints:\n        readOnly: true\n      call: apigee.list-api-proxies\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: apigee-42crunch-publish-gate-capability-skills\n    description: Agent Skill bundle for governance agents enforcing the dual publish gate.\n    skills:\n    - name: apigee-42crunch-publish-gate-capability\n      description: Block capability publishing unless 42Crunch audit and Apigee deployment both succeed; emit an audit record.\n      location: file:///opt/naftiko/skills/apigee-42crunch-publish-gate-capability\n      allowed-tools: publish-with-gates,get-audit-record,get-42crunch-audit,list-apigee-proxies\n      argument-hint: 'Use when promoting a capability to production through Apigee with mandatory 42Crunch security audit.'\n      tools:\n      - name: publish-with-gates\n\
  \        description: Run both gates and publish, or block.\n        from:\n          sourceNamespace: apigee-42crunch-publish-gate-capability-mcp\n          action: publish-with-gates\n      - name: get-audit-record\n        description: Retrieve a per-publish dual-gate audit record.\n        from:\n          sourceNamespace: apigee-42crunch-publish-gate-capability-mcp\n          action: get-audit-record\n      - name: get-42crunch-audit\n        description: Get the 42Crunch security audit report.\n        from:\n          sourceNamespace: apigee-42crunch-publish-gate-capability-mcp\n          action: get-42crunch-audit\n      - name: list-apigee-proxies\n        description: List Apigee proxies.\n        from:\n          sourceNamespace: apigee-42crunch-publish-gate-capability-mcp\n          action: list-apigee-proxies\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/apigee-42crunch-publish-gate-capability.yaml
tags:
- Naftiko
- Apigee
- 42Crunch
- Governance
tools:
- description: Submit a capability for publishing through 42Crunch (security audit) and Apigee (deployment). Returns pass/fail and the per-publish audit record.
  hints:
    readOnly: false
  name: publish-with-gates
- description: Fetch the dual-gate audit record (42Crunch audit score + conformance, Apigee deployment status) for a capability.
  hints:
    readOnly: true
  name: get-audit-record
- description: Fetch the latest 42Crunch security audit report for a registered API.
  hints:
    readOnly: true
  name: get-42crunch-audit
- description: List API proxies in the configured Apigee organization.
  hints:
    readOnly: true
  name: list-apigee-proxies
---
