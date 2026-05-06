---
categories: []
consumed_apis: []
description: Segmind Fashion AI is an in-painting model that edits clothing in an input image based on a text prompt. The image is center-cropped and resized to 512x512 before processing, and the model returns an edited image.
layout: capability
name: Fashion AI API
operations:
- description: Edit clothing in an image
  method: POST
  name: editfashion
  path: /fashion-ai
personas: []
provider_name: Fashion AI
provider_slug: fashion-ai
search_terms:
- editfashion
- edit clothing in an image
- api
- fashion
- ai
- clothing
slug: fashion-ai-capability
source_filename: fashion-ai-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Fashion AI API\n  description: Segmind Fashion AI is an in-painting model that edits clothing in an input image based on a text prompt. The\n    image is center-cropped and resized to 512x512 before processing, and the model returns an edited image.\n  tags:\n  - Fashion\n  - Ai\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: fashion-ai\n    baseUri: https://api.segmind.com/v1\n    description: Fashion AI API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: x-api-key\n      value: '{{FASHION_AI_TOKEN}}'\n    resources:\n    - name: fashion-ai\n      path: /fashion-ai\n      operations:\n      - name: editfashion\n        method: POST\n        description: Edit clothing in an image\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n\
  \    port: 8080\n    namespace: fashion-ai-rest\n    description: REST adapter for Fashion AI API.\n    resources:\n    - path: /fashion-ai\n      name: editfashion\n      operations:\n      - method: POST\n        name: editfashion\n        description: Edit clothing in an image\n        call: fashion-ai.editfashion\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: fashion-ai-mcp\n    transport: http\n    description: MCP adapter for Fashion AI API for AI agent use.\n    tools:\n    - name: editfashion\n      description: Edit clothing in an image\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fashion-ai.editfashion\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    FASHION_AI_TOKEN: FASHION_AI_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/fashion-ai/refs/heads/main/capabilities/fashion-ai-capability.yaml
tags:
- Fashion
- Ai
- API
tools:
- description: Edit clothing in an image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: editfashion
---
