---
categories: []
consumed_apis: []
description: Integrated talent management workflow combining performance reviews, goal setting, learning and development, succession planning, and talent assessments in Workday.
layout: capability
name: Workday Talent Management Workflow
operations:
- description: ''
  method: GET
  name: list-performance-reviews
  path: /v1/performance-reviews
- description: ''
  method: GET
  name: list-courses
  path: /v1/courses
personas: []
provider_name: Workday Integration
provider_slug: workday-integration
search_terms:
- list available learning courses
- list courses
- list employee talent profiles
- succession
- workday
- hcm
- talent
- erp
- integration
- list employee goals
- list employee performance reviews
- list succession plans
- get details of a performance review
- finance
- enterprise
- list performance reviews
- list goals
- list enrollments
- performance
- payroll
- list talent profiles
- get performance review
- learning
- list learning enrollments
slug: talent-management
source_filename: talent-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Workday Talent Management Workflow\"\n  description: \"Integrated talent management workflow combining performance reviews, goal setting, learning and development, succession planning, and talent assessments in Workday.\"\n  tags:\n    - Workday\n    - Integration\n    - Talent\n    - Performance\n    - Learning\n    - Succession\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WORKDAY_INTEGRATION_ACCESS_TOKEN: WORKDAY_INTEGRATION_ACCESS_TOKEN\n      WORKDAY_TENANT: WORKDAY_TENANT\n\ncapability:\n  consumes:\n    - type: http\n      namespace: performance\n      baseUri: https://wd2-impl-services1.workday.com/ccx/service/{tenant}\n      description: \"Workday Performance Management API\"\n      authentication:\n        type: bearer\n        token: \"{{WORKDAY_INTEGRATION_ACCESS_TOKEN}}\"\n      resources:\n        - name: performance-reviews\n          path: /performanceReviews\n\
  \          operations:\n            - name: list-performance-reviews\n              method: GET\n              description: \"List performance reviews\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n            - name: get-performance-review\n              method: GET\n              description: \"Get a performance review\"\n              inputParameters:\n                - name: reviewId\n                  in: path\n                  type: string\n                  required: true\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n        - name: goals\n          path: /goals\n          operations:\n            - name: list-goals\n              method: GET\n              description: \"List goals\"\n              outputRawFormat: json\n              outputParameters:\n\
  \                - name: result\n                  type: object\n                  value: \"$.\"\n    - type: http\n      namespace: learning\n      baseUri: https://wd2-impl-services1.workday.com/ccx/service/{tenant}\n      description: \"Workday Learning API\"\n      authentication:\n        type: bearer\n        token: \"{{WORKDAY_INTEGRATION_ACCESS_TOKEN}}\"\n      resources:\n        - name: courses\n          path: /courses\n          operations:\n            - name: list-courses\n              method: GET\n              description: \"List courses\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n        - name: enrollments\n          path: /learningEnrollments\n          operations:\n            - name: list-enrollments\n              method: GET\n              description: \"List enrollments\"\n              outputRawFormat: json\n              outputParameters:\n\
  \                - name: result\n                  type: object\n                  value: \"$.\"\n    - type: http\n      namespace: talent\n      baseUri: https://wd2-impl-services1.workday.com/ccx/service/{tenant}\n      description: \"Workday Talent API\"\n      authentication:\n        type: bearer\n        token: \"{{WORKDAY_INTEGRATION_ACCESS_TOKEN}}\"\n      resources:\n        - name: talent-profiles\n          path: /talentProfiles\n          operations:\n            - name: list-talent-profiles\n              method: GET\n              description: \"List talent profiles\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n        - name: succession-plans\n          path: /successionPlans\n          operations:\n            - name: list-succession-plans\n              method: GET\n              description: \"List succession plans\"\n              outputRawFormat:\
  \ json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: talent-management-rest-api\n      resources:\n        - path: /v1/performance-reviews\n          name: performance-reviews\n          operations:\n            - method: GET\n              name: list-performance-reviews\n              call: \"performance.list-performance-reviews\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/courses\n          name: courses\n          operations:\n            - method: GET\n              name: list-courses\n              call: \"learning.list-courses\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: talent-management-mcp\n      transport: http\n      tools:\n        - name:\
  \ list-performance-reviews\n          description: \"List employee performance reviews\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"performance.list-performance-reviews\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-performance-review\n          description: \"Get details of a performance review\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"performance.get-performance-review\"\n          with:\n            reviewId: \"tools.reviewId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-goals\n          description: \"List employee goals\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"performance.list-goals\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-courses\n\
  \          description: \"List available learning courses\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"learning.list-courses\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-enrollments\n          description: \"List learning enrollments\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"learning.list-enrollments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-talent-profiles\n          description: \"List employee talent profiles\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"talent.list-talent-profiles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-succession-plans\n          description: \"List succession plans\"\n          hints:\n            readOnly:\
  \ true\n            openWorld: true\n          call: \"talent.list-succession-plans\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday-integration/refs/heads/main/capabilities/talent-management.yaml
tags:
- Workday
- Integration
- Talent
- Performance
- Learning
- Succession
tools:
- description: List employee performance reviews
  hints:
    openWorld: true
    readOnly: true
  name: list-performance-reviews
- description: Get details of a performance review
  hints:
    openWorld: false
    readOnly: true
  name: get-performance-review
- description: List employee goals
  hints:
    openWorld: true
    readOnly: true
  name: list-goals
- description: List available learning courses
  hints:
    openWorld: true
    readOnly: true
  name: list-courses
- description: List learning enrollments
  hints:
    openWorld: true
    readOnly: true
  name: list-enrollments
- description: List employee talent profiles
  hints:
    openWorld: true
    readOnly: true
  name: list-talent-profiles
- description: List succession plans
  hints:
    openWorld: true
    readOnly: true
  name: list-succession-plans
---
