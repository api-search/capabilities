---
api_specs:
- filename: samsara-openapi.yml
  format: yaml
  label: samsara
  slug: samsara
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/samsara/refs/heads/main/openapi/samsara-openapi.yml
categories: []
consumed_apis:
- samsara
description: Safety and compliance workflow combining Samsara safety events, driver coaching, Hours of Service (HOS/ELD) compliance logs, DVIR inspections, and maintenance tracking. Designed for safety managers and compliance officers to monitor driver behavior, enforce regulatory HOS requirements, and track vehicle inspection status.
layout: capability
name: Samsara Safety and Compliance
operations:
- description: List safety events for a time range
  method: GET
  name: list-safety-events
  path: /v1/safety-events
- description: List all DVIR inspection reports
  method: GET
  name: list-dvirs
  path: /v1/dvirs
- description: Submit a DVIR inspection report
  method: POST
  name: create-dvir
  path: /v1/dvirs
- description: List HOS logs for ELD compliance
  method: GET
  name: list-hos-logs
  path: /v1/hos-logs
personas: []
provider_name: Samsara
provider_slug: samsara
search_terms:
- hours of service
- submit a dvir inspection report
- driver safety event monitoring and scoring
- connected operations
- list hours of service eld logs for regulatory compliance reporting
- maintenance
- list safety events for a time range
- dvir
- telematics
- list all dvir vehicle inspection reports
- list all dvir inspection reports
- list hos logs for eld compliance
- samsara
- eld
- inspection
- transportation
- list dvirs
- asset tracking
- logistics
- hours of service eld compliance logs
- driver vehicle inspection reports (dvir)
- safety
- list hos logs
- submit a driver vehicle inspection report (dvir) with defects
- list driver safety events including harsh braking, speeding, and camera events for a time range
- create dvir
- compliance
- iot
- list safety events
- gps tracking
- fleet management
slug: safety-compliance
source_filename: safety-compliance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Samsara Safety and Compliance\"\n  description: >-\n    Safety and compliance workflow combining Samsara safety events, driver coaching,\n    Hours of Service (HOS/ELD) compliance logs, DVIR inspections, and maintenance\n    tracking. Designed for safety managers and compliance officers to monitor driver\n    behavior, enforce regulatory HOS requirements, and track vehicle inspection status.\n  tags:\n    - Compliance\n    - DVIR\n    - ELD\n    - Hours Of Service\n    - Inspection\n    - Maintenance\n    - Safety\n    - Samsara\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SAMSARA_API_TOKEN: SAMSARA_API_TOKEN\n\ncapability:\n  consumes:\n    - import: samsara\n      location: ./shared/samsara.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: safety-compliance-api\n      description: \"Unified REST API for driver safety monitoring and regulatory compliance.\"\
  \n      resources:\n        - path: /v1/safety-events\n          name: safety-events\n          description: \"Driver safety event monitoring and scoring\"\n          operations:\n            - method: GET\n              name: list-safety-events\n              description: \"List safety events for a time range\"\n              call: \"samsara.list-safety-events\"\n              with:\n                startTime: \"rest.startTime\"\n                endTime: \"rest.endTime\"\n                driverIds: \"rest.driverIds\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/dvirs\n          name: dvirs\n          description: \"Driver Vehicle Inspection Reports (DVIR)\"\n          operations:\n            - method: GET\n              name: list-dvirs\n              description: \"List all DVIR inspection reports\"\n              call: \"samsara.list-dvirs\"\n              with:\n                limit: \"rest.limit\"\n    \
  \            after: \"rest.after\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-dvir\n              description: \"Submit a DVIR inspection report\"\n              call: \"samsara.create-dvir\"\n              with:\n                vehicleId: \"rest.vehicleId\"\n                inspectionType: \"rest.inspectionType\"\n                defects: \"rest.defects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/hos-logs\n          name: hos-logs\n          description: \"Hours of Service ELD compliance logs\"\n          operations:\n            - method: GET\n              name: list-hos-logs\n              description: \"List HOS logs for ELD compliance\"\n              call: \"samsara.list-hos-logs\"\n              with:\n                startTime: \"rest.startTime\"\n                endTime: \"rest.endTime\"\
  \n                driverIds: \"rest.driverIds\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: safety-compliance-mcp\n      transport: http\n      description: \"MCP server for AI-assisted safety analysis and compliance monitoring.\"\n      tools:\n        - name: list-safety-events\n          description: \"List driver safety events including harsh braking, speeding, and camera events for a time range\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"samsara.list-safety-events\"\n          with:\n            startTime: \"tools.startTime\"\n            endTime: \"tools.endTime\"\n            driverIds: \"tools.driverIds\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-dvirs\n          description: \"List all DVIR vehicle inspection reports\"\n          hints:\n          \
  \  readOnly: true\n            openWorld: true\n          call: \"samsara.list-dvirs\"\n          with:\n            limit: \"tools.limit\"\n            after: \"tools.after\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-dvir\n          description: \"Submit a Driver Vehicle Inspection Report (DVIR) with defects\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"samsara.create-dvir\"\n          with:\n            vehicleId: \"tools.vehicleId\"\n            inspectionType: \"tools.inspectionType\"\n            defects: \"tools.defects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-hos-logs\n          description: \"List Hours of Service ELD logs for regulatory compliance reporting\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"samsara.list-hos-logs\"\
  \n          with:\n            startTime: \"tools.startTime\"\n            endTime: \"tools.endTime\"\n            driverIds: \"tools.driverIds\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/samsara/refs/heads/main/capabilities/safety-compliance.yaml
tags:
- Compliance
- DVIR
- ELD
- Hours Of Service
- Inspection
- Maintenance
- Safety
- Samsara
tools:
- description: List driver safety events including harsh braking, speeding, and camera events for a time range
  hints:
    openWorld: false
    readOnly: true
  name: list-safety-events
- description: List all DVIR vehicle inspection reports
  hints:
    openWorld: true
    readOnly: true
  name: list-dvirs
- description: Submit a Driver Vehicle Inspection Report (DVIR) with defects
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-dvir
- description: List Hours of Service ELD logs for regulatory compliance reporting
  hints:
    openWorld: false
    readOnly: true
  name: list-hos-logs
---
