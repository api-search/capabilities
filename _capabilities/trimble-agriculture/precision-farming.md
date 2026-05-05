---
api_specs:
- filename: trimble-agriculture-openapi.yml
  format: yaml
  label: trimble-ag
  slug: trimble-ag
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/trimble-agriculture/refs/heads/main/openapi/trimble-agriculture-openapi.yml
categories: []
consumed_apis:
- trimble-ag
description: Unified precision farming capability combining farm setup, field management, crop zone tracking, equipment activity monitoring, work order dispatch, and prescription management. Powers agricultural data workflows for agronomists, custom applicators, and farm management platforms.
layout: capability
name: Trimble Agriculture Precision Farming
operations:
- description: List all farms for an organization
  method: GET
  name: list-farms
  path: /v1/farms
- description: Add a new farm to an organization
  method: POST
  name: create-farm
  path: /v1/farms
- description: List all fields in a farm
  method: GET
  name: list-fields
  path: /v1/fields
- description: Create a new field with boundary
  method: POST
  name: create-field
  path: /v1/fields
- description: List crop zones for an organization and season
  method: GET
  name: list-crop-zones
  path: /v1/crop-zones
- description: List equipment activities (planting, spraying, harvesting)
  method: GET
  name: list-equipment-activities
  path: /v1/equipment-activities
- description: Download as-applied data for compliance and analysis
  method: GET
  name: get-as-applied-data
  path: /v1/equipment-activities/{activityId}/as-applied
- description: List work orders with status filtering
  method: GET
  name: list-work-orders
  path: /v1/work-orders
- description: Create a work order for farm operators
  method: POST
  name: create-work-order
  path: /v1/work-orders
- description: List prescription files
  method: GET
  name: list-prescriptions
  path: /v1/prescriptions
- description: Upload a prescription for Trimble display delivery
  method: POST
  name: create-prescription
  path: /v1/prescriptions
personas: []
provider_name: Trimble Agriculture
provider_slug: trimble-agriculture
search_terms:
- download as-applied field data for compliance and productivity analysis
- work orders
- in-field equipment activities from precision ag displays
- create a work order for farm operators
- farming
- trimble agriculture
- prescriptions
- crop zone tracking by season
- list all fields in a farm
- telematics
- list work orders with status filtering
- as-applied data from field operations
- create work order
- create farm
- precision agriculture
- create a new field with boundary
- field management
- list prescription files
- download as-applied data for compliance and analysis
- list all fields in a farm with their boundaries
- list crop zones for a growing season
- equipment activities
- create prescription
- work order planning and dispatch
- list equipment activities (planting, spraying, harvesting)
- add a new farm to a trimble agriculture organization
- list farms
- list variable-rate prescription files for crop zones
- list crop zones
- list equipment activities
- variable-rate prescription management
- create field
- create a work order to assign field jobs to farm operators
- agriculture
- list prescriptions
- get as applied data
- upload a variable-rate prescription to send to trimble field displays
- upload a prescription for trimble display delivery
- list all farms for an organization
- list in-field equipment activities (planting, spraying, harvesting)
- add a new farm to an organization
- list farm work orders and their completion status
- iot
- list all farms for a trimble agriculture organization
- farm registry
- list fields
- list crop zones for an organization and season
- list work orders
slug: precision-farming
source_filename: precision-farming.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Trimble Agriculture Precision Farming\"\n  description: >-\n    Unified precision farming capability combining farm setup, field management,\n    crop zone tracking, equipment activity monitoring, work order dispatch, and\n    prescription management. Powers agricultural data workflows for agronomists,\n    custom applicators, and farm management platforms.\n  tags:\n    - Trimble Agriculture\n    - Precision Agriculture\n    - Farming\n    - Field Management\n    - Prescriptions\n    - Work Orders\n    - Equipment Activities\n    - IoT\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TRIMBLE_AG_ACCESS_TOKEN: TRIMBLE_AG_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: trimble-ag\n      location: ./shared/trimble-agriculture.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: precision-farming-api\n      description: \"Unified REST API for Trimble\
  \ Agriculture precision farming operations.\"\n      resources:\n        - path: /v1/farms\n          name: farms\n          description: Farm registry\n          operations:\n            - method: GET\n              name: list-farms\n              description: List all farms for an organization\n              call: \"trimble-ag.list-farms\"\n              with:\n                organizationId: \"rest.organizationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-farm\n              description: Add a new farm to an organization\n              call: \"trimble-ag.create-farm\"\n              with:\n                organizationId: \"rest.organizationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/fields\n          name: fields\n          description: Field management\n          operations:\n         \
  \   - method: GET\n              name: list-fields\n              description: List all fields in a farm\n              call: \"trimble-ag.list-fields\"\n              with:\n                organizationId: \"rest.organizationId\"\n                farmId: \"rest.farmId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-field\n              description: Create a new field with boundary\n              call: \"trimble-ag.create-field\"\n              with:\n                organizationId: \"rest.organizationId\"\n                farmId: \"rest.farmId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/crop-zones\n          name: crop-zones\n          description: Crop zone tracking by season\n          operations:\n            - method: GET\n              name: list-crop-zones\n              description: List crop\
  \ zones for an organization and season\n              call: \"trimble-ag.list-crop-zones\"\n              with:\n                organizationId: \"rest.organizationId\"\n                season: \"rest.season\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/equipment-activities\n          name: equipment-activities\n          description: In-field equipment activities from precision ag displays\n          operations:\n            - method: GET\n              name: list-equipment-activities\n              description: List equipment activities (planting, spraying, harvesting)\n              call: \"trimble-ag.list-equipment-activities\"\n              with:\n                organizationId: \"rest.organizationId\"\n                activityType: \"rest.activityType\"\n                startDate: \"rest.startDate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n\
  \        - path: /v1/equipment-activities/{activityId}/as-applied\n          name: as-applied-data\n          description: As-applied data from field operations\n          operations:\n            - method: GET\n              name: get-as-applied-data\n              description: Download as-applied data for compliance and analysis\n              call: \"trimble-ag.get-as-applied-data\"\n              with:\n                organizationId: \"rest.organizationId\"\n                activityId: \"rest.activityId\"\n                format: \"rest.format\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/work-orders\n          name: work-orders\n          description: Work order planning and dispatch\n          operations:\n            - method: GET\n              name: list-work-orders\n              description: List work orders with status filtering\n              call: \"trimble-ag.list-work-orders\"\n            \
  \  with:\n                organizationId: \"rest.organizationId\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-work-order\n              description: Create a work order for farm operators\n              call: \"trimble-ag.create-work-order\"\n              with:\n                organizationId: \"rest.organizationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/prescriptions\n          name: prescriptions\n          description: Variable-rate prescription management\n          operations:\n            - method: GET\n              name: list-prescriptions\n              description: List prescription files\n              call: \"trimble-ag.list-prescriptions\"\n              with:\n                organizationId: \"rest.organizationId\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-prescription\n              description: Upload a prescription for Trimble display delivery\n              call: \"trimble-ag.create-prescription\"\n              with:\n                organizationId: \"rest.organizationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: precision-farming-mcp\n      transport: http\n      description: \"MCP server for AI-assisted precision agriculture data management.\"\n      tools:\n        - name: list-farms\n          description: List all farms for a Trimble Agriculture organization\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trimble-ag.list-farms\"\n          with:\n            organizationId: \"tools.organizationId\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: create-farm\n          description: Add a new farm to a Trimble Agriculture organization\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"trimble-ag.create-farm\"\n          with:\n            organizationId: \"tools.organizationId\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-fields\n          description: List all fields in a farm with their boundaries\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trimble-ag.list-fields\"\n          with:\n            organizationId: \"tools.organizationId\"\n            farmId: \"tools.farmId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-crop-zones\n          description: List crop zones for a growing season\n          hints:\n           \
  \ readOnly: true\n            openWorld: false\n          call: \"trimble-ag.list-crop-zones\"\n          with:\n            organizationId: \"tools.organizationId\"\n            season: \"tools.season\"\n            fieldId: \"tools.fieldId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-equipment-activities\n          description: List in-field equipment activities (planting, spraying, harvesting)\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trimble-ag.list-equipment-activities\"\n          with:\n            organizationId: \"tools.organizationId\"\n            activityType: \"tools.activityType\"\n            startDate: \"tools.startDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-as-applied-data\n          description: Download as-applied field data for compliance and productivity analysis\n       \
  \   hints:\n            readOnly: true\n            openWorld: false\n          call: \"trimble-ag.get-as-applied-data\"\n          with:\n            organizationId: \"tools.organizationId\"\n            activityId: \"tools.activityId\"\n            format: \"tools.format\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-work-orders\n          description: List farm work orders and their completion status\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trimble-ag.list-work-orders\"\n          with:\n            organizationId: \"tools.organizationId\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-work-order\n          description: Create a work order to assign field jobs to farm operators\n          hints:\n            readOnly: false\n            openWorld: false\n     \
  \     call: \"trimble-ag.create-work-order\"\n          with:\n            organizationId: \"tools.organizationId\"\n            title: \"tools.title\"\n            cropZoneId: \"tools.cropZoneId\"\n            activityType: \"tools.activityType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-prescriptions\n          description: List variable-rate prescription files for crop zones\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trimble-ag.list-prescriptions\"\n          with:\n            organizationId: \"tools.organizationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-prescription\n          description: Upload a variable-rate prescription to send to Trimble field displays\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"trimble-ag.create-prescription\"\n\
  \          with:\n            organizationId: \"tools.organizationId\"\n            name: \"tools.name\"\n            cropZoneId: \"tools.cropZoneId\"\n            materialType: \"tools.materialType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/trimble-agriculture/refs/heads/main/capabilities/precision-farming.yaml
tags:
- Trimble Agriculture
- Precision Agriculture
- Farming
- Field Management
- Prescriptions
- Work Orders
- Equipment Activities
- IoT
tools:
- description: List all farms for a Trimble Agriculture organization
  hints:
    openWorld: false
    readOnly: true
  name: list-farms
- description: Add a new farm to a Trimble Agriculture organization
  hints:
    openWorld: false
    readOnly: false
  name: create-farm
- description: List all fields in a farm with their boundaries
  hints:
    openWorld: false
    readOnly: true
  name: list-fields
- description: List crop zones for a growing season
  hints:
    openWorld: false
    readOnly: true
  name: list-crop-zones
- description: List in-field equipment activities (planting, spraying, harvesting)
  hints:
    openWorld: false
    readOnly: true
  name: list-equipment-activities
- description: Download as-applied field data for compliance and productivity analysis
  hints:
    openWorld: false
    readOnly: true
  name: get-as-applied-data
- description: List farm work orders and their completion status
  hints:
    openWorld: false
    readOnly: true
  name: list-work-orders
- description: Create a work order to assign field jobs to farm operators
  hints:
    openWorld: false
    readOnly: false
  name: create-work-order
- description: List variable-rate prescription files for crop zones
  hints:
    openWorld: false
    readOnly: true
  name: list-prescriptions
- description: Upload a variable-rate prescription to send to Trimble field displays
  hints:
    openWorld: false
    readOnly: false
  name: create-prescription
---
