---
categories: []
consumed_apis: []
description: End-to-end workflow that takes a partial device name from a user, resolves it via autocomplete, fetches the matching device record with full specifications and images, and optionally pulls the per-category spec payloads (battery, display, platform, memory, cameras) for downstream insurance, trade-in, and e-commerce flows.
layout: capability
name: Device Lookup Workflow
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
- search
- mobile devices
- data api
- device specifications
- mobileapi
- developer tools
- device lookup
slug: device-lookup
source_filename: device-lookup.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Device Lookup Workflow\n  description: >-\n    End-to-end workflow that takes a partial device name from a user, resolves\n    it via autocomplete, fetches the matching device record with full\n    specifications and images, and optionally pulls the per-category spec\n    payloads (battery, display, platform, memory, cameras) for downstream\n    insurance, trade-in, and e-commerce flows.\n  tags:\n    - Device Lookup\n    - Mobile Devices\n    - MobileAPI\n    - Search\n    - Workflow\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  imports:\n    - shared/mobileapi-capability.yaml\n  workflow:\n    name: device-lookup\n    steps:\n      - name: autocomplete-device\n        description: Resolve a partial device name to a list of canonical suggestions.\n        consume:\n          namespace: mobileapi\n          operation: devices-autocomplete\n          inputs:\n            q: '{{ user_query }}'\n            limit: 10\n\
  \      - name: search-device\n        description: Search for the user's chosen device by name or model number.\n        consume:\n          namespace: mobileapi\n          operation: devices-search\n          inputs:\n            name: '{{ chosen_device_name }}'\n      - name: get-device\n        description: Retrieve the complete device record by id.\n        consume:\n          namespace: mobileapi\n          operation: devices-read\n          inputs:\n            id: '{{ device_id }}'\n      - name: get-device-images\n        description: Fetch high-resolution gallery images for the device.\n        consume:\n          namespace: mobileapi\n          operation: devices-images\n          inputs:\n            id: '{{ device_id }}'\n      - name: get-device-battery\n        description: Fetch the battery sub-resource for trade-in or repair scoring.\n        consume:\n          namespace: mobileapi\n          operation: devices-battery\n          inputs:\n            id: '{{ device_id\
  \ }}'\n      - name: get-device-display\n        description: Fetch the display sub-resource for parts selection.\n        consume:\n          namespace: mobileapi\n          operation: devices-display\n          inputs:\n            id: '{{ device_id }}'\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mobileapi-dev/refs/heads/main/capabilities/device-lookup.yaml
tags:
- Device Lookup
- Mobile Devices
- MobileAPI
- Search
- Workflow
tools: []
---
