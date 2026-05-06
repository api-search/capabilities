---
categories:
- analytics
consumed_apis: []
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
- courses
- skills assessment
- education
- user reports as csv downloads (legacy rest, deprecated)
- user course progress including completion status and viewing history
- reporting
- track user progress across all content types
- analytics
- learning progress
- download course completion report
- download a user report as csv. deprecated - migrate to graphql.
- download a course completion report as csv
- course usage reports as csv downloads (legacy rest, deprecated)
- video training
- daily course engagement metrics and usage statistics
- query content progress
- user progress across all content types including videos, guides, paths, and projects
- download user report
- technology
- track user progress across all content types including videos, guides, paths, interactive courses, and projects.
- download a course usage report as csv. deprecated - migrate to graphql.
- course completion
- query course daily usage
- pluralsight
- engineering metrics
- track user course progress including completion status and viewing history for video courses.
- download course usage report
- retrieve daily course engagement metrics and usage statistics.
- learning
- query course progress
- retrieve daily course engagement metrics
- course completion reports as csv downloads (legacy rest, deprecated)
- download a course usage report as csv
- download a course completion report as csv. deprecated - migrate to graphql.
- download a user report as csv
- track user course progress and completion status
slug: reporting-and-analytics
source_filename: reporting-and-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Pluralsight Reporting And Analytics\n  description: Unified workflow for L&D managers to track learning progress, course completions, daily usage patterns, and\n    generate reports. Combines content progress, course progress, course daily usage, and reports REST APIs.\n  tags:\n  - Pluralsight\n  - Reporting\n  - Analytics\n  - Learning Progress\n  - Course Completion\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    PLURALSIGHT_BEARER_TOKEN: PLURALSIGHT_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: pluralsight-content-progress\n    baseUri: https://paas-api.pluralsight.com\n    description: GraphQL query for tracking user progress across all content types including videos, guides, paths, interactive\n      courses, and projects.\n    authentication:\n      type: bearer\n      token: '{{PLURALSIGHT_BEARER_TOKEN}}'\n    resources:\n    - name: content-progress\n      path:\
  \ /graphql\n      description: Content progress queries via GraphQL\n      operations:\n      - name: query-content-progress\n        method: POST\n        description: Execute GraphQL queries to track user progress across all content types including videos, guides, paths,\n          interactive courses, and projects.\n        inputParameters:\n        - name: query\n          in: body\n          type: string\n          required: true\n          description: The GraphQL query string\n        - name: variables\n          in: body\n          type: object\n          required: false\n          description: Variables for the GraphQL query\n        - name: operationName\n          in: body\n          type: string\n          required: false\n          description: Name of the operation to execute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query:\
  \ '{{tools.query}}'\n            variables: '{{tools.variables}}'\n            operationName: '{{tools.operationName}}'\n  - type: http\n    namespace: pluralsight-course-progress\n    baseUri: https://paas-api.pluralsight.com\n    description: GraphQL query for tracking user course progress including completion status and viewing history for video\n      courses.\n    authentication:\n      type: bearer\n      token: '{{PLURALSIGHT_BEARER_TOKEN}}'\n    resources:\n    - name: course-progress\n      path: /graphql\n      description: Course progress queries via GraphQL\n      operations:\n      - name: query-course-progress\n        method: POST\n        description: Execute GraphQL queries to track user course progress including completion status and viewing history\n          for video courses.\n        inputParameters:\n        - name: query\n          in: body\n          type: string\n          required: true\n          description: The GraphQL query string\n        - name: variables\n\
  \          in: body\n          type: object\n          required: false\n          description: Variables for the GraphQL query\n        - name: operationName\n          in: body\n          type: string\n          required: false\n          description: Name of the operation to execute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            variables: '{{tools.variables}}'\n            operationName: '{{tools.operationName}}'\n  - type: http\n    namespace: pluralsight-course-daily-usage\n    baseUri: https://paas-api.pluralsight.com\n    description: GraphQL query for retrieving daily course engagement metrics and usage statistics.\n    authentication:\n      type: bearer\n      token: '{{PLURALSIGHT_BEARER_TOKEN}}'\n    resources:\n    - name: course-daily-usage\n      path: /graphql\n      description: Course daily\
  \ usage queries via GraphQL\n      operations:\n      - name: query-course-daily-usage\n        method: POST\n        description: Execute GraphQL queries to retrieve daily course engagement metrics and usage statistics.\n        inputParameters:\n        - name: query\n          in: body\n          type: string\n          required: true\n          description: The GraphQL query string\n        - name: variables\n          in: body\n          type: object\n          required: false\n          description: Variables for the GraphQL query\n        - name: operationName\n          in: body\n          type: string\n          required: false\n          description: Name of the operation to execute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            variables: '{{tools.variables}}'\n            operationName: '{{tools.operationName}}'\n\
  \  - type: http\n    namespace: pluralsight-reports-rest\n    baseUri: https://app.pluralsight.com/plans/api/reports/v1\n    description: Legacy REST API for downloading user, course completion, and course usage reports as CSV files. Deprecated.\n    authentication:\n      type: bearer\n      token: '{{PLURALSIGHT_BEARER_TOKEN}}'\n    resources:\n    - name: user-reports\n      path: /users\n      description: User report downloads (deprecated)\n      operations:\n      - name: download-user-report\n        method: GET\n        description: Download a user report as CSV. Deprecated - migrate to GraphQL User Management API.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: course-completion-reports\n      path: /course-completion\n      description: Course completion report downloads (deprecated)\n      operations:\n      - name: download-course-completion-report\n        method: GET\n        description:\
  \ Download a course completion report as CSV. Deprecated - migrate to GraphQL Course Progress API.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: course-usage-reports\n      path: /course-usage\n      description: Course usage report downloads (deprecated)\n      operations:\n      - name: download-course-usage-report\n        method: GET\n        description: Download a course usage report as CSV. Deprecated - migrate to GraphQL Course Daily Usage API.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8084\n    namespace: reporting-analytics-api\n    description: Unified REST API for Pluralsight reporting and analytics including learning progress, course completions,\n      usage, and legacy reports.\n    resources:\n    - path: /v1/content-progress\n      name: content-progress\n\
  \      description: User progress across all content types including videos, guides, paths, and projects\n      operations:\n      - method: POST\n        name: query-content-progress\n        description: Track user progress across all content types\n        call: pluralsight-content-progress.query-content-progress\n        with:\n          query: rest.query\n          variables: rest.variables\n          operationName: rest.operationName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/course-progress\n      name: course-progress\n      description: User course progress including completion status and viewing history\n      operations:\n      - method: POST\n        name: query-course-progress\n        description: Track user course progress and completion status\n        call: pluralsight-course-progress.query-course-progress\n        with:\n          query: rest.query\n          variables: rest.variables\n          operationName: rest.operationName\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/course-daily-usage\n      name: course-daily-usage\n      description: Daily course engagement metrics and usage statistics\n      operations:\n      - method: POST\n        name: query-course-daily-usage\n        description: Retrieve daily course engagement metrics\n        call: pluralsight-course-daily-usage.query-course-daily-usage\n        with:\n          query: rest.query\n          variables: rest.variables\n          operationName: rest.operationName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/user-reports\n      name: user-reports\n      description: User reports as CSV downloads (legacy REST, deprecated)\n      operations:\n      - method: GET\n        name: download-user-report\n        description: Download a user report as CSV\n        call: pluralsight-reports-rest.download-user-report\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/course-completion-reports\n      name: course-completion-reports\n      description: Course completion reports as CSV downloads (legacy REST, deprecated)\n      operations:\n      - method: GET\n        name: download-course-completion-report\n        description: Download a course completion report as CSV\n        call: pluralsight-reports-rest.download-course-completion-report\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/course-usage-reports\n      name: course-usage-reports\n      description: Course usage reports as CSV downloads (legacy REST, deprecated)\n      operations:\n      - method: GET\n        name: download-course-usage-report\n        description: Download a course usage report as CSV\n        call: pluralsight-reports-rest.download-course-usage-report\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9094\n    namespace: reporting-analytics-mcp\n\
  \    transport: http\n    description: MCP server for AI-assisted reporting and analytics across learning progress, course completions, and usage\n      data.\n    tools:\n    - name: query-content-progress\n      description: Track user progress across all content types including videos, guides, paths, interactive courses, and\n        projects.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-content-progress.query-content-progress\n      with:\n        query: tools.query\n        variables: tools.variables\n        operationName: tools.operationName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-course-progress\n      description: Track user course progress including completion status and viewing history for video courses.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-course-progress.query-course-progress\n\
  \      with:\n        query: tools.query\n        variables: tools.variables\n        operationName: tools.operationName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-course-daily-usage\n      description: Retrieve daily course engagement metrics and usage statistics.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-course-daily-usage.query-course-daily-usage\n      with:\n        query: tools.query\n        variables: tools.variables\n        operationName: tools.operationName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: download-user-report\n      description: Download a user report as CSV. Deprecated - migrate to GraphQL.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-reports-rest.download-user-report\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: download-course-completion-report\n      description: Download a course completion report as CSV. Deprecated - migrate to GraphQL.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-reports-rest.download-course-completion-report\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: download-course-usage-report\n      description: Download a course usage report as CSV. Deprecated - migrate to GraphQL.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n        openWorld: true\n      call: pluralsight-reports-rest.download-course-usage-report\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
