---
categories: []
consumed_apis:
- recruiting
description: Recruiting administrator workflow for retrieving recruiting configuration and reference data — job posting sites, screening questionnaires, and veteran status reference values used for EEO and OFCCP compliance reporting.
layout: capability
name: Workday Recruiting Configuration
operations:
- description: List job posting sites
  method: GET
  name: list-job-posting-sites
  path: /v1/job-posting-sites
- description: List questionnaires
  method: GET
  name: list-questionnaires
  path: /v1/questionnaires
- description: List veteran statuses
  method: GET
  name: list-veteran-statuses
  path: /v1/veteran-statuses
personas: []
provider_name: Workday Recruiting
provider_slug: workday-recruiting
search_terms:
- external staffing partner that submits candidates against open requisitions through the agency portal.
- workday
- list veteran status reference values for eeo and ofccp compliance reporting
- saas
- pulls eeo, ofccp, and veteran self-identification reference data for regulatory reporting.
- interview scheduling and interviewer feedback collection.
- sourcer
- drives the day-to-day hiring process — manages requisitions, progresses candidates through stages, schedules interviews, and coordinates screening.
- worker assigned to evaluate candidates — submits interview feedback with competency ratings and hiring recommendations.
- veteran status reference values
- hcm
- public publication of requisitions to internal and external career sites.
- recruiter and hiring manager workflow for scheduling interviews, collecting interviewer feedback, and running pre-hire background screening.
- human resources
- compliance analyst
- hiring manager and recruiter workflow for opening, modifying, freezing, and closing job requisitions and evergreen requisitions, creating positions, and posting jobs to career sites.
- list internal career pages and external job boards configured in workday
- recruiting administrator workflow for retrieving recruiting configuration and reference data — job posting sites, screening questionnaires, and veteran status values for eeo and ofccp compliance.
- configures recruiting reference data — career sites, questionnaires, and reference values used across the recruiting workflows.
- owns hiring decisions for a team — opens and edits requisitions, reviews finalists, and approves offers.
- job posting sites
- talent acquisition
- hiring needs, evergreen requisitions, and position management.
- pre-hire background screening and check packages.
- list veteran statuses
- recruiter
- external agency relationships and candidate submissions.
- recruiting agency
- recruiter and sourcer workflow for managing candidates from sourcing through application progression, including profile management, assessments, referrals, stage moves, offers, bulk applicant import, and agency candidate submissions.
- recruiting
- list recruiting questionnaires used for screening and assessment
- configuration
- list questionnaires
- candidate profiles, attachments, photos, assessments, and referrals.
- recruiting questionnaires
- hiring manager
- compliance
- list job posting sites
- candidate-to-requisition links, stage progression, and offers.
- interviewer
- builds candidate pipelines from external sourcing tools and job boards into workday requisitions.
- recruiting configuration and reference data.
- eeo, ofccp, and veteran self-identification reference values.
- pre-hire records and high-volume bulk applicant import.
- recruiting admin
slug: recruiting-configuration
source_filename: recruiting-configuration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Workday Recruiting Configuration\"\n  description: >-\n    Recruiting administrator workflow for retrieving recruiting configuration\n    and reference data — job posting sites, screening questionnaires, and\n    veteran status reference values used for EEO and OFCCP compliance\n    reporting.\n  tags:\n    - Workday\n    - Recruiting\n    - Configuration\n    - Compliance\n    - HCM\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WORKDAY_RECRUITING_TOKEN: WORKDAY_RECRUITING_TOKEN\n      WORKDAY_TENANT: WORKDAY_TENANT\n\ncapability:\n  consumes:\n    - import: recruiting\n      location: ./shared/recruiting.yaml\n\n  exposes:\n    - type: rest\n      port: 8083\n      namespace: recruiting-configuration-api\n      description: \"Unified REST API for retrieving recruiting configuration and reference data.\"\n      resources:\n        - path: /v1/job-posting-sites\n         \
  \ name: job-posting-sites\n          description: \"Job posting sites\"\n          operations:\n            - method: GET\n              name: list-job-posting-sites\n              description: \"List job posting sites\"\n              call: \"recruiting.list-job-posting-sites\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/questionnaires\n          name: questionnaires\n          description: \"Recruiting questionnaires\"\n          operations:\n            - method: GET\n              name: list-questionnaires\n              description: \"List questionnaires\"\n              call: \"recruiting.list-questionnaires\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/veteran-statuses\n          name: veteran-statuses\n          description: \"Veteran status reference values\"\n          operations:\n            - method: GET\n              name:\
  \ list-veteran-statuses\n              description: \"List veteran statuses\"\n              call: \"recruiting.list-veteran-statuses\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9093\n      namespace: recruiting-configuration-mcp\n      transport: http\n      description: \"MCP server for AI-assisted retrieval of recruiting configuration and reference data.\"\n      tools:\n        - name: list-job-posting-sites\n          description: \"List internal career pages and external job boards configured in Workday\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"recruiting.list-job-posting-sites\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-questionnaires\n          description: \"List recruiting questionnaires used for screening and assessment\"\n          hints:\n            readOnly: true\n\
  \            idempotent: true\n          call: \"recruiting.list-questionnaires\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-veteran-statuses\n          description: \"List veteran status reference values for EEO and OFCCP compliance reporting\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"recruiting.list-veteran-statuses\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday-recruiting/refs/heads/main/capabilities/recruiting-configuration.yaml
tags:
- Workday
- Recruiting
- Configuration
- Compliance
- HCM
tools:
- description: List internal career pages and external job boards configured in Workday
  hints:
    idempotent: true
    readOnly: true
  name: list-job-posting-sites
- description: List recruiting questionnaires used for screening and assessment
  hints:
    idempotent: true
    readOnly: true
  name: list-questionnaires
- description: List veteran status reference values for EEO and OFCCP compliance reporting
  hints:
    idempotent: true
    readOnly: true
  name: list-veteran-statuses
---
