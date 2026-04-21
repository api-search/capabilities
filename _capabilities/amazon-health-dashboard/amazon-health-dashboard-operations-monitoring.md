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
- list aws service health events
- get affected resources
- notifications
- organization-wide events
- monitors aws service health and coordinates response to events
- get org affected entities
- list health events
- get affected aws resources
- get resources affected by health events across the organization
- list aws health events filtering by service, region, or status
- get org event details
- aws health events
- operations
- incident response
- get aws resources affected by specific health events
- get detailed health event information for organization-level events
- Operations Engineer
- Cloud Administrator
- list org events
- resources affected by health events
- list affected entities
- list health events across all accounts in an aws organization
- get comprehensive details about specific aws health events including description and guidance
- list org health events
- list events across the organization
- get event details
- DevOps Engineer
- monitoring
- get the catalog of all aws health event type codes and categories
- manages organization-wide health visibility and notifications
- aws
- tracks events affecting ci/cd and deployment infrastructure
- list events
- service status
- health monitoring
- amazon health dashboard
- get event types
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
