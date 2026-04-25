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
- list alert incidents
- list applications
- new relic
- get applications
- list applications for incident context
- get application
- devops
- observability
- list alert events filtered by product or entity type
- incident response
- get alerts incidents
- get alerts conditions
- list alert conditions for a specific policy
- get alerts violations
- platform
- get application details for incident context
- monitoring
- performance
- alerts
- list alert conditions
- list alert conditions for a policy
- list alert incidents, optionally filtered to only open ones
- infrastructure
- analysis
- analytics
- get alerts events
- apm
- incidents
- sre
- get application details
- get application details for incident investigation
- list alert violations
- list alert events
- list alert violations, optionally filtered to only open ones
- list applications for context
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
