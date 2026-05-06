---
categories: []
consumed_apis: []
description: Provides image analysis capabilities including label detection, face detection, text extraction (OCR), object detection, landmark recognition, and explicit content moderation.
layout: capability
name: Google Cloud Vision API
operations:
- description: Google Cloud Vision Annotate images
  method: POST
  name: annotateimages
  path: /images:annotate
- description: Google Cloud Vision Async annotate images
  method: POST
  name: asyncbatchannotateimages
  path: /images:asyncBatchAnnotate
- description: Google Cloud Vision Annotate files
  method: POST
  name: annotatefiles
  path: /files:annotate
- description: Google Cloud Vision List product sets
  method: GET
  name: listproductsets
  path: /projects/{project}/locations/{location}/productSets
personas: []
provider_name: Google Cloud Vision
provider_slug: google-cloud-vision
search_terms:
- asyncbatchannotateimages
- google cloud vision list product sets
- listproductsets
- computer vision
- image analysis
- machine learning
- cloud
- google
- api
- vision
- google cloud vision async annotate images
- annotatefiles
- ocr
- google cloud vision annotate files
- google cloud
- google cloud vision annotate images
- annotateimages
slug: google-cloud-vision-capability
source_filename: google-cloud-vision-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Vision API\n  description: Provides image analysis capabilities including label detection, face detection, text extraction (OCR), object\n    detection, landmark recognition, and explicit content moderation.\n  tags:\n  - Google\n  - Cloud\n  - Vision\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-vision\n    baseUri: https://vision.googleapis.com/v1\n    description: Google Cloud Vision API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_VISION_TOKEN}}'\n    resources:\n    - name: images-annotate\n      path: /images:annotate\n      operations:\n      - name: annotateimages\n        method: POST\n        description: Google Cloud Vision Annotate images\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images-asyncbatchannotate\n\
  \      path: /images:asyncBatchAnnotate\n      operations:\n      - name: asyncbatchannotateimages\n        method: POST\n        description: Google Cloud Vision Async annotate images\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: files-annotate\n      path: /files:annotate\n      operations:\n      - name: annotatefiles\n        method: POST\n        description: Google Cloud Vision Annotate files\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-locations-location-productsets\n      path: /projects/{project}/locations/{location}/productSets\n      operations:\n      - name: listproductsets\n        method: GET\n        description: Google Cloud Vision List product sets\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n\
  \        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-vision-rest\n    description: REST adapter for Google Cloud Vision API.\n    resources:\n    - path: /images:annotate\n      name: annotateimages\n      operations:\n      - method: POST\n        name: annotateimages\n        description: Google Cloud Vision Annotate images\n        call: google-cloud-vision.annotateimages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /images:asyncBatchAnnotate\n      name: asyncbatchannotateimages\n      operations:\n      - method: POST\n        name: asyncbatchannotateimages\n        description: Google Cloud Vision Async annotate images\n        call: google-cloud-vision.asyncbatchannotateimages\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /files:annotate\n      name: annotatefiles\n      operations:\n      - method: POST\n        name: annotatefiles\n        description: Google Cloud Vision Annotate files\n        call: google-cloud-vision.annotatefiles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/locations/{location}/productSets\n      name: listproductsets\n      operations:\n      - method: GET\n        name: listproductsets\n        description: Google Cloud Vision List product sets\n        call: google-cloud-vision.listproductsets\n        with:\n          project: rest.project\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-vision-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Vision API for AI agent use.\n    tools:\n    - name: annotateimages\n   \
  \   description: Google Cloud Vision Annotate images\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-vision.annotateimages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: asyncbatchannotateimages\n      description: Google Cloud Vision Async annotate images\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-vision.asyncbatchannotateimages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: annotatefiles\n      description: Google Cloud Vision Annotate files\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-vision.annotatefiles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listproductsets\n      description: Google Cloud Vision List product sets\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: google-cloud-vision.listproductsets\n      with:\n        project: tools.project\n        location: tools.location\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_VISION_TOKEN: GOOGLE_CLOUD_VISION_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-vision/refs/heads/main/capabilities/google-cloud-vision-capability.yaml
tags:
- Google
- Cloud
- Vision
- API
tools:
- description: Google Cloud Vision Annotate images
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: annotateimages
- description: Google Cloud Vision Async annotate images
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: asyncbatchannotateimages
- description: Google Cloud Vision Annotate files
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: annotatefiles
- description: Google Cloud Vision List product sets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listproductsets
---
