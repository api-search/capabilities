---
categories: []
consumed_apis: []
description: Unified web analytics capability combining Swetrix Events, Statistics, and Admin APIs. Enables product teams and developers to track user behavior, analyze traffic patterns, manage analytics projects, and monitor errors in a privacy-first, cookieless analytics environment.
layout: capability
name: Swetrix Web Analytics
operations:
- description: Record Pageview Event
  method: POST
  name: record-pageview
  path: /v1/events/pageviews
- description: Record Custom Event
  method: POST
  name: record-custom-event
  path: /v1/events/custom
- description: Record Error Event
  method: POST
  name: record-error
  path: /v1/events/errors
- description: Get Traffic Log
  method: GET
  name: get-traffic-log
  path: /v1/analytics/traffic
- description: Get Performance Metrics
  method: GET
  name: get-performance-metrics
  path: /v1/analytics/performance
- description: Get Live Visitors
  method: GET
  name: get-live-visitors
  path: /v1/analytics/live-visitors
- description: List Sessions
  method: GET
  name: list-sessions
  path: /v1/analytics/sessions
- description: Get Funnel Analysis
  method: GET
  name: get-funnel-analysis
  path: /v1/analytics/funnels
- description: List Error Events
  method: GET
  name: list-errors
  path: /v1/analytics/errors
- description: List Projects
  method: GET
  name: list-projects
  path: /v1/projects
- description: Create Project
  method: POST
  name: create-project
  path: /v1/projects
- description: Get Project
  method: GET
  name: get-project
  path: /v1/projects/{id}
- description: Delete Project
  method: DELETE
  name: delete-project
  path: /v1/projects/{id}
personas: []
provider_name: Swetrix
provider_slug: swetrix
search_terms:
- error tracking
- record revenue
- record custom events
- cookieless tracking
- record a javascript error event for dashboard aggregation
- query frontend performance metrics including dns, tls, ttfb, and page load times
- custom events
- traffic
- analytics
- list individual visitor sessions with device and page details
- record custom event
- record pageview
- record error
- list error events
- create a new swetrix analytics project
- real-time analytics
- record a pageview event to swetrix analytics
- get currently active visitors with device, browser, os, and country details
- record error event
- swetrix
- project management
- create project
- list sessions
- open source
- record pageview events
- query error statistics
- web analytics
- get currently active visitors
- record a custom analytics event with optional metadata
- list all swetrix analytics projects for the account
- list javascript error groups with occurrence counts and affected sessions
- get performance metrics
- list errors
- permanently delete a project and all associated analytics data
- gdpr compliant
- record javascript error events
- get live visitors
- query aggregated traffic data for a project by time bucket and period
- manage analytics projects
- delete project
- query custom event analytics grouped by time for named events
- get project
- list projects
- get configuration and settings for a specific project
- get funnel analysis
- query traffic analytics
- record a revenue transaction (sale, refund, subscription)
- record pageview event
- get custom events
- analyze conversion funnels
- analyze conversion rates across a sequence of pages in a funnel
- query performance metrics
- privacy
- get traffic log
- list visitor sessions
- single project operations
slug: web-analytics
source_filename: web-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Swetrix Web Analytics\n  description: Unified web analytics capability combining Swetrix Events, Statistics, and Admin APIs. Enables product teams\n    and developers to track user behavior, analyze traffic patterns, manage analytics projects, and monitor errors in a privacy-first,\n    cookieless analytics environment.\n  tags:\n  - Analytics\n  - Custom Events\n  - Error Tracking\n  - GDPR Compliant\n  - Open Source\n  - Privacy\n  - Project Management\n  - Swetrix\n  - Traffic\n  - Web Analytics\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SWETRIX_API_KEY: SWETRIX_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: swetrix-events\n    baseUri: https://api.swetrix.com\n    description: Records analytics events for Swetrix projects\n    resources:\n    - name: pageviews\n      path: /log\n      description: Pageview event recording\n      operations:\n      - name: record-pageview\n\
  \        method: POST\n        description: Record Pageview Event\n        inputParameters:\n        - name: pid\n          in: body\n          type: string\n          required: true\n          description: Project ID\n        - name: pg\n          in: body\n          type: string\n          required: false\n          description: Page path\n        - name: lc\n          in: body\n          type: string\n          required: false\n          description: User locale\n        - name: ref\n          in: body\n          type: string\n          required: false\n          description: Referrer URL\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: custom-events\n      path: /log/custom\n      description: Custom event recording\n      operations:\n      - name: record-custom-event\n        method: POST\n        description: Record Custom Event\n        inputParameters:\n        - name: pid\n          in:\
  \ body\n          type: string\n          required: true\n          description: Project ID\n        - name: ev\n          in: body\n          type: string\n          required: true\n          description: Event identifier\n        - name: pg\n          in: body\n          type: string\n          required: false\n          description: Page path\n        - name: meta\n          in: body\n          type: object\n          required: false\n          description: Custom metadata key-value pairs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: heartbeat\n      path: /log/hb\n      description: Session heartbeat events\n      operations:\n      - name: record-heartbeat\n        method: POST\n        description: Record Heartbeat Event\n        inputParameters:\n        - name: pid\n          in: body\n          type: string\n          required: true\n          description: Project ID\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: errors\n      path: /log/error\n      description: JavaScript error recording\n      operations:\n      - name: record-error\n        method: POST\n        description: Record Error Event\n        inputParameters:\n        - name: pid\n          in: body\n          type: string\n          required: true\n          description: Project ID\n        - name: name\n          in: body\n          type: string\n          required: true\n          description: Error name\n        - name: message\n          in: body\n          type: string\n          required: false\n          description: Error message\n        - name: stackTrace\n          in: body\n          type: string\n          required: false\n          description: Stack trace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: revenue\n\
  \      path: /log/revenue\n      description: Revenue transaction recording\n      operations:\n      - name: record-revenue\n        method: POST\n        description: Record Revenue Transaction\n        inputParameters:\n        - name: pid\n          in: body\n          type: string\n          required: true\n          description: Project ID\n        - name: type\n          in: body\n          type: string\n          required: true\n          description: 'Transaction type: sale, refund, subscription'\n        - name: amount\n          in: body\n          type: number\n          required: true\n          description: Transaction amount\n        - name: currency\n          in: body\n          type: string\n          required: true\n          description: ISO 4217 currency code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: swetrix-statistics\n    baseUri: https://api.swetrix.com\n\
  \    description: Queries Swetrix analytics statistics\n    authentication:\n      type: apikey\n      key: X-Api-Key\n      value: '{{SWETRIX_API_KEY}}'\n      placement: header\n    resources:\n    - name: traffic-log\n      path: /v1/log\n      description: Aggregated traffic log data\n      operations:\n      - name: get-traffic-log\n        method: GET\n        description: Get Traffic Log\n        inputParameters:\n        - name: pid\n          in: query\n          type: string\n          required: true\n          description: Project ID\n        - name: timeBucket\n          in: query\n          type: string\n          required: true\n          description: 'Time bucket: minute, hour, day, week, month, year'\n        - name: period\n          in: query\n          type: string\n          required: true\n          description: 'Period: 1h, today, 7d, 4w, 3M, 12M, all'\n        - name: from\n          in: query\n          type: string\n          required: false\n          description:\
  \ Custom range start date YYYY-MM-DD\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: Custom range end date YYYY-MM-DD\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: performance\n      path: /v1/log/performance\n      description: Frontend performance metrics\n      operations:\n      - name: get-performance-metrics\n        method: GET\n        description: Get Performance Metrics\n        inputParameters:\n        - name: pid\n          in: query\n          type: string\n          required: true\n          description: Project ID\n        - name: timeBucket\n          in: query\n          type: string\n          required: true\n          description: Time bucket\n        - name: period\n          in: query\n          type: string\n          required: true\n          description: Period\n        - name: measure\n          in: query\n\
  \          type: string\n          required: false\n          description: 'Aggregation: median, average, p95, quantiles'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: birdseye\n      path: /v1/log/birdseye\n      description: Traffic summary across projects\n      operations:\n      - name: get-birdseye-summary\n        method: GET\n        description: Get Birdseye Traffic Summary\n        inputParameters:\n        - name: pids\n          in: query\n          type: string\n          required: false\n          description: Comma-separated project IDs\n        - name: period\n          in: query\n          type: string\n          required: true\n          description: Time period\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: live-visitors\n      path: /v1/log/live-visitors\n      description: Currently\
  \ active visitors\n      operations:\n      - name: get-live-visitors\n        method: GET\n        description: Get Live Visitors\n        inputParameters:\n        - name: pid\n          in: query\n          type: string\n          required: true\n          description: Project ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sessions\n      path: /v1/log/sessions\n      description: Individual visitor sessions\n      operations:\n      - name: list-sessions\n        method: GET\n        description: List Sessions\n        inputParameters:\n        - name: pid\n          in: query\n          type: string\n          required: true\n          description: Project ID\n        - name: period\n          in: query\n          type: string\n          required: true\n          description: Time period\n        - name: take\n          in: query\n          type: integer\n          required: false\n   \
  \       description: Results per page (max 150)\n        - name: skip\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: funnels\n      path: /v1/log/funnel\n      description: Conversion funnel analysis\n      operations:\n      - name: get-funnel-analysis\n        method: GET\n        description: Get Funnel Analysis\n        inputParameters:\n        - name: pid\n          in: query\n          type: string\n          required: true\n          description: Project ID\n        - name: period\n          in: query\n          type: string\n          required: true\n          description: Time period\n        - name: pages\n          in: query\n          type: string\n          required: false\n          description: JSON array of page paths\n        - name: funnelId\n          in: query\n\
  \          type: string\n          required: false\n          description: Saved funnel ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: errors-list\n      path: /v1/log/errors\n      description: Error event groups\n      operations:\n      - name: list-errors\n        method: GET\n        description: List Error Events\n        inputParameters:\n        - name: pid\n          in: query\n          type: string\n          required: true\n          description: Project ID\n        - name: period\n          in: query\n          type: string\n          required: true\n          description: Time period\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: custom-events-data\n      path: /v1/log/custom-events\n      description: Custom event analytics\n      operations:\n      - name: get-custom-events\n        method:\
  \ GET\n        description: Get Custom Events Data\n        inputParameters:\n        - name: pid\n          in: query\n          type: string\n          required: true\n          description: Project ID\n        - name: timeBucket\n          in: query\n          type: string\n          required: true\n          description: Time bucket\n        - name: period\n          in: query\n          type: string\n          required: true\n          description: Time period\n        - name: customEvents\n          in: query\n          type: string\n          required: true\n          description: JSON array of event names\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: swetrix-admin\n    baseUri: https://api.swetrix.com\n    description: Manages Swetrix analytics projects and resources\n    authentication:\n      type: apikey\n      key: X-Api-Key\n      value: '{{SWETRIX_API_KEY}}'\n\
  \      placement: header\n    resources:\n    - name: projects\n      path: /v1/project\n      description: Analytics project management\n      operations:\n      - name: list-projects\n        method: GET\n        description: List Projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-project\n        method: POST\n        description: Create Project\n        inputParameters:\n        - name: name\n          in: body\n          type: string\n          required: true\n          description: Project display name (max 50 chars)\n        - name: isCaptcha\n          in: body\n          type: boolean\n          required: false\n          description: Enable CAPTCHA tracking\n        - name: isPasswordProtected\n          in: body\n          type: boolean\n          required: false\n          description: Require dashboard password\n        - name: organisationId\n          in: body\n   \
  \       type: string\n          required: false\n          description: Organisation to assign project to\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: project-detail\n      path: /v1/project/{id}\n      description: Single project operations\n      operations:\n      - name: get-project\n        method: GET\n        description: Get Project\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Project ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-project\n        method: PUT\n        description: Update Project\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Project ID\n        - name: name\n          in: body\n \
  \         type: string\n          required: false\n          description: New project name\n        - name: active\n          in: body\n          type: boolean\n          required: false\n          description: Enable/disable tracking\n        - name: public\n          in: body\n          type: boolean\n          required: false\n          description: Public dashboard visibility\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-project\n        method: DELETE\n        description: Delete Project\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Project ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organisations\n      path: /v1/organisation\n      description: Organisation management\n      operations:\n\
  \      - name: list-organisations\n        method: GET\n        description: List Organisations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-organisation\n        method: POST\n        description: Create Organisation\n        inputParameters:\n        - name: name\n          in: body\n          type: string\n          required: true\n          description: Organisation name (max 50 chars)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: swetrix-analytics-api\n    description: Unified REST API for Swetrix web analytics management and querying.\n    resources:\n    - path: /v1/events/pageviews\n      name: pageviews\n      description: Record pageview events\n      operations:\n      - method: POST\n        name: record-pageview\n        description:\
  \ Record Pageview Event\n        call: swetrix-events.record-pageview\n        with:\n          pid: rest.pid\n          pg: rest.pg\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events/custom\n      name: custom-events\n      description: Record custom events\n      operations:\n      - method: POST\n        name: record-custom-event\n        description: Record Custom Event\n        call: swetrix-events.record-custom-event\n        with:\n          pid: rest.pid\n          ev: rest.ev\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events/errors\n      name: error-events\n      description: Record JavaScript error events\n      operations:\n      - method: POST\n        name: record-error\n        description: Record Error Event\n        call: swetrix-events.record-error\n        with:\n          pid: rest.pid\n          name: rest.name\n        outputParameters:\n        - type: object\n        \
  \  mapping: $.\n    - path: /v1/analytics/traffic\n      name: traffic\n      description: Query traffic analytics\n      operations:\n      - method: GET\n        name: get-traffic-log\n        description: Get Traffic Log\n        call: swetrix-statistics.get-traffic-log\n        with:\n          pid: rest.pid\n          timeBucket: rest.timeBucket\n          period: rest.period\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analytics/performance\n      name: performance\n      description: Query performance metrics\n      operations:\n      - method: GET\n        name: get-performance-metrics\n        description: Get Performance Metrics\n        call: swetrix-statistics.get-performance-metrics\n        with:\n          pid: rest.pid\n          timeBucket: rest.timeBucket\n          period: rest.period\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analytics/live-visitors\n      name: live-visitors\n\
  \      description: Get currently active visitors\n      operations:\n      - method: GET\n        name: get-live-visitors\n        description: Get Live Visitors\n        call: swetrix-statistics.get-live-visitors\n        with:\n          pid: rest.pid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analytics/sessions\n      name: sessions\n      description: List visitor sessions\n      operations:\n      - method: GET\n        name: list-sessions\n        description: List Sessions\n        call: swetrix-statistics.list-sessions\n        with:\n          pid: rest.pid\n          period: rest.period\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analytics/funnels\n      name: funnels\n      description: Analyze conversion funnels\n      operations:\n      - method: GET\n        name: get-funnel-analysis\n        description: Get Funnel Analysis\n        call: swetrix-statistics.get-funnel-analysis\n\
  \        with:\n          pid: rest.pid\n          period: rest.period\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analytics/errors\n      name: errors\n      description: Query error statistics\n      operations:\n      - method: GET\n        name: list-errors\n        description: List Error Events\n        call: swetrix-statistics.list-errors\n        with:\n          pid: rest.pid\n          period: rest.period\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects\n      name: projects\n      description: Manage analytics projects\n      operations:\n      - method: GET\n        name: list-projects\n        description: List Projects\n        call: swetrix-admin.list-projects\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-project\n        description: Create Project\n        call: swetrix-admin.create-project\n        with:\n\
  \          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{id}\n      name: project-detail\n      description: Single project operations\n      operations:\n      - method: GET\n        name: get-project\n        description: Get Project\n        call: swetrix-admin.get-project\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-project\n        description: Delete Project\n        call: swetrix-admin.delete-project\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: swetrix-analytics-mcp\n    transport: http\n    description: MCP server for AI-assisted web analytics with Swetrix.\n    tools:\n    - name: record-pageview\n      description: Record a pageview event to Swetrix analytics\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: swetrix-events.record-pageview\n      with:\n        pid: tools.pid\n        pg: tools.pg\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: record-custom-event\n      description: Record a custom analytics event with optional metadata\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: swetrix-events.record-custom-event\n      with:\n        pid: tools.pid\n        ev: tools.ev\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: record-error\n      description: Record a JavaScript error event for dashboard aggregation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: swetrix-events.record-error\n      with:\n        pid: tools.pid\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: record-revenue\n\
  \      description: Record a revenue transaction (sale, refund, subscription)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: swetrix-events.record-revenue\n      with:\n        pid: tools.pid\n        type: tools.type\n        amount: tools.amount\n        currency: tools.currency\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-traffic-log\n      description: Query aggregated traffic data for a project by time bucket and period\n      hints:\n        readOnly: true\n        idempotent: true\n      call: swetrix-statistics.get-traffic-log\n      with:\n        pid: tools.pid\n        timeBucket: tools.timeBucket\n        period: tools.period\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-performance-metrics\n      description: Query frontend performance metrics including DNS, TLS, TTFB, and page load times\n      hints:\n        readOnly: true\n        idempotent:\
  \ true\n      call: swetrix-statistics.get-performance-metrics\n      with:\n        pid: tools.pid\n        timeBucket: tools.timeBucket\n        period: tools.period\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-live-visitors\n      description: Get currently active visitors with device, browser, OS, and country details\n      hints:\n        readOnly: true\n        idempotent: true\n      call: swetrix-statistics.get-live-visitors\n      with:\n        pid: tools.pid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-sessions\n      description: List individual visitor sessions with device and page details\n      hints:\n        readOnly: true\n        idempotent: true\n      call: swetrix-statistics.list-sessions\n      with:\n        pid: tools.pid\n        period: tools.period\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-funnel-analysis\n      description: Analyze conversion\
  \ rates across a sequence of pages in a funnel\n      hints:\n        readOnly: true\n        idempotent: true\n      call: swetrix-statistics.get-funnel-analysis\n      with:\n        pid: tools.pid\n        period: tools.period\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-errors\n      description: List JavaScript error groups with occurrence counts and affected sessions\n      hints:\n        readOnly: true\n        idempotent: true\n      call: swetrix-statistics.list-errors\n      with:\n        pid: tools.pid\n        period: tools.period\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-custom-events\n      description: Query custom event analytics grouped by time for named events\n      hints:\n        readOnly: true\n        idempotent: true\n      call: swetrix-statistics.get-custom-events\n      with:\n        pid: tools.pid\n        timeBucket: tools.timeBucket\n        period: tools.period\n      \
  \  customEvents: tools.customEvents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-projects\n      description: List all Swetrix analytics projects for the account\n      hints:\n        readOnly: true\n        idempotent: true\n      call: swetrix-admin.list-projects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-project\n      description: Create a new Swetrix analytics project\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: swetrix-admin.create-project\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-project\n      description: Get configuration and settings for a specific project\n      hints:\n        readOnly: true\n        idempotent: true\n      call: swetrix-admin.get-project\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: delete-project\n      description: Permanently delete a project and all associated analytics data\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: swetrix-admin.delete-project\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/swetrix/refs/heads/main/capabilities/web-analytics.yaml
tags:
- Analytics
- Custom Events
- Error Tracking
- GDPR Compliant
- Open Source
- Privacy
- Project Management
- Swetrix
- Traffic
- Web Analytics
tools:
- description: Record a pageview event to Swetrix analytics
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: record-pageview
- description: Record a custom analytics event with optional metadata
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: record-custom-event
- description: Record a JavaScript error event for dashboard aggregation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: record-error
- description: Record a revenue transaction (sale, refund, subscription)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: record-revenue
- description: Query aggregated traffic data for a project by time bucket and period
  hints:
    idempotent: true
    readOnly: true
  name: get-traffic-log
- description: Query frontend performance metrics including DNS, TLS, TTFB, and page load times
  hints:
    idempotent: true
    readOnly: true
  name: get-performance-metrics
- description: Get currently active visitors with device, browser, OS, and country details
  hints:
    idempotent: true
    readOnly: true
  name: get-live-visitors
- description: List individual visitor sessions with device and page details
  hints:
    idempotent: true
    readOnly: true
  name: list-sessions
- description: Analyze conversion rates across a sequence of pages in a funnel
  hints:
    idempotent: true
    readOnly: true
  name: get-funnel-analysis
- description: List JavaScript error groups with occurrence counts and affected sessions
  hints:
    idempotent: true
    readOnly: true
  name: list-errors
- description: Query custom event analytics grouped by time for named events
  hints:
    idempotent: true
    readOnly: true
  name: get-custom-events
- description: List all Swetrix analytics projects for the account
  hints:
    idempotent: true
    readOnly: true
  name: list-projects
- description: Create a new Swetrix analytics project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-project
- description: Get configuration and settings for a specific project
  hints:
    idempotent: true
    readOnly: true
  name: get-project
- description: Permanently delete a project and all associated analytics data
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-project
---
