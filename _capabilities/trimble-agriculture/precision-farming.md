---
categories: []
consumed_apis: []
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
- list crop zones
- precision agriculture
- upload a prescription for trimble display delivery
- list crop zones for an organization and season
- list equipment activities
- create a work order for farm operators
- trimble agriculture
- list all fields in a farm with their boundaries
- list work orders with status filtering
- list prescriptions
- create field
- list fields
- get as applied data
- list all fields in a farm
- telematics
- upload a variable-rate prescription to send to trimble field displays
- add a new farm to an organization
- list in-field equipment activities (planting, spraying, harvesting)
- download as-applied field data for compliance and productivity analysis
- create a new field with boundary
- farm registry
- in-field equipment activities from precision ag displays
- iot
- farming
- list work orders
- crop zone tracking by season
- create prescription
- list crop zones for a growing season
- variable-rate prescription management
- create work order
- list variable-rate prescription files for crop zones
- prescriptions
- field management
- list equipment activities (planting, spraying, harvesting)
- list all farms for a trimble agriculture organization
- list prescription files
- list farm work orders and their completion status
- create a work order to assign field jobs to farm operators
- list farms
- create farm
- work orders
- as-applied data from field operations
- add a new farm to a trimble agriculture organization
- work order planning and dispatch
- equipment activities
- download as-applied data for compliance and analysis
- list all farms for an organization
- agriculture
slug: precision-farming
source_filename: precision-farming.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Trimble Agriculture Precision Farming\n  description: Unified precision farming capability combining farm setup, field management, crop zone tracking, equipment\n    activity monitoring, work order dispatch, and prescription management. Powers agricultural data workflows for agronomists,\n    custom applicators, and farm management platforms.\n  tags:\n  - Trimble Agriculture\n  - Precision Agriculture\n  - Farming\n  - Field Management\n  - Prescriptions\n  - Work Orders\n  - Equipment Activities\n  - IoT\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TRIMBLE_AG_ACCESS_TOKEN: TRIMBLE_AG_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: trimble-ag\n    baseUri: https://cloud.api.trimble.com/Trimble-Ag-Software/externalApi/3.0\n    description: Trimble Agriculture Cloud REST API for precision farming data\n    authentication:\n      type: bearer\n      token: '{{TRIMBLE_AG_ACCESS_TOKEN}}'\n\
  \    resources:\n    - name: farms\n      path: /organizations/{organizationId}/farms\n      description: Farm management\n      operations:\n      - name: list-farms\n        method: GET\n        description: List farms for an organization\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-farm\n        method: GET\n        description: Get farm details\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required: true\n        - name: farmId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-farm\n\
  \        method: POST\n        description: Create a new farm\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            address: '{{tools.address}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fields\n      path: /organizations/{organizationId}/farms/{farmId}/fields\n      description: Field management\n      operations:\n      - name: list-fields\n        method: GET\n        description: List fields for a farm\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required: true\n        - name: farmId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n         \
  \ type: object\n          value: $.\n      - name: create-field\n        method: POST\n        description: Create a new field with optional boundary\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required: true\n        - name: farmId\n          in: path\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            boundary: '{{tools.boundary}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: crop-zones\n      path: /organizations/{organizationId}/cropzones\n      description: Crop zone management\n      operations:\n      - name: list-crop-zones\n        method: GET\n        description: List crop zones for an organization\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required:\
  \ true\n        - name: season\n          in: query\n          type: integer\n          required: false\n        - name: fieldId\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: equipment-activities\n      path: /organizations/{organizationId}/equipmentactivities\n      description: Equipment activity data from precision ag displays\n      operations:\n      - name: list-equipment-activities\n        method: GET\n        description: List equipment activities (planting, spraying, harvesting, etc.)\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required: true\n        - name: activityType\n          in: query\n          type: string\n          required: false\n        - name: startDate\n          in: query\n          type: string\n          required: false\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-as-applied-data\n        method: GET\n        description: Download as-applied data for an equipment activity\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required: true\n        - name: activityId\n          in: path\n          type: string\n          required: true\n        - name: format\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: work-orders\n      path: /organizations/{organizationId}/workorders\n      description: Work order planning and assignment\n      operations:\n      - name: list-work-orders\n        method: GET\n        description: List work orders\n        inputParameters:\n        - name: organizationId\n\
  \          in: path\n          type: string\n          required: true\n        - name: status\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-work-order\n        method: POST\n        description: Create a work order for farm operators\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            cropZoneId: '{{tools.cropZoneId}}'\n            activityType: '{{tools.activityType}}'\n            scheduledDate: '{{tools.scheduledDate}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: prescriptions\n      path: /organizations/{organizationId}/prescriptions\n  \
  \    description: Prescription file management\n      operations:\n      - name: list-prescriptions\n        method: GET\n        description: List prescriptions\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-prescription\n        method: POST\n        description: Upload a prescription for variable-rate field application\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            cropZoneId: '{{tools.cropZoneId}}'\n            materialType: '{{tools.materialType}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \  exposes:\n  - type: rest\n    port: 8080\n    namespace: precision-farming-api\n    description: Unified REST API for Trimble Agriculture precision farming operations.\n    resources:\n    - path: /v1/farms\n      name: farms\n      description: Farm registry\n      operations:\n      - method: GET\n        name: list-farms\n        description: List all farms for an organization\n        call: trimble-ag.list-farms\n        with:\n          organizationId: rest.organizationId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-farm\n        description: Add a new farm to an organization\n        call: trimble-ag.create-farm\n        with:\n          organizationId: rest.organizationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/fields\n      name: fields\n      description: Field management\n      operations:\n      - method: GET\n        name: list-fields\n        description:\
  \ List all fields in a farm\n        call: trimble-ag.list-fields\n        with:\n          organizationId: rest.organizationId\n          farmId: rest.farmId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-field\n        description: Create a new field with boundary\n        call: trimble-ag.create-field\n        with:\n          organizationId: rest.organizationId\n          farmId: rest.farmId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/crop-zones\n      name: crop-zones\n      description: Crop zone tracking by season\n      operations:\n      - method: GET\n        name: list-crop-zones\n        description: List crop zones for an organization and season\n        call: trimble-ag.list-crop-zones\n        with:\n          organizationId: rest.organizationId\n          season: rest.season\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /v1/equipment-activities\n      name: equipment-activities\n      description: In-field equipment activities from precision ag displays\n      operations:\n      - method: GET\n        name: list-equipment-activities\n        description: List equipment activities (planting, spraying, harvesting)\n        call: trimble-ag.list-equipment-activities\n        with:\n          organizationId: rest.organizationId\n          activityType: rest.activityType\n          startDate: rest.startDate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/equipment-activities/{activityId}/as-applied\n      name: as-applied-data\n      description: As-applied data from field operations\n      operations:\n      - method: GET\n        name: get-as-applied-data\n        description: Download as-applied data for compliance and analysis\n        call: trimble-ag.get-as-applied-data\n        with:\n          organizationId: rest.organizationId\n          activityId:\
  \ rest.activityId\n          format: rest.format\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/work-orders\n      name: work-orders\n      description: Work order planning and dispatch\n      operations:\n      - method: GET\n        name: list-work-orders\n        description: List work orders with status filtering\n        call: trimble-ag.list-work-orders\n        with:\n          organizationId: rest.organizationId\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-work-order\n        description: Create a work order for farm operators\n        call: trimble-ag.create-work-order\n        with:\n          organizationId: rest.organizationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/prescriptions\n      name: prescriptions\n      description: Variable-rate prescription management\n      operations:\n\
  \      - method: GET\n        name: list-prescriptions\n        description: List prescription files\n        call: trimble-ag.list-prescriptions\n        with:\n          organizationId: rest.organizationId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-prescription\n        description: Upload a prescription for Trimble display delivery\n        call: trimble-ag.create-prescription\n        with:\n          organizationId: rest.organizationId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: precision-farming-mcp\n    transport: http\n    description: MCP server for AI-assisted precision agriculture data management.\n    tools:\n    - name: list-farms\n      description: List all farms for a Trimble Agriculture organization\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trimble-ag.list-farms\n      with:\n        organizationId:\
  \ tools.organizationId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-farm\n      description: Add a new farm to a Trimble Agriculture organization\n      hints:\n        readOnly: false\n        openWorld: false\n      call: trimble-ag.create-farm\n      with:\n        organizationId: tools.organizationId\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-fields\n      description: List all fields in a farm with their boundaries\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trimble-ag.list-fields\n      with:\n        organizationId: tools.organizationId\n        farmId: tools.farmId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-crop-zones\n      description: List crop zones for a growing season\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trimble-ag.list-crop-zones\n      with:\n  \
  \      organizationId: tools.organizationId\n        season: tools.season\n        fieldId: tools.fieldId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-equipment-activities\n      description: List in-field equipment activities (planting, spraying, harvesting)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trimble-ag.list-equipment-activities\n      with:\n        organizationId: tools.organizationId\n        activityType: tools.activityType\n        startDate: tools.startDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-as-applied-data\n      description: Download as-applied field data for compliance and productivity analysis\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trimble-ag.get-as-applied-data\n      with:\n        organizationId: tools.organizationId\n        activityId: tools.activityId\n        format: tools.format\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-work-orders\n      description: List farm work orders and their completion status\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trimble-ag.list-work-orders\n      with:\n        organizationId: tools.organizationId\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-work-order\n      description: Create a work order to assign field jobs to farm operators\n      hints:\n        readOnly: false\n        openWorld: false\n      call: trimble-ag.create-work-order\n      with:\n        organizationId: tools.organizationId\n        title: tools.title\n        cropZoneId: tools.cropZoneId\n        activityType: tools.activityType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-prescriptions\n      description: List variable-rate prescription files for crop zones\n      hints:\n        readOnly: true\n\
  \        openWorld: false\n      call: trimble-ag.list-prescriptions\n      with:\n        organizationId: tools.organizationId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-prescription\n      description: Upload a variable-rate prescription to send to Trimble field displays\n      hints:\n        readOnly: false\n        openWorld: false\n      call: trimble-ag.create-prescription\n      with:\n        organizationId: tools.organizationId\n        name: tools.name\n        cropZoneId: tools.cropZoneId\n        materialType: tools.materialType\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
