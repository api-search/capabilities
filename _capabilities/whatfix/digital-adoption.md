---
categories: []
consumed_apis:
- whatfix
description: Unified digital adoption platform capability composing Whatfix's end-user management, content management, analytics, and segmentation APIs into customer-facing workflows for adoption monitoring, onboarding analytics, and content governance.
layout: capability
name: Whatfix Digital Adoption
operations:
- description: List all end users tracked in Whatfix.
  method: GET
  name: list-end-users
  path: /v1/end-users
- description: Create or update an end user with segmentation attributes.
  method: PUT
  name: upsert-end-user
  path: /v1/end-users
- description: List all content items with optional type and status filters.
  method: GET
  name: list-content
  path: /v1/content
- description: List all user segments.
  method: GET
  name: list-segments
  path: /v1/segments
- description: Get flow views, completions, and completion rates.
  method: GET
  name: get-flow-analytics
  path: /v1/analytics/flows
- description: Get content engagement broken down by end user.
  method: GET
  name: get-end-user-engagement
  path: /v1/analytics/end-users
- description: Get Self Help content view counts.
  method: GET
  name: get-self-help-analytics
  path: /v1/analytics/self-help
- description: Get task list completion status for each end user.
  method: GET
  name: get-user-task-completion
  path: /v1/analytics/task-completion
- description: Download most popular flows report in JSON or CSV.
  method: GET
  name: get-most-popular-flows
  path: /v1/reports/popular-flows
personas: []
provider_name: Whatfix
provider_slug: whatfix
search_terms:
- get flow views, completions, and completion rates.
- in-app guidance
- get analytics for self help widget showing which content users search for and view.
- analytics
- content management
- list segments
- get end user engagement
- get end user engagement analytics showing content interactions per user.
- end user engagement analytics.
- download most popular flows report in json or csv.
- saas management
- list content
- list all user segments defined for content targeting and personalization.
- whatfix content items (flows, tooltips, task lists).
- end user tracking and segmentation.
- get most popular flows
- change management
- list all end users tracked in whatfix for adoption monitoring.
- list all whatfix content items including flows, tooltips, task lists, and surveys.
- user segments for content targeting.
- onboarding
- get flow analytics showing views, completions, and completion rates for a date range.
- most popular flows report.
- user onboarding
- create or update an end user with segmentation attributes.
- user segmentation
- list end users
- get self help analytics
- get self help content view counts.
- get a report of the most popular flows to understand what guidance users engage with most.
- get task list completion status for each end user.
- list all end users tracked in whatfix.
- task list completion analytics per user.
- get content engagement broken down by end user.
- flow performance analytics.
- self help widget content analytics.
- digital adoption
- get flow analytics
- sync an end user into whatfix with segmentation attributes from your identity system.
- upsert end user
- list all content items with optional type and status filters.
- list all user segments.
- get task list completion status for onboarding or training tracking per user.
- get user task completion
slug: digital-adoption
source_filename: digital-adoption.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Whatfix Digital Adoption\"\n  description: >-\n    Unified digital adoption platform capability composing Whatfix's end-user management,\n    content management, analytics, and segmentation APIs into customer-facing workflows\n    for adoption monitoring, onboarding analytics, and content governance.\n  tags:\n    - Digital Adoption\n    - Analytics\n    - Onboarding\n    - Content Management\n    - User Segmentation\n    - Change Management\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WHATFIX_API_TOKEN: WHATFIX_API_TOKEN\n      WHATFIX_ACCOUNT_ID: WHATFIX_ACCOUNT_ID\n      WHATFIX_USER_EMAIL: WHATFIX_USER_EMAIL\n\ncapability:\n  consumes:\n    - import: whatfix\n      location: ./shared/whatfix-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: digital-adoption-api\n      description: \"Unified REST API for digital adoption monitoring, user management,\
  \ and analytics.\"\n      resources:\n        - path: /v1/end-users\n          name: end-users\n          description: \"End user tracking and segmentation.\"\n          operations:\n            - method: GET\n              name: list-end-users\n              description: \"List all end users tracked in Whatfix.\"\n              call: \"whatfix.list-end-users\"\n              with:\n                page: \"rest.page\"\n                pageSize: \"rest.pageSize\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: upsert-end-user\n              description: \"Create or update an end user with segmentation attributes.\"\n              call: \"whatfix.upsert-end-user\"\n              with:\n                userId: \"rest.userId\"\n                email: \"rest.email\"\n                name: \"rest.name\"\n                attributes: \"rest.attributes\"\n              outputParameters:\n       \
  \         - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/content\n          name: content\n          description: \"Whatfix content items (flows, tooltips, task lists).\"\n          operations:\n            - method: GET\n              name: list-content\n              description: \"List all content items with optional type and status filters.\"\n              call: \"whatfix.list-content\"\n              with:\n                type: \"rest.type\"\n                status: \"rest.status\"\n                page: \"rest.page\"\n                pageSize: \"rest.pageSize\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/segments\n          name: segments\n          description: \"User segments for content targeting.\"\n          operations:\n            - method: GET\n              name: list-segments\n              description: \"List all user segments.\"\n              call: \"whatfix.list-segments\"\
  \n              with:\n                page: \"rest.page\"\n                pageSize: \"rest.pageSize\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/analytics/flows\n          name: flow-analytics\n          description: \"Flow performance analytics.\"\n          operations:\n            - method: GET\n              name: get-flow-analytics\n              description: \"Get flow views, completions, and completion rates.\"\n              call: \"whatfix.get-flow-analytics\"\n              with:\n                startDate: \"rest.startDate\"\n                endDate: \"rest.endDate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/analytics/end-users\n          name: user-engagement\n          description: \"End user engagement analytics.\"\n          operations:\n            - method: GET\n              name: get-end-user-engagement\n \
  \             description: \"Get content engagement broken down by end user.\"\n              call: \"whatfix.get-end-user-engagement\"\n              with:\n                startDate: \"rest.startDate\"\n                endDate: \"rest.endDate\"\n                page: \"rest.page\"\n                pageSize: \"rest.pageSize\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/analytics/self-help\n          name: self-help-analytics\n          description: \"Self Help widget content analytics.\"\n          operations:\n            - method: GET\n              name: get-self-help-analytics\n              description: \"Get Self Help content view counts.\"\n              call: \"whatfix.get-self-help-analytics\"\n              with:\n                startDate: \"rest.startDate\"\n                endDate: \"rest.endDate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\
  \n\n        - path: /v1/analytics/task-completion\n          name: task-completion\n          description: \"Task list completion analytics per user.\"\n          operations:\n            - method: GET\n              name: get-user-task-completion\n              description: \"Get task list completion status for each end user.\"\n              call: \"whatfix.get-user-task-completion\"\n              with:\n                startDate: \"rest.startDate\"\n                endDate: \"rest.endDate\"\n                page: \"rest.page\"\n                pageSize: \"rest.pageSize\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/reports/popular-flows\n          name: popular-flows-report\n          description: \"Most popular flows report.\"\n          operations:\n            - method: GET\n              name: get-most-popular-flows\n              description: \"Download most popular flows report in JSON or CSV.\"\n \
  \             call: \"whatfix.get-most-popular-flows\"\n              with:\n                format: \"rest.format\"\n                startDate: \"rest.startDate\"\n                endDate: \"rest.endDate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: digital-adoption-mcp\n      transport: http\n      description: \"MCP server for AI-assisted digital adoption monitoring and content management.\"\n      tools:\n        - name: list-end-users\n          description: \"List all end users tracked in Whatfix for adoption monitoring.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"whatfix.list-end-users\"\n          with:\n            page: \"tools.page\"\n            pageSize: \"tools.pageSize\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: upsert-end-user\n          description:\
  \ \"Sync an end user into Whatfix with segmentation attributes from your identity system.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"whatfix.upsert-end-user\"\n          with:\n            userId: \"tools.userId\"\n            email: \"tools.email\"\n            name: \"tools.name\"\n            attributes: \"tools.attributes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-content\n          description: \"List all Whatfix content items including flows, tooltips, task lists, and surveys.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"whatfix.list-content\"\n          with:\n            type: \"tools.type\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-segments\n          description: \"List all user segments defined\
  \ for content targeting and personalization.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"whatfix.list-segments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-flow-analytics\n          description: \"Get flow analytics showing views, completions, and completion rates for a date range.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"whatfix.get-flow-analytics\"\n          with:\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-end-user-engagement\n          description: \"Get end user engagement analytics showing content interactions per user.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"whatfix.get-end-user-engagement\"\n       \
  \   with:\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-self-help-analytics\n          description: \"Get analytics for Self Help widget showing which content users search for and view.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"whatfix.get-self-help-analytics\"\n          with:\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-user-task-completion\n          description: \"Get task list completion status for onboarding or training tracking per user.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"whatfix.get-user-task-completion\"\n          with:\n            startDate: \"tools.startDate\"\n  \
  \          endDate: \"tools.endDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-most-popular-flows\n          description: \"Get a report of the most popular flows to understand what guidance users engage with most.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"whatfix.get-most-popular-flows\"\n          with:\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/whatfix/refs/heads/main/capabilities/digital-adoption.yaml
tags:
- Digital Adoption
- Analytics
- Onboarding
- Content Management
- User Segmentation
- Change Management
tools:
- description: List all end users tracked in Whatfix for adoption monitoring.
  hints:
    openWorld: true
    readOnly: true
  name: list-end-users
- description: Sync an end user into Whatfix with segmentation attributes from your identity system.
  hints:
    idempotent: true
    readOnly: false
  name: upsert-end-user
- description: List all Whatfix content items including flows, tooltips, task lists, and surveys.
  hints:
    openWorld: true
    readOnly: true
  name: list-content
- description: List all user segments defined for content targeting and personalization.
  hints:
    openWorld: true
    readOnly: true
  name: list-segments
- description: Get flow analytics showing views, completions, and completion rates for a date range.
  hints:
    openWorld: false
    readOnly: true
  name: get-flow-analytics
- description: Get end user engagement analytics showing content interactions per user.
  hints:
    openWorld: false
    readOnly: true
  name: get-end-user-engagement
- description: Get analytics for Self Help widget showing which content users search for and view.
  hints:
    openWorld: false
    readOnly: true
  name: get-self-help-analytics
- description: Get task list completion status for onboarding or training tracking per user.
  hints:
    openWorld: false
    readOnly: true
  name: get-user-task-completion
- description: Get a report of the most popular flows to understand what guidance users engage with most.
  hints:
    openWorld: false
    readOnly: true
  name: get-most-popular-flows
---
