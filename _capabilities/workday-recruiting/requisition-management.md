---
categories: []
consumed_apis:
- recruiting
description: Hiring manager and recruiter workflow for opening, modifying, freezing, and closing job requisitions and evergreen requisitions, creating positions in the position management staffing model, and posting jobs to internal and external career sites.
layout: capability
name: Workday Recruiting Requisition Management
operations:
- description: List job requisitions
  method: GET
  name: list-job-requisitions
  path: /v1/job-requisitions
- description: Create a job requisition
  method: POST
  name: create-job-requisition
  path: /v1/job-requisitions
- description: Get a job requisition
  method: GET
  name: get-job-requisition
  path: /v1/job-requisitions/{jobRequisitionId}
- description: Edit a job requisition
  method: PATCH
  name: edit-job-requisition
  path: /v1/job-requisitions/{jobRequisitionId}
- description: Close a job requisition
  method: POST
  name: close-job-requisition
  path: /v1/job-requisitions/{jobRequisitionId}/close
- description: Freeze or unfreeze a job requisition
  method: POST
  name: manage-job-requisition-freeze
  path: /v1/job-requisitions/{jobRequisitionId}/freeze
- description: List evergreen requisitions
  method: GET
  name: list-evergreen-requisitions
  path: /v1/evergreen-requisitions
- description: Create an evergreen requisition
  method: POST
  name: create-evergreen-requisition
  path: /v1/evergreen-requisitions
- description: Get an evergreen requisition
  method: GET
  name: get-evergreen-requisition
  path: /v1/evergreen-requisitions/{evergreenRequisitionId}
- description: Close an evergreen requisition
  method: POST
  name: close-evergreen-requisition
  path: /v1/evergreen-requisitions/{evergreenRequisitionId}/close
- description: List positions
  method: GET
  name: list-positions
  path: /v1/positions
- description: Create a position
  method: POST
  name: create-position
  path: /v1/positions
- description: List job postings
  method: GET
  name: list-job-postings
  path: /v1/job-postings
- description: Get a job posting
  method: GET
  name: get-job-posting
  path: /v1/job-postings/{jobPostingId}
- description: Update a job posting
  method: PATCH
  name: update-job-posting
  path: /v1/job-postings/{jobPostingId}
- description: Post a job to career sites
  method: POST
  name: post-job
  path: /v1/job-postings/{jobPostingId}/post
- description: Unpost a job from career sites
  method: POST
  name: unpost-job
  path: /v1/job-postings/{jobPostingId}/unpost
personas: []
provider_name: Workday Recruiting
provider_slug: workday-recruiting
search_terms:
- hiring needs, evergreen requisitions, and position management.
- post a job to internal and external career sites
- get details of a specific evergreen requisition
- get evergreen requisition
- get details of a specific job requisition
- get a job posting
- list job postings
- get an evergreen requisition
- interview scheduling and interviewer feedback collection.
- create job requisition
- hiring manager
- get details of a specific job posting
- worker assigned to evaluate candidates — submits interview feedback with competency ratings and hiring recommendations.
- edit a job requisition
- human resources
- create a position
- get job requisition
- evergreen requisitions
- candidate profiles, attachments, photos, assessments, and referrals.
- unpost job
- create an evergreen requisition
- job postings
- candidate-to-requisition links, stage progression, and offers.
- saas
- list job requisitions with optional filters by status, organization, or update date
- pre-hire records and high-volume bulk applicant import.
- recruiting administrator workflow for retrieving recruiting configuration and reference data — job posting sites, screening questionnaires, and veteran status values for eeo and ofccp compliance.
- list evergreen requisitions used for ongoing hiring needs
- edit an open job requisition
- create position
- eeo, ofccp, and veteran self-identification reference values.
- manage job requisition freeze
- compliance analyst
- external agency relationships and candidate submissions.
- unpost a job from career sites
- get job posting
- drives the day-to-day hiring process — manages requisitions, progresses candidates through stages, schedules interviews, and coordinates screening.
- positions
- close an evergreen requisition
- individual job requisition
- edit job requisition
- interviewer
- recruiting configuration and reference data.
- recruiter
- workday
- pulls eeo, ofccp, and veteran self-identification reference data for regulatory reporting.
- close an evergreen requisition with no pending events
- list position management positions and their fill status
- hcm
- update an existing job posting (start/end dates)
- create and open a new position in the position management staffing model
- close job requisition
- create a job requisition
- external staffing partner that submits candidates against open requisitions through the agency portal.
- list positions
- builds candidate pipelines from external sourcing tools and job boards into workday requisitions.
- get a job requisition
- individual evergreen requisition
- recruiting agency
- list job postings with optional filters by requisition or posting site
- freeze or unfreeze a job requisition
- close a job requisition
- close evergreen requisition
- update job posting
- post job
- recruiter and hiring manager workflow for scheduling interviews, collecting interviewer feedback, and running pre-hire background screening.
- individual job posting
- hiring manager and recruiter workflow for opening, modifying, freezing, and closing job requisitions and evergreen requisitions, creating positions, and posting jobs to career sites.
- create a new evergreen requisition for ongoing hiring needs
- sourcer
- talent acquisition
- freeze or unfreeze a job requisition to halt or resume hiring
- configures recruiting reference data — career sites, questionnaires, and reference values used across the recruiting workflows.
- recruiting admin
- owns hiring decisions for a team — opens and edits requisitions, reviews finalists, and approves offers.
- close a job requisition that has no pending events
- job requisitions
- pre-hire background screening and check packages.
- list job requisitions
- public publication of requisitions to internal and external career sites.
- recruiting
- remove a job posting from career sites
- recruiter and sourcer workflow for managing candidates from sourcing through application progression, including profile management, assessments, referrals, stage moves, offers, bulk applicant import, and agency candidate submissions.
- post a job to career sites
- create evergreen requisition
- update a job posting
- create a new job requisition for an open position
- list evergreen requisitions
slug: requisition-management
source_filename: requisition-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Workday Recruiting Requisition Management\"\n  description: >-\n    Hiring manager and recruiter workflow for opening, modifying, freezing, and\n    closing job requisitions and evergreen requisitions, creating positions in\n    the position management staffing model, and posting jobs to internal and\n    external career sites.\n  tags:\n    - Workday\n    - Recruiting\n    - Job Requisitions\n    - Job Postings\n    - Positions\n    - HCM\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WORKDAY_RECRUITING_TOKEN: WORKDAY_RECRUITING_TOKEN\n      WORKDAY_TENANT: WORKDAY_TENANT\n\ncapability:\n  consumes:\n    - import: recruiting\n      location: ./shared/recruiting.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: requisition-management-api\n      description: \"Unified REST API for opening, modifying, and posting job requisitions.\"\n      resources:\n\
  \        - path: /v1/job-requisitions\n          name: job-requisitions\n          description: \"Job requisitions\"\n          operations:\n            - method: GET\n              name: list-job-requisitions\n              description: \"List job requisitions\"\n              call: \"recruiting.list-job-requisitions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-job-requisition\n              description: \"Create a job requisition\"\n              call: \"recruiting.create-job-requisition\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/job-requisitions/{jobRequisitionId}\n          name: job-requisition-by-id\n          description: \"Individual job requisition\"\n          operations:\n            - method: GET\n              name: get-job-requisition\n              description: \"Get a job requisition\"\
  \n              call: \"recruiting.get-job-requisition\"\n              with:\n                jobRequisitionId: \"rest.jobRequisitionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: edit-job-requisition\n              description: \"Edit a job requisition\"\n              call: \"recruiting.edit-job-requisition\"\n              with:\n                jobRequisitionId: \"rest.jobRequisitionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/job-requisitions/{jobRequisitionId}/close\n          name: job-requisition-close\n          description: \"Close a job requisition\"\n          operations:\n            - method: POST\n              name: close-job-requisition\n              description: \"Close a job requisition\"\n              call: \"recruiting.close-job-requisition\"\n              with:\n           \
  \     jobRequisitionId: \"rest.jobRequisitionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/job-requisitions/{jobRequisitionId}/freeze\n          name: job-requisition-freeze\n          description: \"Freeze or unfreeze a job requisition\"\n          operations:\n            - method: POST\n              name: manage-job-requisition-freeze\n              description: \"Freeze or unfreeze a job requisition\"\n              call: \"recruiting.manage-job-requisition-freeze\"\n              with:\n                jobRequisitionId: \"rest.jobRequisitionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/evergreen-requisitions\n          name: evergreen-requisitions\n          description: \"Evergreen requisitions\"\n          operations:\n            - method: GET\n              name: list-evergreen-requisitions\n              description:\
  \ \"List evergreen requisitions\"\n              call: \"recruiting.list-evergreen-requisitions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-evergreen-requisition\n              description: \"Create an evergreen requisition\"\n              call: \"recruiting.create-evergreen-requisition\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/evergreen-requisitions/{evergreenRequisitionId}\n          name: evergreen-requisition-by-id\n          description: \"Individual evergreen requisition\"\n          operations:\n            - method: GET\n              name: get-evergreen-requisition\n              description: \"Get an evergreen requisition\"\n              call: \"recruiting.get-evergreen-requisition\"\n              with:\n                evergreenRequisitionId: \"rest.evergreenRequisitionId\"\n    \
  \          outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/evergreen-requisitions/{evergreenRequisitionId}/close\n          name: evergreen-requisition-close\n          description: \"Close an evergreen requisition\"\n          operations:\n            - method: POST\n              name: close-evergreen-requisition\n              description: \"Close an evergreen requisition\"\n              call: \"recruiting.close-evergreen-requisition\"\n              with:\n                evergreenRequisitionId: \"rest.evergreenRequisitionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/positions\n          name: positions\n          description: \"Positions\"\n          operations:\n            - method: GET\n              name: list-positions\n              description: \"List positions\"\n              call: \"recruiting.list-positions\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-position\n              description: \"Create a position\"\n              call: \"recruiting.create-position\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/job-postings\n          name: job-postings\n          description: \"Job postings\"\n          operations:\n            - method: GET\n              name: list-job-postings\n              description: \"List job postings\"\n              call: \"recruiting.list-job-postings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/job-postings/{jobPostingId}\n          name: job-posting-by-id\n          description: \"Individual job posting\"\n          operations:\n            - method: GET\n              name: get-job-posting\n              description: \"Get a job posting\"\
  \n              call: \"recruiting.get-job-posting\"\n              with:\n                jobPostingId: \"rest.jobPostingId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-job-posting\n              description: \"Update a job posting\"\n              call: \"recruiting.update-job-posting\"\n              with:\n                jobPostingId: \"rest.jobPostingId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/job-postings/{jobPostingId}/post\n          name: job-posting-post\n          description: \"Post a job to career sites\"\n          operations:\n            - method: POST\n              name: post-job\n              description: \"Post a job to career sites\"\n              call: \"recruiting.post-job\"\n              with:\n                jobPostingId: \"rest.jobPostingId\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/job-postings/{jobPostingId}/unpost\n          name: job-posting-unpost\n          description: \"Unpost a job from career sites\"\n          operations:\n            - method: POST\n              name: unpost-job\n              description: \"Unpost a job from career sites\"\n              call: \"recruiting.unpost-job\"\n              with:\n                jobPostingId: \"rest.jobPostingId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: requisition-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted job requisition opening, posting, and lifecycle management.\"\n      tools:\n        - name: list-job-requisitions\n          description: \"List job requisitions with optional filters by status, organization, or update date\"\n          hints:\n            readOnly:\
  \ true\n            idempotent: true\n          call: \"recruiting.list-job-requisitions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-job-requisition\n          description: \"Create a new job requisition for an open position\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"recruiting.create-job-requisition\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-job-requisition\n          description: \"Get details of a specific job requisition\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"recruiting.get-job-requisition\"\n          with:\n            jobRequisitionId: \"tools.jobRequisitionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: edit-job-requisition\n          description: \"Edit an open job requisition\"\
  \n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"recruiting.edit-job-requisition\"\n          with:\n            jobRequisitionId: \"tools.jobRequisitionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: close-job-requisition\n          description: \"Close a job requisition that has no pending events\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"recruiting.close-job-requisition\"\n          with:\n            jobRequisitionId: \"tools.jobRequisitionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: manage-job-requisition-freeze\n          description: \"Freeze or unfreeze a job requisition to halt or resume hiring\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"recruiting.manage-job-requisition-freeze\"\
  \n          with:\n            jobRequisitionId: \"tools.jobRequisitionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-evergreen-requisitions\n          description: \"List evergreen requisitions used for ongoing hiring needs\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"recruiting.list-evergreen-requisitions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-evergreen-requisition\n          description: \"Create a new evergreen requisition for ongoing hiring needs\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"recruiting.create-evergreen-requisition\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-evergreen-requisition\n          description: \"Get details of a specific evergreen requisition\"\n\
  \          hints:\n            readOnly: true\n            idempotent: true\n          call: \"recruiting.get-evergreen-requisition\"\n          with:\n            evergreenRequisitionId: \"tools.evergreenRequisitionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: close-evergreen-requisition\n          description: \"Close an evergreen requisition with no pending events\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"recruiting.close-evergreen-requisition\"\n          with:\n            evergreenRequisitionId: \"tools.evergreenRequisitionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-positions\n          description: \"List position management positions and their fill status\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"recruiting.list-positions\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-position\n          description: \"Create and open a new position in the position management staffing model\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"recruiting.create-position\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-job-postings\n          description: \"List job postings with optional filters by requisition or posting site\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"recruiting.list-job-postings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-job-posting\n          description: \"Get details of a specific job posting\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"recruiting.get-job-posting\"\
  \n          with:\n            jobPostingId: \"tools.jobPostingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-job-posting\n          description: \"Update an existing job posting (start/end dates)\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"recruiting.update-job-posting\"\n          with:\n            jobPostingId: \"tools.jobPostingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: post-job\n          description: \"Post a job to internal and external career sites\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"recruiting.post-job\"\n          with:\n            jobPostingId: \"tools.jobPostingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: unpost-job\n          description: \"Remove a job posting\
  \ from career sites\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"recruiting.unpost-job\"\n          with:\n            jobPostingId: \"tools.jobPostingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday-recruiting/refs/heads/main/capabilities/requisition-management.yaml
tags:
- Workday
- Recruiting
- Job Requisitions
- Job Postings
- Positions
- HCM
tools:
- description: List job requisitions with optional filters by status, organization, or update date
  hints:
    idempotent: true
    readOnly: true
  name: list-job-requisitions
- description: Create a new job requisition for an open position
  hints:
    idempotent: false
    readOnly: false
  name: create-job-requisition
- description: Get details of a specific job requisition
  hints:
    idempotent: true
    readOnly: true
  name: get-job-requisition
- description: Edit an open job requisition
  hints:
    idempotent: true
    readOnly: false
  name: edit-job-requisition
- description: Close a job requisition that has no pending events
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: close-job-requisition
- description: Freeze or unfreeze a job requisition to halt or resume hiring
  hints:
    idempotent: true
    readOnly: false
  name: manage-job-requisition-freeze
- description: List evergreen requisitions used for ongoing hiring needs
  hints:
    idempotent: true
    readOnly: true
  name: list-evergreen-requisitions
- description: Create a new evergreen requisition for ongoing hiring needs
  hints:
    idempotent: false
    readOnly: false
  name: create-evergreen-requisition
- description: Get details of a specific evergreen requisition
  hints:
    idempotent: true
    readOnly: true
  name: get-evergreen-requisition
- description: Close an evergreen requisition with no pending events
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: close-evergreen-requisition
- description: List position management positions and their fill status
  hints:
    idempotent: true
    readOnly: true
  name: list-positions
- description: Create and open a new position in the position management staffing model
  hints:
    idempotent: false
    readOnly: false
  name: create-position
- description: List job postings with optional filters by requisition or posting site
  hints:
    idempotent: true
    readOnly: true
  name: list-job-postings
- description: Get details of a specific job posting
  hints:
    idempotent: true
    readOnly: true
  name: get-job-posting
- description: Update an existing job posting (start/end dates)
  hints:
    idempotent: true
    readOnly: false
  name: update-job-posting
- description: Post a job to internal and external career sites
  hints:
    idempotent: true
    readOnly: false
  name: post-job
- description: Remove a job posting from career sites
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: unpost-job
---
