---
categories: []
consumed_apis: []
description: A capability that consumes Figma design system (files, components, tokens) and exposes the design-system context as REST + MCP tools so AI-assisted UI work in Copilot/Claude grounds against the actual brand library instead of hallucinating component names.
layout: capability
name: Figma Design System Context Capability
operations:
- description: Return components, component sets, styles, and local variables for a Figma file as a single design-system snapshot.
  method: GET
  name: get-design-system-context
  path: /design-system/{{file_key}}
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- list local variables (design tokens) defined in a figma file. requires enterprise plan.
- governance
- figma
- spec-driven integration
- get design system context
- design system
- list all published components in a figma file (name, key, description, containing_frame).
- list color, text, effect, and grid styles defined in a figma file.
- list styles
- return components, component sets, styles, and local variables for a figma file as a single design-system snapshot.
- list local variables
- ai
- api integration
- list components
- capabilities
- mcp
- fetch components, component sets, styles, and design tokens (local variables) for a figma file so an agent can ground ui suggestions against the real brand library.
- naftiko
slug: figma-design-system-context-capability
source_filename: figma-design-system-context-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Figma Design System Context Capability\n  description: A capability that consumes Figma design system (files, components, tokens) and exposes the design-system context as REST + MCP tools so AI-assisted UI work in Copilot/Claude grounds against the actual brand library instead of hallucinating component names.\n  tags:\n  - Naftiko\n  - Figma\n  - Design System\n  created: '2026-05-01'\n  modified: '2026-05-04'\nbinds:\n- namespace: figma-env\n  description: Figma personal access token or OAuth bearer with file_read scope.\n  keys:\n    FIGMA_TOKEN: FIGMA_TOKEN\ncapability:\n  consumes:\n  - namespace: figma\n    type: http\n    baseUri: https://api.figma.com\n    authentication:\n      type: bearer\n      token: '{{FIGMA_TOKEN}}'\n    resources:\n    - name: file\n      path: /v1/files/{{file_key}}\n      operations:\n      - name: get-file\n        method: GET\n        inputParameters:\n        - name: file_key\n          in: path\n\
  \          description: Figma file key (from the file URL).\n    - name: components\n      path: /v1/files/{{file_key}}/components\n      operations:\n      - name: list-components\n        method: GET\n        inputParameters:\n        - name: file_key\n          in: path\n    - name: component-sets\n      path: /v1/files/{{file_key}}/component_sets\n      operations:\n      - name: list-component-sets\n        method: GET\n        inputParameters:\n        - name: file_key\n          in: path\n    - name: styles\n      path: /v1/files/{{file_key}}/styles\n      operations:\n      - name: list-styles\n        method: GET\n        inputParameters:\n        - name: file_key\n          in: path\n    - name: variables\n      path: /v1/files/{{file_key}}/variables/local\n      operations:\n      - name: list-local-variables\n        method: GET\n        inputParameters:\n        - name: file_key\n          in: path\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace:\
  \ figma-design-system-context-capability-rest\n    description: REST API exposing a unified Figma design-system context for a given file.\n    resources:\n    - name: design-system\n      path: /design-system/{{file_key}}\n      operations:\n      - method: GET\n        name: get-design-system-context\n        description: Return components, component sets, styles, and local variables for a Figma file as a single design-system snapshot.\n        inputParameters:\n        - name: file_key\n          in: path\n          type: string\n          description: Figma file key.\n        call: figma.get-file\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: figma-design-system-context-capability-mcp\n    description: MCP server exposing the Figma design system as grounded context for AI coding agents.\n    tools:\n    - name: get-design-system-context\n      description: Fetch components, component sets, styles, and design tokens (local variables) for a Figma file so an agent\
  \ can ground UI suggestions against the real brand library.\n      hints:\n        readOnly: true\n      inputParameters:\n      - name: file_key\n        type: string\n        required: true\n        description: Figma file key.\n      call: figma.get-file\n    - name: list-components\n      description: List all published components in a Figma file (name, key, description, containing_frame).\n      hints:\n        readOnly: true\n      inputParameters:\n      - name: file_key\n        type: string\n        required: true\n      call: figma.list-components\n    - name: list-styles\n      description: List color, text, effect, and grid styles defined in a Figma file.\n      hints:\n        readOnly: true\n      inputParameters:\n      - name: file_key\n        type: string\n        required: true\n      call: figma.list-styles\n    - name: list-local-variables\n      description: List local variables (design tokens) defined in a Figma file. Requires Enterprise plan.\n      hints:\n   \
  \     readOnly: true\n      inputParameters:\n      - name: file_key\n        type: string\n        required: true\n      call: figma.list-local-variables\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: figma-design-system-context-capability-skills\n    description: Agent Skill bundle that gives Claude Code or Copilot grounded access to a Figma design system.\n    skills:\n    - name: figma-design-system-context-capability\n      description: Ground UI generation against a real Figma design system rather than hallucinated component names.\n      location: file:///opt/naftiko/skills/figma-design-system-context-capability\n      allowed-tools: get-design-system-context,list-components,list-styles,list-local-variables\n      argument-hint: 'Use when generating or refactoring UI code that should match an existing Figma design system.'\n      tools:\n      - name: get-design-system-context\n        description: Unified design-system snapshot for a Figma file.\n      \
  \  from:\n          sourceNamespace: figma-design-system-context-capability-mcp\n          action: get-design-system-context\n      - name: list-components\n        description: List published components.\n        from:\n          sourceNamespace: figma-design-system-context-capability-mcp\n          action: list-components\n      - name: list-styles\n        description: List color/text/effect/grid styles.\n        from:\n          sourceNamespace: figma-design-system-context-capability-mcp\n          action: list-styles\n      - name: list-local-variables\n        description: List local variables (design tokens).\n        from:\n          sourceNamespace: figma-design-system-context-capability-mcp\n          action: list-local-variables\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/figma-design-system-context-capability.yaml
tags:
- Naftiko
- Figma
- Design System
tools:
- description: Fetch components, component sets, styles, and design tokens (local variables) for a Figma file so an agent can ground UI suggestions against the real brand library.
  hints:
    readOnly: true
  name: get-design-system-context
- description: List all published components in a Figma file (name, key, description, containing_frame).
  hints:
    readOnly: true
  name: list-components
- description: List color, text, effect, and grid styles defined in a Figma file.
  hints:
    readOnly: true
  name: list-styles
- description: List local variables (design tokens) defined in a Figma file. Requires Enterprise plan.
  hints:
    readOnly: true
  name: list-local-variables
---
