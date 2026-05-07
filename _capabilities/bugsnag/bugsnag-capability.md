---
categories: []
consumed_apis: []
description: The Bugsnag Build API allows you to provide information about your application builds, releases, and deployments. By notifying Bugsnag when you deploy, you can track which releases introduced new errors, view error trends across releases, and identify regressions. The API accepts build metadata including version numbers, source control information, and release stages. It integrates with CI/CD pipelines to automate release tracking.
layout: capability
name: Bugsnag Build API
operations:
- description: Notify Bugsnag of a new build
  method: POST
  name: createbuild
  path: /
personas: []
provider_name: bugsnag
provider_slug: bugsnag
search_terms:
- notify bugsnag of a new build
- createbuild
- bugsnag
- api
slug: bugsnag-capability
source_filename: bugsnag-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Bugsnag Build API\n  description: The Bugsnag Build API allows you to provide information about your application builds, releases, and deployments.\n    By notifying Bugsnag when you deploy, you can track which releases introduced new errors, view error trends across releases,\n    and identify regressions. The API accepts build metadata including version numbers, source control information, and release\n    stages. It integrates with CI/CD pipelines to automate release tracking.\n  tags:\n  - Bugsnag\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: bugsnag\n    baseUri: https://build.bugsnag.com\n    description: Bugsnag Build API HTTP API.\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: createbuild\n        method: POST\n        description: Notify Bugsnag of a new build\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: bugsnag-rest\n    description: REST adapter for Bugsnag Build API.\n    resources:\n    - path: /\n      name: createbuild\n      operations:\n      - method: POST\n        name: createbuild\n        description: Notify Bugsnag of a new build\n        call: bugsnag.createbuild\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: bugsnag-mcp\n    transport: http\n    description: MCP adapter for Bugsnag Build API for AI agent use.\n    tools:\n    - name: createbuild\n      description: Notify Bugsnag of a new build\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: bugsnag.createbuild\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bugsnag/refs/heads/main/capabilities/bugsnag-capability.yaml
tags:
- Bugsnag
- API
tools:
- description: Notify Bugsnag of a new build
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbuild
---
