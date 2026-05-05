---
categories: []
consumed_apis:
- recruiting
description: Recruiter and hiring manager workflow for scheduling interviews, collecting and reviewing interviewer feedback, and running pre-hire background screening. Combines the Workday Recruiting interview and background check operations into a single hiring evaluation surface.
layout: capability
name: Workday Recruiting Interview and Screening
operations:
- description: List interviews
  method: GET
  name: list-interviews
  path: /v1/interviews
- description: Schedule an interview
  method: POST
  name: schedule-interview
  path: /v1/interviews
- description: Get an interview
  method: GET
  name: get-interview
  path: /v1/interviews/{interviewId}
- description: List interview feedback
  method: GET
  name: list-interview-feedback
  path: /v1/interviews/{interviewId}/feedback
- description: Submit interview feedback
  method: POST
  name: submit-interview-feedback
  path: /v1/interviews/{interviewId}/feedback
- description: List background checks
  method: GET
  name: list-background-checks
  path: /v1/background-checks
- description: Submit a background check
  method: POST
  name: submit-background-check
  path: /v1/background-checks
- description: List background check packages
  method: GET
  name: list-background-check-packages
  path: /v1/background-check-packages
personas: []
provider_name: Workday Recruiting
provider_slug: workday-recruiting
search_terms:
- external staffing partner that submits candidates against open requisitions through the agency portal.
- workday
- saas
- load background check results from an external screening provider
- pulls eeo, ofccp, and veteran self-identification reference data for regulatory reporting.
- get interview
- sourcer
- drives the day-to-day hiring process — manages requisitions, progresses candidates through stages, schedules interviews, and coordinates screening.
- interview scheduling and interviewer feedback collection.
- worker assigned to evaluate candidates — submits interview feedback with competency ratings and hiring recommendations.
- submit interview feedback
- hcm
- list available background check packages for screening
- list background check results for candidates
- recruiter and hiring manager workflow for scheduling interviews, collecting interviewer feedback, and running pre-hire background screening.
- compliance analyst
- public publication of requisitions to internal and external career sites.
- schedule interview
- hiring manager and recruiter workflow for opening, modifying, freezing, and closing job requisitions and evergreen requisitions, creating positions, and posting jobs to career sites.
- human resources
- recruiting administrator workflow for retrieving recruiting configuration and reference data — job posting sites, screening questionnaires, and veteran status values for eeo and ofccp compliance.
- list feedback submitted by interviewers for a specific interview
- submit background check
- configures recruiting reference data — career sites, questionnaires, and reference values used across the recruiting workflows.
- get an interview
- owns hiring decisions for a team — opens and edits requisitions, reviews finalists, and approves offers.
- list interview feedback
- talent acquisition
- hiring needs, evergreen requisitions, and position management.
- pre-hire background screening and check packages.
- recruiter
- background check packages
- get details of a specific interview
- external agency relationships and candidate submissions.
- recruiting agency
- recruiter and sourcer workflow for managing candidates from sourcing through application progression, including profile management, assessments, referrals, stage moves, offers, bulk applicant import, and agency candidate submissions.
- recruiting
- list scheduled interviews with filters by application or date range
- submit a background check
- candidate profiles, attachments, photos, assessments, and referrals.
- schedule a new interview for a job application
- background checks
- interview feedback
- hiring manager
- schedule an interview
- list interviews
- list background check packages
- submit overall rating, competency ratings, and hiring recommendation for an interview
- recruiting configuration and reference data.
- individual interview
- candidate-to-requisition links, stage progression, and offers.
- interviewer
- builds candidate pipelines from external sourcing tools and job boards into workday requisitions.
- interviews
- list background checks
- eeo, ofccp, and veteran self-identification reference values.
- pre-hire records and high-volume bulk applicant import.
- recruiting admin
slug: interview-and-screening
source_filename: interview-and-screening.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Workday Recruiting Interview and Screening\"\n  description: >-\n    Recruiter and hiring manager workflow for scheduling interviews, collecting\n    and reviewing interviewer feedback, and running pre-hire background\n    screening. Combines the Workday Recruiting interview and background check\n    operations into a single hiring evaluation surface.\n  tags:\n    - Workday\n    - Recruiting\n    - Interviews\n    - Background Checks\n    - HCM\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WORKDAY_RECRUITING_TOKEN: WORKDAY_RECRUITING_TOKEN\n      WORKDAY_TENANT: WORKDAY_TENANT\n\ncapability:\n  consumes:\n    - import: recruiting\n      location: ./shared/recruiting.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: interview-and-screening-api\n      description: \"Unified REST API for interview scheduling, feedback collection, and background screening.\"\
  \n      resources:\n        - path: /v1/interviews\n          name: interviews\n          description: \"Interviews\"\n          operations:\n            - method: GET\n              name: list-interviews\n              description: \"List interviews\"\n              call: \"recruiting.list-interviews\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: schedule-interview\n              description: \"Schedule an interview\"\n              call: \"recruiting.schedule-interview\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/interviews/{interviewId}\n          name: interview-by-id\n          description: \"Individual interview\"\n          operations:\n            - method: GET\n              name: get-interview\n              description: \"Get an interview\"\n              call: \"recruiting.get-interview\"\n    \
  \          with:\n                interviewId: \"rest.interviewId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/interviews/{interviewId}/feedback\n          name: interview-feedback\n          description: \"Interview feedback\"\n          operations:\n            - method: GET\n              name: list-interview-feedback\n              description: \"List interview feedback\"\n              call: \"recruiting.list-interview-feedback\"\n              with:\n                interviewId: \"rest.interviewId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: submit-interview-feedback\n              description: \"Submit interview feedback\"\n              call: \"recruiting.submit-interview-feedback\"\n              with:\n                interviewId: \"rest.interviewId\"\n              outputParameters:\n         \
  \       - type: object\n                  mapping: \"$.\"\n        - path: /v1/background-checks\n          name: background-checks\n          description: \"Background checks\"\n          operations:\n            - method: GET\n              name: list-background-checks\n              description: \"List background checks\"\n              call: \"recruiting.list-background-checks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: submit-background-check\n              description: \"Submit a background check\"\n              call: \"recruiting.submit-background-check\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/background-check-packages\n          name: background-check-packages\n          description: \"Background check packages\"\n          operations:\n            - method: GET\n              name: list-background-check-packages\n\
  \              description: \"List background check packages\"\n              call: \"recruiting.list-background-check-packages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: interview-and-screening-mcp\n      transport: http\n      description: \"MCP server for AI-assisted interview scheduling, feedback, and background screening.\"\n      tools:\n        - name: list-interviews\n          description: \"List scheduled interviews with filters by application or date range\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"recruiting.list-interviews\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: schedule-interview\n          description: \"Schedule a new interview for a job application\"\n          hints:\n            readOnly: false\n            idempotent: false\n         \
  \ call: \"recruiting.schedule-interview\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-interview\n          description: \"Get details of a specific interview\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"recruiting.get-interview\"\n          with:\n            interviewId: \"tools.interviewId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-interview-feedback\n          description: \"List feedback submitted by interviewers for a specific interview\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"recruiting.list-interview-feedback\"\n          with:\n            interviewId: \"tools.interviewId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-interview-feedback\n          description: \"Submit overall\
  \ rating, competency ratings, and hiring recommendation for an interview\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"recruiting.submit-interview-feedback\"\n          with:\n            interviewId: \"tools.interviewId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-background-checks\n          description: \"List background check results for candidates\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"recruiting.list-background-checks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-background-check\n          description: \"Load background check results from an external screening provider\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"recruiting.submit-background-check\"\n          outputParameters:\n    \
  \        - type: object\n              mapping: \"$.\"\n        - name: list-background-check-packages\n          description: \"List available background check packages for screening\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"recruiting.list-background-check-packages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday-recruiting/refs/heads/main/capabilities/interview-and-screening.yaml
tags:
- Workday
- Recruiting
- Interviews
- Background Checks
- HCM
tools:
- description: List scheduled interviews with filters by application or date range
  hints:
    idempotent: true
    readOnly: true
  name: list-interviews
- description: Schedule a new interview for a job application
  hints:
    idempotent: false
    readOnly: false
  name: schedule-interview
- description: Get details of a specific interview
  hints:
    idempotent: true
    readOnly: true
  name: get-interview
- description: List feedback submitted by interviewers for a specific interview
  hints:
    idempotent: true
    readOnly: true
  name: list-interview-feedback
- description: Submit overall rating, competency ratings, and hiring recommendation for an interview
  hints:
    idempotent: false
    readOnly: false
  name: submit-interview-feedback
- description: List background check results for candidates
  hints:
    idempotent: true
    readOnly: true
  name: list-background-checks
- description: Load background check results from an external screening provider
  hints:
    idempotent: false
    readOnly: false
  name: submit-background-check
- description: List available background check packages for screening
  hints:
    idempotent: true
    readOnly: true
  name: list-background-check-packages
---
