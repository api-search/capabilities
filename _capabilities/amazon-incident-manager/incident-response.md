---
consumed_apis:
- ssm-incidents
description: Unified capability for operations teams to manage incident response plans, respond to active incidents, update timelines, and coordinate responders.
layout: capability
name: Amazon Incident Manager - Incident Response
operations:
- description: List all response plans
  method: GET
  name: list-response-plans
  path: /v1/response-plans
- description: List active incidents
  method: GET
  name: list-incidents
  path: /v1/incidents
- description: Create a new incident
  method: POST
  name: create-incident
  path: /v1/incidents
personas: []
provider_name: Amazon Incident Manager
provider_slug: amazon-incident-manager
search_terms:
- update incident
- list all incident response plans
- list response plans
- creating, tracking, and resolving operational incidents
- get incident
- create response plan
- Operations Engineer
- Site Reliability Engineer
- create a new incident response plan with escalation contacts
- update the summary or status of an active incident
- list timeline events
- list all response plans
- list incidents
- aws
- automated incident response plans and escalation
- manage active incidents
- devops
- list active incidents
- incident management
- manages incident response plans and responds to operational incidents
- list active and recent incidents
- create incident
- manage incident response plans
- monitors system reliability and coordinates incident resolution
- get details of a specific incident
- operations
- list timeline events for an incident
- create a new incident
- start a new incident and trigger response plan
- automation
slug: incident-response
tags:
- AWS
- Incident Management
- DevOps
- Operations
- Automation
tools:
- description: List all incident response plans
  hints:
    openWorld: true
    readOnly: true
  name: list-response-plans
- description: Create a new incident response plan with escalation contacts
  hints:
    readOnly: false
  name: create-response-plan
- description: List active and recent incidents
  hints:
    openWorld: true
    readOnly: true
  name: list-incidents
- description: Start a new incident and trigger response plan
  hints:
    readOnly: false
  name: create-incident
- description: Update the summary or status of an active incident
  hints:
    readOnly: false
  name: update-incident
- description: Get details of a specific incident
  hints:
    readOnly: true
  name: get-incident
- description: List timeline events for an incident
  hints:
    openWorld: true
    readOnly: true
  name: list-timeline-events
---
