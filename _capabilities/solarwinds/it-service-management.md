---
categories:
- incident-management
consumed_apis:
- service-desk
- orion
description: Workflow for IT service management combining Service Desk incident/change management with Orion infrastructure data for IT support and service delivery teams.
layout: capability
name: SolarWinds IT Service Management
operations:
- description: List incidents
  method: GET
  name: list-incidents
  path: /v1/incidents
- description: List service requests
  method: GET
  name: list-service-requests
  path: /v1/service-requests
- description: List change requests
  method: GET
  name: list-changes
  path: /v1/changes
- description: List hardware assets
  method: GET
  name: list-assets
  path: /v1/assets
personas: []
provider_name: SolarWinds
provider_slug: solarwinds
search_terms:
- list service requests
- get incident details
- change management
- network monitoring
- observability
- itsm
- asset management
- database monitoring
- create incident
- create a new incident
- list change requests
- query orion infrastructure data via swql
- list hardware assets
- service desk
- list changes
- list service desk incidents
- query infrastructure
- infrastructure
- ip address management
- list assets
- application monitoring
- get incident
- log management
- incident management
- list incidents
- service request management
- it management
- solarwinds
slug: it-service-management
source_filename: it-service-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SolarWinds IT Service Management\"\n  description: \"Workflow for IT service management combining Service Desk incident/change management with Orion infrastructure data for IT support and service delivery teams.\"\n  tags:\n    - SolarWinds\n    - ITSM\n    - Service Desk\n    - Incident Management\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SWSD_API_TOKEN: SWSD_API_TOKEN\n      ORION_USERNAME: ORION_USERNAME\n      ORION_PASSWORD: ORION_PASSWORD\n\ncapability:\n  consumes:\n    - import: service-desk\n      location: ./shared/service-desk.yaml\n    - import: orion\n      location: ./shared/orion.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: itsm-api\n      description: \"Unified REST API for SolarWinds IT service management.\"\n      resources:\n        - path: /v1/incidents\n          name: incidents\n          description: \"Incident management\"\
  \n          operations:\n            - method: GET\n              name: list-incidents\n              description: \"List incidents\"\n              call: \"service-desk.list-incidents\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/service-requests\n          name: service-requests\n          description: \"Service request management\"\n          operations:\n            - method: GET\n              name: list-service-requests\n              description: \"List service requests\"\n              call: \"service-desk.list-service-requests\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/changes\n          name: changes\n          description: \"Change management\"\n          operations:\n            - method: GET\n              name: list-changes\n              description: \"List change requests\"\n              call: \"service-desk.list-changes\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/assets\n          name: assets\n          description: \"Asset management\"\n          operations:\n            - method: GET\n              name: list-assets\n              description: \"List hardware assets\"\n              call: \"service-desk.list-assets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: itsm-mcp\n      transport: http\n      description: \"MCP server for AI-assisted IT service management.\"\n      tools:\n        - name: list-incidents\n          description: \"List service desk incidents\"\n          hints:\n            readOnly: true\n          call: \"service-desk.list-incidents\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-incident\n          description: \"Get incident details\"\
  \n          hints:\n            readOnly: true\n          call: \"service-desk.get-incident\"\n          with:\n            incidentId: \"tools.incidentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-incident\n          description: \"Create a new incident\"\n          hints:\n            readOnly: false\n          call: \"service-desk.create-incident\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-service-requests\n          description: \"List service requests\"\n          hints:\n            readOnly: true\n          call: \"service-desk.list-service-requests\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-changes\n          description: \"List change requests\"\n          hints:\n            readOnly: true\n          call: \"service-desk.list-changes\"\n          outputParameters:\n     \
  \       - type: object\n              mapping: \"$.\"\n        - name: list-assets\n          description: \"List hardware assets\"\n          hints:\n            readOnly: true\n          call: \"service-desk.list-assets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-infrastructure\n          description: \"Query Orion infrastructure data via SWQL\"\n          hints:\n            readOnly: true\n          call: \"orion.query-swis\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/solarwinds/refs/heads/main/capabilities/it-service-management.yaml
tags:
- SolarWinds
- ITSM
- Service Desk
- Incident Management
tools:
- description: List service desk incidents
  hints:
    readOnly: true
  name: list-incidents
- description: Get incident details
  hints:
    readOnly: true
  name: get-incident
- description: Create a new incident
  hints:
    readOnly: false
  name: create-incident
- description: List service requests
  hints:
    readOnly: true
  name: list-service-requests
- description: List change requests
  hints:
    readOnly: true
  name: list-changes
- description: List hardware assets
  hints:
    readOnly: true
  name: list-assets
- description: Query Orion infrastructure data via SWQL
  hints:
    readOnly: true
  name: query-infrastructure
---
