---
categories:
- incident-management
consumed_apis: []
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
- ip address management
- infrastructure
- log management
- query orion infrastructure data via swql
- it management
- create incident
- network monitoring
- incident management
- list changes
- list change requests
- change management
- itsm
- application monitoring
- create a new incident
- observability
- service request management
- database monitoring
- query infrastructure
- get incident details
- list assets
- solarwinds
- list hardware assets
- service desk
- get incident
- list incidents
- asset management
- list service desk incidents
slug: it-service-management
source_filename: it-service-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SolarWinds IT Service Management\n  description: Workflow for IT service management combining Service Desk incident/change management with Orion infrastructure\n    data for IT support and service delivery teams.\n  tags:\n  - SolarWinds\n  - ITSM\n  - Service Desk\n  - Incident Management\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SWSD_API_TOKEN: SWSD_API_TOKEN\n    ORION_USERNAME: ORION_USERNAME\n    ORION_PASSWORD: ORION_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: service-desk\n    baseUri: https://api.samanage.com\n    description: SolarWinds Service Desk REST API\n    authentication:\n      type: bearer\n      token: '{{SWSD_API_TOKEN}}'\n    resources:\n    - name: incidents\n      path: /incidents.json\n      description: Incident management\n      operations:\n      - name: list-incidents\n        method: GET\n        description: List incidents\n        inputParameters:\n\
  \        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Items per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-incident\n        method: POST\n        description: Create an incident\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            incident:\n              name: '{{tools.name}}'\n              description: '{{tools.description}}'\n      - name: get-incident\n        method: GET\n        description: Get incident details\n        inputParameters:\n        - name: incidentId\n          in: path\n          type: integer\n          required: true\n\
  \          description: Incident ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-incident\n        method: PUT\n        description: Update an incident\n        inputParameters:\n        - name: incidentId\n          in: path\n          type: integer\n          required: true\n          description: Incident ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: service-requests\n      path: /service_requests.json\n      description: Service request management\n      operations:\n      - name: list-service-requests\n        method: GET\n        description: List service requests\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-service-request\n        method: POST\n        description: Create a service\
  \ request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: changes\n      path: /changes.json\n      description: Change management\n      operations:\n      - name: list-changes\n        method: GET\n        description: List change requests\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: assets\n      path: /hardwares.json\n      description: Asset management\n      operations:\n      - name: list-assets\n        method: GET\n        description: List hardware assets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: orion\n    baseUri: https://localhost:17774/SolarWinds/InformationService/v3/Json\n    description: SolarWinds Orion Platform SWIS REST API\n    authentication:\n      type: basic\n  \
  \    username: '{{ORION_USERNAME}}'\n      password: '{{ORION_PASSWORD}}'\n    resources:\n    - name: query\n      path: /Query\n      description: SWQL query execution\n      operations:\n      - name: query-swis\n        method: GET\n        description: Execute a SWQL query\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: SWQL query string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: crud\n      path: /\n      description: CRUD operations on SWIS entities\n      operations:\n      - name: create-entity\n        method: POST\n        description: Create a SWIS entity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: read-entity\n        method: GET\n        description: Read a SWIS entity\n        inputParameters:\n\
  \        - name: uri\n          in: path\n          type: string\n          required: true\n          description: SWIS entity URI\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-entity\n        method: POST\n        description: Update a SWIS entity\n        inputParameters:\n        - name: uri\n          in: path\n          type: string\n          required: true\n          description: SWIS entity URI\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-entity\n        method: DELETE\n        description: Delete a SWIS entity\n        inputParameters:\n        - name: uri\n          in: path\n          type: string\n          required: true\n          description: SWIS entity URI\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n   \
  \       value: $.\n      - name: invoke-verb\n        method: POST\n        description: Invoke a verb on a SWIS entity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bulk\n      path: /BulkDelete\n      description: Bulk operations\n      operations:\n      - name: bulk-delete\n        method: POST\n        description: Delete multiple SWIS entities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: itsm-api\n    description: Unified REST API for SolarWinds IT service management.\n    resources:\n    - path: /v1/incidents\n      name: incidents\n      description: Incident management\n      operations:\n      - method: GET\n        name: list-incidents\n        description: List incidents\n        call: service-desk.list-incidents\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/service-requests\n      name: service-requests\n      description: Service request management\n      operations:\n      - method: GET\n        name: list-service-requests\n        description: List service requests\n        call: service-desk.list-service-requests\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/changes\n      name: changes\n      description: Change management\n      operations:\n      - method: GET\n        name: list-changes\n        description: List change requests\n        call: service-desk.list-changes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/assets\n      name: assets\n      description: Asset management\n      operations:\n      - method: GET\n        name: list-assets\n        description: List hardware assets\n        call: service-desk.list-assets\n        outputParameters:\n        - type: object\n   \
  \       mapping: $.\n  - type: mcp\n    port: 9092\n    namespace: itsm-mcp\n    transport: http\n    description: MCP server for AI-assisted IT service management.\n    tools:\n    - name: list-incidents\n      description: List service desk incidents\n      hints:\n        readOnly: true\n      call: service-desk.list-incidents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-incident\n      description: Get incident details\n      hints:\n        readOnly: true\n      call: service-desk.get-incident\n      with:\n        incidentId: tools.incidentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-incident\n      description: Create a new incident\n      hints:\n        readOnly: false\n      call: service-desk.create-incident\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-service-requests\n      description: List service requests\n      hints:\n        readOnly: true\n\
  \      call: service-desk.list-service-requests\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-changes\n      description: List change requests\n      hints:\n        readOnly: true\n      call: service-desk.list-changes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-assets\n      description: List hardware assets\n      hints:\n        readOnly: true\n      call: service-desk.list-assets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-infrastructure\n      description: Query Orion infrastructure data via SWQL\n      hints:\n        readOnly: true\n      call: orion.query-swis\n      with:\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
