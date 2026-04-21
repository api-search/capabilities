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
- applied materials
- check equipment status
- equipment monitoring
- schedule preventive maintenance
- technicians performing scheduled and emergency equipment maintenance
- equipment
- manufacturing
- semiconductor
- scheduling and recording equipment maintenance activities
- fab operations
- tracking and monitoring semiconductor manufacturing equipment
- engineers overseeing semiconductor equipment operation and performance
- list fab equipment
- materials engineering
- schedules preventive maintenance for semiconductor manufacturing equipment
- view maintenance history
- views maintenance history and upcoming scheduled maintenance for equipment
- lists all semiconductor manufacturing equipment in the fab
- monitor fab equipment status and manage maintenance schedules
- checks the operational status of a specific piece of fab equipment
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
