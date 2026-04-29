---
categories: []
consumed_apis:
- appsmith
description: Workflow capability for building and managing internal tools using the Appsmith low-code platform. Supports developers creating workflow applications with connected datasources and team workspaces.
layout: capability
name: Appsmith Internal Tool Builder
operations: []
personas: []
provider_name: Appsmith
provider_slug: appsmith
search_terms:
- low-code
- workflow automation
- list team workspaces
- list connected datasources
- appsmith
- build and deploy low-code internal tools with appsmith
- lists datasources connected to appsmith for powering internal tools
- open source
- list internal tools
- creating and managing low-code applications
- lists workspaces available for organizing internal tools
- creates a new internal tool application in appsmith
- internal tools
- lists all low-code internal tool applications built in appsmith
- developer productivity
- developer tools
- create internal tool
- builds low-code internal tools and workflow applications
- connecting databases and apis to power application data
- manages workspaces and application access for teams
slug: internal-tool-builder
source_filename: internal-tool-builder.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Appsmith Internal Tool Builder\n  description: >-\n    Workflow capability for building and managing internal tools using the Appsmith\n    low-code platform. Supports developers creating workflow applications with\n    connected datasources and team workspaces.\n  tags:\n    - Appsmith\n    - Low-Code\n    - Internal Tools\n    - Developer Productivity\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      APPSMITH_API_TOKEN: APPSMITH_API_TOKEN\n\ncapability:\n  consumes:\n    - import: appsmith\n      location: ./shared/appsmith-api.yaml\n\n  exposes:\n    - type: mcp\n      port: 9090\n      namespace: internal-tool-mcp\n      transport: http\n      description: MCP server for AI-assisted internal tool building with Appsmith.\n      tools:\n        - name: list-internal-tools\n          description: Lists all low-code internal tool applications built in Appsmith\n          hints:\n\
  \            readOnly: true\n            idempotent: true\n          call: \"appsmith.list-applications\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-internal-tool\n          description: Creates a new internal tool application in Appsmith\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"appsmith.create-application\"\n          with:\n            name: \"tools.name\"\n            workspaceId: \"tools.workspaceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-team-workspaces\n          description: Lists workspaces available for organizing internal tools\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"appsmith.list-workspaces\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-connected-datasources\n\
  \          description: Lists datasources connected to Appsmith for powering internal tools\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"appsmith.list-datasources\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/appsmith/refs/heads/main/capabilities/internal-tool-builder.yaml
tags:
- Appsmith
- Low-Code
- Internal Tools
- Developer Productivity
tools:
- description: Lists all low-code internal tool applications built in Appsmith
  hints:
    idempotent: true
    readOnly: true
  name: list-internal-tools
- description: Creates a new internal tool application in Appsmith
  hints:
    destructive: false
    readOnly: false
  name: create-internal-tool
- description: Lists workspaces available for organizing internal tools
  hints:
    idempotent: true
    readOnly: true
  name: list-team-workspaces
- description: Lists datasources connected to Appsmith for powering internal tools
  hints:
    idempotent: true
    readOnly: true
  name: list-connected-datasources
---
