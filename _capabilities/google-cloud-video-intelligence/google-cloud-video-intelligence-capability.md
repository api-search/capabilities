---
categories: []
consumed_apis: []
description: Makes videos searchable and discoverable by extracting metadata and annotations using machine learning.
layout: capability
name: Google Cloud Video Intelligence API
operations:
- description: Google Cloud Video Intelligence Annotate video
  method: POST
  name: annotatevideo
  path: /videos:annotate
- description: Google Cloud Video Intelligence Get operation status
  method: GET
  name: getoperation
  path: /operations/{operationId}
- description: Google Cloud Video Intelligence Delete operation
  method: DELETE
  name: deleteoperation
  path: /operations/{operationId}
personas: []
provider_name: Google Cloud Video Intelligence
provider_slug: google-cloud-video-intelligence
search_terms:
- intelligence
- annotatevideo
- deleteoperation
- google cloud video intelligence get operation status
- machine learning
- cloud
- google
- api
- object detection
- video intelligence
- video
- google cloud video intelligence annotate video
- getoperation
- google cloud video intelligence delete operation
- video analysis
- google cloud
- content moderation
slug: google-cloud-video-intelligence-capability
source_filename: google-cloud-video-intelligence-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Video Intelligence API\n  description: Makes videos searchable and discoverable by extracting metadata and annotations using machine learning.\n  tags:\n  - Google\n  - Cloud\n  - Video\n  - Intelligence\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-video-intelligence\n    baseUri: https://videointelligence.googleapis.com/v1\n    description: Google Cloud Video Intelligence API HTTP API.\n    resources:\n    - name: videos-annotate\n      path: /videos:annotate\n      operations:\n      - name: annotatevideo\n        method: POST\n        description: Google Cloud Video Intelligence Annotate video\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: operations-operationid\n      path: /operations/{operationId}\n      operations:\n      - name: getoperation\n\
  \        method: GET\n        description: Google Cloud Video Intelligence Get operation status\n        inputParameters:\n        - name: operationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteoperation\n        method: DELETE\n        description: Google Cloud Video Intelligence Delete operation\n        inputParameters:\n        - name: operationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-video-intelligence-rest\n    description: REST adapter for Google Cloud Video Intelligence API.\n    resources:\n    - path: /videos:annotate\n      name: annotatevideo\n      operations:\n      - method:\
  \ POST\n        name: annotatevideo\n        description: Google Cloud Video Intelligence Annotate video\n        call: google-cloud-video-intelligence.annotatevideo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /operations/{operationId}\n      name: getoperation\n      operations:\n      - method: GET\n        name: getoperation\n        description: Google Cloud Video Intelligence Get operation status\n        call: google-cloud-video-intelligence.getoperation\n        with:\n          operationId: rest.operationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /operations/{operationId}\n      name: deleteoperation\n      operations:\n      - method: DELETE\n        name: deleteoperation\n        description: Google Cloud Video Intelligence Delete operation\n        call: google-cloud-video-intelligence.deleteoperation\n        with:\n          operationId: rest.operationId\n        outputParameters:\n \
  \       - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-video-intelligence-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Video Intelligence API for AI agent use.\n    tools:\n    - name: annotatevideo\n      description: Google Cloud Video Intelligence Annotate video\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-video-intelligence.annotatevideo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getoperation\n      description: Google Cloud Video Intelligence Get operation status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-video-intelligence.getoperation\n      with:\n        operationId: tools.operationId\n      inputParameters:\n      - name: operationId\n        type: string\n        description: operationId\n        required: true\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteoperation\n      description: Google Cloud Video Intelligence Delete operation\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-video-intelligence.deleteoperation\n      with:\n        operationId: tools.operationId\n      inputParameters:\n      - name: operationId\n        type: string\n        description: operationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-video-intelligence/refs/heads/main/capabilities/google-cloud-video-intelligence-capability.yaml
tags:
- Google
- Cloud
- Video
- Intelligence
- API
tools:
- description: Google Cloud Video Intelligence Annotate video
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: annotatevideo
- description: Google Cloud Video Intelligence Get operation status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getoperation
- description: Google Cloud Video Intelligence Delete operation
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteoperation
---
