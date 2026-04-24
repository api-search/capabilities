---
consumed_apis:
- rest-api
description: Incident response workflow combining alerts, incidents, violations, and events for SREs investigating and resolving production issues detected by New Relic.
layout: capability
name: New Relic Incident Response
operations:
- description: List alert incidents
  method: GET
  name: get-alerts-incidents
  path: /v1/incidents
- description: List alert violations
  method: GET
  name: get-alerts-violations
  path: /v1/violations
- description: List alert events
  method: GET
  name: get-alerts-events
  path: /v1/alert-events
- description: List alert conditions for a policy
  method: GET
  name: get-alerts-conditions
  path: /v1/alert-conditions
- description: List applications
  method: GET
  name: get-applications
  path: /v1/applications
- description: Get application details
  method: GET
  name: get-application
  path: /v1/applications/{id}
personas: []
provider_name: New Relic
provider_slug: new-relic
search_terms:
- observability
- list alert events filtered by product or entity type
- get application
- list alert events
- list alert incidents
- get application details for incident context
- get alerts incidents
- monitoring
- devops
- get application details
- list applications for context
- analytics
- list alert incidents, optionally filtered to only open ones
- list applications
- incidents
- list alert violations
- get applications
- apm
- list alert conditions for a specific policy
- get alerts conditions
- new relic
- alerts
- list alert conditions
- get application details for incident investigation
- list alert conditions for a policy
- analysis
- sre
- list alert violations, optionally filtered to only open ones
- list applications for incident context
- platform
- incident response
- get alerts violations
- get alerts events
- infrastructure
- performance
slug: incident-response
tags:
- New Relic
- Incident Response
- SRE
- Alerts
- Incidents
tools:
- description: List alert incidents, optionally filtered to only open ones
  hints:
    openWorld: true
    readOnly: true
  name: get-alerts-incidents
- description: List alert violations, optionally filtered to only open ones
  hints:
    openWorld: true
    readOnly: true
  name: get-alerts-violations
- description: List alert events filtered by product or entity type
  hints:
    openWorld: true
    readOnly: true
  name: get-alerts-events
- description: List alert conditions for a specific policy
  hints:
    openWorld: true
    readOnly: true
  name: get-alerts-conditions
- description: List applications for incident context
  hints:
    openWorld: true
    readOnly: true
  name: get-applications
- description: Get application details for incident investigation
  hints:
    openWorld: true
    readOnly: true
  name: get-application
---
