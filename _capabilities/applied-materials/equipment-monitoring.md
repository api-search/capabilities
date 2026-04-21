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
- materials engineering
- applied materials
- manufacturing
- check equipment status
- fab operations
- views maintenance history and upcoming scheduled maintenance for equipment
- equipment monitoring
- monitor fab equipment status and manage maintenance schedules
- view maintenance history
- semiconductor
- schedules preventive maintenance for semiconductor manufacturing equipment
- scheduling and recording equipment maintenance activities
- engineers overseeing semiconductor equipment operation and performance
- lists all semiconductor manufacturing equipment in the fab
- list fab equipment
- checks the operational status of a specific piece of fab equipment
- equipment
- tracking and monitoring semiconductor manufacturing equipment
- technicians performing scheduled and emergency equipment maintenance
- schedule preventive maintenance
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
