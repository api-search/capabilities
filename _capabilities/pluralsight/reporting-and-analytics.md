---
api_specs:
- filename: content-progress.yml
  format: yaml
  label: pluralsight-content-progress
  slug: pluralsight-content-progress
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/pluralsight/refs/heads/main/openapi/content-progress.yml
- filename: course-progress.yml
  format: yaml
  label: pluralsight-course-progress
  slug: pluralsight-course-progress
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/pluralsight/refs/heads/main/openapi/course-progress.yml
- filename: course-daily-usage.yml
  format: yaml
  label: pluralsight-course-daily-usage
  slug: pluralsight-course-daily-usage
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/pluralsight/refs/heads/main/openapi/course-daily-usage.yml
- filename: reports-rest.yml
  format: yaml
  label: pluralsight-reports-rest
  slug: pluralsight-reports-rest
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/pluralsight/refs/heads/main/openapi/reports-rest.yml
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
- download a course usage report as csv. deprecated - migrate to graphql.
- download a user report as csv. deprecated - migrate to graphql.
- reporting
- track user course progress including completion status and viewing history for video courses.
- download user report
- user reports as csv downloads (legacy rest, deprecated)
- download a course usage report as csv
- learning progress
- course completion
- query course progress
- course completion reports as csv downloads (legacy rest, deprecated)
- skills assessment
- user course progress including completion status and viewing history
- analytics
- query course daily usage
- course usage reports as csv downloads (legacy rest, deprecated)
- retrieve daily course engagement metrics and usage statistics.
- track user progress across all content types including videos, guides, paths, interactive courses, and projects.
- query content progress
- education
- video training
- courses
- technology
- download a course completion report as csv. deprecated - migrate to graphql.
- learning
- engineering metrics
- track user course progress and completion status
- download course usage report
- download a user report as csv
- pluralsight
- track user progress across all content types
- daily course engagement metrics and usage statistics
- download a course completion report as csv
- retrieve daily course engagement metrics
- download course completion report
- user progress across all content types including videos, guides, paths, and projects
slug: reporting-and-analytics
source_filename: reporting-and-analytics.yaml
source_heading: Capability Spec
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
