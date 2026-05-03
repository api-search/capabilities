---
categories: []
consumed_apis: []
description: A capability over SharePoint document search that rightsizes the response to a token-budgeted Copilot context object.
layout: capability
name: M365 Sharepoint Document Rightsize Capability
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
- a capability over sharepoint document search that rightsizes the response to a token-budgeted copilot context object.
- example op
- governance
slug: m365-sharepoint-document-rightsize-capability
source_filename: m365-sharepoint-document-rightsize-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: M365 Sharepoint Document Rightsize Capability\n  description: A capability over SharePoint document search that rightsizes the response to a token-budgeted Copilot context object.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: m365-sharepoint-document-rightsize-capability-rest\n    description: REST API for M365 Sharepoint Document Rightsize Capability.\n    resources:\n    - name: example\n      path: /example\n\
  \      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: m365-sharepoint-document-rightsize-capability-mcp\n    description: MCP server exposing M365 Sharepoint Document Rightsize Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability over SharePoint document search that rightsizes the response to a token-budgeted Copilot context object.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: m365-sharepoint-document-rightsize-capability-skills\n    description: Agent Skill bundle for M365 Sharepoint Document Rightsize Capability.\n    skills:\n    - name: m365-sharepoint-document-rightsize-capability\n      description: A capability over SharePoint document search that rightsizes the response to a token-budgeted Copilot context object.\n      location: file:///opt/naftiko/skills/m365-sharepoint-document-rightsize-capability\n\
  \      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability over SharePoint document search that rightsizes the response to a token-budgeted Copilot context object.\n        from:\n          sourceNamespace: m365-sharepoint-document-rightsize-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/m365-sharepoint-document-rightsize-capability.yaml
tags:
- Naftiko
tools:
- description: A capability over SharePoint document search that rightsizes the response to a token-budgeted Copilot context object.
  hints:
    readOnly: true
  name: example
---
