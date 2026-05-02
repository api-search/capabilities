---
categories: []
consumed_apis: []
description: A capability that ingests Azure DevOps build + release events and auto-fills Backstage entity TechDocs/CI annotations for the relevant service.
layout: capability
name: Azure Devops Pipeline To Backstage Entity
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
- capabilities
- naftiko
- mcp
- example op
- a capability that ingests azure devops build + release events and auto-fills backstage entity techdocs/ci annotations for the relevant service.
- example
- governance
slug: azure-devops-pipeline-to-backstage-entity
source_filename: azure-devops-pipeline-to-backstage-entity.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Azure Devops Pipeline To Backstage Entity\n  description: A capability that ingests Azure DevOps build + release events and auto-fills Backstage entity TechDocs/CI annotations for the relevant service.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: azure-devops-pipeline-to-backstage-entity-rest\n    description: REST API for Azure Devops Pipeline To Backstage Entity.\n    resources:\n    - name: example\n      path:\
  \ /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: azure-devops-pipeline-to-backstage-entity-mcp\n    description: MCP server exposing Azure Devops Pipeline To Backstage Entity for AI agents.\n    tools:\n    - name: example\n      description: A capability that ingests Azure DevOps build + release events and auto-fills Backstage entity TechDocs/CI annotations for the relevant service.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: azure-devops-pipeline-to-backstage-entity-skills\n    description: Agent Skill bundle for Azure Devops Pipeline To Backstage Entity.\n    skills:\n    - name: azure-devops-pipeline-to-backstage-entity\n      description: A capability that ingests Azure DevOps build + release events and auto-fills Backstage entity TechDocs/CI annotations for\
  \ the relevant service.\n      location: file:///opt/naftiko/skills/azure-devops-pipeline-to-backstage-entity\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that ingests Azure DevOps build + release events and auto-fills Backstage entity TechDocs/CI annotations for the relevant service.\n        from:\n          sourceNamespace: azure-devops-pipeline-to-backstage-entity-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/azure-devops-pipeline-to-backstage-entity.yaml
tags:
- Naftiko
tools:
- description: A capability that ingests Azure DevOps build + release events and auto-fills Backstage entity TechDocs/CI annotations for the relevant service.
  hints:
    readOnly: true
  name: example
---
