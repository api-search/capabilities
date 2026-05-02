---
categories: []
consumed_apis: []
description: A capability that consumes Figma design system (files, components, tokens) and exposes the design-system context as REST + MCP tools so AI-assisted UI work in Copilot/Claude grounds against the actual brand library instead of hallucinating component names.
layout: capability
name: Figma Design System Context Capability
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
- a capability that consumes figma design system (files, components, tokens) and exposes the design-system context as rest + mcp tools so ai-assisted ui work in copilot/claude grounds against the actual brand library instead of hallucinating component names.
- capabilities
- naftiko
- mcp
- example op
- example
- governance
slug: figma-design-system-context-capability
source_filename: figma-design-system-context-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Figma Design System Context Capability\n  description: A capability that consumes Figma design system (files, components, tokens) and exposes the design-system context as REST + MCP tools so AI-assisted UI work in Copilot/Claude grounds against the actual brand library instead of hallucinating component names.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: figma-design-system-context-capability-rest\n    description:\
  \ REST API for Figma Design System Context Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: figma-design-system-context-capability-mcp\n    description: MCP server exposing Figma Design System Context Capability for AI agents.\n    tools:\n    - name: example\n      description: A capability that consumes Figma design system (files, components, tokens) and exposes the design-system context as REST + MCP tools so AI-assisted UI work in Copilot/Claude grounds against the actual brand library instead of hallucinating component names.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: figma-design-system-context-capability-skills\n    description: Agent Skill bundle for Figma Design System Context Capability.\n  \
  \  skills:\n    - name: figma-design-system-context-capability\n      description: A capability that consumes Figma design system (files, components, tokens) and exposes the design-system context as REST + MCP tools so AI-assisted UI work in Copilot/Claude grounds against the actual brand library instead of hallucinating component names.\n      location: file:///opt/naftiko/skills/figma-design-system-context-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A capability that consumes Figma design system (files, components, tokens) and exposes the design-system context as REST + MCP tools so AI-assisted UI work in Copilot/Claude grounds against the actual brand library instead of hallucinating component names.\n        from:\n          sourceNamespace: figma-design-system-context-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/figma-design-system-context-capability.yaml
tags:
- Naftiko
tools:
- description: A capability that consumes Figma design system (files, components, tokens) and exposes the design-system context as REST + MCP tools so AI-assisted UI work in Copilot/Claude grounds against the actual brand library instead of hallucinating component names.
  hints:
    readOnly: true
  name: example
---
