---
categories: []
consumed_apis: []
description: A capability that fans out across GitHub + GitLab + Bitbucket scan results from and exposes a unified MCP shift-left view.
layout: capability
name: Gitlab Bitbucket Multi Scm Shift Left Capability
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
- example op
- a capability that fans out across github + gitlab + bitbucket scan results from and exposes a unified mcp shift-left view.
- governance
slug: gitlab-bitbucket-multi-scm-shift-left-capability
source_filename: gitlab-bitbucket-multi-scm-shift-left-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Gitlab Bitbucket Multi Scm Shift Left Capability\n  description: A capability that fans out across GitHub + GitLab + Bitbucket scan results from and exposes a unified MCP shift-left view.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: gitlab-bitbucket-multi-scm-shift-left-capability-rest\n    description: REST API for Gitlab Bitbucket Multi Scm Shift Left Capability.\n    resources:\n    - name: example\n      path:\
  \ /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: gitlab-bitbucket-multi-scm-shift-left-capability-mcp\n    description: MCP server exposing Gitlab Bitbucket Multi Scm Shift Left Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability that fans out across GitHub + GitLab + Bitbucket scan results from and exposes a unified MCP shift-left view.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: gitlab-bitbucket-multi-scm-shift-left-capability-skills\n    description: Agent Skill bundle for Gitlab Bitbucket Multi Scm Shift Left Capability.\n    skills:\n    - name: gitlab-bitbucket-multi-scm-shift-left-capability\n      description: A capability that fans out across GitHub + GitLab + Bitbucket scan results from and exposes a unified MCP\
  \ shift-left view.\n      location: file:///opt/naftiko/skills/gitlab-bitbucket-multi-scm-shift-left-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that fans out across GitHub + GitLab + Bitbucket scan results from and exposes a unified MCP shift-left view.\n        from:\n          sourceNamespace: gitlab-bitbucket-multi-scm-shift-left-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/gitlab-bitbucket-multi-scm-shift-left-capability.yaml
tags:
- Naftiko
tools:
- description: A capability that fans out across GitHub + GitLab + Bitbucket scan results from and exposes a unified MCP shift-left view.
  hints:
    readOnly: true
  name: example
---
