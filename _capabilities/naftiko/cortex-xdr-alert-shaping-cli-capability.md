---
categories: []
consumed_apis: []
description: A CLI-runnable capability wrapping the Cortex XDR alerts API, returning a shaped agent context object — designed to bypass the Docker container startup blocker.
layout: capability
name: Cortex Xdr Alert Shaping Cli Capability
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
- a cli-runnable capability wrapping the cortex xdr alerts api, returning a shaped agent context object — designed to bypass the docker container startup blocker.
- capabilities
- example op
- governance
slug: cortex-xdr-alert-shaping-cli-capability
source_filename: cortex-xdr-alert-shaping-cli-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Cortex Xdr Alert Shaping Cli Capability\n  description: A CLI-runnable capability wrapping the Cortex XDR alerts API, returning a shaped agent context object — designed to bypass the Docker container startup blocker.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: cortex-xdr-alert-shaping-cli-capability-rest\n    description: REST API for Cortex Xdr Alert Shaping Cli Capability.\n    resources:\n    - name: example\n\
  \      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: cortex-xdr-alert-shaping-cli-capability-mcp\n    description: MCP server exposing Cortex Xdr Alert Shaping Cli Capability for AI agents.\n    tools:\n    - name: example\n      description: A CLI-runnable capability wrapping the Cortex XDR alerts API, returning a shaped agent context object — designed to bypass the Docker container startup blocker.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: cortex-xdr-alert-shaping-cli-capability-skills\n    description: Agent Skill bundle for Cortex Xdr Alert Shaping Cli Capability.\n    skills:\n    - name: cortex-xdr-alert-shaping-cli-capability\n      description: A CLI-runnable capability wrapping the Cortex XDR alerts API, returning a shaped agent context object\
  \ — designed to bypass the Docker container startup blocker.\n      location: file:///opt/naftiko/skills/cortex-xdr-alert-shaping-cli-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A CLI-runnable capability wrapping the Cortex XDR alerts API, returning a shaped agent context object — designed to bypass the Docker container startup blocker.\n        from:\n          sourceNamespace: cortex-xdr-alert-shaping-cli-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/cortex-xdr-alert-shaping-cli-capability.yaml
tags:
- Naftiko
tools:
- description: A CLI-runnable capability wrapping the Cortex XDR alerts API, returning a shaped agent context object — designed to bypass the Docker container startup blocker.
  hints:
    readOnly: true
  name: example
---
