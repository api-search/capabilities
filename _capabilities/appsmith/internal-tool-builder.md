---
categories: []
consumed_apis: []
description: Workflow capability for building and managing internal tools using the Appsmith low-code platform. Supports developers creating workflow applications with connected datasources and team workspaces.
layout: capability
name: Appsmith Internal Tool Builder
operations: []
personas: []
provider_name: Appsmith
provider_slug: appsmith
search_terms:
- appsmith
- list team workspaces
- low-code
- developer tools
- manages workspaces and application access for teams
- lists all low-code internal tool applications built in appsmith
- list connected datasources
- open source
- builds low-code internal tools and workflow applications
- build and deploy low-code internal tools with appsmith
- lists datasources connected to appsmith for powering internal tools
- workflow automation
- developer productivity
- creates a new internal tool application in appsmith
- internal tools
- list internal tools
- create internal tool
- connecting databases and apis to power application data
- lists workspaces available for organizing internal tools
- creating and managing low-code applications
slug: internal-tool-builder
source_filename: internal-tool-builder.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Appsmith Internal Tool Builder\n  description: Workflow capability for building and managing internal tools using the Appsmith low-code platform. Supports\n    developers creating workflow applications with connected datasources and team workspaces.\n  tags:\n  - Appsmith\n  - Low-Code\n  - Internal Tools\n  - Developer Productivity\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    APPSMITH_API_TOKEN: APPSMITH_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: appsmith\n    baseUri: https://app.appsmith.com/api/v1\n    description: Appsmith platform API\n    authentication:\n      type: bearer\n      token: '{{APPSMITH_API_TOKEN}}'\n    resources:\n    - name: applications\n      path: /applications\n      description: Low-code application management\n      operations:\n      - name: list-applications\n        method: GET\n        description: Returns a list of Appsmith applications\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-application\n        method: POST\n        description: Creates a new application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            workspaceId: '{{tools.workspaceId}}'\n      - name: get-application\n        method: GET\n        description: Returns a specific application\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n          description: Application identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces\n      path: /workspaces\n      description: Workspace management\n    \
  \  operations:\n      - name: list-workspaces\n        method: GET\n        description: Returns a list of workspaces\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datasources\n      path: /datasources\n      description: Connected datasource management\n      operations:\n      - name: list-datasources\n        method: GET\n        description: Returns connected datasources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: mcp\n    port: 9090\n    namespace: internal-tool-mcp\n    transport: http\n    description: MCP server for AI-assisted internal tool building with Appsmith.\n    tools:\n    - name: list-internal-tools\n      description: Lists all low-code internal tool applications built in Appsmith\n      hints:\n        readOnly: true\n        idempotent: true\n      call: appsmith.list-applications\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-internal-tool\n      description: Creates a new internal tool application in Appsmith\n      hints:\n        readOnly: false\n        destructive: false\n      call: appsmith.create-application\n      with:\n        name: tools.name\n        workspaceId: tools.workspaceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-team-workspaces\n      description: Lists workspaces available for organizing internal tools\n      hints:\n        readOnly: true\n        idempotent: true\n      call: appsmith.list-workspaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-connected-datasources\n      description: Lists datasources connected to Appsmith for powering internal tools\n      hints:\n        readOnly: true\n        idempotent: true\n      call: appsmith.list-datasources\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n"
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
