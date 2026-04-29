---
api_specs:
- filename: recruiting.yml
  format: yaml
  label: workday-recruiting
  slug: workday-recruiting
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/workday/refs/heads/main/openapi/recruiting.yml
- filename: talent.yml
  format: yaml
  label: workday-talent
  slug: workday-talent
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/workday/refs/heads/main/openapi/talent.yml
categories:
- recruiting-ats
consumed_apis:
- workday-recruiting
- workday-talent
- workday-performance
description: Unified talent and performance management combining Recruiting, Talent, and Performance Management APIs for HR and talent leads to manage hiring pipelines, career development, and performance evaluations.
layout: capability
name: Workday Talent and Performance
operations:
- description: List job requisitions
  method: GET
  name: list-requisitions
  path: /v1/job-requisitions
- description: List candidates
  method: GET
  name: list-candidates
  path: /v1/candidates
- description: List performance reviews
  method: GET
  name: list-reviews
  path: /v1/performance-reviews
- description: List succession plans
  method: GET
  name: list-succession-plans
  path: /v1/succession-plans
personas: []
provider_name: Workday
provider_slug: workday
search_terms:
- performance get goals
- performance request feedback
- candidates
- recruiting list applications
- performance give badge
- workday
- cloud computing
- list feedback badges
- recruiting list requisitions
- list reviews
- get a job application by id
- recruiting get application
- give a feedback badge to a worker
- request feedback for a worker
- enterprise software
- talent get skills
- list all prospects
- recruiting list candidates
- list requisitions
- recruiting get candidate
- talent get profile
- hcm
- job requisitions
- saas
- get certifications for a worker
- talent list succession plans
- list job requisitions
- list performance reviews
- performance reviews
- recruiting
- list candidates
- performance list reviews
- list all job requisitions
- financial management
- list all job applications
- list succession plans
- talent list mentorships
- recruiting get requisition
- list all candidates
- performance
- get a candidate by id
- succession plans
- talent get certifications
- get skills for a worker
- recruiting list prospects
- list mentorships
- list all job postings
- talent management
- performance list badges
- recruiting list postings
- get a job requisition by id
- get talent profile for a worker
- get goals for a worker
slug: talent-and-performance
source_filename: talent-and-performance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Workday Talent and Performance\"\n  description: \"Unified talent and performance management combining Recruiting, Talent, and Performance Management APIs for HR and talent leads to manage hiring pipelines, career development, and performance evaluations.\"\n  tags:\n    - Workday\n    - Talent Management\n    - Performance\n    - Recruiting\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      WORKDAY_OAUTH_TOKEN: WORKDAY_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: workday-recruiting\n      location: ./shared/recruiting.yaml\n    - import: workday-talent\n      location: ./shared/talent.yaml\n    - import: workday-performance\n      location: ./shared/performance-management.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: talent-performance-api\n      description: \"Unified REST API for talent and performance management.\"\n      resources:\n \
  \       - path: /v1/job-requisitions\n          name: requisitions\n          description: \"Job requisitions\"\n          operations:\n            - method: GET\n              name: list-requisitions\n              description: \"List job requisitions\"\n              call: \"workday-recruiting.get-job-requisitions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/candidates\n          name: candidates\n          description: \"Candidates\"\n          operations:\n            - method: GET\n              name: list-candidates\n              description: \"List candidates\"\n              call: \"workday-recruiting.get-candidates\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/performance-reviews\n          name: reviews\n          description: \"Performance reviews\"\n          operations:\n            - method: GET\n              name: list-reviews\n\
  \              description: \"List performance reviews\"\n              call: \"workday-performance.get-performance-reviews\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/succession-plans\n          name: succession\n          description: \"Succession plans\"\n          operations:\n            - method: GET\n              name: list-succession-plans\n              description: \"List succession plans\"\n              call: \"workday-talent.get-succession-plans\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: talent-performance-mcp\n      transport: http\n      description: \"MCP server for AI-assisted talent and performance management.\"\n      tools:\n        - name: recruiting-list-requisitions\n          description: \"List all job requisitions\"\n          hints:\n            readOnly: true\n      \
  \    call: \"workday-recruiting.get-job-requisitions\"\n          with:\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: recruiting-get-requisition\n          description: \"Get a job requisition by ID\"\n          hints:\n            readOnly: true\n          call: \"workday-recruiting.get-job-requisition-by-id\"\n          with:\n            ID: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: recruiting-list-postings\n          description: \"List all job postings\"\n          hints:\n            readOnly: true\n          call: \"workday-recruiting.get-job-postings\"\n          with:\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: recruiting-list-candidates\n          description: \"List all candidates\"\n          hints:\n         \
  \   readOnly: true\n          call: \"workday-recruiting.get-candidates\"\n          with:\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: recruiting-get-candidate\n          description: \"Get a candidate by ID\"\n          hints:\n            readOnly: true\n          call: \"workday-recruiting.get-candidate-by-id\"\n          with:\n            ID: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: recruiting-list-applications\n          description: \"List all job applications\"\n          hints:\n            readOnly: true\n          call: \"workday-recruiting.get-job-applications\"\n          with:\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: recruiting-get-application\n          description: \"Get a job application by ID\"\n  \
  \        hints:\n            readOnly: true\n          call: \"workday-recruiting.get-job-application-by-id\"\n          with:\n            ID: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: recruiting-list-prospects\n          description: \"List all prospects\"\n          hints:\n            readOnly: true\n          call: \"workday-recruiting.get-prospects\"\n          with:\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: talent-get-profile\n          description: \"Get talent profile for a worker\"\n          hints:\n            readOnly: true\n          call: \"workday-talent.get-talent-profile\"\n          with:\n            worker: \"tools.worker\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: talent-list-mentorships\n          description: \"List mentorships\"\
  \n          hints:\n            readOnly: true\n          call: \"workday-talent.get-mentorships\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: talent-get-skills\n          description: \"Get skills for a worker\"\n          hints:\n            readOnly: true\n          call: \"workday-talent.get-worker-skills\"\n          with:\n            worker: \"tools.worker\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: talent-get-certifications\n          description: \"Get certifications for a worker\"\n          hints:\n            readOnly: true\n          call: \"workday-talent.get-worker-certifications\"\n          with:\n            worker: \"tools.worker\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: talent-list-succession-plans\n          description: \"List succession plans\"\n          hints:\n            readOnly:\
  \ true\n          call: \"workday-talent.get-succession-plans\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: performance-get-goals\n          description: \"Get goals for a worker\"\n          hints:\n            readOnly: true\n          call: \"workday-performance.get-worker-goals\"\n          with:\n            worker: \"tools.worker\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: performance-list-reviews\n          description: \"List performance reviews\"\n          hints:\n            readOnly: true\n          call: \"workday-performance.get-performance-reviews\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: performance-list-badges\n          description: \"List feedback badges\"\n          hints:\n            readOnly: true\n          call: \"workday-performance.get-feedback-badges\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: performance-give-badge\n          description: \"Give a feedback badge to a worker\"\n          hints:\n            readOnly: false\n          call: \"workday-performance.give-feedback-badge\"\n          with:\n            worker: \"tools.worker\"\n            badge: \"tools.badge\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: performance-request-feedback\n          description: \"Request feedback for a worker\"\n          hints:\n            readOnly: false\n          call: \"workday-performance.request-feedback\"\n          with:\n            worker: \"tools.worker\"\n            message: \"tools.message\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday/refs/heads/main/capabilities/talent-and-performance.yaml
tags:
- Workday
- Talent Management
- Performance
- Recruiting
tools:
- description: List all job requisitions
  hints:
    readOnly: true
  name: recruiting-list-requisitions
- description: Get a job requisition by ID
  hints:
    readOnly: true
  name: recruiting-get-requisition
- description: List all job postings
  hints:
    readOnly: true
  name: recruiting-list-postings
- description: List all candidates
  hints:
    readOnly: true
  name: recruiting-list-candidates
- description: Get a candidate by ID
  hints:
    readOnly: true
  name: recruiting-get-candidate
- description: List all job applications
  hints:
    readOnly: true
  name: recruiting-list-applications
- description: Get a job application by ID
  hints:
    readOnly: true
  name: recruiting-get-application
- description: List all prospects
  hints:
    readOnly: true
  name: recruiting-list-prospects
- description: Get talent profile for a worker
  hints:
    readOnly: true
  name: talent-get-profile
- description: List mentorships
  hints:
    readOnly: true
  name: talent-list-mentorships
- description: Get skills for a worker
  hints:
    readOnly: true
  name: talent-get-skills
- description: Get certifications for a worker
  hints:
    readOnly: true
  name: talent-get-certifications
- description: List succession plans
  hints:
    readOnly: true
  name: talent-list-succession-plans
- description: Get goals for a worker
  hints:
    readOnly: true
  name: performance-get-goals
- description: List performance reviews
  hints:
    readOnly: true
  name: performance-list-reviews
- description: List feedback badges
  hints:
    readOnly: true
  name: performance-list-badges
- description: Give a feedback badge to a worker
  hints:
    readOnly: false
  name: performance-give-badge
- description: Request feedback for a worker
  hints:
    readOnly: false
  name: performance-request-feedback
---
