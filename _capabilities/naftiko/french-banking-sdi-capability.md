---
categories: []
consumed_apis: []
description: A French-banking capability with SDI methodology language in the spec, paired with a Compliance Frameworks (GDPR) governance layer.
layout: capability
name: French Banking Sdi Capability
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- example
- mcp
- ai
- naftiko
- api integration
- spec-driven integration
- capabilities
- a french-banking capability with sdi methodology language in the spec, paired with a compliance frameworks (gdpr) governance layer.
- example op
- governance
slug: french-banking-sdi-capability
source_filename: french-banking-sdi-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: French Banking Sdi Capability\n  description: A French-banking capability with SDI methodology language in the spec, paired with a Compliance Frameworks (GDPR) governance layer.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: french-banking-sdi-capability-rest\n    description: REST API for French Banking Sdi Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method:\
  \ GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: french-banking-sdi-capability-mcp\n    description: MCP server exposing French Banking Sdi Capability for AI agents.\n    tools:\n    - name: example\n      description: A French-banking capability with SDI methodology language in the spec, paired with a Compliance Frameworks (GDPR) governance layer.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: french-banking-sdi-capability-skills\n    description: Agent Skill bundle for French Banking Sdi Capability.\n    skills:\n    - name: french-banking-sdi-capability\n      description: A French-banking capability with SDI methodology language in the spec, paired with a Compliance Frameworks (GDPR) governance layer.\n      location: file:///opt/naftiko/skills/french-banking-sdi-capability\n      allowed-tools: example\n\
  \      tools:\n      - name: example\n        description: A French-banking capability with SDI methodology language in the spec, paired with a Compliance Frameworks (GDPR) governance layer.\n        from:\n          sourceNamespace: french-banking-sdi-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/french-banking-sdi-capability.yaml
tags:
- Naftiko
tools:
- description: A French-banking capability with SDI methodology language in the spec, paired with a Compliance Frameworks (GDPR) governance layer.
  hints:
    readOnly: true
  name: example
---
