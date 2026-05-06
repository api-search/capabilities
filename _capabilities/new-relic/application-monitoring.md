---
categories:
- monitoring
consumed_apis: []
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
- get application metrics
- send custom events for application tracking
- apm
- list deployment records for an application
- list hosts for an application
- list available metric names for an application
- record a new deployment
- infrastructure
- developer
- analytics
- update application settings
- list application hosts
- devops
- deployments
- manage deployments
- get details of a specific application
- send custom events
- record a new deployment for an application
- monitoring
- query metric data
- list key transactions
- query metric data points for an application
- get or update an application
- new relic
- send events
- application monitoring
- update application
- observability
- get key transactions
- get application details
- list application metrics
- get applications
- get deployments
- create deployment
- list available metric names
- list all monitored applications
- performance
- platform
- query metric data for an application
- get application hosts
- get application
- analysis
- list deployments for an application
- list applications
- get application metrics data
slug: application-monitoring
source_filename: application-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: New Relic Application Monitoring\n  description: Application performance monitoring workflow combining application metrics, deployments, hosts, and custom events\n    for developers tracking application health and release impact.\n  tags:\n  - New Relic\n  - Application Monitoring\n  - Developer\n  - APM\n  - Deployments\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    NEW_RELIC_API_KEY: NEW_RELIC_API_KEY\n    NEW_RELIC_INSERT_KEY: NEW_RELIC_INSERT_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: rest-api\n    baseUri: https://api.newrelic.com/v2\n    description: New Relic REST API v2 for managing applications, alerts, and retrieving monitoring data.\n    authentication:\n      type: apikey\n      key: Api-Key\n      value: '{{NEW_RELIC_API_KEY}}'\n      placement: header\n    resources:\n    - name: applications\n      path: /applications.json\n      description: Manage monitored\
  \ applications\n      operations:\n      - name: get-applications\n        method: GET\n        description: Retrieves a paginated list of all applications.\n        inputParameters:\n        - name: filter[name]\n          in: query\n          type: string\n          required: false\n          description: Filter by application name.\n        - name: filter[host]\n          in: query\n          type: string\n          required: false\n          description: Filter by application host.\n        - name: filter[ids]\n          in: query\n          type: array\n          required: false\n          description: Filter by application IDs.\n        - name: filter[language]\n          in: query\n          type: string\n          required: false\n          description: Filter by application language.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Pagination index.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: application-detail\n      path: /applications/{id}.json\n      description: Get, update, or delete a specific application\n      operations:\n      - name: get-application\n        method: GET\n        description: Retrieves a specific application by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Application ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-application\n        method: PUT\n        description: Updates an application's settings.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Application ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n        body:\n          type: json\n          data:\n            application: '{{tools.application}}'\n      - name: delete-application\n        method: DELETE\n        description: Removes an application from New Relic.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Application ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: application-deployments\n      path: /applications/{application_id}/deployments.json\n      description: Manage application deployments\n      operations:\n      - name: get-deployments\n        method: GET\n        description: Retrieves deployment records for an application.\n        inputParameters:\n        - name: application_id\n          in: path\n          type: integer\n          required: true\n          description: Application ID.\n        - name:\
  \ page\n          in: query\n          type: integer\n          required: false\n          description: Pagination index.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-deployment\n        method: POST\n        description: Records a new deployment for an application.\n        inputParameters:\n        - name: application_id\n          in: path\n          type: integer\n          required: true\n          description: Application ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            deployment: '{{tools.deployment}}'\n    - name: application-hosts\n      path: /applications/{application_id}/hosts.json\n      description: List application hosts\n      operations:\n      - name: get-application-hosts\n        method: GET\n        description: Retrieves\
  \ a list of hosts for an application.\n        inputParameters:\n        - name: application_id\n          in: path\n          type: integer\n          required: true\n          description: Application ID.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Pagination index.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: application-metrics\n      path: /applications/{application_id}/metrics.json\n      description: List application metrics\n      operations:\n      - name: get-application-metrics\n        method: GET\n        description: Retrieves available metric names for an application.\n        inputParameters:\n        - name: application_id\n          in: path\n          type: integer\n          required: true\n          description: Application ID.\n        - name: name\n          in: query\n          type: string\n  \
  \        required: false\n          description: Filter by metric name.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Pagination index.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: application-metrics-data\n      path: /applications/{application_id}/metrics/data.json\n      description: Query application metric data\n      operations:\n      - name: get-application-metrics-data\n        method: GET\n        description: Retrieves metric data for an application.\n        inputParameters:\n        - name: application_id\n          in: path\n          type: integer\n          required: true\n          description: Application ID.\n        - name: names[]\n          in: query\n          type: array\n          required: true\n          description: Metric names to retrieve.\n        - name: from\n          in: query\n       \
  \   type: string\n          required: false\n          description: Start of the time range.\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: End of the time range.\n        - name: period\n          in: query\n          type: integer\n          required: false\n          description: Period in seconds for data point aggregation.\n        - name: summarize\n          in: query\n          type: boolean\n          required: false\n          description: Whether to return a single summarized data point.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: key-transactions\n      path: /key_transactions.json\n      description: List key transactions\n      operations:\n      - name: get-key-transactions\n        method: GET\n        description: Retrieves a list of key transactions.\n        inputParameters:\n        - name: filter[name]\n\
  \          in: query\n          type: string\n          required: false\n          description: Filter by key transaction name.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Pagination index.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alerts-policies\n      path: /alerts_policies.json\n      description: Manage alert policies\n      operations:\n      - name: get-alerts-policies\n        method: GET\n        description: Retrieves a list of alert policies.\n        inputParameters:\n        - name: filter[name]\n          in: query\n          type: string\n          required: false\n          description: Filter by policy name.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Pagination index.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-alerts-policy\n        method: POST\n        description: Creates a new alert policy.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            policy: '{{tools.policy}}'\n    - name: alerts-policy-detail\n      path: /alerts_policies/{policy_id}.json\n      description: Update or delete an alert policy\n      operations:\n      - name: update-alerts-policy\n        method: PUT\n        description: Updates an alert policy.\n        inputParameters:\n        - name: policy_id\n          in: path\n          type: integer\n          required: true\n          description: Policy ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type:\
  \ json\n          data:\n            policy: '{{tools.policy}}'\n      - name: delete-alerts-policy\n        method: DELETE\n        description: Deletes an alert policy.\n        inputParameters:\n        - name: policy_id\n          in: path\n          type: integer\n          required: true\n          description: Policy ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alerts-conditions\n      path: /alerts_conditions.json\n      description: List alert conditions\n      operations:\n      - name: get-alerts-conditions\n        method: GET\n        description: Retrieves a list of alert conditions.\n        inputParameters:\n        - name: policy_id\n          in: query\n          type: integer\n          required: true\n          description: Policy ID to filter conditions.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description:\
  \ Pagination index.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alerts-incidents\n      path: /alerts_incidents.json\n      description: List alert incidents\n      operations:\n      - name: get-alerts-incidents\n        method: GET\n        description: Retrieves a list of alert incidents.\n        inputParameters:\n        - name: only_open\n          in: query\n          type: boolean\n          required: false\n          description: Filter for only open incidents.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Pagination index.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alerts-violations\n      path: /alerts_violations.json\n      description: List alert violations\n      operations:\n      - name: get-alerts-violations\n\
  \        method: GET\n        description: Retrieves a list of alert violations.\n        inputParameters:\n        - name: only_open\n          in: query\n          type: boolean\n          required: false\n          description: Filter for only open violations.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Pagination index.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alerts-events\n      path: /alerts_events.json\n      description: List alert events\n      operations:\n      - name: get-alerts-events\n        method: GET\n        description: Retrieves a list of alert events.\n        inputParameters:\n        - name: filter[product]\n          in: query\n          type: string\n          required: false\n          description: Filter by product type.\n        - name: filter[entity_type]\n          in: query\n      \
  \    type: string\n          required: false\n          description: Filter by entity type.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Pagination index.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: event-api\n    baseUri: https://insights-collector.newrelic.com\n    description: New Relic Event API for ingesting custom events.\n    authentication:\n      type: apikey\n      key: Api-Key\n      value: '{{NEW_RELIC_INSERT_KEY}}'\n      placement: header\n    resources:\n    - name: events\n      path: /v1/accounts/{accountId}/events\n      description: Send custom events\n      operations:\n      - name: send-events\n        method: POST\n        description: Sends one or more custom events to a New Relic account.\n        inputParameters:\n        - name: accountId\n          in: path\n          type:\
  \ integer\n          required: true\n          description: The New Relic account ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: '{{tools.events}}'\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: application-monitoring-api\n    description: Unified REST API for New Relic application performance monitoring.\n    resources:\n    - path: /v1/applications\n      name: applications\n      description: List applications\n      operations:\n      - method: GET\n        name: get-applications\n        description: List all monitored applications\n        call: rest-api.get-applications\n        with:\n          filter[name]: rest.filter_name\n          filter[host]: rest.filter_host\n          filter[language]: rest.filter_language\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/{id}\n\
  \      name: application-detail\n      description: Get or update an application\n      operations:\n      - method: GET\n        name: get-application\n        description: Get application details\n        call: rest-api.get-application\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-application\n        description: Update application settings\n        call: rest-api.update-application\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deployments/{applicationId}\n      name: deployments\n      description: Manage deployments\n      operations:\n      - method: GET\n        name: get-deployments\n        description: List deployments for an application\n        call: rest-api.get-deployments\n        with:\n          application_id: rest.applicationId\n          page: rest.page\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: POST\n        name: create-deployment\n        description: Record a new deployment\n        call: rest-api.create-deployment\n        with:\n          application_id: rest.applicationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/hosts/{applicationId}\n      name: hosts\n      description: List application hosts\n      operations:\n      - method: GET\n        name: get-application-hosts\n        description: List hosts for an application\n        call: rest-api.get-application-hosts\n        with:\n          application_id: rest.applicationId\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics/{applicationId}\n      name: application-metrics\n      description: List application metrics\n      operations:\n      - method: GET\n        name: get-application-metrics\n        description: List available metric\
  \ names\n        call: rest-api.get-application-metrics\n        with:\n          application_id: rest.applicationId\n          name: rest.name\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics/{applicationId}/data\n      name: application-metrics-data\n      description: Query metric data\n      operations:\n      - method: GET\n        name: get-application-metrics-data\n        description: Query metric data for an application\n        call: rest-api.get-application-metrics-data\n        with:\n          application_id: rest.applicationId\n          names[]: rest.names\n          from: rest.from\n          to: rest.to\n          period: rest.period\n          summarize: rest.summarize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/key-transactions\n      name: key-transactions\n      description: List key transactions\n      operations:\n      - method: GET\n     \
  \   name: get-key-transactions\n        description: List key transactions\n        call: rest-api.get-key-transactions\n        with:\n          filter[name]: rest.filter_name\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events/{accountId}\n      name: custom-events\n      description: Send custom events\n      operations:\n      - method: POST\n        name: send-events\n        description: Send custom events for application tracking\n        call: event-api.send-events\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9092\n    namespace: application-monitoring-mcp\n    transport: http\n    description: MCP server for AI-assisted New Relic application performance monitoring.\n    tools:\n    - name: get-applications\n      description: List all monitored applications\n      hints:\n        readOnly: true\n   \
  \     openWorld: true\n      call: rest-api.get-applications\n      with:\n        filter[name]: tools.filter_name\n        filter[host]: tools.filter_host\n        filter[language]: tools.filter_language\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-application\n      description: Get details of a specific application\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rest-api.get-application\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-application\n      description: Update application settings\n      hints:\n        readOnly: false\n        idempotent: true\n        openWorld: true\n      call: rest-api.update-application\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-deployments\n      description: List deployment records for an application\n  \
  \    hints:\n        readOnly: true\n        openWorld: true\n      call: rest-api.get-deployments\n      with:\n        application_id: tools.application_id\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-deployment\n      description: Record a new deployment for an application\n      hints:\n        readOnly: false\n        openWorld: true\n      call: rest-api.create-deployment\n      with:\n        application_id: tools.application_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-application-hosts\n      description: List hosts for an application\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rest-api.get-application-hosts\n      with:\n        application_id: tools.application_id\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-application-metrics\n      description: List available metric\
  \ names for an application\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rest-api.get-application-metrics\n      with:\n        application_id: tools.application_id\n        name: tools.name\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-application-metrics-data\n      description: Query metric data points for an application\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rest-api.get-application-metrics-data\n      with:\n        application_id: tools.application_id\n        names[]: tools.names\n        from: tools.from\n        to: tools.to\n        period: tools.period\n        summarize: tools.summarize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-key-transactions\n      description: List key transactions\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rest-api.get-key-transactions\n      with:\n\
  \        filter[name]: tools.filter_name\n        page: tools.page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-events\n      description: Send custom events for application tracking\n      hints:\n        readOnly: false\n        openWorld: true\n      call: event-api.send-events\n      with:\n        accountId: tools.accountId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
