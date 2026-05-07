---
categories: []
consumed_apis: []
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
- opentelemetry
- list annotations for a project
- dashboard management
- get details of a specific alert rule
- devops
- create alert
- distributed tracing
- list annotations
- create a deployment or event annotation
- list deployment and event annotations for a project
- list dashboards for a project
- list all uptrace projects
- delete annotation
- alert rule management
- create a new alert rule
- create a new uptrace project
- apm
- list all uptrace observability projects
- monitoring
- delete alert
- list alert rules for a project
- delete an alert rule
- project management
- get details of a specific chart annotation
- get details and dsn for a specific uptrace project
- get project details and dsn
- get alert rule details
- chart annotations for deployment and event tracking
- uptrace
- create project
- list projects
- create a new monitoring alert rule using promql
- observability
- create a new dashboard
- sre
- individual annotation
- individual alert rule
- create dashboard
- get annotation details
- create a new uptrace observability project
- list alerts
- get alert
- list dashboards
- delete an annotation
- get project
- get annotation
- individual project
- create a deployment annotation marking a release or incident on dashboards
- alerting
- delete a chart annotation
- create annotation
slug: observability-and-monitoring
source_filename: observability-and-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Uptrace Observability and Monitoring\n  description: Workflow capability for Uptrace APM observability and monitoring workflows, combining annotations for deployment\n    tracking, alert rule management, dashboard operations, and project management. Designed for platform engineering teams,\n    SREs, and DevOps practitioners managing application observability with OpenTelemetry.\n  tags:\n  - Uptrace\n  - APM\n  - Observability\n  - OpenTelemetry\n  - SRE\n  - DevOps\n  - Monitoring\n  - Alerting\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UPTRACE_API_TOKEN: UPTRACE_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: uptrace\n    baseUri: https://api.uptrace.dev\n    description: Uptrace APM REST API\n    authentication:\n      type: bearer\n      token: '{{UPTRACE_API_TOKEN}}'\n    resources:\n    - name: annotations\n      path: /api/v1/annotations\n      description: Chart\
  \ annotation management\n      operations:\n      - name: list-annotations\n        method: GET\n        description: List annotations for a project in a time range\n        inputParameters:\n        - name: projectId\n          in: query\n          type: integer\n          required: true\n        - name: startTime\n          in: query\n          type: string\n          required: false\n        - name: endTime\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-annotation\n        method: POST\n        description: Create a deployment or event annotation on dashboards\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            projectId: '{{tools.projectId}}'\n            name: '{{tools.name}}'\n\
  \            description: '{{tools.description}}'\n            tags: '{{tools.tags}}'\n            attrs: '{{tools.attrs}}'\n            time: '{{tools.time}}'\n    - name: annotation\n      path: /api/v1/annotations/{annotationId}\n      description: Individual annotation operations\n      operations:\n      - name: get-annotation\n        method: GET\n        description: Get annotation details\n        inputParameters:\n        - name: annotationId\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-annotation\n        method: DELETE\n        description: Delete an annotation\n        inputParameters:\n        - name: annotationId\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: alerts\n      path: /api/v1/alerts\n      description: Alert rule management\n      operations:\n      - name: list-alerts\n        method: GET\n        description: List alert rules for a project\n        inputParameters:\n        - name: projectId\n          in: query\n          type: integer\n          required: true\n        - name: state\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-alert\n        method: POST\n        description: Create a new alert rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            projectId: '{{tools.projectId}}'\n            name: '{{tools.name}}'\n            type: '{{tools.alertType}}'\n            query: '{{tools.query}}'\n\
  \            forDuration: '{{tools.forDuration}}'\n            condition: '{{tools.condition}}'\n            notificationChannels: '{{tools.notificationChannels}}'\n    - name: projects\n      path: /api/v1/projects\n      description: Project management\n      operations:\n      - name: list-projects\n        method: GET\n        description: List all projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-project\n        method: POST\n        description: Create a new Uptrace project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            slug: '{{tools.slug}}'\n    - name: project\n      path: /api/v1/projects/{projectId}\n      description: Individual project operations\n      operations:\n      - name: get-project\n\
  \        method: GET\n        description: Get project details including DSN\n        inputParameters:\n        - name: projectId\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dashboards\n      path: /api/v1/dashboards\n      description: Dashboard management\n      operations:\n      - name: list-dashboards\n        method: GET\n        description: List dashboards for a project\n        inputParameters:\n        - name: projectId\n          in: query\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: uptrace-observability-api\n    description: Unified REST API for Uptrace observability and monitoring workflows.\n    resources:\n    - path:\
  \ /v1/projects\n      name: projects\n      description: Project management\n      operations:\n      - method: GET\n        name: list-projects\n        description: List all Uptrace projects\n        call: uptrace.list-projects\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-project\n        description: Create a new Uptrace project\n        call: uptrace.create-project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}\n      name: project\n      description: Individual project\n      operations:\n      - method: GET\n        name: get-project\n        description: Get project details and DSN\n        call: uptrace.get-project\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/annotations\n      name: annotations\n      description: Chart annotations for deployment\
  \ and event tracking\n      operations:\n      - method: GET\n        name: list-annotations\n        description: List annotations for a project\n        call: uptrace.list-annotations\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-annotation\n        description: Create a deployment or event annotation\n        call: uptrace.create-annotation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/annotations/{annotationId}\n      name: annotation\n      description: Individual annotation\n      operations:\n      - method: GET\n        name: get-annotation\n        description: Get annotation details\n        call: uptrace.get-annotation\n        with:\n          annotationId: rest.annotationId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-annotation\n  \
  \      description: Delete an annotation\n        call: uptrace.delete-annotation\n        with:\n          annotationId: rest.annotationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/alerts\n      name: alerts\n      description: Alert rule management\n      operations:\n      - method: GET\n        name: list-alerts\n        description: List alert rules for a project\n        call: uptrace.list-alerts\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-alert\n        description: Create a new alert rule\n        call: uptrace.create-alert\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/alerts/{alertId}\n      name: alert\n      description: Individual alert rule\n      operations:\n      - method: GET\n        name: get-alert\n        description: Get alert rule details\n      \
  \  call: uptrace.get-alert\n        with:\n          alertId: rest.alertId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-alert\n        description: Delete an alert rule\n        call: uptrace.delete-alert\n        with:\n          alertId: rest.alertId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/dashboards\n      name: dashboards\n      description: Dashboard management\n      operations:\n      - method: GET\n        name: list-dashboards\n        description: List dashboards for a project\n        call: uptrace.list-dashboards\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-dashboard\n        description: Create a new dashboard\n        call: uptrace.create-dashboard\n        outputParameters:\n        - type: object\n          mapping: $.\n  -\
  \ type: mcp\n    port: 9090\n    namespace: uptrace-observability-mcp\n    transport: http\n    description: MCP server for AI-assisted Uptrace observability and monitoring workflows.\n    tools:\n    - name: list-projects\n      description: List all Uptrace observability projects\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uptrace.list-projects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-project\n      description: Get details and DSN for a specific Uptrace project\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uptrace.get-project\n      with:\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-project\n      description: Create a new Uptrace observability project\n      hints:\n        readOnly: false\n        openWorld: false\n      call: uptrace.create-project\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: list-annotations\n      description: List deployment and event annotations for a project\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uptrace.list-annotations\n      with:\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-annotation\n      description: Create a deployment annotation marking a release or incident on dashboards\n      hints:\n        readOnly: false\n        openWorld: false\n      call: uptrace.create-annotation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-annotation\n      description: Get details of a specific chart annotation\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uptrace.get-annotation\n      with:\n        annotationId: tools.annotationId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-annotation\n      description:\
  \ Delete a chart annotation\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: uptrace.delete-annotation\n      with:\n        annotationId: tools.annotationId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-alerts\n      description: List alert rules for a project\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uptrace.list-alerts\n      with:\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-alert\n      description: Create a new monitoring alert rule using PromQL\n      hints:\n        readOnly: false\n        openWorld: false\n      call: uptrace.create-alert\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-alert\n      description: Get details of a specific alert rule\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uptrace.get-alert\n\
  \      with:\n        alertId: tools.alertId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-alert\n      description: Delete an alert rule\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: uptrace.delete-alert\n      with:\n        alertId: tools.alertId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-dashboards\n      description: List dashboards for a project\n      hints:\n        readOnly: true\n        openWorld: false\n      call: uptrace.list-dashboards\n      with:\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
