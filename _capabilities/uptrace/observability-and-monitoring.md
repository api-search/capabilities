---
api_specs:
- filename: uptrace-openapi.yml
  format: yaml
  label: uptrace
  slug: uptrace
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/uptrace/refs/heads/main/openapi/uptrace-openapi.yml
categories: []
consumed_apis:
- uptrace
description: Workflow capability for Uptrace APM observability and monitoring workflows, combining annotations for deployment tracking, alert rule management, dashboard operations, and project management. Designed for platform engineering teams, SREs, and DevOps practitioners managing application observability with OpenTelemetry.
layout: capability
name: Uptrace Observability and Monitoring
operations:
- description: List all Uptrace projects
  method: GET
  name: list-projects
  path: /v1/projects
- description: Create a new Uptrace project
  method: POST
  name: create-project
  path: /v1/projects
- description: Get project details and DSN
  method: GET
  name: get-project
  path: /v1/projects/{projectId}
- description: List annotations for a project
  method: GET
  name: list-annotations
  path: /v1/annotations
- description: Create a deployment or event annotation
  method: POST
  name: create-annotation
  path: /v1/annotations
- description: Get annotation details
  method: GET
  name: get-annotation
  path: /v1/annotations/{annotationId}
- description: Delete an annotation
  method: DELETE
  name: delete-annotation
  path: /v1/annotations/{annotationId}
- description: List alert rules for a project
  method: GET
  name: list-alerts
  path: /v1/alerts
- description: Create a new alert rule
  method: POST
  name: create-alert
  path: /v1/alerts
- description: Get alert rule details
  method: GET
  name: get-alert
  path: /v1/alerts/{alertId}
- description: Delete an alert rule
  method: DELETE
  name: delete-alert
  path: /v1/alerts/{alertId}
- description: List dashboards for a project
  method: GET
  name: list-dashboards
  path: /v1/dashboards
- description: Create a new dashboard
  method: POST
  name: create-dashboard
  path: /v1/dashboards
personas: []
provider_name: Uptrace
provider_slug: uptrace
search_terms:
- get alert
- individual annotation
- list projects
- get details of a specific alert rule
- monitoring
- apm
- list alert rules for a project
- create a new alert rule
- create a new uptrace observability project
- create a new dashboard
- get details of a specific chart annotation
- create project
- create a deployment annotation marking a release or incident on dashboards
- delete an alert rule
- chart annotations for deployment and event tracking
- list all uptrace projects
- list alerts
- get annotation
- project management
- individual alert rule
- create alert
- get details and dsn for a specific uptrace project
- create a new monitoring alert rule using promql
- create a new uptrace project
- list dashboards
- alerting
- delete a chart annotation
- dashboard management
- alert rule management
- create a deployment or event annotation
- opentelemetry
- list dashboards for a project
- delete annotation
- delete an annotation
- list annotations
- create dashboard
- list all uptrace observability projects
- uptrace
- get annotation details
- delete alert
- observability
- distributed tracing
- individual project
- list deployment and event annotations for a project
- get project
- list annotations for a project
- get project details and dsn
- devops
- create annotation
- get alert rule details
- sre
slug: observability-and-monitoring
source_filename: observability-and-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Uptrace Observability and Monitoring\"\n  description: >-\n    Workflow capability for Uptrace APM observability and monitoring workflows,\n    combining annotations for deployment tracking, alert rule management,\n    dashboard operations, and project management. Designed for platform\n    engineering teams, SREs, and DevOps practitioners managing application\n    observability with OpenTelemetry.\n  tags:\n    - Uptrace\n    - APM\n    - Observability\n    - OpenTelemetry\n    - SRE\n    - DevOps\n    - Monitoring\n    - Alerting\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UPTRACE_API_TOKEN: UPTRACE_API_TOKEN\n\ncapability:\n  consumes:\n    - import: uptrace\n      location: ./shared/uptrace.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: uptrace-observability-api\n      description: \"Unified REST API for Uptrace observability and monitoring\
  \ workflows.\"\n      resources:\n        - path: /v1/projects\n          name: projects\n          description: \"Project management\"\n          operations:\n            - method: GET\n              name: list-projects\n              description: \"List all Uptrace projects\"\n              call: \"uptrace.list-projects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-project\n              description: \"Create a new Uptrace project\"\n              call: \"uptrace.create-project\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{projectId}\n          name: project\n          description: \"Individual project\"\n          operations:\n            - method: GET\n              name: get-project\n              description: \"Get project details and DSN\"\n              call: \"uptrace.get-project\"\
  \n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/annotations\n          name: annotations\n          description: \"Chart annotations for deployment and event tracking\"\n          operations:\n            - method: GET\n              name: list-annotations\n              description: \"List annotations for a project\"\n              call: \"uptrace.list-annotations\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-annotation\n              description: \"Create a deployment or event annotation\"\n              call: \"uptrace.create-annotation\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/annotations/{annotationId}\n\
  \          name: annotation\n          description: \"Individual annotation\"\n          operations:\n            - method: GET\n              name: get-annotation\n              description: \"Get annotation details\"\n              call: \"uptrace.get-annotation\"\n              with:\n                annotationId: \"rest.annotationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-annotation\n              description: \"Delete an annotation\"\n              call: \"uptrace.delete-annotation\"\n              with:\n                annotationId: \"rest.annotationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/alerts\n          name: alerts\n          description: \"Alert rule management\"\n          operations:\n            - method: GET\n              name: list-alerts\n              description:\
  \ \"List alert rules for a project\"\n              call: \"uptrace.list-alerts\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-alert\n              description: \"Create a new alert rule\"\n              call: \"uptrace.create-alert\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/alerts/{alertId}\n          name: alert\n          description: \"Individual alert rule\"\n          operations:\n            - method: GET\n              name: get-alert\n              description: \"Get alert rule details\"\n              call: \"uptrace.get-alert\"\n              with:\n                alertId: \"rest.alertId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n\
  \              name: delete-alert\n              description: \"Delete an alert rule\"\n              call: \"uptrace.delete-alert\"\n              with:\n                alertId: \"rest.alertId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/dashboards\n          name: dashboards\n          description: \"Dashboard management\"\n          operations:\n            - method: GET\n              name: list-dashboards\n              description: \"List dashboards for a project\"\n              call: \"uptrace.list-dashboards\"\n              with:\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-dashboard\n              description: \"Create a new dashboard\"\n              call: \"uptrace.create-dashboard\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: uptrace-observability-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Uptrace observability and monitoring workflows.\"\n      tools:\n        - name: list-projects\n          description: \"List all Uptrace observability projects\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uptrace.list-projects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-project\n          description: \"Get details and DSN for a specific Uptrace project\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uptrace.get-project\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-project\n          description: \"\
  Create a new Uptrace observability project\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"uptrace.create-project\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-annotations\n          description: \"List deployment and event annotations for a project\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uptrace.list-annotations\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-annotation\n          description: \"Create a deployment annotation marking a release or incident on dashboards\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"uptrace.create-annotation\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        -\
  \ name: get-annotation\n          description: \"Get details of a specific chart annotation\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uptrace.get-annotation\"\n          with:\n            annotationId: \"tools.annotationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-annotation\n          description: \"Delete a chart annotation\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"uptrace.delete-annotation\"\n          with:\n            annotationId: \"tools.annotationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-alerts\n          description: \"List alert rules for a project\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uptrace.list-alerts\"\n          with:\n        \
  \    projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-alert\n          description: \"Create a new monitoring alert rule using PromQL\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"uptrace.create-alert\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-alert\n          description: \"Get details of a specific alert rule\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uptrace.get-alert\"\n          with:\n            alertId: \"tools.alertId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-alert\n          description: \"Delete an alert rule\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"uptrace.delete-alert\"\
  \n          with:\n            alertId: \"tools.alertId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-dashboards\n          description: \"List dashboards for a project\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"uptrace.list-dashboards\"\n          with:\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/uptrace/refs/heads/main/capabilities/observability-and-monitoring.yaml
tags:
- Uptrace
- APM
- Observability
- OpenTelemetry
- SRE
- DevOps
- Monitoring
- Alerting
tools:
- description: List all Uptrace observability projects
  hints:
    openWorld: false
    readOnly: true
  name: list-projects
- description: Get details and DSN for a specific Uptrace project
  hints:
    openWorld: false
    readOnly: true
  name: get-project
- description: Create a new Uptrace observability project
  hints:
    openWorld: false
    readOnly: false
  name: create-project
- description: List deployment and event annotations for a project
  hints:
    openWorld: false
    readOnly: true
  name: list-annotations
- description: Create a deployment annotation marking a release or incident on dashboards
  hints:
    openWorld: false
    readOnly: false
  name: create-annotation
- description: Get details of a specific chart annotation
  hints:
    openWorld: false
    readOnly: true
  name: get-annotation
- description: Delete a chart annotation
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-annotation
- description: List alert rules for a project
  hints:
    openWorld: false
    readOnly: true
  name: list-alerts
- description: Create a new monitoring alert rule using PromQL
  hints:
    openWorld: false
    readOnly: false
  name: create-alert
- description: Get details of a specific alert rule
  hints:
    openWorld: false
    readOnly: true
  name: get-alert
- description: Delete an alert rule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-alert
- description: List dashboards for a project
  hints:
    openWorld: false
    readOnly: true
  name: list-dashboards
---
