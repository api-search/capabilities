---
categories: []
consumed_apis:
- recruiting
description: Recruiter and sourcer workflow for managing the candidate pipeline from sourcing through application progression. Covers candidate profile and attachment management, candidate assessments and referrals, job application stage moves and offer initiation, high-volume applicant import, and recruiting agency candidate submissions.
layout: capability
name: Workday Recruiting Candidate Pipeline
operations:
- description: List candidates
  method: GET
  name: list-candidates
  path: /v1/candidates
- description: Create a candidate
  method: POST
  name: create-candidate
  path: /v1/candidates
- description: Get a candidate
  method: GET
  name: get-candidate
  path: /v1/candidates/{candidateId}
- description: Update a candidate
  method: PATCH
  name: update-candidate
  path: /v1/candidates/{candidateId}
- description: List candidate attachments
  method: GET
  name: list-candidate-attachments
  path: /v1/candidates/{candidateId}/attachments
- description: Add a candidate attachment
  method: POST
  name: add-candidate-attachment
  path: /v1/candidates/{candidateId}/attachments
- description: Get the candidate photo
  method: GET
  name: get-candidate-photo
  path: /v1/candidates/{candidateId}/photo
- description: Update the candidate photo
  method: PUT
  name: update-candidate-photo
  path: /v1/candidates/{candidateId}/photo
- description: Assess a candidate
  method: POST
  name: assess-candidate
  path: /v1/candidates/{candidateId}/assess
- description: Refer a candidate
  method: POST
  name: refer-candidate
  path: /v1/candidates/{candidateId}/refer
- description: List job applications
  method: GET
  name: list-job-applications
  path: /v1/job-applications
- description: Get a job application
  method: GET
  name: get-job-application
  path: /v1/job-applications/{jobApplicationId}
- description: Move candidate to a different stage
  method: POST
  name: move-candidate-stage
  path: /v1/job-applications/{jobApplicationId}/move
- description: Initiate an offer
  method: POST
  name: initiate-offer
  path: /v1/job-applications/{jobApplicationId}/offer
- description: List applicants
  method: GET
  name: list-applicants
  path: /v1/applicants
- description: Import applicants in bulk
  method: POST
  name: import-applicants
  path: /v1/applicants/import
- description: List recruiting agencies
  method: GET
  name: list-recruiting-agencies
  path: /v1/recruiting-agencies
- description: Get a recruiting agency
  method: GET
  name: get-recruiting-agency
  path: /v1/recruiting-agencies/{recruitingAgencyId}
- description: Submit an agency candidate
  method: POST
  name: submit-agency-candidate
  path: /v1/recruiting-agencies/{recruitingAgencyId}/candidates
personas: []
provider_name: Workday Recruiting
provider_slug: workday-recruiting
search_terms:
- submit an agency candidate
- drives the day-to-day hiring process — manages requisitions, progresses candidates through stages, schedules interviews, and coordinates screening.
- public publication of requisitions to internal and external career sites.
- recruiter and hiring manager workflow for scheduling interviews, collecting interviewer feedback, and running pre-hire background screening.
- recruiting agencies
- update candidate photo
- create a new candidate record
- list recruiting agencies configured for external sourcing
- owns hiring decisions for a team — opens and edits requisitions, reviews finalists, and approves offers.
- get a candidate
- pre-hire background screening and check packages.
- update the candidate photo
- external agency relationships and candidate submissions.
- applicants
- get a recruiting agency
- initiate offer
- list resumes, cover letters, and other attachments for a candidate
- recruiting admin
- import applicants in bulk
- initiate an employment offer for a job application
- add a candidate attachment
- saas
- interview scheduling and interviewer feedback collection.
- list candidate attachments
- candidate referral
- create a candidate
- list applicants
- candidates
- compliance analyst
- move candidate to a different stage
- individual job application
- submit agency candidate
- recruiting
- job applications
- refer a candidate
- submit agency candidates
- get details of a specific job application and its current stage
- candidate-to-requisition links, stage progression, and offers.
- candidate attachments
- recruiting configuration and reference data.
- create candidate
- pre-hire records and high-volume bulk applicant import.
- submit a candidate from a recruiting agency for a job requisition
- list candidates
- update candidate
- pulls eeo, ofccp, and veteran self-identification reference data for regulatory reporting.
- move candidate stage
- get a candidate's full profile and application history
- update an existing candidate record
- bulk applicant import
- hcm
- human resources
- get a candidate's photo
- list candidate profiles with filters by name, email, or update date
- recruiting administrator workflow for retrieving recruiting configuration and reference data — job posting sites, screening questionnaires, and veteran status values for eeo and ofccp compliance.
- get a job application
- configures recruiting reference data — career sites, questionnaires, and reference values used across the recruiting workflows.
- high-volume bulk applicant import for retail, hospitality, or seasonal hiring
- talent acquisition
- list job applications
- recruiter
- individual candidate
- recruiting agency
- list job applications with filters by requisition, candidate, or stage
- recruiter and sourcer workflow for managing candidates from sourcing through application progression, including profile management, assessments, referrals, stage moves, offers, bulk applicant import, and agency candidate submissions.
- upload a resume, cover letter, or other attachment to a candidate
- hiring manager
- get the candidate photo
- list recruiting agencies
- initiate an offer
- update a candidate
- submit a candidate assessment and optionally advance the application
- builds candidate pipelines from external sourcing tools and job boards into workday requisitions.
- get candidate
- add candidate attachment
- assess candidate
- external staffing partner that submits candidates against open requisitions through the agency portal.
- workday
- get job application
- sourcer
- upload or replace a candidate's photo
- candidate photo
- worker assigned to evaluate candidates — submits interview feedback with competency ratings and hiring recommendations.
- move a candidate to a different recruiting or disposition stage
- refer candidate
- hiring manager and recruiter workflow for opening, modifying, freezing, and closing job requisitions and evergreen requisitions, creating positions, and posting jobs to career sites.
- get recruiting agency
- assess a candidate
- hiring needs, evergreen requisitions, and position management.
- list pre-hire and applicant records
- candidate profiles, attachments, photos, assessments, and referrals.
- candidate assessment
- submit a candidate referral from an existing worker
- individual recruiting agency
- import applicants
- get details of a specific recruiting agency
- get candidate photo
- interviewer
- eeo, ofccp, and veteran self-identification reference values.
slug: candidate-pipeline
source_filename: candidate-pipeline.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Workday Recruiting Candidate Pipeline\"\n  description: >-\n    Recruiter and sourcer workflow for managing the candidate pipeline from\n    sourcing through application progression. Covers candidate profile and\n    attachment management, candidate assessments and referrals, job application\n    stage moves and offer initiation, high-volume applicant import, and\n    recruiting agency candidate submissions.\n  tags:\n    - Workday\n    - Recruiting\n    - Candidates\n    - Job Applications\n    - Applicants\n    - Recruiting Agencies\n    - HCM\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WORKDAY_RECRUITING_TOKEN: WORKDAY_RECRUITING_TOKEN\n      WORKDAY_TENANT: WORKDAY_TENANT\n\ncapability:\n  consumes:\n    - import: recruiting\n      location: ./shared/recruiting.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: candidate-pipeline-api\n      description:\
  \ \"Unified REST API for candidate sourcing, application tracking, and offers.\"\n      resources:\n        - path: /v1/candidates\n          name: candidates\n          description: \"Candidates\"\n          operations:\n            - method: GET\n              name: list-candidates\n              description: \"List candidates\"\n              call: \"recruiting.list-candidates\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-candidate\n              description: \"Create a candidate\"\n              call: \"recruiting.create-candidate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/candidates/{candidateId}\n          name: candidate-by-id\n          description: \"Individual candidate\"\n          operations:\n            - method: GET\n              name: get-candidate\n              description: \"Get\
  \ a candidate\"\n              call: \"recruiting.get-candidate\"\n              with:\n                candidateId: \"rest.candidateId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-candidate\n              description: \"Update a candidate\"\n              call: \"recruiting.update-candidate\"\n              with:\n                candidateId: \"rest.candidateId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/candidates/{candidateId}/attachments\n          name: candidate-attachments\n          description: \"Candidate attachments\"\n          operations:\n            - method: GET\n              name: list-candidate-attachments\n              description: \"List candidate attachments\"\n              call: \"recruiting.list-candidate-attachments\"\n              with:\n                candidateId: \"\
  rest.candidateId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-candidate-attachment\n              description: \"Add a candidate attachment\"\n              call: \"recruiting.add-candidate-attachment\"\n              with:\n                candidateId: \"rest.candidateId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/candidates/{candidateId}/photo\n          name: candidate-photo\n          description: \"Candidate photo\"\n          operations:\n            - method: GET\n              name: get-candidate-photo\n              description: \"Get the candidate photo\"\n              call: \"recruiting.get-candidate-photo\"\n              with:\n                candidateId: \"rest.candidateId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n         \
  \   - method: PUT\n              name: update-candidate-photo\n              description: \"Update the candidate photo\"\n              call: \"recruiting.update-candidate-photo\"\n              with:\n                candidateId: \"rest.candidateId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/candidates/{candidateId}/assess\n          name: candidate-assess\n          description: \"Candidate assessment\"\n          operations:\n            - method: POST\n              name: assess-candidate\n              description: \"Assess a candidate\"\n              call: \"recruiting.assess-candidate\"\n              with:\n                candidateId: \"rest.candidateId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/candidates/{candidateId}/refer\n          name: candidate-refer\n          description: \"Candidate referral\"\n          operations:\n\
  \            - method: POST\n              name: refer-candidate\n              description: \"Refer a candidate\"\n              call: \"recruiting.refer-candidate\"\n              with:\n                candidateId: \"rest.candidateId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/job-applications\n          name: job-applications\n          description: \"Job applications\"\n          operations:\n            - method: GET\n              name: list-job-applications\n              description: \"List job applications\"\n              call: \"recruiting.list-job-applications\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/job-applications/{jobApplicationId}\n          name: job-application-by-id\n          description: \"Individual job application\"\n          operations:\n            - method: GET\n              name: get-job-application\n\
  \              description: \"Get a job application\"\n              call: \"recruiting.get-job-application\"\n              with:\n                jobApplicationId: \"rest.jobApplicationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/job-applications/{jobApplicationId}/move\n          name: job-application-move\n          description: \"Move candidate stage\"\n          operations:\n            - method: POST\n              name: move-candidate-stage\n              description: \"Move candidate to a different stage\"\n              call: \"recruiting.move-candidate-stage\"\n              with:\n                jobApplicationId: \"rest.jobApplicationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/job-applications/{jobApplicationId}/offer\n          name: job-application-offer\n          description: \"Initiate offer\"\n          operations:\n\
  \            - method: POST\n              name: initiate-offer\n              description: \"Initiate an offer\"\n              call: \"recruiting.initiate-offer\"\n              with:\n                jobApplicationId: \"rest.jobApplicationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applicants\n          name: applicants\n          description: \"Applicants\"\n          operations:\n            - method: GET\n              name: list-applicants\n              description: \"List applicants\"\n              call: \"recruiting.list-applicants\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applicants/import\n          name: applicants-import\n          description: \"Bulk applicant import\"\n          operations:\n            - method: POST\n              name: import-applicants\n              description: \"Import applicants in bulk\"\
  \n              call: \"recruiting.import-applicants\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/recruiting-agencies\n          name: recruiting-agencies\n          description: \"Recruiting agencies\"\n          operations:\n            - method: GET\n              name: list-recruiting-agencies\n              description: \"List recruiting agencies\"\n              call: \"recruiting.list-recruiting-agencies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/recruiting-agencies/{recruitingAgencyId}\n          name: recruiting-agency-by-id\n          description: \"Individual recruiting agency\"\n          operations:\n            - method: GET\n              name: get-recruiting-agency\n              description: \"Get a recruiting agency\"\n              call: \"recruiting.get-recruiting-agency\"\n              with:\n               \
  \ recruitingAgencyId: \"rest.recruitingAgencyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/recruiting-agencies/{recruitingAgencyId}/candidates\n          name: recruiting-agency-candidates\n          description: \"Submit agency candidates\"\n          operations:\n            - method: POST\n              name: submit-agency-candidate\n              description: \"Submit an agency candidate\"\n              call: \"recruiting.submit-agency-candidate\"\n              with:\n                recruitingAgencyId: \"rest.recruitingAgencyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: candidate-pipeline-mcp\n      transport: http\n      description: \"MCP server for AI-assisted candidate sourcing, screening, and application progression.\"\n      tools:\n        - name: list-candidates\n          description:\
  \ \"List candidate profiles with filters by name, email, or update date\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"recruiting.list-candidates\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-candidate\n          description: \"Create a new candidate record\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"recruiting.create-candidate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-candidate\n          description: \"Get a candidate's full profile and application history\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"recruiting.get-candidate\"\n          with:\n            candidateId: \"tools.candidateId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-candidate\n\
  \          description: \"Update an existing candidate record\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"recruiting.update-candidate\"\n          with:\n            candidateId: \"tools.candidateId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-candidate-attachments\n          description: \"List resumes, cover letters, and other attachments for a candidate\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"recruiting.list-candidate-attachments\"\n          with:\n            candidateId: \"tools.candidateId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-candidate-attachment\n          description: \"Upload a resume, cover letter, or other attachment to a candidate\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call:\
  \ \"recruiting.add-candidate-attachment\"\n          with:\n            candidateId: \"tools.candidateId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-candidate-photo\n          description: \"Get a candidate's photo\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"recruiting.get-candidate-photo\"\n          with:\n            candidateId: \"tools.candidateId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-candidate-photo\n          description: \"Upload or replace a candidate's photo\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"recruiting.update-candidate-photo\"\n          with:\n            candidateId: \"tools.candidateId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: assess-candidate\n        \
  \  description: \"Submit a candidate assessment and optionally advance the application\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"recruiting.assess-candidate\"\n          with:\n            candidateId: \"tools.candidateId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: refer-candidate\n          description: \"Submit a candidate referral from an existing worker\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"recruiting.refer-candidate\"\n          with:\n            candidateId: \"tools.candidateId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-job-applications\n          description: \"List job applications with filters by requisition, candidate, or stage\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"recruiting.list-job-applications\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-job-application\n          description: \"Get details of a specific job application and its current stage\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"recruiting.get-job-application\"\n          with:\n            jobApplicationId: \"tools.jobApplicationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: move-candidate-stage\n          description: \"Move a candidate to a different recruiting or disposition stage\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"recruiting.move-candidate-stage\"\n          with:\n            jobApplicationId: \"tools.jobApplicationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: initiate-offer\n          description: \"Initiate\
  \ an employment offer for a job application\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"recruiting.initiate-offer\"\n          with:\n            jobApplicationId: \"tools.jobApplicationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-applicants\n          description: \"List pre-hire and applicant records\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"recruiting.list-applicants\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: import-applicants\n          description: \"High-volume bulk applicant import for retail, hospitality, or seasonal hiring\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"recruiting.import-applicants\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\
  \        - name: list-recruiting-agencies\n          description: \"List recruiting agencies configured for external sourcing\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"recruiting.list-recruiting-agencies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-recruiting-agency\n          description: \"Get details of a specific recruiting agency\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"recruiting.get-recruiting-agency\"\n          with:\n            recruitingAgencyId: \"tools.recruitingAgencyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-agency-candidate\n          description: \"Submit a candidate from a recruiting agency for a job requisition\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"recruiting.submit-agency-candidate\"\
  \n          with:\n            recruitingAgencyId: \"tools.recruitingAgencyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday-recruiting/refs/heads/main/capabilities/candidate-pipeline.yaml
tags:
- Workday
- Recruiting
- Candidates
- Job Applications
- Applicants
- Recruiting Agencies
- HCM
tools:
- description: List candidate profiles with filters by name, email, or update date
  hints:
    idempotent: true
    readOnly: true
  name: list-candidates
- description: Create a new candidate record
  hints:
    idempotent: false
    readOnly: false
  name: create-candidate
- description: Get a candidate's full profile and application history
  hints:
    idempotent: true
    readOnly: true
  name: get-candidate
- description: Update an existing candidate record
  hints:
    idempotent: true
    readOnly: false
  name: update-candidate
- description: List resumes, cover letters, and other attachments for a candidate
  hints:
    idempotent: true
    readOnly: true
  name: list-candidate-attachments
- description: Upload a resume, cover letter, or other attachment to a candidate
  hints:
    idempotent: false
    readOnly: false
  name: add-candidate-attachment
- description: Get a candidate's photo
  hints:
    idempotent: true
    readOnly: true
  name: get-candidate-photo
- description: Upload or replace a candidate's photo
  hints:
    idempotent: true
    readOnly: false
  name: update-candidate-photo
- description: Submit a candidate assessment and optionally advance the application
  hints:
    idempotent: false
    readOnly: false
  name: assess-candidate
- description: Submit a candidate referral from an existing worker
  hints:
    idempotent: false
    readOnly: false
  name: refer-candidate
- description: List job applications with filters by requisition, candidate, or stage
  hints:
    idempotent: true
    readOnly: true
  name: list-job-applications
- description: Get details of a specific job application and its current stage
  hints:
    idempotent: true
    readOnly: true
  name: get-job-application
- description: Move a candidate to a different recruiting or disposition stage
  hints:
    idempotent: false
    readOnly: false
  name: move-candidate-stage
- description: Initiate an employment offer for a job application
  hints:
    idempotent: false
    readOnly: false
  name: initiate-offer
- description: List pre-hire and applicant records
  hints:
    idempotent: true
    readOnly: true
  name: list-applicants
- description: High-volume bulk applicant import for retail, hospitality, or seasonal hiring
  hints:
    idempotent: false
    readOnly: false
  name: import-applicants
- description: List recruiting agencies configured for external sourcing
  hints:
    idempotent: true
    readOnly: true
  name: list-recruiting-agencies
- description: Get details of a specific recruiting agency
  hints:
    idempotent: true
    readOnly: true
  name: get-recruiting-agency
- description: Submit a candidate from a recruiting agency for a job requisition
  hints:
    idempotent: false
    readOnly: false
  name: submit-agency-candidate
---
