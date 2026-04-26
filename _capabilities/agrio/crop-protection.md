---
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
- field specialists diagnosing plant health issues in crops
- disease and pest identification from plant images
- credit balance and api usage monitoring
- agricultural consultants providing plant health recommendations
- supported crop catalog.
- list all supported crop types.
- ai-powered plant disease diagnosis and crop advisory
- diagnose
- list supported crops
- developers building crop advisory and farm management applications
- Precision Agriculture Developer
- crop protection
- pest detection
- check credit balance
- supported crop types for diagnosis
- ai diagnosis
- get credit
- list all crop types supported by agrio's ai diagnosis service.
- account credit management.
- Agronomist
- ai
- plant health diagnosis.
- agriculture
- list crops
- agrio
- get current credit balance.
- crop advisory
- check remaining api credits for plant diagnosis requests.
- diagnose plant disease
- submit a plant image for ai-powered diagnosis of diseases, pests, and nutrient deficiencies. returns ranked diagnoses with confidence scores and scientific names.
- diagnose plant diseases and pests from an uploaded image.
- plant disease
- Crop Advisor
slug: crop-protection
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
