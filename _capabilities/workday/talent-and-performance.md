---
categories:
- recruiting-ats
consumed_apis: []
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
- get goals for a worker
- list requisitions
- list job requisitions
- recruiting list postings
- list all job postings
- performance request feedback
- list all job requisitions
- recruiting
- get skills for a worker
- talent get skills
- recruiting list applications
- list all job applications
- talent management
- recruiting list candidates
- get certifications for a worker
- recruiting get application
- list all candidates
- cloud computing
- performance get goals
- give a feedback badge to a worker
- performance list badges
- list candidates
- workday
- financial management
- recruiting list requisitions
- talent list succession plans
- saas
- recruiting get requisition
- recruiting list prospects
- hcm
- get a job requisition by id
- list succession plans
- candidates
- performance list reviews
- list performance reviews
- talent list mentorships
- succession plans
- list reviews
- performance
- get a candidate by id
- talent get certifications
- recruiting get candidate
- talent get profile
- list all prospects
- enterprise software
- get a job application by id
- list mentorships
- list feedback badges
- performance give badge
- job requisitions
- get talent profile for a worker
- request feedback for a worker
- performance reviews
slug: talent-and-performance
source_filename: talent-and-performance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Workday Talent and Performance\n  description: Unified talent and performance management combining Recruiting, Talent, and Performance Management APIs for\n    HR and talent leads to manage hiring pipelines, career development, and performance evaluations.\n  tags:\n  - Workday\n  - Talent Management\n  - Performance\n  - Recruiting\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WORKDAY_OAUTH_TOKEN: WORKDAY_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: workday-recruiting\n    baseUri: https://wd2-impl-services1.workday.com/ccx/api/v1/{tenant}/recruiting\n    description: Workday Recruiting REST API.\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_OAUTH_TOKEN}}'\n    resources:\n    - name: recruiting\n      path: /\n      description: Recruiting operations\n      operations:\n      - name: get-job-requisitions\n        method: GET\n        description:\
  \ Returns job requisitions.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-job-requisition-by-id\n        method: GET\n        description: Returns a job requisition by ID.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: Requisition ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-job-postings\n        method: GET\n        description: Returns job postings.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-job-posting-by-id\n        method: GET\n        description: Returns a job posting by ID.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: Posting ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-candidates\n        method: GET\n        description: Returns candidates.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-candidate-by-id\n        method: GET\n        description: Returns a candidate by ID.\n        inputParameters:\n\
  \        - name: ID\n          in: path\n          type: string\n          required: true\n          description: Candidate ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-job-applications\n        method: GET\n        description: Returns job applications.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-job-application-by-id\n        method: GET\n        description: Returns a job application by ID.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: Application ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: get-prospects\n        method: GET\n        description: Returns prospects.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: workday-talent\n    baseUri: https://wd2-impl-services1.workday.com/ccx/api/v1/{tenant}/talent\n    description: Workday Talent Management REST API.\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_OAUTH_TOKEN}}'\n    resources:\n    - name: talent\n      path: /\n      description: Talent management operations\n      operations:\n      - name: get-talent-profile\n        method: GET\n        description: Returns a talent profile for a worker.\n        inputParameters:\n        - name: worker\n          in: query\n    \
  \      type: string\n          required: true\n          description: Worker ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-mentorships\n        method: GET\n        description: Returns mentorships.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-worker-skills\n        method: GET\n        description: Returns skills for a worker.\n        inputParameters:\n        - name: worker\n          in: query\n          type: string\n          required: true\n          description: Worker ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-worker-certifications\n        method: GET\n        description: Returns certifications for a worker.\n        inputParameters:\n        - name: worker\n         \
  \ in: query\n          type: string\n          required: true\n          description: Worker ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-succession-plans\n        method: GET\n        description: Returns succession plans.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-succession-plan-by-id\n        method: GET\n        description: Returns a succession plan by ID.\n        inputParameters:\n        - name: ID\n          in: path\n          type: string\n          required: true\n          description: Succession plan ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: workday-performance\n    baseUri: https://wd2-impl-services1.workday.com/ccx/api/v1/{tenant}/performanceManagement\n\
  \    description: Workday Performance Management REST API.\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_OAUTH_TOKEN}}'\n    resources:\n    - name: performance\n      path: /\n      description: Performance management operations\n      operations:\n      - name: get-worker-goals\n        method: GET\n        description: Returns goals for a worker.\n        inputParameters:\n        - name: worker\n          in: query\n          type: string\n          required: true\n          description: Worker ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-performance-reviews\n        method: GET\n        description: Returns performance reviews.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-feedback-badges\n        method: GET\n        description: Returns feedback badges.\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: give-feedback-badge\n        method: POST\n        description: Gives a feedback badge to a worker.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            worker: '{{tools.worker}}'\n            badge: '{{tools.badge}}'\n      - name: request-feedback\n        method: POST\n        description: Requests feedback for a worker.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            worker: '{{tools.worker}}'\n            message: '{{tools.message}}'\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: talent-performance-api\n    description: Unified REST API for talent and\
  \ performance management.\n    resources:\n    - path: /v1/job-requisitions\n      name: requisitions\n      description: Job requisitions\n      operations:\n      - method: GET\n        name: list-requisitions\n        description: List job requisitions\n        call: workday-recruiting.get-job-requisitions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/candidates\n      name: candidates\n      description: Candidates\n      operations:\n      - method: GET\n        name: list-candidates\n        description: List candidates\n        call: workday-recruiting.get-candidates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/performance-reviews\n      name: reviews\n      description: Performance reviews\n      operations:\n      - method: GET\n        name: list-reviews\n        description: List performance reviews\n        call: workday-performance.get-performance-reviews\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/succession-plans\n      name: succession\n      description: Succession plans\n      operations:\n      - method: GET\n        name: list-succession-plans\n        description: List succession plans\n        call: workday-talent.get-succession-plans\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: talent-performance-mcp\n    transport: http\n    description: MCP server for AI-assisted talent and performance management.\n    tools:\n    - name: recruiting-list-requisitions\n      description: List all job requisitions\n      hints:\n        readOnly: true\n      call: workday-recruiting.get-job-requisitions\n      with:\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: recruiting-get-requisition\n      description: Get a job requisition by ID\n      hints:\n        readOnly: true\n      call: workday-recruiting.get-job-requisition-by-id\n\
  \      with:\n        ID: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: recruiting-list-postings\n      description: List all job postings\n      hints:\n        readOnly: true\n      call: workday-recruiting.get-job-postings\n      with:\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: recruiting-list-candidates\n      description: List all candidates\n      hints:\n        readOnly: true\n      call: workday-recruiting.get-candidates\n      with:\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: recruiting-get-candidate\n      description: Get a candidate by ID\n      hints:\n        readOnly: true\n      call: workday-recruiting.get-candidate-by-id\n      with:\n        ID: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: recruiting-list-applications\n      description: List all job\
  \ applications\n      hints:\n        readOnly: true\n      call: workday-recruiting.get-job-applications\n      with:\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: recruiting-get-application\n      description: Get a job application by ID\n      hints:\n        readOnly: true\n      call: workday-recruiting.get-job-application-by-id\n      with:\n        ID: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: recruiting-list-prospects\n      description: List all prospects\n      hints:\n        readOnly: true\n      call: workday-recruiting.get-prospects\n      with:\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: talent-get-profile\n      description: Get talent profile for a worker\n      hints:\n        readOnly: true\n      call: workday-talent.get-talent-profile\n      with:\n        worker: tools.worker\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: talent-list-mentorships\n      description: List mentorships\n      hints:\n        readOnly: true\n      call: workday-talent.get-mentorships\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: talent-get-skills\n      description: Get skills for a worker\n      hints:\n        readOnly: true\n      call: workday-talent.get-worker-skills\n      with:\n        worker: tools.worker\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: talent-get-certifications\n      description: Get certifications for a worker\n      hints:\n        readOnly: true\n      call: workday-talent.get-worker-certifications\n      with:\n        worker: tools.worker\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: talent-list-succession-plans\n      description: List succession plans\n      hints:\n        readOnly: true\n      call: workday-talent.get-succession-plans\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: performance-get-goals\n      description: Get goals for a worker\n      hints:\n        readOnly: true\n      call: workday-performance.get-worker-goals\n      with:\n        worker: tools.worker\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: performance-list-reviews\n      description: List performance reviews\n      hints:\n        readOnly: true\n      call: workday-performance.get-performance-reviews\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: performance-list-badges\n      description: List feedback badges\n      hints:\n        readOnly: true\n      call: workday-performance.get-feedback-badges\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: performance-give-badge\n      description: Give a feedback badge to a worker\n      hints:\n        readOnly: false\n      call: workday-performance.give-feedback-badge\n\
  \      with:\n        worker: tools.worker\n        badge: tools.badge\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: performance-request-feedback\n      description: Request feedback for a worker\n      hints:\n        readOnly: false\n      call: workday-performance.request-feedback\n      with:\n        worker: tools.worker\n        message: tools.message\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
