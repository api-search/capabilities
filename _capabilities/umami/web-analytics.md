---
categories: []
consumed_apis: []
description: Web analytics workflow for tracking website performance, visitor behavior, and real-time data using Umami's privacy-first analytics platform.
layout: capability
name: Umami Web Analytics
operations:
- description: List all tracked websites
  method: GET
  name: list-websites
  path: /v1/websites
- description: Get website analytics statistics
  method: GET
  name: get-stats
  path: /v1/websites/{websiteId}/stats
- description: Get metrics by dimension
  method: GET
  name: get-metrics
  path: /v1/websites/{websiteId}/metrics
personas: []
provider_name: Umami
provider_slug: umami
search_terms:
- custom event collection and analysis
- get active visitors
- cookieless tracking
- get website stats
- accessing and analyzing website statistics, metrics, and pageviews
- get analytics metrics broken down by a dimension such as url, browser, country, device, or referrer
- website analytics
- track website performance, visitor behavior, and real-time analytics
- get metrics
- reviews overall analytics and manages website configuration
- analytics
- umami
- get website pageviews
- website metrics by dimension
- monitors site performance, integrates tracking, and manages websites
- list teams
- dashboards
- list all websites being tracked in umami
- get pageview time series data for a website bucketed by time unit
- get summarized analytics statistics for a website including pageviews, visitors, visits, and bounce rate
- get website analytics statistics
- exports and analyzes raw session and event data for bi reporting
- get metrics by dimension
- analyzes website traffic, referrers, and campaign performance
- list sessions
- open source
- get website metrics
- web analytics
- website listings
- list websites
- website statistics
- user account management (self-hosted admin only)
- list all tracked websites
- list visitor sessions for a website with browser, os, device, and country details
- managing tracked websites, their configuration, and team access
- get the number of visitors currently active on a website
- list all teams in umami
- get stats
- privacy
- session data, active visitors, and behavioral tracking
slug: web-analytics
source_filename: web-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Umami Web Analytics\"\n  description: \"Web analytics workflow for tracking website performance, visitor behavior, and real-time data using Umami's privacy-first analytics platform.\"\n  tags:\n    - Umami\n    - Analytics\n    - Web Analytics\n    - Privacy\n    - Dashboards\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n  personas:\n    - Marketing Analyst\n    - Web Developer\n    - Site Owner\n    - Data Analyst\n\nimports:\n  - url: shared/umami.yaml\n    namespace: umami\n\ncapability:\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: web-analytics-api\n      resources:\n        - path: /v1/websites\n          name: websites\n          description: \"Website listings\"\n          operations:\n            - method: GET\n              name: list-websites\n              description: \"List all tracked websites\"\n              call: \"umami.list-websites\"\n              outputParameters:\n         \
  \       - type: object\n                  mapping: \"$.\"\n        - path: /v1/websites/{websiteId}/stats\n          name: stats\n          description: \"Website statistics\"\n          operations:\n            - method: GET\n              name: get-stats\n              description: \"Get website analytics statistics\"\n              call: \"umami.get-website-stats\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/websites/{websiteId}/metrics\n          name: metrics\n          description: \"Website metrics by dimension\"\n          operations:\n            - method: GET\n              name: get-metrics\n              description: \"Get metrics by dimension\"\n              call: \"umami.get-website-metrics\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9080\n      namespace: web-analytics-mcp\n      transport: http\n      tools:\n\
  \        - name: list-websites\n          description: \"List all websites being tracked in Umami\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"umami.list-websites\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-website-stats\n          description: \"Get summarized analytics statistics for a website including pageviews, visitors, visits, and bounce rate\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"umami.get-website-stats\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-website-pageviews\n          description: \"Get pageview time series data for a website bucketed by time unit\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"umami.get-website-pageviews\"\n          outputParameters:\n            - type: object\n    \
  \          mapping: \"$.\"\n        - name: get-website-metrics\n          description: \"Get analytics metrics broken down by a dimension such as URL, browser, country, device, or referrer\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"umami.get-website-metrics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-active-visitors\n          description: \"Get the number of visitors currently active on a website\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"umami.get-active-visitors\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-sessions\n          description: \"List visitor sessions for a website with browser, OS, device, and country details\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"umami.list-sessions\"\n       \
  \   outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-teams\n          description: \"List all teams in Umami\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"umami.list-teams\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/umami/refs/heads/main/capabilities/web-analytics.yaml
tags:
- Umami
- Analytics
- Web Analytics
- Privacy
- Dashboards
tools:
- description: List all websites being tracked in Umami
  hints:
    openWorld: true
    readOnly: true
  name: list-websites
- description: Get summarized analytics statistics for a website including pageviews, visitors, visits, and bounce rate
  hints:
    openWorld: true
    readOnly: true
  name: get-website-stats
- description: Get pageview time series data for a website bucketed by time unit
  hints:
    openWorld: true
    readOnly: true
  name: get-website-pageviews
- description: Get analytics metrics broken down by a dimension such as URL, browser, country, device, or referrer
  hints:
    openWorld: true
    readOnly: true
  name: get-website-metrics
- description: Get the number of visitors currently active on a website
  hints:
    openWorld: true
    readOnly: true
  name: get-active-visitors
- description: List visitor sessions for a website with browser, OS, device, and country details
  hints:
    openWorld: true
    readOnly: true
  name: list-sessions
- description: List all teams in Umami
  hints:
    openWorld: true
    readOnly: true
  name: list-teams
---
