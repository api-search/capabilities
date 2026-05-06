---
categories:
- monitoring
consumed_apis: []
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
- list events
- aws
- tracks events affecting ci/cd and deployment infrastructure
- amazon health dashboard
- get resources affected by health events across the organization
- get aws resources affected by specific health events
- DevOps Engineer
- list health events across all accounts in an aws organization
- aws health events
- get org event details
- get org affected entities
- get affected aws resources
- get the catalog of all aws health event type codes and categories
- monitoring
- list org events
- operations
- manages organization-wide health visibility and notifications
- service status
- list events across the organization
- get event types
- list aws health events filtering by service, region, or status
- organization-wide events
- list org health events
- Cloud Administrator
- resources affected by health events
- list aws service health events
- notifications
- get event details
- Operations Engineer
- get affected resources
- list health events
- monitors aws service health and coordinates response to events
- get detailed health event information for organization-level events
- incident response
- get comprehensive details about specific aws health events including description and guidance
- health monitoring
- list affected entities
slug: amazon-health-dashboard-operations-monitoring
source_filename: amazon-health-dashboard-operations-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Health Dashboard Operations Monitoring\n  description: Workflow capability for operations teams using AWS Health Dashboard to monitor AWS service health, track events\n    affecting resources, and coordinate incident response to AWS infrastructure events.\n  tags:\n  - Amazon Health Dashboard\n  - Operations\n  - Monitoring\n  - Incident Response\n  - AWS\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-health-dashboard\n    baseUri: https://health.us-east-1.amazonaws.com\n    description: Amazon Health Dashboard / AWS Health API\n    authentication:\n      type: bearer\n      token: '{{AWS_AUTH_HEADER}}'\n    resources:\n    - name: events\n      path: /events\n      description: AWS health events affecting services\n\
  \      operations:\n      - name: DescribeEvents\n        method: POST\n        description: List AWS health events with optional filters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribeEventDetails\n        method: POST\n        description: Get detailed information about specific events\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribeAffectedEntities\n        method: POST\n        description: Get entities affected by events\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-types\n      path: /event-types\n      description: AWS Health event type catalog\n      operations:\n      - name: DescribeEventTypes\n        method: POST\n        description: Get available event types\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: org-events\n      path: /organization/events\n      description: Organization-wide health events\n      operations:\n      - name: DescribeEventsForOrganization\n        method: POST\n        description: Get events across all organization accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8086\n    namespace: health-ops-api\n    description: Unified REST API for AWS Health Dashboard operations monitoring.\n    resources:\n    - path: /v1/events\n      name: events\n      description: AWS health events\n      operations:\n      - method: GET\n        name: list-events\n        description: List AWS service health events\n        call: amazon-health-dashboard.DescribeEvents\n        outputParameters:\n        - type: object\n          mapping: $.\n  \
  \  - path: /v1/affected-entities\n      name: affected-entities\n      description: Resources affected by health events\n      operations:\n      - method: GET\n        name: list-affected-entities\n        description: Get affected AWS resources\n        call: amazon-health-dashboard.DescribeAffectedEntities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/org-events\n      name: org-events\n      description: Organization-wide events\n      operations:\n      - method: GET\n        name: list-org-events\n        description: List events across the organization\n        call: amazon-health-dashboard.DescribeEventsForOrganization\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9096\n    namespace: health-ops-mcp\n    transport: http\n    description: MCP server for AI-assisted AWS Health Dashboard operations monitoring.\n    tools:\n    - name: list-health-events\n      description: List AWS health\
  \ events filtering by service, region, or status\n      hints:\n        readOnly: true\n        openWorld: true\n      call: amazon-health-dashboard.DescribeEvents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-event-details\n      description: Get comprehensive details about specific AWS health events including description and guidance\n      hints:\n        readOnly: true\n      call: amazon-health-dashboard.DescribeEventDetails\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-affected-resources\n      description: Get AWS resources affected by specific health events\n      hints:\n        readOnly: true\n      call: amazon-health-dashboard.DescribeAffectedEntities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-event-types\n      description: Get the catalog of all AWS health event type codes and categories\n      hints:\n        readOnly: true\n      call: amazon-health-dashboard.DescribeEventTypes\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-org-health-events\n      description: List health events across all accounts in an AWS Organization\n      hints:\n        readOnly: true\n      call: amazon-health-dashboard.DescribeEventsForOrganization\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-org-affected-entities\n      description: Get resources affected by health events across the organization\n      hints:\n        readOnly: true\n      call: amazon-health-dashboard.DescribeAffectedEntitiesForOrganization\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-org-event-details\n      description: Get detailed health event information for organization-level events\n      hints:\n        readOnly: true\n      call: amazon-health-dashboard.DescribeEventDetailsForOrganization\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-health-dashboard/refs/heads/main/capabilities/amazon-health-dashboard-operations-monitoring.yaml
tags:
- Amazon Health Dashboard
- Operations
- Monitoring
- Incident Response
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
