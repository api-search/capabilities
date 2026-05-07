---
categories: []
consumed_apis: []
description: Unified observability monitoring capability combining SigNoz's alerts, dashboards, metrics, traces, logs, and infrastructure monitoring APIs into a single workflow. Designed for DevOps engineers, SREs, and platform teams managing distributed system observability, incident detection, and performance analysis.
layout: capability
name: SigNoz Observability Monitoring
operations:
- description: List all configured alert rules
  method: GET
  name: list-alerts
  path: /v1/alerts
- description: Create a new alert rule for observability monitoring
  method: POST
  name: create-alert
  path: /v1/alerts
- description: Get details of a specific alert rule
  method: GET
  name: get-alert
  path: /v1/alerts/{id}
- description: Delete an alert rule
  method: DELETE
  name: delete-alert
  path: /v1/alerts/{id}
- description: List all notification channels
  method: GET
  name: list-channels
  path: /v1/channels
- description: Create a new notification channel
  method: POST
  name: create-channel
  path: /v1/channels
- description: List all available metrics in the platform
  method: GET
  name: list-metrics
  path: /v1/metrics
- description: Query metrics, traces, or logs over a time range
  method: POST
  name: query-range
  path: /v1/query
- description: Get distributed trace waterfall by trace ID
  method: GET
  name: get-trace
  path: /v1/traces/{traceId}
- description: List all monitored infrastructure hosts
  method: GET
  name: list-hosts
  path: /v1/hosts
- description: List all ingestion keys
  method: GET
  name: list-ingestion-keys
  path: /v1/ingestion-keys
- description: Create a new ingestion key
  method: POST
  name: create-ingestion-key
  path: /v1/ingestion-keys
personas: []
provider_name: SigNoz
provider_slug: signoz
search_terms:
- opentelemetry
- get details of a specific alert rule
- query telemetry
- create ingestion key
- create alert
- distributed tracing
- list all available metrics in the signoz metrics catalog
- list channels
- infrastructure monitoring
- individual alert rule operations
- notification channel management
- create a new ingestion key
- apm
- list all ingestion keys
- get the distributed trace waterfall view for a specific trace id to analyze request flow
- delete alert
- list all configured alert rules
- list notification channels
- distributed trace inspection
- ingestion key management for telemetry data collection
- cloud monitoring
- open source
- delete an alert rule
- create a new ingestion key for authenticating telemetry data collection
- query metrics, distributed traces, or logs data over a specified time range
- list all monitored infrastructure hosts
- create notification channel
- logs
- infrastructure
- metrics catalog and inspection
- list all available metrics in the platform
- list all telemetry ingestion keys for the organization
- query range
- dashboards
- observability
- create a new alert rule for observability monitoring
- get trace
- sre
- list all configured alert rules in the signoz observability platform
- infrastructure host monitoring
- unified telemetry query endpoint
- list alerts
- get details of a specific alert rule by id
- create channel
- get alert
- list hosts
- list ingestion keys
- list all notification channels
- alert rule management for observability monitoring
- delete an alert rule from signoz
- create a new notification channel
- metrics
- list metrics
- list infrastructure hosts
- query metrics, traces, or logs over a time range
- get trace waterfall
- create a new observability alert rule with threshold conditions
- alerting
- get distributed trace waterfall by trace id
- list all monitored infrastructure hosts and their current status
- list all alert notification channels (slack, pagerduty, email, webhook)
- create a new alert notification channel
slug: observability-monitoring
source_filename: observability-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SigNoz Observability Monitoring\n  description: Unified observability monitoring capability combining SigNoz's alerts, dashboards, metrics, traces, logs, and\n    infrastructure monitoring APIs into a single workflow. Designed for DevOps engineers, SREs, and platform teams managing\n    distributed system observability, incident detection, and performance analysis.\n  tags:\n  - APM\n  - Alerting\n  - Dashboards\n  - Distributed Tracing\n  - Infrastructure\n  - Logs\n  - Metrics\n  - Observability\n  - OpenTelemetry\n  - SRE\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SIGNOZ_API_KEY: SIGNOZ_API_KEY\n    SIGNOZ_HOST: SIGNOZ_HOST\n    SIGNOZ_PORT: SIGNOZ_PORT\ncapability:\n  consumes:\n  - type: http\n    namespace: signoz\n    baseUri: https://{{env.SIGNOZ_HOST}}:{{env.SIGNOZ_PORT}}\n    description: SigNoz observability platform REST API\n    authentication:\n      type: apikey\n      key:\
  \ SigNoz-Api-Key\n      value: '{{env.SIGNOZ_API_KEY}}'\n      placement: header\n    resources:\n    - name: alerts\n      path: /api/v2/rules\n      description: Alert rules management\n      operations:\n      - name: list-alerts\n        method: GET\n        description: List all alert rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-alert\n        method: POST\n        description: Create a new alert rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            severity: '{{tools.severity}}'\n            alertType: '{{tools.alertType}}'\n            condition: '{{tools.condition}}'\n            channels: '{{tools.channels}}'\n      - name: get-alert\n      \
  \  method: GET\n        description: Get a specific alert rule by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Alert rule ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-alert\n        method: DELETE\n        description: Delete an alert rule\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Alert rule ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dashboards\n      path: /api/v1/public/dashboards\n      description: Public dashboard access\n      operations:\n      - name: get-public-dashboard\n        method: GET\n        description: Get a public dashboard by ID\n        inputParameters:\n        - name:\
  \ id\n          in: path\n          type: string\n          required: true\n          description: Dashboard ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: query\n      path: /api/v5/query_range\n      description: Query telemetry data including traces, logs, and metrics\n      operations:\n      - name: query-range\n        method: POST\n        description: Execute a query over a time range for metrics, traces, or logs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            start: '{{tools.start}}'\n            end: '{{tools.end}}'\n            step: '{{tools.step}}'\n            compositeQuery: '{{tools.compositeQuery}}'\n    - name: ingestion-keys\n      path: /api/v2/gateway/ingestion_keys\n      description: Manage ingestion keys for telemetry data authentication\n\
  \      operations:\n      - name: list-ingestion-keys\n        method: GET\n        description: List all ingestion keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-ingestion-key\n        method: POST\n        description: Create a new ingestion key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: channels\n      path: /api/v1/channels\n      description: Notification channels management\n      operations:\n      - name: list-channels\n        method: GET\n        description: List all notification channels\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-channel\n        method: POST\n        description:\
  \ Create a new notification channel\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n            data: '{{tools.data}}'\n    - name: metrics\n      path: /api/v2/metrics\n      description: Metrics catalog and inspection\n      operations:\n      - name: list-metrics\n        method: GET\n        description: List all available metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: infra-hosts\n      path: /api/v2/infra_monitoring/hosts\n      description: Infrastructure host monitoring\n      operations:\n      - name: list-hosts\n        method: GET\n        description: List monitored infrastructure hosts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n    - name: traces\n      path: /api/v3/traces\n      description: Distributed trace data access\n      operations:\n      - name: get-trace-waterfall\n        method: GET\n        description: Get trace waterfall view by trace ID\n        inputParameters:\n        - name: traceID\n          in: path\n          type: string\n          required: true\n          description: Trace ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /api/v2/users\n      description: User management\n      operations:\n      - name: list-users\n        method: GET\n        description: List all users in the organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-current-user\n        method: GET\n        description: Get the currently authenticated user\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: signoz-observability-api\n    description: Unified REST API for SigNoz observability monitoring workflows.\n    resources:\n    - path: /v1/alerts\n      name: alerts\n      description: Alert rule management for observability monitoring\n      operations:\n      - method: GET\n        name: list-alerts\n        description: List all configured alert rules\n        call: signoz.list-alerts\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-alert\n        description: Create a new alert rule for observability monitoring\n        call: signoz.create-alert\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/alerts/{id}\n      name: alert\n      description: Individual alert rule operations\n      operations:\n\
  \      - method: GET\n        name: get-alert\n        description: Get details of a specific alert rule\n        call: signoz.get-alert\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-alert\n        description: Delete an alert rule\n        call: signoz.delete-alert\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/channels\n      name: channels\n      description: Notification channel management\n      operations:\n      - method: GET\n        name: list-channels\n        description: List all notification channels\n        call: signoz.list-channels\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-channel\n        description: Create a new notification channel\n        call: signoz.create-channel\n        outputParameters:\n   \
  \     - type: object\n          mapping: $.\n    - path: /v1/metrics\n      name: metrics\n      description: Metrics catalog and inspection\n      operations:\n      - method: GET\n        name: list-metrics\n        description: List all available metrics in the platform\n        call: signoz.list-metrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/query\n      name: query\n      description: Unified telemetry query endpoint\n      operations:\n      - method: POST\n        name: query-range\n        description: Query metrics, traces, or logs over a time range\n        call: signoz.query-range\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/traces/{traceId}\n      name: trace\n      description: Distributed trace inspection\n      operations:\n      - method: GET\n        name: get-trace\n        description: Get distributed trace waterfall by trace ID\n        call: signoz.get-trace-waterfall\n\
  \        with:\n          traceID: rest.traceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/hosts\n      name: hosts\n      description: Infrastructure host monitoring\n      operations:\n      - method: GET\n        name: list-hosts\n        description: List all monitored infrastructure hosts\n        call: signoz.list-hosts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ingestion-keys\n      name: ingestion-keys\n      description: Ingestion key management for telemetry data collection\n      operations:\n      - method: GET\n        name: list-ingestion-keys\n        description: List all ingestion keys\n        call: signoz.list-ingestion-keys\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-ingestion-key\n        description: Create a new ingestion key\n        call: signoz.create-ingestion-key\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: signoz-observability-mcp\n    transport: http\n    description: MCP server for AI-assisted observability monitoring, incident investigation, and performance analysis.\n    tools:\n    - name: list-alerts\n      description: List all configured alert rules in the SigNoz observability platform\n      hints:\n        readOnly: true\n        idempotent: true\n      call: signoz.list-alerts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-alert\n      description: Create a new observability alert rule with threshold conditions\n      hints:\n        readOnly: false\n        idempotent: false\n      call: signoz.create-alert\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-alert\n      description: Get details of a specific alert rule by ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: signoz.get-alert\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-alert\n      description: Delete an alert rule from SigNoz\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: signoz.delete-alert\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-notification-channels\n      description: List all alert notification channels (Slack, PagerDuty, email, webhook)\n      hints:\n        readOnly: true\n        idempotent: true\n      call: signoz.list-channels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-notification-channel\n      description: Create a new alert notification channel\n      hints:\n        readOnly: false\n        idempotent: false\n      call: signoz.create-channel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-telemetry\n      description: Query metrics, distributed traces, or logs\
  \ data over a specified time range\n      hints:\n        readOnly: true\n        idempotent: true\n      call: signoz.query-range\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-metrics\n      description: List all available metrics in the SigNoz metrics catalog\n      hints:\n        readOnly: true\n        idempotent: true\n      call: signoz.list-metrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-trace-waterfall\n      description: Get the distributed trace waterfall view for a specific trace ID to analyze request flow\n      hints:\n        readOnly: true\n        idempotent: true\n      call: signoz.get-trace-waterfall\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-infrastructure-hosts\n      description: List all monitored infrastructure hosts and their current status\n      hints:\n        readOnly: true\n        idempotent: true\n      call: signoz.list-hosts\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-ingestion-keys\n      description: List all telemetry ingestion keys for the organization\n      hints:\n        readOnly: true\n        idempotent: true\n      call: signoz.list-ingestion-keys\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-ingestion-key\n      description: Create a new ingestion key for authenticating telemetry data collection\n      hints:\n        readOnly: false\n        idempotent: false\n      call: signoz.create-ingestion-key\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/signoz/refs/heads/main/capabilities/observability-monitoring.yaml
tags:
- APM
- Alerting
- Dashboards
- Distributed Tracing
- Infrastructure
- Logs
- Metrics
- Observability
- OpenTelemetry
- SRE
tools:
- description: List all configured alert rules in the SigNoz observability platform
  hints:
    idempotent: true
    readOnly: true
  name: list-alerts
- description: Create a new observability alert rule with threshold conditions
  hints:
    idempotent: false
    readOnly: false
  name: create-alert
- description: Get details of a specific alert rule by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-alert
- description: Delete an alert rule from SigNoz
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-alert
- description: List all alert notification channels (Slack, PagerDuty, email, webhook)
  hints:
    idempotent: true
    readOnly: true
  name: list-notification-channels
- description: Create a new alert notification channel
  hints:
    idempotent: false
    readOnly: false
  name: create-notification-channel
- description: Query metrics, distributed traces, or logs data over a specified time range
  hints:
    idempotent: true
    readOnly: true
  name: query-telemetry
- description: List all available metrics in the SigNoz metrics catalog
  hints:
    idempotent: true
    readOnly: true
  name: list-metrics
- description: Get the distributed trace waterfall view for a specific trace ID to analyze request flow
  hints:
    idempotent: true
    readOnly: true
  name: get-trace-waterfall
- description: List all monitored infrastructure hosts and their current status
  hints:
    idempotent: true
    readOnly: true
  name: list-infrastructure-hosts
- description: List all telemetry ingestion keys for the organization
  hints:
    idempotent: true
    readOnly: true
  name: list-ingestion-keys
- description: Create a new ingestion key for authenticating telemetry data collection
  hints:
    idempotent: false
    readOnly: false
  name: create-ingestion-key
---
