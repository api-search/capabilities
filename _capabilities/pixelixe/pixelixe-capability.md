---
categories: []
consumed_apis: []
description: High-quality and ultra-fast Image Editing API. Resize, Crop, Flip, Rotate, Contrast, Opacify, Blur and transform your photos with APIs.
layout: capability
name: Pixelixe
operations:
- description: Pixelixe Authenticate API Key
  method: GET
  name: get-authentication-v2
  path: /authentication/v2
- description: Pixelixe Search Documents
  method: GET
  name: get-document-search-v2
  path: /document/search/v2
- description: Pixelixe Delete a Document
  method: DELETE
  name: delete-document-delete-v2
  path: /document/delete/v2
- description: Pixelixe Automate Image Generation
  method: POST
  name: post-graphic-automation-v2
  path: /graphic/automation/v2
personas: []
provider_name: Pixelixe
provider_slug: pixelixe
search_terms:
- delete document delete v2
- graphics
- get authentication v2
- pixelixe delete a document
- pixelixe
- pixelixe search documents
- get document search v2
- api
- pixelixe automate image generation
- post graphic automation v2
- images
- pixelixe authenticate api key
slug: pixelixe-capability
source_filename: pixelixe-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Pixelixe\n  description: High-quality and ultra-fast Image Editing API. Resize, Crop, Flip, Rotate, Contrast, Opacify, Blur and transform\n    your photos with APIs.\n  tags:\n  - Pixelixe\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: pixelixe\n    baseUri: https://studio.pixelixe.com/api\n    description: Pixelixe HTTP API.\n    authentication:\n      type: bearer\n      token: '{{PIXELIXE_TOKEN}}'\n    resources:\n    - name: authentication-v2\n      path: /authentication/v2\n      operations:\n      - name: get-authentication-v2\n        method: GET\n        description: Pixelixe Authenticate API Key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: document-search-v2\n      path: /document/search/v2\n      operations:\n      - name: get-document-search-v2\n        method:\
  \ GET\n        description: Pixelixe Search Documents\n        inputParameters:\n        - name: document_uid\n          in: query\n          type: string\n          description: Unique identifier for the document.\n        - name: user_uid\n          in: query\n          type: string\n          description: Unique identifier for the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: document-delete-v2\n      path: /document/delete/v2\n      operations:\n      - name: delete-document-delete-v2\n        method: DELETE\n        description: Pixelixe Delete a Document\n        inputParameters:\n        - name: document_uid\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: graphic-automation-v2\n      path: /graphic/automation/v2\n      operations:\n\
  \      - name: post-graphic-automation-v2\n        method: POST\n        description: Pixelixe Automate Image Generation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: pixelixe-rest\n    description: REST adapter for Pixelixe.\n    resources:\n    - path: /authentication/v2\n      name: get-authentication-v2\n      operations:\n      - method: GET\n        name: get-authentication-v2\n        description: Pixelixe Authenticate API Key\n        call: pixelixe.get-authentication-v2\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /document/search/v2\n      name: get-document-search-v2\n      operations:\n      - method: GET\n        name: get-document-search-v2\n        description: Pixelixe Search Documents\n        call: pixelixe.get-document-search-v2\n        outputParameters:\n        - type: object\n      \
  \    mapping: $.\n    - path: /document/delete/v2\n      name: delete-document-delete-v2\n      operations:\n      - method: DELETE\n        name: delete-document-delete-v2\n        description: Pixelixe Delete a Document\n        call: pixelixe.delete-document-delete-v2\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /graphic/automation/v2\n      name: post-graphic-automation-v2\n      operations:\n      - method: POST\n        name: post-graphic-automation-v2\n        description: Pixelixe Automate Image Generation\n        call: pixelixe.post-graphic-automation-v2\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: pixelixe-mcp\n    transport: http\n    description: MCP adapter for Pixelixe for AI agent use.\n    tools:\n    - name: get-authentication-v2\n      description: Pixelixe Authenticate API Key\n      hints:\n        readOnly: true\n        destructive: false\n      \
  \  idempotent: true\n      call: pixelixe.get-authentication-v2\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-document-search-v2\n      description: Pixelixe Search Documents\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: pixelixe.get-document-search-v2\n      with:\n        document_uid: tools.document_uid\n        user_uid: tools.user_uid\n      inputParameters:\n      - name: document_uid\n        type: string\n        description: Unique identifier for the document.\n      - name: user_uid\n        type: string\n        description: Unique identifier for the user.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-document-delete-v2\n      description: Pixelixe Delete a Document\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: pixelixe.delete-document-delete-v2\n      with:\n        document_uid:\
  \ tools.document_uid\n      inputParameters:\n      - name: document_uid\n        type: string\n        description: document_uid\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-graphic-automation-v2\n      description: Pixelixe Automate Image Generation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: pixelixe.post-graphic-automation-v2\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PIXELIXE_TOKEN: PIXELIXE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/pixelixe/refs/heads/main/capabilities/pixelixe-capability.yaml
tags:
- Pixelixe
- API
tools:
- description: Pixelixe Authenticate API Key
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-authentication-v2
- description: Pixelixe Search Documents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-document-search-v2
- description: Pixelixe Delete a Document
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-document-delete-v2
- description: Pixelixe Automate Image Generation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-graphic-automation-v2
---
