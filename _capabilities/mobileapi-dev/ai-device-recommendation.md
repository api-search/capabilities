---
categories: []
consumed_apis: []
description: Workflow that uses MobileAPI's natural-language query endpoint to translate plain-English questions ("phones with 8GB+ RAM under 200g", "best camera phones from 2024") into structured device results, then enriches the top match with full specifications and images for a conversational recommender experience. Requires a paid plan.
layout: capability
name: AI Device Recommendation Workflow
operations: []
personas: []
provider_name: MobileAPI.dev
provider_slug: mobileapi-dev
search_terms:
- saas
- rest api
- mobile data
- workflow
- phone specs
- recommendation
- data api
- device specifications
- ai
- natural language query
- mobileapi
- developer tools
slug: ai-device-recommendation
source_filename: ai-device-recommendation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AI Device Recommendation Workflow\n  description: >-\n    Workflow that uses MobileAPI's natural-language query endpoint to\n    translate plain-English questions (\"phones with 8GB+ RAM under 200g\",\n    \"best camera phones from 2024\") into structured device results, then\n    enriches the top match with full specifications and images for a\n    conversational recommender experience. Requires a paid plan.\n  tags:\n    - AI\n    - Natural Language Query\n    - Recommendation\n    - MobileAPI\n    - Workflow\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  imports:\n    - shared/mobileapi-capability.yaml\n  workflow:\n    name: ai-device-recommendation\n    steps:\n      - name: ai-query\n        description: Translate the user's natural-language question into structured device results.\n        consume:\n          namespace: mobileapi\n          operation: devices-ai-query\n          inputs:\n            query: '{{\
  \ user_question }}'\n      - name: get-top-match\n        description: Retrieve the full device record for the top recommendation.\n        consume:\n          namespace: mobileapi\n          operation: devices-read\n          inputs:\n            id: '{{ top_device_id }}'\n      - name: get-images\n        description: Fetch product images for the recommended device.\n        consume:\n          namespace: mobileapi\n          operation: devices-images\n          inputs:\n            id: '{{ top_device_id }}'\n      - name: get-camera\n        description: Pull the main camera sub-resource for the recommended device.\n        consume:\n          namespace: mobileapi\n          operation: devices-main-camera\n          inputs:\n            id: '{{ top_device_id }}'\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mobileapi-dev/refs/heads/main/capabilities/ai-device-recommendation.yaml
tags:
- AI
- Natural Language Query
- Recommendation
- MobileAPI
- Workflow
tools: []
---
