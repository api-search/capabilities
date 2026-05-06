---
categories: []
consumed_apis: []
description: The ReadMe Developer Metrics API provides endpoints for sending API logs and retrieving analytics data including page quality scores, page view statistics, and search analytics. It powers the Developer Dashboard.
layout: capability
name: ReadMe Developer Metrics API
operations:
- description: Submit API request logs
  method: POST
  name: post-request
  path: /request
- description: Retrieve page quality scores
  method: GET
  name: get-quality
  path: /quality
- description: Retrieve page view statistics
  method: GET
  name: get-pageviews
  path: /pageviews
- description: Retrieve search analytics
  method: GET
  name: get-search
  path: /search
personas: []
provider_name: ReadMe
provider_slug: readme
search_terms:
- get pageviews
- post request
- documentation
- readme
- developer hub
- platform
- api
- submit api request logs
- retrieve page view statistics
- analytics
- retrieve search analytics
- get search
- portals
- retrieve page quality scores
- get quality
slug: readme-capability
source_filename: readme-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ReadMe Developer Metrics API\n  description: The ReadMe Developer Metrics API provides endpoints for sending API logs and retrieving analytics data including\n    page quality scores, page view statistics, and search analytics. It powers the Developer Dashboard.\n  tags:\n  - Readme\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: readme\n    baseUri: https://metrics.readme.io/v1\n    description: ReadMe Developer Metrics API HTTP API.\n    authentication:\n      type: basic\n      username: '{{README_USERNAME}}'\n      password: '{{README_PASSWORD}}'\n    resources:\n    - name: request\n      path: /request\n      operations:\n      - name: post-request\n        method: POST\n        description: Submit API request logs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: quality\n\
  \      path: /quality\n      operations:\n      - name: get-quality\n        method: GET\n        description: Retrieve page quality scores\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pageviews\n      path: /pageviews\n      operations:\n      - name: get-pageviews\n        method: GET\n        description: Retrieve page view statistics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      operations:\n      - name: get-search\n        method: GET\n        description: Retrieve search analytics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: readme-rest\n    description: REST adapter for ReadMe Developer Metrics API.\n    resources:\n \
  \   - path: /request\n      name: post-request\n      operations:\n      - method: POST\n        name: post-request\n        description: Submit API request logs\n        call: readme.post-request\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /quality\n      name: get-quality\n      operations:\n      - method: GET\n        name: get-quality\n        description: Retrieve page quality scores\n        call: readme.get-quality\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pageviews\n      name: get-pageviews\n      operations:\n      - method: GET\n        name: get-pageviews\n        description: Retrieve page view statistics\n        call: readme.get-pageviews\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /search\n      name: get-search\n      operations:\n      - method: GET\n        name: get-search\n        description: Retrieve search analytics\n        call:\
  \ readme.get-search\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: readme-mcp\n    transport: http\n    description: MCP adapter for ReadMe Developer Metrics API for AI agent use.\n    tools:\n    - name: post-request\n      description: Submit API request logs\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: readme.post-request\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-quality\n      description: Retrieve page quality scores\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: readme.get-quality\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-pageviews\n      description: Retrieve page view statistics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: readme.get-pageviews\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-search\n      description: Retrieve search analytics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: readme.get-search\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    README_USERNAME: README_USERNAME\n    README_PASSWORD: README_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/readme/refs/heads/main/capabilities/readme-capability.yaml
tags:
- Readme
- API
tools:
- description: Submit API request logs
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-request
- description: Retrieve page quality scores
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-quality
- description: Retrieve page view statistics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-pageviews
- description: Retrieve search analytics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-search
---
