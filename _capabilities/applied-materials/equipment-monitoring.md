---
categories: []
consumed_apis: []
description: Workflow capability for monitoring and maintaining semiconductor manufacturing equipment from Applied Materials. Supports fab operations teams tracking equipment status and scheduling preventive maintenance.
layout: capability
name: Applied Materials Equipment Monitoring
operations: []
personas: []
provider_name: Applied Materials
provider_slug: applied-materials
search_terms:
- semiconductor
- manufacturing
- applied materials
- equipment monitoring
- scheduling and recording equipment maintenance activities
- fab operations
- engineers overseeing semiconductor equipment operation and performance
- technicians performing scheduled and emergency equipment maintenance
- checks the operational status of a specific piece of fab equipment
- equipment
- tracking and monitoring semiconductor manufacturing equipment
- materials engineering
- view maintenance history
- list fab equipment
- monitor fab equipment status and manage maintenance schedules
- check equipment status
- views maintenance history and upcoming scheduled maintenance for equipment
- schedules preventive maintenance for semiconductor manufacturing equipment
- schedule preventive maintenance
- lists all semiconductor manufacturing equipment in the fab
slug: equipment-monitoring
source_filename: equipment-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Applied Materials Equipment Monitoring\n  description: Workflow capability for monitoring and maintaining semiconductor manufacturing equipment from Applied Materials.\n    Supports fab operations teams tracking equipment status and scheduling preventive maintenance.\n  tags:\n  - Applied Materials\n  - Semiconductor\n  - Manufacturing\n  - Equipment Monitoring\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AMAT_API_TOKEN: AMAT_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: amat\n    baseUri: https://api.applied-materials.com/v1\n    description: Applied Materials equipment management API\n    authentication:\n      type: bearer\n      token: '{{AMAT_API_TOKEN}}'\n    resources:\n    - name: equipment\n      path: /equipment\n      description: Semiconductor manufacturing equipment\n      operations:\n      - name: list-equipment\n        method: GET\n        description:\
  \ Returns a list of manufacturing equipment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-equipment\n        method: GET\n        description: Returns details for a specific piece of equipment\n        inputParameters:\n        - name: equipmentId\n          in: path\n          type: string\n          required: true\n          description: Equipment identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: maintenance\n      path: /maintenance\n      description: Equipment maintenance records\n      operations:\n      - name: list-maintenance\n        method: GET\n        description: Returns maintenance records\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: schedule-maintenance\n        method: POST\n\
  \        description: Schedules a maintenance event\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            equipmentId: '{{tools.equipmentId}}'\n            type: '{{tools.type}}'\n            scheduledDate: '{{tools.scheduledDate}}'\n  exposes:\n  - type: mcp\n    port: 9090\n    namespace: equipment-monitoring-mcp\n    transport: http\n    description: MCP server for AI-assisted semiconductor equipment monitoring.\n    tools:\n    - name: list-fab-equipment\n      description: Lists all semiconductor manufacturing equipment in the fab\n      hints:\n        readOnly: true\n        idempotent: true\n      call: amat.list-equipment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-equipment-status\n      description: Checks the operational status of a specific piece of fab equipment\n      hints:\n        readOnly:\
  \ true\n        idempotent: true\n      call: amat.get-equipment\n      with:\n        equipmentId: tools.equipmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: view-maintenance-history\n      description: Views maintenance history and upcoming scheduled maintenance for equipment\n      hints:\n        readOnly: true\n        idempotent: true\n      call: amat.list-maintenance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: schedule-preventive-maintenance\n      description: Schedules preventive maintenance for semiconductor manufacturing equipment\n      hints:\n        readOnly: false\n        destructive: false\n      call: amat.schedule-maintenance\n      with:\n        equipmentId: tools.equipmentId\n        type: tools.type\n        scheduledDate: tools.scheduledDate\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/applied-materials/refs/heads/main/capabilities/equipment-monitoring.yaml
tags:
- Applied Materials
- Semiconductor
- Manufacturing
- Equipment Monitoring
tools:
- description: Lists all semiconductor manufacturing equipment in the fab
  hints:
    idempotent: true
    readOnly: true
  name: list-fab-equipment
- description: Checks the operational status of a specific piece of fab equipment
  hints:
    idempotent: true
    readOnly: true
  name: check-equipment-status
- description: Views maintenance history and upcoming scheduled maintenance for equipment
  hints:
    idempotent: true
    readOnly: true
  name: view-maintenance-history
- description: Schedules preventive maintenance for semiconductor manufacturing equipment
  hints:
    destructive: false
    readOnly: false
  name: schedule-preventive-maintenance
---
