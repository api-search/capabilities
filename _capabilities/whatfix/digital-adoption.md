---
categories: []
consumed_apis: []
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
- get analytics for self help widget showing which content users search for and view.
- get a report of the most popular flows to understand what guidance users engage with most.
- get most popular flows
- list all user segments.
- list all end users tracked in whatfix for adoption monitoring.
- analytics
- list all whatfix content items including flows, tooltips, task lists, and surveys.
- list segments
- upsert end user
- user segmentation
- saas management
- list all end users tracked in whatfix.
- get flow views, completions, and completion rates.
- get task list completion status for each end user.
- end user tracking and segmentation.
- self help widget content analytics.
- content management
- get end user engagement
- sync an end user into whatfix with segmentation attributes from your identity system.
- change management
- get flow analytics
- get task list completion status for onboarding or training tracking per user.
- get self help analytics
- get self help content view counts.
- download most popular flows report in json or csv.
- onboarding
- get user task completion
- user onboarding
- get flow analytics showing views, completions, and completion rates for a date range.
- flow performance analytics.
- list content
- get content engagement broken down by end user.
- whatfix content items (flows, tooltips, task lists).
- user segments for content targeting.
- get end user engagement analytics showing content interactions per user.
- list end users
- task list completion analytics per user.
- list all user segments defined for content targeting and personalization.
- digital adoption
- end user engagement analytics.
- most popular flows report.
- create or update an end user with segmentation attributes.
- list all content items with optional type and status filters.
- in-app guidance
slug: digital-adoption
source_filename: digital-adoption.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Whatfix Digital Adoption\n  description: Unified digital adoption platform capability composing Whatfix's end-user management, content management, analytics,\n    and segmentation APIs into customer-facing workflows for adoption monitoring, onboarding analytics, and content governance.\n  tags:\n  - Digital Adoption\n  - Analytics\n  - Onboarding\n  - Content Management\n  - User Segmentation\n  - Change Management\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WHATFIX_API_TOKEN: WHATFIX_API_TOKEN\n    WHATFIX_ACCOUNT_ID: WHATFIX_ACCOUNT_ID\n    WHATFIX_USER_EMAIL: WHATFIX_USER_EMAIL\ncapability:\n  consumes:\n  - type: http\n    namespace: whatfix\n    baseUri: https://whatfix.com/api/v1\n    description: Whatfix REST API v1 for digital adoption platform management.\n    authentication:\n      type: apikey\n      key: x-whatfix-integration-key\n      value: '{{WHATFIX_API_TOKEN}}'\n      placement:\
  \ header\n    resources:\n    - name: end-users\n      path: /{{WHATFIX_ACCOUNT_ID}}/end-users\n      description: Manage and query end users tracked by Whatfix.\n      operations:\n      - name: list-end-users\n        method: GET\n        description: Returns a paginated list of all end users tracked in the Whatfix platform.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Results per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: upsert-end-user\n        method: PUT\n        description: Creates or updates an end user record with custom segmentation attributes.\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n\
  \          required: true\n          description: Unique identifier for the end user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            userId: '{{tools.userId}}'\n            email: '{{tools.email}}'\n            name: '{{tools.name}}'\n            attributes: '{{tools.attributes}}'\n    - name: content\n      path: /{{WHATFIX_ACCOUNT_ID}}/content\n      description: Manage Whatfix content items including flows, tooltips, task lists, and more.\n      operations:\n      - name: list-content\n        method: GET\n        description: Returns a paginated list of all content items for the account.\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Filter by content type.\n        - name: status\n          in: query\n          type: string\n          required:\
  \ false\n          description: Filter by content status.\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics-flows\n      path: /{{WHATFIX_ACCOUNT_ID}}/analytics/flows\n      description: Flow analytics including views, completions, and completion rates.\n      operations:\n      - name: get-flow-analytics\n        method: GET\n        description: Returns analytics data for all flows for the specified date range.\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date (ISO 8601).\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description:\
  \ End date (ISO 8601).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics-end-users\n      path: /{{WHATFIX_ACCOUNT_ID}}/analytics/end-users\n      description: End user engagement analytics.\n      operations:\n      - name: get-end-user-engagement\n        method: GET\n        description: Returns engagement analytics broken down by end user.\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n          required: false\n        - name: endDate\n          in: query\n          type: string\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ analytics-self-help\n      path: /{{WHATFIX_ACCOUNT_ID}}/analytics/self-help\n      description: Self Help widget content analytics.\n      operations:\n      - name: get-self-help-analytics\n        method: GET\n        description: Returns analytics for Self Help widget content views.\n        inputParameters:\n        - name: startDate\n          in: query\n          type: string\n          required: false\n        - name: endDate\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics-task-completion\n      path: /{{WHATFIX_ACCOUNT_ID}}/analytics/task-completion\n      description: Task list completion status per user.\n      operations:\n      - name: get-user-task-completion\n        method: GET\n        description: Returns task list completion status for each end user.\n        inputParameters:\n        - name: startDate\n\
  \          in: query\n          type: string\n          required: false\n        - name: endDate\n          in: query\n          type: string\n          required: false\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports\n      path: /{{WHATFIX_ACCOUNT_ID}}/reports/summary/mostPopularFlows\n      description: Report downloads for analytics data.\n      operations:\n      - name: get-most-popular-flows\n        method: GET\n        description: Downloads a report of the most popular flows ranked by view count.\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Output format: json or csv.'\n        - name: startDate\n\
  \          in: query\n          type: string\n          required: false\n        - name: endDate\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: segments\n      path: /{{WHATFIX_ACCOUNT_ID}}/segments\n      description: User segments for content targeting.\n      operations:\n      - name: list-segments\n        method: GET\n        description: Returns all user segments defined in the Whatfix account.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: digital-adoption-api\n\
  \    description: Unified REST API for digital adoption monitoring, user management, and analytics.\n    resources:\n    - path: /v1/end-users\n      name: end-users\n      description: End user tracking and segmentation.\n      operations:\n      - method: GET\n        name: list-end-users\n        description: List all end users tracked in Whatfix.\n        call: whatfix.list-end-users\n        with:\n          page: rest.page\n          pageSize: rest.pageSize\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: upsert-end-user\n        description: Create or update an end user with segmentation attributes.\n        call: whatfix.upsert-end-user\n        with:\n          userId: rest.userId\n          email: rest.email\n          name: rest.name\n          attributes: rest.attributes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/content\n      name: content\n      description: Whatfix\
  \ content items (flows, tooltips, task lists).\n      operations:\n      - method: GET\n        name: list-content\n        description: List all content items with optional type and status filters.\n        call: whatfix.list-content\n        with:\n          type: rest.type\n          status: rest.status\n          page: rest.page\n          pageSize: rest.pageSize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/segments\n      name: segments\n      description: User segments for content targeting.\n      operations:\n      - method: GET\n        name: list-segments\n        description: List all user segments.\n        call: whatfix.list-segments\n        with:\n          page: rest.page\n          pageSize: rest.pageSize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analytics/flows\n      name: flow-analytics\n      description: Flow performance analytics.\n      operations:\n      - method: GET\n\
  \        name: get-flow-analytics\n        description: Get flow views, completions, and completion rates.\n        call: whatfix.get-flow-analytics\n        with:\n          startDate: rest.startDate\n          endDate: rest.endDate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analytics/end-users\n      name: user-engagement\n      description: End user engagement analytics.\n      operations:\n      - method: GET\n        name: get-end-user-engagement\n        description: Get content engagement broken down by end user.\n        call: whatfix.get-end-user-engagement\n        with:\n          startDate: rest.startDate\n          endDate: rest.endDate\n          page: rest.page\n          pageSize: rest.pageSize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analytics/self-help\n      name: self-help-analytics\n      description: Self Help widget content analytics.\n      operations:\n      - method:\
  \ GET\n        name: get-self-help-analytics\n        description: Get Self Help content view counts.\n        call: whatfix.get-self-help-analytics\n        with:\n          startDate: rest.startDate\n          endDate: rest.endDate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analytics/task-completion\n      name: task-completion\n      description: Task list completion analytics per user.\n      operations:\n      - method: GET\n        name: get-user-task-completion\n        description: Get task list completion status for each end user.\n        call: whatfix.get-user-task-completion\n        with:\n          startDate: rest.startDate\n          endDate: rest.endDate\n          page: rest.page\n          pageSize: rest.pageSize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports/popular-flows\n      name: popular-flows-report\n      description: Most popular flows report.\n      operations:\n\
  \      - method: GET\n        name: get-most-popular-flows\n        description: Download most popular flows report in JSON or CSV.\n        call: whatfix.get-most-popular-flows\n        with:\n          format: rest.format\n          startDate: rest.startDate\n          endDate: rest.endDate\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: digital-adoption-mcp\n    transport: http\n    description: MCP server for AI-assisted digital adoption monitoring and content management.\n    tools:\n    - name: list-end-users\n      description: List all end users tracked in Whatfix for adoption monitoring.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: whatfix.list-end-users\n      with:\n        page: tools.page\n        pageSize: tools.pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: upsert-end-user\n      description: Sync an end user into Whatfix with\
  \ segmentation attributes from your identity system.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: whatfix.upsert-end-user\n      with:\n        userId: tools.userId\n        email: tools.email\n        name: tools.name\n        attributes: tools.attributes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-content\n      description: List all Whatfix content items including flows, tooltips, task lists, and surveys.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: whatfix.list-content\n      with:\n        type: tools.type\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-segments\n      description: List all user segments defined for content targeting and personalization.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: whatfix.list-segments\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: get-flow-analytics\n      description: Get flow analytics showing views, completions, and completion rates for a date range.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: whatfix.get-flow-analytics\n      with:\n        startDate: tools.startDate\n        endDate: tools.endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-end-user-engagement\n      description: Get end user engagement analytics showing content interactions per user.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: whatfix.get-end-user-engagement\n      with:\n        startDate: tools.startDate\n        endDate: tools.endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-self-help-analytics\n      description: Get analytics for Self Help widget showing which content users search for and view.\n      hints:\n        readOnly: true\n        openWorld: false\n      call:\
  \ whatfix.get-self-help-analytics\n      with:\n        startDate: tools.startDate\n        endDate: tools.endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user-task-completion\n      description: Get task list completion status for onboarding or training tracking per user.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: whatfix.get-user-task-completion\n      with:\n        startDate: tools.startDate\n        endDate: tools.endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-most-popular-flows\n      description: Get a report of the most popular flows to understand what guidance users engage with most.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: whatfix.get-most-popular-flows\n      with:\n        startDate: tools.startDate\n        endDate: tools.endDate\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
