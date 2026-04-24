---
consumed_apis:
- amazon-health-dashboard
description: Workflow capability for operations teams using AWS Health Dashboard to monitor AWS service health, track events affecting resources, and coordinate incident response to AWS infrastructure events.
layout: capability
name: Amazon Health Dashboard Operations Monitoring
operations:
- description: List AWS service health events
  method: GET
  name: list-events
  path: /v1/events
- description: Get affected AWS resources
  method: GET
  name: list-affected-entities
  path: /v1/affected-entities
- description: List events across the organization
  method: GET
  name: list-org-events
  path: /v1/org-events
personas: []
provider_name: Amazon Health Dashboard
provider_slug: amazon-health-dashboard
search_terms:
- manages organization-wide health visibility and notifications
- organization-wide events
- list aws health events filtering by service, region, or status
- Operations Engineer
- get aws resources affected by specific health events
- get org affected entities
- Cloud Administrator
- list health events
- get org event details
- list org health events
- list org events
- monitoring
- get event types
- list aws service health events
- get detailed health event information for organization-level events
- tracks events affecting ci/cd and deployment infrastructure
- get event details
- list events across the organization
- list affected entities
- get the catalog of all aws health event type codes and categories
- list health events across all accounts in an aws organization
- get affected resources
- get resources affected by health events across the organization
- get comprehensive details about specific aws health events including description and guidance
- monitors aws service health and coordinates response to events
- health monitoring
- service status
- get affected aws resources
- resources affected by health events
- notifications
- aws
- amazon health dashboard
- operations
- incident response
- list events
- DevOps Engineer
- aws health events
slug: amazon-health-dashboard-operations-monitoring
tags:
- Amazon Health Dashboard
- Operations
- Monitoring
- Incident Response
- AWS
tools:
- description: List AWS health events filtering by service, region, or status
  hints:
    openWorld: true
    readOnly: true
  name: list-health-events
- description: Get comprehensive details about specific AWS health events including description and guidance
  hints:
    readOnly: true
  name: get-event-details
- description: Get AWS resources affected by specific health events
  hints:
    readOnly: true
  name: get-affected-resources
- description: Get the catalog of all AWS health event type codes and categories
  hints:
    readOnly: true
  name: get-event-types
- description: List health events across all accounts in an AWS Organization
  hints:
    readOnly: true
  name: list-org-health-events
- description: Get resources affected by health events across the organization
  hints:
    readOnly: true
  name: get-org-affected-entities
- description: Get detailed health event information for organization-level events
  hints:
    readOnly: true
  name: get-org-event-details
---
