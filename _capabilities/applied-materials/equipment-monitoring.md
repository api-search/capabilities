---
categories: []
consumed_apis:
- amat
description: Workflow capability for monitoring and maintaining semiconductor manufacturing equipment from Applied Materials. Supports fab operations teams tracking equipment status and scheduling preventive maintenance.
layout: capability
name: Applied Materials Equipment Monitoring
operations: []
personas: []
provider_name: Applied Materials
provider_slug: applied-materials
search_terms:
- manufacturing
- schedules preventive maintenance for semiconductor manufacturing equipment
- checks the operational status of a specific piece of fab equipment
- scheduling and recording equipment maintenance activities
- materials engineering
- view maintenance history
- lists all semiconductor manufacturing equipment in the fab
- list fab equipment
- fab operations
- applied materials
- tracking and monitoring semiconductor manufacturing equipment
- engineers overseeing semiconductor equipment operation and performance
- check equipment status
- equipment
- semiconductor
- technicians performing scheduled and emergency equipment maintenance
- equipment monitoring
- views maintenance history and upcoming scheduled maintenance for equipment
- schedule preventive maintenance
- monitor fab equipment status and manage maintenance schedules
slug: equipment-monitoring
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Applied Materials Equipment Monitoring\n  description: >-\n    Workflow capability for monitoring and maintaining semiconductor manufacturing\n    equipment from Applied Materials. Supports fab operations teams tracking\n    equipment status and scheduling preventive maintenance.\n  tags:\n    - Applied Materials\n    - Semiconductor\n    - Manufacturing\n    - Equipment Monitoring\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AMAT_API_TOKEN: AMAT_API_TOKEN\n\ncapability:\n  consumes:\n    - import: amat\n      location: ./shared/applied-materials-api.yaml\n\n  exposes:\n    - type: mcp\n      port: 9090\n      namespace: equipment-monitoring-mcp\n      transport: http\n      description: MCP server for AI-assisted semiconductor equipment monitoring.\n      tools:\n        - name: list-fab-equipment\n          description: Lists all semiconductor manufacturing equipment in\
  \ the fab\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"amat.list-equipment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: check-equipment-status\n          description: Checks the operational status of a specific piece of fab equipment\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"amat.get-equipment\"\n          with:\n            equipmentId: \"tools.equipmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: view-maintenance-history\n          description: Views maintenance history and upcoming scheduled maintenance for equipment\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"amat.list-maintenance\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: schedule-preventive-maintenance\n\
  \          description: Schedules preventive maintenance for semiconductor manufacturing equipment\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"amat.schedule-maintenance\"\n          with:\n            equipmentId: \"tools.equipmentId\"\n            type: \"tools.type\"\n            scheduledDate: \"tools.scheduledDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
