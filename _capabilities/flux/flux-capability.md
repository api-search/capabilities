---
categories: []
consumed_apis: []
description: REST API for editing and transforming existing images using Black Forest Labs' FLUX.1 Kontext models. The Kontext models accept an input image and a text prompt describing desired edits, returning a modified image. They support context-aware in-painting, object replacement, style transfer, background changes, and image-to-image transformations while preserving important visual context. Authentication requires an API key in the X-Key header. Requests are asynchronous and require polling for results.
layout: capability
name: Flux Image Editing API
operations:
- description: Edit image with FLUX.1 Kontext [pro]
  method: POST
  name: editimagekontextpro
  path: /flux-kontext-pro
- description: Edit image with FLUX.1 Kontext [max]
  method: POST
  name: editimagekontextmax
  path: /flux-kontext-max
- description: Flux Poll for editing result
  method: GET
  name: geteditresult
  path: /get_result
personas: []
provider_name: Flux
provider_slug: flux
search_terms:
- flux poll for editing result
- flux
- editimagekontextpro
- image generation
- machine learning
- edit image with flux.1 kontext [pro]
- edit image with flux.1 kontext [max]
- text to image
- api
- geteditresult
- ai
- editimagekontextmax
- open source
slug: flux-capability
source_filename: flux-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Flux Image Editing API\n  description: REST API for editing and transforming existing images using Black Forest Labs' FLUX.1 Kontext models. The Kontext\n    models accept an input image and a text prompt describing desired edits, returning a modified image. They support context-aware\n    in-painting, object replacement, style transfer, background changes, and image-to-image transformations while preserving\n    important visual context. Authentication requires an API key in the X-Key header. Requests are asynchronous and require\n    polling for results.\n  tags:\n  - Flux\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: flux\n    baseUri: https://api.bfl.ai/v1\n    description: Flux Image Editing API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-Key\n      value: '{{FLUX_TOKEN}}'\n    resources:\n    - name: flux-kontext-pro\n\
  \      path: /flux-kontext-pro\n      operations:\n      - name: editimagekontextpro\n        method: POST\n        description: Edit image with FLUX.1 Kontext [pro]\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: flux-kontext-max\n      path: /flux-kontext-max\n      operations:\n      - name: editimagekontextmax\n        method: POST\n        description: Edit image with FLUX.1 Kontext [max]\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: get-result\n      path: /get_result\n      operations:\n      - name: geteditresult\n        method: GET\n        description: Flux Poll for editing result\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: flux-rest\n    description:\
  \ REST adapter for Flux Image Editing API.\n    resources:\n    - path: /flux-kontext-pro\n      name: editimagekontextpro\n      operations:\n      - method: POST\n        name: editimagekontextpro\n        description: Edit image with FLUX.1 Kontext [pro]\n        call: flux.editimagekontextpro\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /flux-kontext-max\n      name: editimagekontextmax\n      operations:\n      - method: POST\n        name: editimagekontextmax\n        description: Edit image with FLUX.1 Kontext [max]\n        call: flux.editimagekontextmax\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /get_result\n      name: geteditresult\n      operations:\n      - method: GET\n        name: geteditresult\n        description: Flux Poll for editing result\n        call: flux.geteditresult\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n  \
  \  namespace: flux-mcp\n    transport: http\n    description: MCP adapter for Flux Image Editing API for AI agent use.\n    tools:\n    - name: editimagekontextpro\n      description: Edit image with FLUX.1 Kontext [pro]\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: flux.editimagekontextpro\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: editimagekontextmax\n      description: Edit image with FLUX.1 Kontext [max]\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: flux.editimagekontextmax\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: geteditresult\n      description: Flux Poll for editing result\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: flux.geteditresult\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace:\
  \ env\n  keys:\n    FLUX_TOKEN: FLUX_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/flux/refs/heads/main/capabilities/flux-capability.yaml
tags:
- Flux
- API
tools:
- description: Edit image with FLUX.1 Kontext [pro]
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: editimagekontextpro
- description: Edit image with FLUX.1 Kontext [max]
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: editimagekontextmax
- description: Flux Poll for editing result
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: geteditresult
---
