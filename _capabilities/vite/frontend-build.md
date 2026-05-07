---
categories: []
consumed_apis: []
description: Workflow capability for frontend developers using Vite. Combines the JavaScript API and Plugin API to support dev server management, production builds, preview serving, and editor integration in a unified interface. Targeted at build system integrators, CI/CD pipelines, and IDE plugins.
layout: capability
name: Vite Frontend Build Workflow
operations:
- description: Ping the Vite dev server to confirm it is running.
  method: GET
  name: ping-dev-server
  path: /v1/dev-server/ping
- description: Open a source file at a specific line/column in the IDE.
  method: GET
  name: open-in-editor
  path: /v1/editor/open
personas: []
provider_name: Vite
provider_slug: vite
search_terms:
- open a vite project source file at the specified line and column in the ide. useful for navigating to build errors.
- ping the vite dev server to confirm it is running.
- open source files in the configured ide.
- check whether the vite development server is running and healthy.
- check vite dev server health.
- dev server
- ping dev server
- bundler
- build tools
- open a source file at a specific line/column in the ide.
- development server
- open in editor
- plugin api
- ping vite dev server
- typescript
- esm
- hot module replacement
- frontend
- vite
- open source file in editor
- javascript
slug: frontend-build
source_filename: frontend-build.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Vite Frontend Build Workflow\n  description: Workflow capability for frontend developers using Vite. Combines the JavaScript API and Plugin API to support\n    dev server management, production builds, preview serving, and editor integration in a unified interface. Targeted at\n    build system integrators, CI/CD pipelines, and IDE plugins.\n  tags:\n  - Vite\n  - Build Tools\n  - Dev Server\n  - Frontend\n  - Hot Module Replacement\n  - JavaScript\n  - TypeScript\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VITE_DEV_SERVER_HOST: VITE_DEV_SERVER_HOST\ncapability:\n  consumes:\n  - type: http\n    namespace: vite-js-api\n    baseUri: http://localhost:5173\n    description: Vite development server endpoints for health checks and file serving.\n    resources:\n    - name: dev-server\n      path: /__vite_ping\n      description: Dev server health and connectivity.\n      operations:\n      - name:\
  \ ping-dev-server\n        method: GET\n        description: Ping the Vite dev server to confirm it is running.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: string\n          value: $.\n    - name: editor\n      path: /__open-in-editor\n      description: Open a source file in the configured editor.\n      operations:\n      - name: open-in-editor\n        method: GET\n        description: Open a source file at a specific line/column in the IDE.\n        inputParameters:\n        - name: file\n          in: query\n          type: string\n          required: true\n          description: Relative path to the source file\n        - name: line\n          in: query\n          type: integer\n          required: false\n          description: Line number to navigate to\n        - name: column\n          in: query\n          type: integer\n          required: false\n          description: Column number to navigate to\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: vite-build-api\n    description: Unified REST API for Vite frontend build and development workflows.\n    resources:\n    - path: /v1/dev-server/ping\n      name: dev-server-health\n      description: Check Vite dev server health.\n      operations:\n      - method: GET\n        name: ping-dev-server\n        description: Ping the Vite dev server to confirm it is running.\n        call: vite-js-api.ping-dev-server\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/editor/open\n      name: editor-integration\n      description: Open source files in the configured IDE.\n      operations:\n      - method: GET\n        name: open-in-editor\n        description: Open a source file at a specific line/column in the IDE.\n        call: vite-js-api.open-in-editor\n        with:\n          file:\
  \ rest.file\n          line: rest.line\n          column: rest.column\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: vite-build-mcp\n    transport: http\n    description: MCP server for AI-assisted Vite build and development tooling.\n    tools:\n    - name: ping-vite-dev-server\n      description: Check whether the Vite development server is running and healthy.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vite-js-api.ping-dev-server\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: open-source-file-in-editor\n      description: Open a Vite project source file at the specified line and column in the IDE. Useful for navigating to build\n        errors.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vite-js-api.open-in-editor\n      with:\n        file: tools.file\n        line: tools.line\n        column: tools.column\n \
  \     outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vite/refs/heads/main/capabilities/frontend-build.yaml
tags:
- Vite
- Build Tools
- Dev Server
- Frontend
- Hot Module Replacement
- JavaScript
- TypeScript
tools:
- description: Check whether the Vite development server is running and healthy.
  hints:
    idempotent: true
    readOnly: true
  name: ping-vite-dev-server
- description: Open a Vite project source file at the specified line and column in the IDE. Useful for navigating to build errors.
  hints:
    idempotent: true
    readOnly: true
  name: open-source-file-in-editor
---
