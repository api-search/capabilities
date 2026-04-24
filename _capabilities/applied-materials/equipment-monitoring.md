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
- engineers overseeing semiconductor equipment operation and performance
- equipment monitoring
- technicians performing scheduled and emergency equipment maintenance
- equipment
- schedule preventive maintenance
- tracking and monitoring semiconductor manufacturing equipment
- checks the operational status of a specific piece of fab equipment
- semiconductor
- manufacturing
- view maintenance history
- monitor fab equipment status and manage maintenance schedules
- fab operations
- lists all semiconductor manufacturing equipment in the fab
- check equipment status
- schedules preventive maintenance for semiconductor manufacturing equipment
- materials engineering
- list fab equipment
- applied materials
- views maintenance history and upcoming scheduled maintenance for equipment
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
