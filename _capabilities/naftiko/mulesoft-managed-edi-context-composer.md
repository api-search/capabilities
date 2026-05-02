---
categories: []
consumed_apis: []
description: A capability that joins MuleSoft-managed EDI flows + a Salesforce Einstein lookup and returns one composed context object — the integration-sprawl rightsizer for an AI assistant.
layout: capability
name: Mulesoft Managed Edi Context Composer
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- ai
- api integration
- spec-driven integration
- a capability that joins mulesoft-managed edi flows + a salesforce einstein lookup and returns one composed context object — the integration-sprawl rightsizer for an ai assistant.
- capabilities
- naftiko
- mcp
- example op
- example
- governance
slug: mulesoft-managed-edi-context-composer
source_filename: mulesoft-managed-edi-context-composer.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Mulesoft Managed Edi Context Composer\n  description: A capability that joins MuleSoft-managed EDI flows + a Salesforce Einstein lookup and returns one composed context object — the integration-sprawl rightsizer for an AI assistant.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: mulesoft-managed-edi-context-composer-rest\n    description: REST API for Mulesoft Managed Edi Context Composer.\n    resources:\n    - name:\
  \ example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: mulesoft-managed-edi-context-composer-mcp\n    description: MCP server exposing Mulesoft Managed Edi Context Composer for AI agents.\n    tools:\n    - name: example\n      description: A capability that joins MuleSoft-managed EDI flows + a Salesforce Einstein lookup and returns one composed context object — the integration-sprawl rightsizer for an AI assistant.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: mulesoft-managed-edi-context-composer-skills\n    description: Agent Skill bundle for Mulesoft Managed Edi Context Composer.\n    skills:\n    - name: mulesoft-managed-edi-context-composer\n      description: A capability that joins MuleSoft-managed EDI flows + a Salesforce Einstein lookup and\
  \ returns one composed context object — the integration-sprawl rightsizer for an AI assistant.\n      location: file:///opt/naftiko/skills/mulesoft-managed-edi-context-composer\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that joins MuleSoft-managed EDI flows + a Salesforce Einstein lookup and returns one composed context object — the integration-sprawl rightsizer for an AI assistant.\n        from:\n          sourceNamespace: mulesoft-managed-edi-context-composer-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/mulesoft-managed-edi-context-composer.yaml
tags:
- Naftiko
tools:
- description: A capability that joins MuleSoft-managed EDI flows + a Salesforce Einstein lookup and returns one composed context object — the integration-sprawl rightsizer for an AI assistant.
  hints:
    readOnly: true
  name: example
---
