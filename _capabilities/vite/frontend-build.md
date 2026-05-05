---
categories: []
consumed_apis:
- vite-js-api
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
- open in editor
- open source file in editor
- open a vite project source file at the specified line and column in the ide. useful for navigating to build errors.
- frontend
- check whether the vite development server is running and healthy.
- open a source file at a specific line/column in the ide.
- check vite dev server health.
- hot module replacement
- bundler
- ping dev server
- development server
- plugin api
- ping vite dev server
- ping the vite dev server to confirm it is running.
- open source files in the configured ide.
- dev server
- typescript
- javascript
- vite
- build tools
- esm
slug: frontend-build
source_filename: frontend-build.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Vite Frontend Build Workflow\"\n  description: >-\n    Workflow capability for frontend developers using Vite. Combines the\n    JavaScript API and Plugin API to support dev server management, production\n    builds, preview serving, and editor integration in a unified interface.\n    Targeted at build system integrators, CI/CD pipelines, and IDE plugins.\n  tags:\n    - Vite\n    - Build Tools\n    - Dev Server\n    - Frontend\n    - Hot Module Replacement\n    - JavaScript\n    - TypeScript\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VITE_DEV_SERVER_HOST: VITE_DEV_SERVER_HOST\n\ncapability:\n  consumes:\n    - import: vite-js-api\n      location: ./shared/javascript-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: vite-build-api\n      description: \"Unified REST API for Vite frontend build and development workflows.\"\n      resources:\n \
  \       - path: /v1/dev-server/ping\n          name: dev-server-health\n          description: \"Check Vite dev server health.\"\n          operations:\n            - method: GET\n              name: ping-dev-server\n              description: \"Ping the Vite dev server to confirm it is running.\"\n              call: \"vite-js-api.ping-dev-server\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/editor/open\n          name: editor-integration\n          description: \"Open source files in the configured IDE.\"\n          operations:\n            - method: GET\n              name: open-in-editor\n              description: \"Open a source file at a specific line/column in the IDE.\"\n              call: \"vite-js-api.open-in-editor\"\n              with:\n                file: \"rest.file\"\n                line: \"rest.line\"\n                column: \"rest.column\"\n              outputParameters:\n          \
  \      - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: vite-build-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Vite build and development tooling.\"\n      tools:\n        - name: ping-vite-dev-server\n          description: \"Check whether the Vite development server is running and healthy.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vite-js-api.ping-dev-server\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: open-source-file-in-editor\n          description: \"Open a Vite project source file at the specified line and column in the IDE. Useful for navigating to build errors.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vite-js-api.open-in-editor\"\n          with:\n            file: \"tools.file\"\n            line: \"tools.line\"\n   \
  \         column: \"tools.column\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
