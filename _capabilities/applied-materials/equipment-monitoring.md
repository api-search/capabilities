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
- schedule preventive maintenance
- check equipment status
- view maintenance history
- materials engineering
- views maintenance history and upcoming scheduled maintenance for equipment
- equipment monitoring
- equipment
- lists all semiconductor manufacturing equipment in the fab
- tracking and monitoring semiconductor manufacturing equipment
- manufacturing
- technicians performing scheduled and emergency equipment maintenance
- semiconductor
- schedules preventive maintenance for semiconductor manufacturing equipment
- applied materials
- fab operations
- engineers overseeing semiconductor equipment operation and performance
- checks the operational status of a specific piece of fab equipment
- monitor fab equipment status and manage maintenance schedules
- scheduling and recording equipment maintenance activities
- list fab equipment
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
