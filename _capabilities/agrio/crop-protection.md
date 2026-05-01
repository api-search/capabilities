---
categories: []
consumed_apis:
- agrio
description: Unified crop protection capability combining Agrio's AI-powered plant disease diagnosis, pest detection, and crop advisory services. Used by agronomists, crop advisors, and precision agriculture platforms to identify plant health issues and recommend treatments.
layout: capability
name: Agrio Crop Protection
operations:
- description: Get current credit balance.
  method: GET
  name: get-credit
  path: /v1/credit
- description: List all supported crop types.
  method: GET
  name: list-crops
  path: /v1/crops
- description: Diagnose plant diseases and pests from an uploaded image.
  method: POST
  name: diagnose
  path: /v1/diagnose
personas: []
provider_name: agrio
provider_slug: agrio
search_terms:
- list supported crops
- list all supported crop types.
- supported crop types for diagnosis
- crop advisory
- check remaining api credits for plant diagnosis requests.
- agricultural consultants providing plant health recommendations
- Precision Agriculture Developer
- ai-powered plant disease diagnosis and crop advisory
- field specialists diagnosing plant health issues in crops
- Agronomist
- plant health diagnosis.
- check credit balance
- crop protection
- agriculture
- Crop Advisor
- ai diagnosis
- credit balance and api usage monitoring
- disease and pest identification from plant images
- list all crop types supported by agrio's ai diagnosis service.
- diagnose plant diseases and pests from an uploaded image.
- ai
- plant disease
- diagnose plant disease
- get current credit balance.
- agrio
- list crops
- account credit management.
- supported crop catalog.
- submit a plant image for ai-powered diagnosis of diseases, pests, and nutrient deficiencies. returns ranked diagnoses with confidence scores and scientific names.
- get credit
- pest detection
- diagnose
- developers building crop advisory and farm management applications
slug: crop-protection
source_filename: crop-protection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Agrio Crop Protection\n  description: >-\n    Unified crop protection capability combining Agrio's AI-powered plant disease\n    diagnosis, pest detection, and crop advisory services. Used by agronomists,\n    crop advisors, and precision agriculture platforms to identify plant health\n    issues and recommend treatments.\n  tags:\n    - Agrio\n    - Agriculture\n    - Plant Disease\n    - Crop Protection\n    - AI Diagnosis\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AGRIO_API_KEY: AGRIO_API_KEY\n\ncapability:\n  consumes:\n    - import: agrio\n      location: ./shared/agrio-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: crop-protection-api\n      description: Unified REST API for AI-powered crop protection and plant disease diagnosis.\n      resources:\n        - path: /v1/credit\n          name: credit\n          description: Account credit\
  \ management.\n          operations:\n            - method: GET\n              name: get-credit\n              description: Get current credit balance.\n              call: \"agrio.get-credit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/crops\n          name: crops\n          description: Supported crop catalog.\n          operations:\n            - method: GET\n              name: list-crops\n              description: List all supported crop types.\n              call: \"agrio.get-supported-crops\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/diagnose\n          name: diagnose\n          description: Plant health diagnosis.\n          operations:\n            - method: POST\n              name: diagnose\n              description: Diagnose plant diseases and pests from an uploaded image.\n              call: \"agrio.diagnose-plant\"\
  \n              with:\n                crop_id: \"rest.crop_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: crop-protection-mcp\n      transport: http\n      description: MCP server for AI-assisted crop protection and plant disease diagnosis.\n      tools:\n        - name: check-credit-balance\n          description: Check remaining API credits for plant diagnosis requests.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"agrio.get-credit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-supported-crops\n          description: List all crop types supported by Agrio's AI diagnosis service.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"agrio.get-supported-crops\"\n          outputParameters:\n            - type: object\n   \
  \           mapping: \"$.\"\n        - name: diagnose-plant-disease\n          description: >-\n            Submit a plant image for AI-powered diagnosis of diseases, pests, and\n            nutrient deficiencies. Returns ranked diagnoses with confidence scores\n            and scientific names.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"agrio.diagnose-plant\"\n          with:\n            crop_id: \"tools.crop_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/agrio/refs/heads/main/capabilities/crop-protection.yaml
tags:
- Agrio
- Agriculture
- Plant Disease
- Crop Protection
- AI Diagnosis
tools:
- description: Check remaining API credits for plant diagnosis requests.
  hints:
    openWorld: false
    readOnly: true
  name: check-credit-balance
- description: List all crop types supported by Agrio's AI diagnosis service.
  hints:
    openWorld: true
    readOnly: true
  name: list-supported-crops
- description: Submit a plant image for AI-powered diagnosis of diseases, pests, and nutrient deficiencies. Returns ranked diagnoses with confidence scores and scientific names.
  hints:
    openWorld: true
    readOnly: true
  name: diagnose-plant-disease
---
