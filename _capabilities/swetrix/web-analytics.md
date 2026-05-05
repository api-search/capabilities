---
categories: []
consumed_apis:
- swetrix-events
- swetrix-statistics
- swetrix-admin
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
- get performance metrics
- analyze conversion funnels
- query frontend performance metrics including dns, tls, ttfb, and page load times
- analyze conversion rates across a sequence of pages in a funnel
- get currently active visitors with device, browser, os, and country details
- record error event
- record pageview
- gdpr compliant
- web analytics
- record revenue
- open source
- create a new swetrix analytics project
- analytics
- traffic
- record a revenue transaction (sale, refund, subscription)
- record javascript error events
- query traffic analytics
- list individual visitor sessions with device and page details
- error tracking
- get traffic log
- custom events
- permanently delete a project and all associated analytics data
- list projects
- query custom event analytics grouped by time for named events
- get custom events
- record custom events
- get currently active visitors
- record a javascript error event for dashboard aggregation
- swetrix
- record pageview events
- get configuration and settings for a specific project
- query error statistics
- list errors
- list error events
- single project operations
- get funnel analysis
- query performance metrics
- manage analytics projects
- list visitor sessions
- delete project
- project management
- list sessions
- list all swetrix analytics projects for the account
- list javascript error groups with occurrence counts and affected sessions
- cookieless tracking
- real-time analytics
- record a pageview event to swetrix analytics
- get live visitors
- record custom event
- record pageview event
- create project
- get project
- record a custom analytics event with optional metadata
- query aggregated traffic data for a project by time bucket and period
- privacy
- record error
slug: web-analytics
source_filename: web-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Swetrix Web Analytics\"\n  description: >-\n    Unified web analytics capability combining Swetrix Events, Statistics, and\n    Admin APIs. Enables product teams and developers to track user behavior,\n    analyze traffic patterns, manage analytics projects, and monitor errors\n    in a privacy-first, cookieless analytics environment.\n  tags:\n    - Analytics\n    - Custom Events\n    - Error Tracking\n    - GDPR Compliant\n    - Open Source\n    - Privacy\n    - Project Management\n    - Swetrix\n    - Traffic\n    - Web Analytics\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      SWETRIX_API_KEY: SWETRIX_API_KEY\n\ncapability:\n  consumes:\n    - import: swetrix-events\n      location: ./shared/swetrix-events.yaml\n    - import: swetrix-statistics\n      location: ./shared/swetrix-statistics.yaml\n    - import: swetrix-admin\n      location: ./shared/swetrix-admin.yaml\n\n\
  \  exposes:\n    - type: rest\n      port: 8080\n      namespace: swetrix-analytics-api\n      description: \"Unified REST API for Swetrix web analytics management and querying.\"\n      resources:\n        # Event Tracking\n        - path: /v1/events/pageviews\n          name: pageviews\n          description: \"Record pageview events\"\n          operations:\n            - method: POST\n              name: record-pageview\n              description: \"Record Pageview Event\"\n              call: \"swetrix-events.record-pageview\"\n              with:\n                pid: \"rest.pid\"\n                pg: \"rest.pg\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/events/custom\n          name: custom-events\n          description: \"Record custom events\"\n          operations:\n            - method: POST\n              name: record-custom-event\n              description: \"Record Custom Event\"\n          \
  \    call: \"swetrix-events.record-custom-event\"\n              with:\n                pid: \"rest.pid\"\n                ev: \"rest.ev\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/events/errors\n          name: error-events\n          description: \"Record JavaScript error events\"\n          operations:\n            - method: POST\n              name: record-error\n              description: \"Record Error Event\"\n              call: \"swetrix-events.record-error\"\n              with:\n                pid: \"rest.pid\"\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # Statistics & Analytics\n        - path: /v1/analytics/traffic\n          name: traffic\n          description: \"Query traffic analytics\"\n          operations:\n            - method: GET\n              name: get-traffic-log\n            \
  \  description: \"Get Traffic Log\"\n              call: \"swetrix-statistics.get-traffic-log\"\n              with:\n                pid: \"rest.pid\"\n                timeBucket: \"rest.timeBucket\"\n                period: \"rest.period\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/analytics/performance\n          name: performance\n          description: \"Query performance metrics\"\n          operations:\n            - method: GET\n              name: get-performance-metrics\n              description: \"Get Performance Metrics\"\n              call: \"swetrix-statistics.get-performance-metrics\"\n              with:\n                pid: \"rest.pid\"\n                timeBucket: \"rest.timeBucket\"\n                period: \"rest.period\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/analytics/live-visitors\n          name: live-visitors\n\
  \          description: \"Get currently active visitors\"\n          operations:\n            - method: GET\n              name: get-live-visitors\n              description: \"Get Live Visitors\"\n              call: \"swetrix-statistics.get-live-visitors\"\n              with:\n                pid: \"rest.pid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/analytics/sessions\n          name: sessions\n          description: \"List visitor sessions\"\n          operations:\n            - method: GET\n              name: list-sessions\n              description: \"List Sessions\"\n              call: \"swetrix-statistics.list-sessions\"\n              with:\n                pid: \"rest.pid\"\n                period: \"rest.period\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/analytics/funnels\n          name: funnels\n          description:\
  \ \"Analyze conversion funnels\"\n          operations:\n            - method: GET\n              name: get-funnel-analysis\n              description: \"Get Funnel Analysis\"\n              call: \"swetrix-statistics.get-funnel-analysis\"\n              with:\n                pid: \"rest.pid\"\n                period: \"rest.period\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/analytics/errors\n          name: errors\n          description: \"Query error statistics\"\n          operations:\n            - method: GET\n              name: list-errors\n              description: \"List Error Events\"\n              call: \"swetrix-statistics.list-errors\"\n              with:\n                pid: \"rest.pid\"\n                period: \"rest.period\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # Project Management\n        - path: /v1/projects\n\
  \          name: projects\n          description: \"Manage analytics projects\"\n          operations:\n            - method: GET\n              name: list-projects\n              description: \"List Projects\"\n              call: \"swetrix-admin.list-projects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-project\n              description: \"Create Project\"\n              call: \"swetrix-admin.create-project\"\n              with:\n                name: \"rest.name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{id}\n          name: project-detail\n          description: \"Single project operations\"\n          operations:\n            - method: GET\n              name: get-project\n              description: \"Get Project\"\n              call: \"swetrix-admin.get-project\"\n          \
  \    with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-project\n              description: \"Delete Project\"\n              call: \"swetrix-admin.delete-project\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: swetrix-analytics-mcp\n      transport: http\n      description: \"MCP server for AI-assisted web analytics with Swetrix.\"\n      tools:\n        # Event Tracking\n        - name: record-pageview\n          description: \"Record a pageview event to Swetrix analytics\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"swetrix-events.record-pageview\"\n          with:\n            pid: \"tools.pid\"\
  \n            pg: \"tools.pg\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: record-custom-event\n          description: \"Record a custom analytics event with optional metadata\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"swetrix-events.record-custom-event\"\n          with:\n            pid: \"tools.pid\"\n            ev: \"tools.ev\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: record-error\n          description: \"Record a JavaScript error event for dashboard aggregation\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"swetrix-events.record-error\"\n          with:\n            pid: \"tools.pid\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n       \
  \       mapping: \"$.\"\n\n        - name: record-revenue\n          description: \"Record a revenue transaction (sale, refund, subscription)\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"swetrix-events.record-revenue\"\n          with:\n            pid: \"tools.pid\"\n            type: \"tools.type\"\n            amount: \"tools.amount\"\n            currency: \"tools.currency\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        # Statistics\n        - name: get-traffic-log\n          description: \"Query aggregated traffic data for a project by time bucket and period\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"swetrix-statistics.get-traffic-log\"\n          with:\n            pid: \"tools.pid\"\n            timeBucket: \"tools.timeBucket\"\n            period: \"tools.period\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: get-performance-metrics\n          description: \"Query frontend performance metrics including DNS, TLS, TTFB, and page load times\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"swetrix-statistics.get-performance-metrics\"\n          with:\n            pid: \"tools.pid\"\n            timeBucket: \"tools.timeBucket\"\n            period: \"tools.period\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-live-visitors\n          description: \"Get currently active visitors with device, browser, OS, and country details\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"swetrix-statistics.get-live-visitors\"\n          with:\n            pid: \"tools.pid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name:\
  \ list-sessions\n          description: \"List individual visitor sessions with device and page details\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"swetrix-statistics.list-sessions\"\n          with:\n            pid: \"tools.pid\"\n            period: \"tools.period\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-funnel-analysis\n          description: \"Analyze conversion rates across a sequence of pages in a funnel\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"swetrix-statistics.get-funnel-analysis\"\n          with:\n            pid: \"tools.pid\"\n            period: \"tools.period\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-errors\n          description: \"List JavaScript error groups with occurrence counts and affected sessions\"\n          hints:\n\
  \            readOnly: true\n            idempotent: true\n          call: \"swetrix-statistics.list-errors\"\n          with:\n            pid: \"tools.pid\"\n            period: \"tools.period\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-custom-events\n          description: \"Query custom event analytics grouped by time for named events\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"swetrix-statistics.get-custom-events\"\n          with:\n            pid: \"tools.pid\"\n            timeBucket: \"tools.timeBucket\"\n            period: \"tools.period\"\n            customEvents: \"tools.customEvents\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        # Project Management\n        - name: list-projects\n          description: \"List all Swetrix analytics projects for the account\"\n          hints:\n            readOnly:\
  \ true\n            idempotent: true\n          call: \"swetrix-admin.list-projects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-project\n          description: \"Create a new Swetrix analytics project\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"swetrix-admin.create-project\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-project\n          description: \"Get configuration and settings for a specific project\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"swetrix-admin.get-project\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-project\n          description:\
  \ \"Permanently delete a project and all associated analytics data\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"swetrix-admin.delete-project\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
