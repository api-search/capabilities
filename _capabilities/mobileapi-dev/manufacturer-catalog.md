---
categories: []
consumed_apis: []
description: Workflow for building a manufacturer-driven device catalog. Lists all manufacturers, fetches a single manufacturer's profile, then enumerates devices for that manufacturer and (optionally) by launch year or device type to power category navigation, brand pages, and "new releases" feeds.
layout: capability
name: Manufacturer Catalog Workflow
operations: []
personas: []
provider_name: MobileAPI.dev
provider_slug: mobileapi-dev
search_terms:
- saas
- rest api
- mobile data
- workflow
- catalog
- phone specs
- mobile devices
- data api
- device specifications
- mobileapi
- manufacturers
- developer tools
slug: manufacturer-catalog
source_filename: manufacturer-catalog.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Manufacturer Catalog Workflow\n  description: >-\n    Workflow for building a manufacturer-driven device catalog. Lists all\n    manufacturers, fetches a single manufacturer's profile, then enumerates\n    devices for that manufacturer and (optionally) by launch year or device\n    type to power category navigation, brand pages, and \"new releases\" feeds.\n  tags:\n    - Catalog\n    - Manufacturers\n    - MobileAPI\n    - Mobile Devices\n    - Workflow\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  imports:\n    - shared/mobileapi-capability.yaml\n  workflow:\n    name: manufacturer-catalog\n    steps:\n      - name: list-manufacturers\n        description: Retrieve all known manufacturers.\n        consume:\n          namespace: mobileapi\n          operation: manufacturers-list\n      - name: get-manufacturer\n        description: Retrieve details for the selected manufacturer.\n        consume:\n          namespace:\
  \ mobileapi\n          operation: manufacturers-read\n          inputs:\n            id: '{{ manufacturer_id }}'\n      - name: devices-by-manufacturer\n        description: List all devices for the manufacturer.\n        consume:\n          namespace: mobileapi\n          operation: devices-by-manufacturer\n          inputs:\n            manufacturer: '{{ manufacturer_name }}'\n      - name: devices-by-year\n        description: Filter recent releases for the manufacturer by launch year.\n        consume:\n          namespace: mobileapi\n          operation: devices-by-year\n          inputs:\n            year: '{{ launch_year }}'\n      - name: devices-by-type\n        description: Filter manufacturer devices by type (phone, tablet, watch, laptop).\n        consume:\n          namespace: mobileapi\n          operation: devices-by-type\n          inputs:\n            device_type: '{{ device_type }}'\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mobileapi-dev/refs/heads/main/capabilities/manufacturer-catalog.yaml
tags:
- Catalog
- Manufacturers
- MobileAPI
- Mobile Devices
- Workflow
tools: []
---
