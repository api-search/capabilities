---
categories:
- monitoring
consumed_apis:
- rest-api
- event-api
description: Application performance monitoring workflow combining application metrics, deployments, hosts, and custom events for developers tracking application health and release impact.
layout: capability
name: New Relic Application Monitoring
operations:
- description: List all monitored applications
  method: GET
  name: get-applications
  path: /v1/applications
- description: Get application details
  method: GET
  name: get-application
  path: /v1/applications/{id}
- description: Update application settings
  method: PUT
  name: update-application
  path: /v1/applications/{id}
- description: List deployments for an application
  method: GET
  name: get-deployments
  path: /v1/deployments/{applicationId}
- description: Record a new deployment
  method: POST
  name: create-deployment
  path: /v1/deployments/{applicationId}
- description: List hosts for an application
  method: GET
  name: get-application-hosts
  path: /v1/hosts/{applicationId}
- description: List available metric names
  method: GET
  name: get-application-metrics
  path: /v1/metrics/{applicationId}
- description: Query metric data for an application
  method: GET
  name: get-application-metrics-data
  path: /v1/metrics/{applicationId}/data
- description: List key transactions
  method: GET
  name: get-key-transactions
  path: /v1/key-transactions
- description: Send custom events for application tracking
  method: POST
  name: send-events
  path: /v1/events/{accountId}
personas: []
provider_name: New Relic
provider_slug: new-relic
search_terms:
- get or update an application
- get deployments
- list available metric names
- observability
- list deployment records for an application
- record a new deployment for an application
- create deployment
- get details of a specific application
- apm
- manage deployments
- performance
- send custom events
- list application metrics
- send custom events for application tracking
- record a new deployment
- analysis
- platform
- analytics
- list application hosts
- list applications
- get application metrics
- query metric data
- developer
- get applications
- new relic
- list deployments for an application
- update application settings
- list all monitored applications
- list available metric names for an application
- get application details
- get application metrics data
- send events
- list hosts for an application
- infrastructure
- application monitoring
- deployments
- devops
- query metric data points for an application
- get application
- update application
- query metric data for an application
- monitoring
- get application hosts
- list key transactions
- get key transactions
slug: application-monitoring
source_filename: application-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"New Relic Application Monitoring\"\n  description: \"Application performance monitoring workflow combining application metrics, deployments, hosts, and custom events for developers tracking application health and release impact.\"\n  tags:\n    - New Relic\n    - Application Monitoring\n    - Developer\n    - APM\n    - Deployments\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      NEW_RELIC_API_KEY: NEW_RELIC_API_KEY\n      NEW_RELIC_INSERT_KEY: NEW_RELIC_INSERT_KEY\n\ncapability:\n  consumes:\n    - import: rest-api\n      location: ./shared/rest-api.yaml\n    - import: event-api\n      location: ./shared/event-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: application-monitoring-api\n      description: \"Unified REST API for New Relic application performance monitoring.\"\n      resources:\n        - path: /v1/applications\n          name: applications\n\
  \          description: \"List applications\"\n          operations:\n            - method: GET\n              name: get-applications\n              description: \"List all monitored applications\"\n              call: \"rest-api.get-applications\"\n              with:\n                filter[name]: \"rest.filter_name\"\n                filter[host]: \"rest.filter_host\"\n                filter[language]: \"rest.filter_language\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applications/{id}\n          name: application-detail\n          description: \"Get or update an application\"\n          operations:\n            - method: GET\n              name: get-application\n              description: \"Get application details\"\n              call: \"rest-api.get-application\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n               \
  \ - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-application\n              description: \"Update application settings\"\n              call: \"rest-api.update-application\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/deployments/{applicationId}\n          name: deployments\n          description: \"Manage deployments\"\n          operations:\n            - method: GET\n              name: get-deployments\n              description: \"List deployments for an application\"\n              call: \"rest-api.get-deployments\"\n              with:\n                application_id: \"rest.applicationId\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-deployment\n \
  \             description: \"Record a new deployment\"\n              call: \"rest-api.create-deployment\"\n              with:\n                application_id: \"rest.applicationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/hosts/{applicationId}\n          name: hosts\n          description: \"List application hosts\"\n          operations:\n            - method: GET\n              name: get-application-hosts\n              description: \"List hosts for an application\"\n              call: \"rest-api.get-application-hosts\"\n              with:\n                application_id: \"rest.applicationId\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/metrics/{applicationId}\n          name: application-metrics\n          description: \"List application metrics\"\n          operations:\n            - method:\
  \ GET\n              name: get-application-metrics\n              description: \"List available metric names\"\n              call: \"rest-api.get-application-metrics\"\n              with:\n                application_id: \"rest.applicationId\"\n                name: \"rest.name\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/metrics/{applicationId}/data\n          name: application-metrics-data\n          description: \"Query metric data\"\n          operations:\n            - method: GET\n              name: get-application-metrics-data\n              description: \"Query metric data for an application\"\n              call: \"rest-api.get-application-metrics-data\"\n              with:\n                application_id: \"rest.applicationId\"\n                names[]: \"rest.names\"\n                from: \"rest.from\"\n                to: \"rest.to\"\n                period:\
  \ \"rest.period\"\n                summarize: \"rest.summarize\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/key-transactions\n          name: key-transactions\n          description: \"List key transactions\"\n          operations:\n            - method: GET\n              name: get-key-transactions\n              description: \"List key transactions\"\n              call: \"rest-api.get-key-transactions\"\n              with:\n                filter[name]: \"rest.filter_name\"\n                page: \"rest.page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/events/{accountId}\n          name: custom-events\n          description: \"Send custom events\"\n          operations:\n            - method: POST\n              name: send-events\n              description: \"Send custom events for application tracking\"\n              call: \"\
  event-api.send-events\"\n              with:\n                accountId: \"rest.accountId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: application-monitoring-mcp\n      transport: http\n      description: \"MCP server for AI-assisted New Relic application performance monitoring.\"\n      tools:\n        - name: get-applications\n          description: \"List all monitored applications\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rest-api.get-applications\"\n          with:\n            filter[name]: \"tools.filter_name\"\n            filter[host]: \"tools.filter_host\"\n            filter[language]: \"tools.filter_language\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-application\n          description: \"Get details of a specific\
  \ application\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rest-api.get-application\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-application\n          description: \"Update application settings\"\n          hints:\n            readOnly: false\n            idempotent: true\n            openWorld: true\n          call: \"rest-api.update-application\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-deployments\n          description: \"List deployment records for an application\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rest-api.get-deployments\"\n          with:\n            application_id: \"tools.application_id\"\n            page: \"tools.page\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: create-deployment\n          description: \"Record a new deployment for an application\"\n          hints:\n            readOnly: false\n            openWorld: true\n          call: \"rest-api.create-deployment\"\n          with:\n            application_id: \"tools.application_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-application-hosts\n          description: \"List hosts for an application\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rest-api.get-application-hosts\"\n          with:\n            application_id: \"tools.application_id\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-application-metrics\n          description: \"List available metric names for an application\"\n          hints:\n\
  \            readOnly: true\n            openWorld: true\n          call: \"rest-api.get-application-metrics\"\n          with:\n            application_id: \"tools.application_id\"\n            name: \"tools.name\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-application-metrics-data\n          description: \"Query metric data points for an application\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rest-api.get-application-metrics-data\"\n          with:\n            application_id: \"tools.application_id\"\n            names[]: \"tools.names\"\n            from: \"tools.from\"\n            to: \"tools.to\"\n            period: \"tools.period\"\n            summarize: \"tools.summarize\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-key-transactions\n          description: \"List\
  \ key transactions\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"rest-api.get-key-transactions\"\n          with:\n            filter[name]: \"tools.filter_name\"\n            page: \"tools.page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-events\n          description: \"Send custom events for application tracking\"\n          hints:\n            readOnly: false\n            openWorld: true\n          call: \"event-api.send-events\"\n          with:\n            accountId: \"tools.accountId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/new-relic/refs/heads/main/capabilities/application-monitoring.yaml
tags:
- New Relic
- Application Monitoring
- Developer
- APM
- Deployments
tools:
- description: List all monitored applications
  hints:
    openWorld: true
    readOnly: true
  name: get-applications
- description: Get details of a specific application
  hints:
    openWorld: true
    readOnly: true
  name: get-application
- description: Update application settings
  hints:
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-application
- description: List deployment records for an application
  hints:
    openWorld: true
    readOnly: true
  name: get-deployments
- description: Record a new deployment for an application
  hints:
    openWorld: true
    readOnly: false
  name: create-deployment
- description: List hosts for an application
  hints:
    openWorld: true
    readOnly: true
  name: get-application-hosts
- description: List available metric names for an application
  hints:
    openWorld: true
    readOnly: true
  name: get-application-metrics
- description: Query metric data points for an application
  hints:
    openWorld: true
    readOnly: true
  name: get-application-metrics-data
- description: List key transactions
  hints:
    openWorld: true
    readOnly: true
  name: get-key-transactions
- description: Send custom events for application tracking
  hints:
    openWorld: true
    readOnly: false
  name: send-events
---
