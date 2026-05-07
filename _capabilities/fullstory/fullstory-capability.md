---
categories: []
consumed_apis: []
description: 'The FullStory Segments Export API provides an asynchronous workflow for downloading captured event data from FullStory. Developers can initiate export jobs to aggregate segment data, query for the status of running jobs, and retrieve download URLs for completed exports. Two types of segment data are available for export: individuals matching a segment and events performed by those individuals. This API is useful for integrating FullStory behavioral data into external analytics pipelines and data warehouses.'
layout: capability
name: FullStory Segments Export API
operations:
- description: List segments
  method: GET
  name: listsegments
  path: /segments/v1
- description: Get a segment
  method: GET
  name: getsegment
  path: /segments/v1/{segmentId}
- description: Create a segment export
  method: POST
  name: createsegmentexport
  path: /segments/v1/exports
- description: Get operation status
  method: GET
  name: getoperationstatus
  path: /operations/v1/{operationId}
personas: []
provider_name: FullStory
provider_slug: fullstory
search_terms:
- list segments
- analytics
- webhooks
- get operation status
- session replay
- data export
- fullstory
- getoperationstatus
- create a segment export
- api
- get a segment
- digital experience
- createsegmentexport
- getsegment
- listsegments
slug: fullstory-capability
source_filename: fullstory-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: FullStory Segments Export API\n  description: 'The FullStory Segments Export API provides an asynchronous workflow for downloading captured event data from\n    FullStory. Developers can initiate export jobs to aggregate segment data, query for the status of running jobs, and retrieve\n    download URLs for completed exports. Two types of segment data are available for export: individuals matching a segment\n    and events performed by those individuals. This API is useful for integrating FullStory behavioral data into external\n    analytics pipelines and data warehouses.'\n  tags:\n  - Fullstory\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: fullstory\n    baseUri: https://api.fullstory.com\n    description: FullStory Segments Export API HTTP API.\n    authentication:\n      type: basic\n      username: '{{FULLSTORY_USERNAME}}'\n      password: '{{FULLSTORY_PASSWORD}}'\n\
  \    resources:\n    - name: segments-v1\n      path: /segments/v1\n      operations:\n      - name: listsegments\n        method: GET\n        description: List segments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: segments-v1-segmentid\n      path: /segments/v1/{segmentId}\n      operations:\n      - name: getsegment\n        method: GET\n        description: Get a segment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: segments-v1-exports\n      path: /segments/v1/exports\n      operations:\n      - name: createsegmentexport\n        method: POST\n        description: Create a segment export\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: operations-v1-operationid\n      path: /operations/v1/{operationId}\n \
  \     operations:\n      - name: getoperationstatus\n        method: GET\n        description: Get operation status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: fullstory-rest\n    description: REST adapter for FullStory Segments Export API.\n    resources:\n    - path: /segments/v1\n      name: listsegments\n      operations:\n      - method: GET\n        name: listsegments\n        description: List segments\n        call: fullstory.listsegments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /segments/v1/{segmentId}\n      name: getsegment\n      operations:\n      - method: GET\n        name: getsegment\n        description: Get a segment\n        call: fullstory.getsegment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /segments/v1/exports\n      name: createsegmentexport\n\
  \      operations:\n      - method: POST\n        name: createsegmentexport\n        description: Create a segment export\n        call: fullstory.createsegmentexport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /operations/v1/{operationId}\n      name: getoperationstatus\n      operations:\n      - method: GET\n        name: getoperationstatus\n        description: Get operation status\n        call: fullstory.getoperationstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: fullstory-mcp\n    transport: http\n    description: MCP adapter for FullStory Segments Export API for AI agent use.\n    tools:\n    - name: listsegments\n      description: List segments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fullstory.listsegments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsegment\n\
  \      description: Get a segment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fullstory.getsegment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsegmentexport\n      description: Create a segment export\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fullstory.createsegmentexport\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getoperationstatus\n      description: Get operation status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fullstory.getoperationstatus\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    FULLSTORY_USERNAME: FULLSTORY_USERNAME\n    FULLSTORY_PASSWORD: FULLSTORY_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/fullstory/refs/heads/main/capabilities/fullstory-capability.yaml
tags:
- Fullstory
- API
tools:
- description: List segments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsegments
- description: Get a segment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsegment
- description: Create a segment export
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsegmentexport
- description: Get operation status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getoperationstatus
---
