---
categories: []
consumed_apis: []
description: The npm Hooks API allows developers to subscribe to notifications about changes in the npm registry. Hooks send HTTP POST payloads to a configured URI whenever a package is changed, enabling developers to build integrations that respond to registry events in real time. Users can add hooks to follow specific packages, track all activity of given npm users, or monitor all packages within an organization or user scope. The API provides endpoints for creating, listing, updating, and deleting hook subscriptions. Note that npm hooks services have been deprecated as of July 2024.
layout: capability
name: npm Hooks API
operations:
- description: List webhooks
  method: GET
  name: listhooks
  path: /-/npm/v1/hooks
- description: Create a webhook
  method: POST
  name: createhook
  path: /-/npm/v1/hooks/hook
- description: Get a webhook
  method: GET
  name: gethook
  path: /-/npm/v1/hooks/hook/{id}
- description: Update a webhook
  method: PUT
  name: updatehook
  path: /-/npm/v1/hooks/hook/{id}
- description: Delete a webhook
  method: DELETE
  name: deletehook
  path: /-/npm/v1/hooks/hook/{id}
personas: []
provider_name: npm
provider_slug: npm
search_terms:
- npm
- createhook
- node.js
- update a webhook
- package management
- javascript
- updatehook
- packages
- api
- security
- get a webhook
- create a webhook
- listhooks
- gethook
- list webhooks
- deletehook
- registry
- delete a webhook
slug: npm-capability
source_filename: npm-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: npm Hooks API\n  description: The npm Hooks API allows developers to subscribe to notifications about changes in the npm registry. Hooks\n    send HTTP POST payloads to a configured URI whenever a package is changed, enabling developers to build integrations that\n    respond to registry events in real time. Users can add hooks to follow specific packages, track all activity of given\n    npm users, or monitor all packages within an organization or user scope. The API provides endpoints for creating, listing,\n    updating, and deleting hook subscriptions. Note that npm hooks services have been deprecated as of July 2024.\n  tags:\n  - Npm\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: npm\n    baseUri: https://registry.npmjs.org\n    description: npm Hooks API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{NPM_TOKEN}}'\n    resources:\n    - name:\
  \ npm-v1-hooks\n      path: /-/npm/v1/hooks\n      operations:\n      - name: listhooks\n        method: GET\n        description: List webhooks\n        inputParameters:\n        - name: package\n          in: query\n          type: string\n          description: Filter hooks by package name. Does not support regular expressions.\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of hooks to return.\n        - name: offset\n          in: query\n          type: integer\n          description: Number of hooks to skip for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: npm-v1-hooks-hook\n      path: /-/npm/v1/hooks/hook\n      operations:\n      - name: createhook\n        method: POST\n        description: Create a webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: npm-v1-hooks-hook-id\n      path: /-/npm/v1/hooks/hook/{id}\n      operations:\n      - name: gethook\n        method: GET\n        description: Get a webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatehook\n        method: PUT\n        description: Update a webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletehook\n        method: DELETE\n        description: Delete a webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: npm-rest\n    description: REST adapter for npm Hooks API.\n    resources:\n    - path: /-/npm/v1/hooks\n      name: listhooks\n      operations:\n      - method: GET\n        name: listhooks\n\
  \        description: List webhooks\n        call: npm.listhooks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /-/npm/v1/hooks/hook\n      name: createhook\n      operations:\n      - method: POST\n        name: createhook\n        description: Create a webhook\n        call: npm.createhook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /-/npm/v1/hooks/hook/{id}\n      name: gethook\n      operations:\n      - method: GET\n        name: gethook\n        description: Get a webhook\n        call: npm.gethook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /-/npm/v1/hooks/hook/{id}\n      name: updatehook\n      operations:\n      - method: PUT\n        name: updatehook\n        description: Update a webhook\n        call: npm.updatehook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /-/npm/v1/hooks/hook/{id}\n      name: deletehook\n\
  \      operations:\n      - method: DELETE\n        name: deletehook\n        description: Delete a webhook\n        call: npm.deletehook\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: npm-mcp\n    transport: http\n    description: MCP adapter for npm Hooks API for AI agent use.\n    tools:\n    - name: listhooks\n      description: List webhooks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: npm.listhooks\n      with:\n        package: tools.package\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: package\n        type: string\n        description: Filter hooks by package name. Does not support regular expressions.\n      - name: limit\n        type: integer\n        description: Maximum number of hooks to return.\n      - name: offset\n        type: integer\n        description: Number of hooks to skip for\
  \ pagination.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createhook\n      description: Create a webhook\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: npm.createhook\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gethook\n      description: Get a webhook\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: npm.gethook\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatehook\n      description: Update a webhook\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: npm.updatehook\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletehook\n      description: Delete a webhook\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: npm.deletehook\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    NPM_TOKEN: NPM_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/npm/refs/heads/main/capabilities/npm-capability.yaml
tags:
- Npm
- API
tools:
- description: List webhooks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listhooks
- description: Create a webhook
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createhook
- description: Get a webhook
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethook
- description: Update a webhook
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatehook
- description: Delete a webhook
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletehook
---
