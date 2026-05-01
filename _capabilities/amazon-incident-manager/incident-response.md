---
categories:
- incident-management
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
- list active incidents
- list timeline events for an incident
- create incident
- automated incident response plans and escalation
- Site Reliability Engineer
- manages incident response plans and responds to operational incidents
- monitors system reliability and coordinates incident resolution
- manage active incidents
- create response plan
- list incidents
- operations
- update incident
- list timeline events
- list all response plans
- devops
- create a new incident
- automation
- update the summary or status of an active incident
- get details of a specific incident
- create a new incident response plan with escalation contacts
- incident management
- start a new incident and trigger response plan
- aws
- manage incident response plans
- list active and recent incidents
- Operations Engineer
- creating, tracking, and resolving operational incidents
- list response plans
- get incident
- list all incident response plans
slug: incident-response
source_filename: incident-response.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: Amazon Incident Manager - Incident Response\n  description: Unified capability for operations teams to manage incident response plans, respond to active incidents, update timelines, and coordinate responders.\n  tags:\n    - AWS\n    - Incident Management\n    - DevOps\n    - Operations\n    - Automation\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n    - import: ssm-incidents\n      location: ./shared/ssm-incidents.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: incident-response-api\n      description: Unified REST API for incident response management.\n      resources:\n        - path: /v1/response-plans\n          name: response-plans\n          description: Manage incident response plans\n          operations:\n            - method: GET\n\
  \              name: list-response-plans\n              description: List all response plans\n              call: \"ssm-incidents.list-response-plans\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/incidents\n          name: incidents\n          description: Manage active incidents\n          operations:\n            - method: GET\n              name: list-incidents\n              description: List active incidents\n              call: \"ssm-incidents.list-incident-records\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-incident\n              description: Create a new incident\n              call: \"ssm-incidents.create-incident\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9090\n      namespace: incident-response-mcp\n\
  \      transport: http\n      description: MCP server for AI-assisted incident response.\n      tools:\n        - name: list-response-plans\n          description: List all incident response plans\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ssm-incidents.list-response-plans\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-response-plan\n          description: Create a new incident response plan with escalation contacts\n          hints:\n            readOnly: false\n          call: \"ssm-incidents.create-response-plan\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-incidents\n          description: List active and recent incidents\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ssm-incidents.list-incident-records\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: create-incident\n          description: Start a new incident and trigger response plan\n          hints:\n            readOnly: false\n          call: \"ssm-incidents.create-incident\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-incident\n          description: Update the summary or status of an active incident\n          hints:\n            readOnly: false\n          call: \"ssm-incidents.update-incident-record\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-incident\n          description: Get details of a specific incident\n          hints:\n            readOnly: true\n          call: \"ssm-incidents.get-incident-record\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-timeline-events\n          description: List timeline events for an incident\n\
  \          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ssm-incidents.list-timeline-events\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-incident-manager/refs/heads/main/capabilities/incident-response.yaml
tags:
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
