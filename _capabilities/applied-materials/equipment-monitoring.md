---
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
- views maintenance history and upcoming scheduled maintenance for equipment
- engineers overseeing semiconductor equipment operation and performance
- check equipment status
- checks the operational status of a specific piece of fab equipment
- equipment
- materials engineering
- fab operations
- equipment monitoring
- lists all semiconductor manufacturing equipment in the fab
- semiconductor
- list fab equipment
- schedules preventive maintenance for semiconductor manufacturing equipment
- view maintenance history
- applied materials
- tracking and monitoring semiconductor manufacturing equipment
- technicians performing scheduled and emergency equipment maintenance
- schedule preventive maintenance
- monitor fab equipment status and manage maintenance schedules
- scheduling and recording equipment maintenance activities
slug: equipment-monitoring
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
