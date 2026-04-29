---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Incident Management
operations: []
personas: []
provider_name: BigPanda
provider_slug: bigpanda
search_terms:
- monitoring
- platform
- site reliability engineer managing incidents and alert correlation
- ai-powered correlation of alerts into actionable incidents
- ingest change events to correlate with alert spikes
- full incident lifecycle from alert ingestion to resolution
- incidents
- it operations manager overseeing incident response
- triage, acknowledge, and resolve correlated incidents
- schedule maintenance windows to suppress expected alerts
slug: incident-management
source_yaml: "name: Incident Management\ndescription: >-\n  Workflow capability for managing IT incidents using BigPanda AIOps,\n  including alert ingestion, incident triage, environment management,\n  and maintenance scheduling.\nversion: v1\n\nimports:\n  - shared/bigpanda.yaml\n\ntools:\n  - name: send-alert\n    import: bigpanda.send-alert\n    description: >-\n      Ingest a monitoring alert from any source into BigPanda for AI-powered\n      correlation and incident creation.\n    inputSchema:\n      type: object\n      required:\n        - app_key\n        - status\n        - host\n      properties:\n        app_key:\n          type: string\n          description: BigPanda application key for routing\n        status:\n          type: string\n          description: Alert status (critical, warning, ok, acknowledged)\n        host:\n          type: string\n          description: Hostname associated with the alert\n        check:\n          type: string\n          description: Check or\
  \ metric name\n        description:\n          type: string\n          description: Human-readable alert description\n  - name: list-environments\n    import: bigpanda.list-environments\n    description: List all BigPanda environments for incident grouping.\n  - name: create-environment\n    import: bigpanda.create-environment\n    description: Create a new environment to group related incidents.\n    inputSchema:\n      type: object\n      required:\n        - name\n        - condition\n      properties:\n        name:\n          type: string\n          description: Environment name\n        condition:\n          type: string\n          description: Filter condition for grouping incidents\n  - name: list-incidents\n    import: bigpanda.list-incidents\n    description: List active and resolved incidents for an environment.\n    inputSchema:\n      type: object\n      required:\n        - environment_id\n      properties:\n        environment_id:\n          type: string\n          description:\
  \ Environment ID to list incidents for\n        active:\n          type: boolean\n          description: Filter to show only active incidents\n  - name: get-incident\n    import: bigpanda.get-incident\n    description: Get full details of a specific incident including correlated alerts.\n    inputSchema:\n      type: object\n      required:\n        - environment_id\n        - incident_id\n      properties:\n        environment_id:\n          type: string\n          description: Environment ID\n        incident_id:\n          type: string\n          description: Incident ID\n  - name: list-maintenance-plans\n    import: bigpanda.list-maintenance-plans\n    description: List all scheduled maintenance plans.\n  - name: create-maintenance-plan\n    import: bigpanda.create-maintenance-plan\n    description: Schedule a maintenance window to suppress alerts for specified hosts.\n    inputSchema:\n      type: object\n      required:\n        - name\n        - condition\n        - start\n    \
  \    - end\n      properties:\n        name:\n          type: string\n          description: Maintenance plan name\n        condition:\n          type: string\n          description: Host filter condition\n        start:\n          type: integer\n          description: Start Unix timestamp\n        end:\n          type: integer\n          description: End Unix timestamp\n  - name: send-change\n    import: bigpanda.send-change\n    description: Ingest a deployment or configuration change for correlation with alerts.\n    inputSchema:\n      type: object\n      required:\n        - summary\n        - status\n      properties:\n        summary:\n          type: string\n          description: Change summary description\n        status:\n          type: string\n          description: Change status (started, success, failure)\n        hosts:\n          type: array\n          description: Affected hosts\n  - name: get-audit-logs\n    import: bigpanda.get-audit-logs\n    description: Retrieve\
  \ audit logs for compliance and troubleshooting.\n\nexpose:\n  rest:\n    port: 8080\n  mcp:\n    port: 9080\n\npersonas:\n  - id: sre-engineer\n    name: SRE Engineer\n    description: Site reliability engineer managing incidents and alert correlation\n  - id: it-ops-manager\n    name: IT Ops Manager\n    description: IT operations manager overseeing incident response and maintenance scheduling\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/bigpanda/refs/heads/main/capabilities/incident-management.yaml
tags: []
tools: []
---
