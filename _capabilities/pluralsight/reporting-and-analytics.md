---
categories:
- analytics
consumed_apis:
- pluralsight-content-progress
- pluralsight-course-progress
- pluralsight-course-daily-usage
- pluralsight-reports-rest
description: Unified workflow for L&D managers to track learning progress, course completions, daily usage patterns, and generate reports. Combines content progress, course progress, course daily usage, and reports REST APIs.
layout: capability
name: Pluralsight Reporting And Analytics
operations:
- description: Track user progress across all content types
  method: POST
  name: query-content-progress
  path: /v1/content-progress
- description: Track user course progress and completion status
  method: POST
  name: query-course-progress
  path: /v1/course-progress
- description: Retrieve daily course engagement metrics
  method: POST
  name: query-course-daily-usage
  path: /v1/course-daily-usage
- description: Download a user report as CSV
  method: GET
  name: download-user-report
  path: /v1/user-reports
- description: Download a course completion report as CSV
  method: GET
  name: download-course-completion-report
  path: /v1/course-completion-reports
- description: Download a course usage report as CSV
  method: GET
  name: download-course-usage-report
  path: /v1/course-usage-reports
personas: []
provider_name: Pluralsight
provider_slug: pluralsight
search_terms:
- retrieve daily course engagement metrics
- download course completion report
- track user progress across all content types
- track user course progress including completion status and viewing history for video courses.
- analytics
- track user progress across all content types including videos, guides, paths, interactive courses, and projects.
- user course progress including completion status and viewing history
- learning
- course completion
- query course progress
- user progress across all content types including videos, guides, paths, and projects
- download user report
- download a course usage report as csv
- download course usage report
- download a course completion report as csv
- retrieve daily course engagement metrics and usage statistics.
- course completion reports as csv downloads (legacy rest, deprecated)
- download a user report as csv. deprecated - migrate to graphql.
- learning progress
- user reports as csv downloads (legacy rest, deprecated)
- education
- track user course progress and completion status
- engineering metrics
- daily course engagement metrics and usage statistics
- download a user report as csv
- course usage reports as csv downloads (legacy rest, deprecated)
- skills assessment
- download a course completion report as csv. deprecated - migrate to graphql.
- query content progress
- query course daily usage
- courses
- reporting
- pluralsight
- technology
- download a course usage report as csv. deprecated - migrate to graphql.
- video training
slug: reporting-and-analytics
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Pluralsight Reporting And Analytics\"\n  description: \"Unified workflow for L&D managers to track learning progress, course completions, daily usage patterns, and generate reports. Combines content progress, course progress, course daily usage, and reports REST APIs.\"\n  tags:\n    - Pluralsight\n    - Reporting\n    - Analytics\n    - Learning Progress\n    - Course Completion\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      PLURALSIGHT_BEARER_TOKEN: PLURALSIGHT_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: pluralsight-content-progress\n      location: ./shared/content-progress.yaml\n    - import: pluralsight-course-progress\n      location: ./shared/course-progress.yaml\n    - import: pluralsight-course-daily-usage\n      location: ./shared/course-daily-usage.yaml\n    - import: pluralsight-reports-rest\n      location: ./shared/reports-rest.yaml\n\n  exposes:\n\
  \    - type: rest\n      port: 8084\n      namespace: reporting-analytics-api\n      description: \"Unified REST API for Pluralsight reporting and analytics including learning progress, course completions, usage, and legacy reports.\"\n      resources:\n        - path: /v1/content-progress\n          name: content-progress\n          description: \"User progress across all content types including videos, guides, paths, and projects\"\n          operations:\n            - method: POST\n              name: query-content-progress\n              description: \"Track user progress across all content types\"\n              call: \"pluralsight-content-progress.query-content-progress\"\n              with:\n                query: \"rest.query\"\n                variables: \"rest.variables\"\n                operationName: \"rest.operationName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/course-progress\n          name:\
  \ course-progress\n          description: \"User course progress including completion status and viewing history\"\n          operations:\n            - method: POST\n              name: query-course-progress\n              description: \"Track user course progress and completion status\"\n              call: \"pluralsight-course-progress.query-course-progress\"\n              with:\n                query: \"rest.query\"\n                variables: \"rest.variables\"\n                operationName: \"rest.operationName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/course-daily-usage\n          name: course-daily-usage\n          description: \"Daily course engagement metrics and usage statistics\"\n          operations:\n            - method: POST\n              name: query-course-daily-usage\n              description: \"Retrieve daily course engagement metrics\"\n              call: \"pluralsight-course-daily-usage.query-course-daily-usage\"\
  \n              with:\n                query: \"rest.query\"\n                variables: \"rest.variables\"\n                operationName: \"rest.operationName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/user-reports\n          name: user-reports\n          description: \"User reports as CSV downloads (legacy REST, deprecated)\"\n          operations:\n            - method: GET\n              name: download-user-report\n              description: \"Download a user report as CSV\"\n              call: \"pluralsight-reports-rest.download-user-report\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/course-completion-reports\n          name: course-completion-reports\n          description: \"Course completion reports as CSV downloads (legacy REST, deprecated)\"\n          operations:\n            - method: GET\n              name: download-course-completion-report\n\
  \              description: \"Download a course completion report as CSV\"\n              call: \"pluralsight-reports-rest.download-course-completion-report\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/course-usage-reports\n          name: course-usage-reports\n          description: \"Course usage reports as CSV downloads (legacy REST, deprecated)\"\n          operations:\n            - method: GET\n              name: download-course-usage-report\n              description: \"Download a course usage report as CSV\"\n              call: \"pluralsight-reports-rest.download-course-usage-report\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9094\n      namespace: reporting-analytics-mcp\n      transport: http\n      description: \"MCP server for AI-assisted reporting and analytics across learning progress, course completions,\
  \ and usage data.\"\n      tools:\n        - name: query-content-progress\n          description: \"Track user progress across all content types including videos, guides, paths, interactive courses, and projects.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-content-progress.query-content-progress\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n            operationName: \"tools.operationName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-course-progress\n          description: \"Track user course progress including completion status and viewing history for video courses.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-course-progress.query-course-progress\"\
  \n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n            operationName: \"tools.operationName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-course-daily-usage\n          description: \"Retrieve daily course engagement metrics and usage statistics.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-course-daily-usage.query-course-daily-usage\"\n          with:\n            query: \"tools.query\"\n            variables: \"tools.variables\"\n            operationName: \"tools.operationName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: download-user-report\n          description: \"Download a user report as CSV. Deprecated - migrate to GraphQL.\"\n          hints:\n            readOnly: true\n\
  \            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-reports-rest.download-user-report\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: download-course-completion-report\n          description: \"Download a course completion report as CSV. Deprecated - migrate to GraphQL.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          call: \"pluralsight-reports-rest.download-course-completion-report\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: download-course-usage-report\n          description: \"Download a course usage report as CSV. Deprecated - migrate to GraphQL.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n        \
  \  call: \"pluralsight-reports-rest.download-course-usage-report\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/pluralsight/refs/heads/main/capabilities/reporting-and-analytics.yaml
tags:
- Pluralsight
- Reporting
- Analytics
- Learning Progress
- Course Completion
tools:
- description: Track user progress across all content types including videos, guides, paths, interactive courses, and projects.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-content-progress
- description: Track user course progress including completion status and viewing history for video courses.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-course-progress
- description: Retrieve daily course engagement metrics and usage statistics.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-course-daily-usage
- description: Download a user report as CSV. Deprecated - migrate to GraphQL.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: download-user-report
- description: Download a course completion report as CSV. Deprecated - migrate to GraphQL.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: download-course-completion-report
- description: Download a course usage report as CSV. Deprecated - migrate to GraphQL.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: download-course-usage-report
---
