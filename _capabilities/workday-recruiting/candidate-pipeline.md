---
categories: []
consumed_apis: []
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
- list applicants
- list candidate attachments
- list candidates
- get a candidate's photo
- candidate-to-requisition links, stage progression, and offers.
- get the candidate photo
- assess candidate
- upload or replace a candidate's photo
- create candidate
- add candidate attachment
- submit an agency candidate
- candidate attachments
- create a candidate
- update an existing candidate record
- recruiter and sourcer workflow for managing candidates from sourcing through application progression, including profile management, assessments, referrals, stage moves, offers, bulk applicant import, and agency candidate submissions.
- individual candidate
- submit agency candidate
- worker assigned to evaluate candidates — submits interview feedback with competency ratings and hiring recommendations.
- individual recruiting agency
- hiring manager
- hiring needs, evergreen requisitions, and position management.
- update candidate
- refer a candidate
- initiate an employment offer for a job application
- recruiter and hiring manager workflow for scheduling interviews, collecting interviewer feedback, and running pre-hire background screening.
- builds candidate pipelines from external sourcing tools and job boards into workday requisitions.
- get candidate photo
- update candidate photo
- workday
- compliance analyst
- recruiter
- import applicants in bulk
- submit a candidate referral from an existing worker
- drives the day-to-day hiring process — manages requisitions, progresses candidates through stages, schedules interviews, and coordinates screening.
- refer candidate
- recruiting
- get details of a specific job application and its current stage
- submit a candidate from a recruiting agency for a job requisition
- eeo, ofccp, and veteran self-identification reference values.
- owns hiring decisions for a team — opens and edits requisitions, reviews finalists, and approves offers.
- configures recruiting reference data — career sites, questionnaires, and reference values used across the recruiting workflows.
- list recruiting agencies configured for external sourcing
- move candidate stage
- get details of a specific recruiting agency
- list candidate profiles with filters by name, email, or update date
- pre-hire records and high-volume bulk applicant import.
- interview scheduling and interviewer feedback collection.
- add a candidate attachment
- list job applications with filters by requisition, candidate, or stage
- initiate offer
- recruiting agency
- saas
- initiate an offer
- external agency relationships and candidate submissions.
- hcm
- move candidate to a different stage
- recruiting administrator workflow for retrieving recruiting configuration and reference data — job posting sites, screening questionnaires, and veteran status values for eeo and ofccp compliance.
- update a candidate
- high-volume bulk applicant import for retail, hospitality, or seasonal hiring
- list job applications
- get a candidate's full profile and application history
- update the candidate photo
- recruiting configuration and reference data.
- individual job application
- get a candidate
- recruiting admin
- job applications
- get a job application
- candidates
- assess a candidate
- upload a resume, cover letter, or other attachment to a candidate
- hiring manager and recruiter workflow for opening, modifying, freezing, and closing job requisitions and evergreen requisitions, creating positions, and posting jobs to career sites.
- list recruiting agencies
- create a new candidate record
- get a recruiting agency
- list pre-hire and applicant records
- recruiting agencies
- bulk applicant import
- pre-hire background screening and check packages.
- candidate assessment
- public publication of requisitions to internal and external career sites.
- import applicants
- talent acquisition
- list resumes, cover letters, and other attachments for a candidate
- interviewer
- move a candidate to a different recruiting or disposition stage
- submit agency candidates
- candidate referral
- submit a candidate assessment and optionally advance the application
- get candidate
- human resources
- get job application
- candidate photo
- get recruiting agency
- candidate profiles, attachments, photos, assessments, and referrals.
- pulls eeo, ofccp, and veteran self-identification reference data for regulatory reporting.
- applicants
- external staffing partner that submits candidates against open requisitions through the agency portal.
- sourcer
slug: candidate-pipeline
source_filename: candidate-pipeline.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Workday Recruiting Candidate Pipeline\n  description: Recruiter and sourcer workflow for managing the candidate pipeline from sourcing through application progression.\n    Covers candidate profile and attachment management, candidate assessments and referrals, job application stage moves and\n    offer initiation, high-volume applicant import, and recruiting agency candidate submissions.\n  tags:\n  - Workday\n  - Recruiting\n  - Candidates\n  - Job Applications\n  - Applicants\n  - Recruiting Agencies\n  - HCM\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WORKDAY_RECRUITING_TOKEN: WORKDAY_RECRUITING_TOKEN\n    WORKDAY_TENANT: WORKDAY_TENANT\ncapability:\n  consumes:\n  - type: http\n    namespace: recruiting\n    baseUri: https://{{WORKDAY_TENANT}}.workday.com/ccx/api/recruiting/v41.2\n    description: Workday Recruiting REST API for managing the full hiring lifecycle.\n    authentication:\n\
  \      type: bearer\n      token: '{{WORKDAY_RECRUITING_TOKEN}}'\n    resources:\n    - name: job-requisitions\n      path: /jobRequisitions\n      description: Job requisition collection\n      operations:\n      - name: list-job-requisitions\n        method: GET\n        description: Retrieve a collection of job requisitions with optional filters\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status (Open, Filled, Frozen, Closed, Draft)\n        - name: supervisoryOrganization\n          in: query\n          type: string\n          required: false\n          description: Filter by supervisory organization\
  \ Workday ID\n        - name: updatedFrom\n          in: query\n          type: string\n          required: false\n          description: Return requisitions updated on or after this date-time\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-job-requisition\n        method: POST\n        description: Create a new job requisition for a position\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            jobProfile: '{{tools.jobProfile}}'\n            position: '{{tools.position}}'\n            supervisoryOrganization: '{{tools.supervisoryOrganization}}'\n            hiringManager: '{{tools.hiringManager}}'\n            recruiter: '{{tools.recruiter}}'\n            numberOfOpenings: '{{tools.numberOfOpenings}}'\n            location: '{{tools.location}}'\n            workerType: '{{tools.workerType}}'\n            timeType: '{{tools.timeType}}'\n\
  \            targetHireDate: '{{tools.targetHireDate}}'\n            jobDescription: '{{tools.jobDescription}}'\n            qualifications: '{{tools.qualifications}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-requisition-by-id\n      path: /jobRequisitions/{jobRequisitionId}\n      description: Individual job requisition\n      operations:\n      - name: get-job-requisition\n        method: GET\n        description: Retrieve details of a specific job requisition\n        inputParameters:\n        - name: jobRequisitionId\n          in: path\n          type: string\n          required: true\n          description: Job requisition Workday ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: edit-job-requisition\n        method: PATCH\n        description: Update an open job requisition\n        inputParameters:\n\
  \        - name: jobRequisitionId\n          in: path\n          type: string\n          required: true\n          description: Job requisition Workday ID\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            jobProfile: '{{tools.jobProfile}}'\n            numberOfOpenings: '{{tools.numberOfOpenings}}'\n            location: '{{tools.location}}'\n            workerType: '{{tools.workerType}}'\n            timeType: '{{tools.timeType}}'\n            targetHireDate: '{{tools.targetHireDate}}'\n            jobDescription: '{{tools.jobDescription}}'\n            qualifications: '{{tools.qualifications}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-requisition-close\n      path: /jobRequisitions/{jobRequisitionId}/close\n      description: Close a job requisition\n      operations:\n      - name: close-job-requisition\n        method: POST\n\
  \        description: Close a job requisition that has no pending events\n        inputParameters:\n        - name: jobRequisitionId\n          in: path\n          type: string\n          required: true\n          description: Job requisition Workday ID\n        body:\n          type: json\n          data:\n            closeReason: '{{tools.closeReason}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-requisition-freeze\n      path: /jobRequisitions/{jobRequisitionId}/freeze\n      description: Freeze or unfreeze a job requisition\n      operations:\n      - name: manage-job-requisition-freeze\n        method: POST\n        description: Freeze or unfreeze a job requisition\n        inputParameters:\n        - name: jobRequisitionId\n          in: path\n          type: string\n          required: true\n          description: Job requisition Workday ID\n        body:\n          type: json\n \
  \         data:\n            freeze: '{{tools.freeze}}'\n            reason: '{{tools.reason}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: evergreen-requisitions\n      path: /evergreenRequisitions\n      description: Evergreen requisition collection\n      operations:\n      - name: list-evergreen-requisitions\n        method: GET\n        description: Retrieve a collection of evergreen requisitions\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-evergreen-requisition\n        method:\
  \ POST\n        description: Create a new evergreen requisition for ongoing hiring needs\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            jobProfile: '{{tools.jobProfile}}'\n            supervisoryOrganization: '{{tools.supervisoryOrganization}}'\n            hiringManager: '{{tools.hiringManager}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: evergreen-requisition-by-id\n      path: /evergreenRequisitions/{evergreenRequisitionId}\n      description: Individual evergreen requisition\n      operations:\n      - name: get-evergreen-requisition\n        method: GET\n        description: Retrieve details of a specific evergreen requisition\n        inputParameters:\n        - name: evergreenRequisitionId\n          in: path\n          type: string\n          required: true\n          description: Evergreen requisition Workday ID\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: evergreen-requisition-close\n      path: /evergreenRequisitions/{evergreenRequisitionId}/close\n      description: Close an evergreen requisition\n      operations:\n      - name: close-evergreen-requisition\n        method: POST\n        description: Close an evergreen requisition with no pending events\n        inputParameters:\n        - name: evergreenRequisitionId\n          in: path\n          type: string\n          required: true\n          description: Evergreen requisition Workday ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidates\n      path: /candidates\n      description: Candidate collection\n      operations:\n      - name: list-candidates\n        method: GET\n        description: Retrieve a collection of candidates with optional filters\n        inputParameters:\n\
  \        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: updatedFrom\n          in: query\n          type: string\n          required: false\n          description: Return candidates updated on or after this date-time\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Filter candidates by name (partial match)\n        - name: email\n          in: query\n          type: string\n          required: false\n          description: Filter candidates by email address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-candidate\n        method: POST\n        description: Create a new candidate\
  \ record\n        body:\n          type: json\n          data:\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            email: '{{tools.email}}'\n            phone: '{{tools.phone}}'\n            address: '{{tools.address}}'\n            source: '{{tools.source}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidate-by-id\n      path: /candidates/{candidateId}\n      description: Individual candidate\n      operations:\n      - name: get-candidate\n        method: GET\n        description: Retrieve details of a specific candidate\n        inputParameters:\n        - name: candidateId\n          in: path\n          type: string\n          required: true\n          description: Candidate Workday ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-candidate\n\
  \        method: PATCH\n        description: Update an existing candidate record\n        inputParameters:\n        - name: candidateId\n          in: path\n          type: string\n          required: true\n          description: Candidate Workday ID\n        body:\n          type: json\n          data:\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            email: '{{tools.email}}'\n            phone: '{{tools.phone}}'\n            address: '{{tools.address}}'\n            source: '{{tools.source}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidate-attachments\n      path: /candidates/{candidateId}/attachments\n      description: Candidate attachments\n      operations:\n      - name: list-candidate-attachments\n        method: GET\n        description: Retrieve attachments for a candidate\n        inputParameters:\n        - name: candidateId\n\
  \          in: path\n          type: string\n          required: true\n          description: Candidate Workday ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-candidate-attachment\n        method: POST\n        description: Upload an attachment to a candidate record\n        inputParameters:\n        - name: candidateId\n          in: path\n          type: string\n          required: true\n          description: Candidate Workday ID\n        body:\n          type: multipart\n          data:\n            file: '{{tools.file}}'\n            category: '{{tools.category}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidate-photo\n      path: /candidates/{candidateId}/photo\n      description: Candidate photo\n      operations:\n      - name: get-candidate-photo\n        method: GET\n        description:\
  \ Retrieve the candidate photo\n        inputParameters:\n        - name: candidateId\n          in: path\n          type: string\n          required: true\n          description: Candidate Workday ID\n        outputRawFormat: binary\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-candidate-photo\n        method: PUT\n        description: Upload or replace the candidate photo\n        inputParameters:\n        - name: candidateId\n          in: path\n          type: string\n          required: true\n          description: Candidate Workday ID\n        body:\n          type: binary\n          data:\n            file: '{{tools.file}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidate-assess\n      path: /candidates/{candidateId}/assess\n      description: Candidate assessment\n      operations:\n      - name: assess-candidate\n\
  \        method: POST\n        description: Create or modify a candidate assessment\n        inputParameters:\n        - name: candidateId\n          in: path\n          type: string\n          required: true\n          description: Candidate Workday ID\n        body:\n          type: json\n          data:\n            assessmentCategory: '{{tools.assessmentCategory}}'\n            result: '{{tools.result}}'\n            score: '{{tools.score}}'\n            comments: '{{tools.comments}}'\n            assessedOn: '{{tools.assessedOn}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidate-refer\n      path: /candidates/{candidateId}/refer\n      description: Candidate referral\n      operations:\n      - name: refer-candidate\n        method: POST\n        description: Submit a candidate referral from an existing worker\n        inputParameters:\n        - name: candidateId\n          in: path\n\
  \          type: string\n          required: true\n          description: Candidate Workday ID\n        body:\n          type: json\n          data:\n            jobRequisition: '{{tools.jobRequisition}}'\n            referrer: '{{tools.referrer}}'\n            referralComments: '{{tools.referralComments}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-applications\n      path: /jobApplications\n      description: Job application collection\n      operations:\n      - name: list-job-applications\n        method: GET\n        description: Retrieve a collection of job applications with optional filters\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination\
  \ offset\n        - name: jobRequisition\n          in: query\n          type: string\n          required: false\n          description: Filter by job requisition Workday ID\n        - name: candidate\n          in: query\n          type: string\n          required: false\n          description: Filter by candidate Workday ID\n        - name: stage\n          in: query\n          type: string\n          required: false\n          description: Filter by recruiting stage\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-application-by-id\n      path: /jobApplications/{jobApplicationId}\n      description: Individual job application\n      operations:\n      - name: get-job-application\n        method: GET\n        description: Retrieve details of a specific job application\n        inputParameters:\n        - name: jobApplicationId\n          in: path\n          type: string\n          required:\
  \ true\n          description: Job application Workday ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-application-move\n      path: /jobApplications/{jobApplicationId}/move\n      description: Move candidate to a different stage\n      operations:\n      - name: move-candidate-stage\n        method: POST\n        description: Move a candidate to a different recruiting or disposition stage\n        inputParameters:\n        - name: jobApplicationId\n          in: path\n          type: string\n          required: true\n          description: Job application Workday ID\n        body:\n          type: json\n          data:\n            stage: '{{tools.stage}}'\n            reason: '{{tools.reason}}'\n            comments: '{{tools.comments}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-application-offer\n\
  \      path: /jobApplications/{jobApplicationId}/offer\n      description: Initiate an employment offer\n      operations:\n      - name: initiate-offer\n        method: POST\n        description: Initiate an employment offer for a job application\n        inputParameters:\n        - name: jobApplicationId\n          in: path\n          type: string\n          required: true\n          description: Job application Workday ID\n        body:\n          type: json\n          data:\n            proposedStartDate: '{{tools.proposedStartDate}}'\n            compensationAmount: '{{tools.compensationAmount}}'\n            compensationFrequency: '{{tools.compensationFrequency}}'\n            currency: '{{tools.currency}}'\n            expirationDate: '{{tools.expirationDate}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-postings\n      path: /jobPostings\n      description: Job posting collection\n\
  \      operations:\n      - name: list-job-postings\n        method: GET\n        description: Retrieve a collection of job postings with optional filters\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: jobRequisition\n          in: query\n          type: string\n          required: false\n          description: Filter by job requisition Workday ID\n        - name: postingSite\n          in: query\n          type: string\n          required: false\n          description: Filter by posting site Workday ID\n        - name: active\n          in: query\n          type: boolean\n          required: false\n          description: Filter by active posting status\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: job-posting-by-id\n      path: /jobPostings/{jobPostingId}\n      description: Individual job posting\n      operations:\n      - name: get-job-posting\n        method: GET\n        description: Retrieve details of a specific job posting\n        inputParameters:\n        - name: jobPostingId\n          in: path\n          type: string\n          required: true\n          description: Job posting Workday ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-job-posting\n        method: PATCH\n        description: Update an existing job posting\n        inputParameters:\n        - name: jobPostingId\n          in: path\n          type: string\n          required: true\n          description: Job posting Workday ID\n        body:\n          type: json\n          data:\n            startDate: '{{tools.startDate}}'\n\
  \            endDate: '{{tools.endDate}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-posting-post\n      path: /jobPostings/{jobPostingId}/post\n      description: Post a job to career sites\n      operations:\n      - name: post-job\n        method: POST\n        description: Post a job to internal and external career sites\n        inputParameters:\n        - name: jobPostingId\n          in: path\n          type: string\n          required: true\n          description: Job posting Workday ID\n        body:\n          type: json\n          data:\n            postingSites: '{{tools.postingSites}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-posting-unpost\n      path: /jobPostings/{jobPostingId}/unpost\n      description: Unpost a job from career sites\n      operations:\n      - name: unpost-job\n\
  \        method: POST\n        description: Remove a job posting from career sites\n        inputParameters:\n        - name: jobPostingId\n          in: path\n          type: string\n          required: true\n          description: Job posting Workday ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: interviews\n      path: /interviews\n      description: Interview collection\n      operations:\n      - name: list-interviews\n        method: GET\n        description: Retrieve a collection of scheduled interviews with optional filters\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: jobApplication\n          in: query\n\
  \          type: string\n          required: false\n          description: Filter by job application Workday ID\n        - name: dateFrom\n          in: query\n          type: string\n          required: false\n          description: Return interviews scheduled on or after this date\n        - name: dateTo\n          in: query\n          type: string\n          required: false\n          description: Return interviews scheduled on or before this date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: schedule-interview\n        method: POST\n        description: Schedule a new interview for a job application\n        body:\n          type: json\n          data:\n            jobApplication: '{{tools.jobApplication}}'\n            interviewType: '{{tools.interviewType}}'\n            scheduledDate: '{{tools.scheduledDate}}'\n            startTime: '{{tools.startTime}}'\n            endTime: '{{tools.endTime}}'\n\
  \            interviewers: '{{tools.interviewers}}'\n            location: '{{tools.location}}'\n            webConferenceUrl: '{{tools.webConferenceUrl}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: interview-by-id\n      path: /interviews/{interviewId}\n      description: Individual interview\n      operations:\n      - name: get-interview\n        method: GET\n        description: Retrieve details of a specific interview\n        inputParameters:\n        - name: interviewId\n          in: path\n          type: string\n          required: true\n          description: Interview Workday ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: interview-feedback\n      path: /interviews/{interviewId}/feedback\n      description: Interview feedback\n      operations:\n      - name: list-interview-feedback\n\
  \        method: GET\n        description: Retrieve feedback submitted for an interview\n        inputParameters:\n        - name: interviewId\n          in: path\n          type: string\n          required: true\n          description: Interview Workday ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: submit-interview-feedback\n        method: POST\n        description: Submit feedback for a completed interview\n        inputParameters:\n        - name: interviewId\n          in: path\n          type: string\n          required: true\n          description: Interview Workday ID\n        body:\n          type: json\n          data:\n            overallRating: '{{tools.overallRating}}'\n            competencyRatings: '{{tools.competencyRatings}}'\n            comments: '{{tools.comments}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: background-checks\n      path: /backgroundChecks\n      description: Background check collection\n      operations:\n      - name: list-background-checks\n        method: GET\n        description: Retrieve a collection of background check results\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: candidate\n          in: query\n          type: string\n          required: false\n          description: Filter by candidate Workday ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: submit-background-check\n        method: POST\n        description: Load background check results from an external\
  \ provider\n        body:\n          type: json\n          data:\n            candidate: '{{tools.candidate}}'\n            jobApplication: '{{tools.jobApplication}}'\n            package: '{{tools.package}}'\n            status: '{{tools.status}}'\n            result: '{{tools.result}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: background-check-packages\n      path: /backgroundCheckPackages\n      description: Background check package collection\n      operations:\n      - name: list-background-check-packages\n        method: GET\n        description: Retrieve available background check packages\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination\
  \ offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recruiting-agencies\n      path: /recruitingAgencies\n      description: Recruiting agency collection\n      operations:\n      - name: list-recruiting-agencies\n        method: GET\n        description: Retrieve a collection of recruiting agencies\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recruiting-agency-by-id\n      path: /recruitingAgencies/{recruitingAgencyId}\n      description: Individual recruiting agency\n      operations:\n   \
  \   - name: get-recruiting-agency\n        method: GET\n        description: Retrieve details of a specific recruiting agency\n        inputParameters:\n        - name: recruitingAgencyId\n          in: path\n          type: string\n          required: true\n          description: Recruiting agency Workday ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recruiting-agency-candidates\n      path: /recruitingAgencies/{recruitingAgencyId}/candidates\n      description: Submit candidates from a recruiting agency\n      operations:\n      - name: submit-agency-candidate\n        method: POST\n        description: Submit a candidate from a recruiting agency for a job requisition\n        inputParameters:\n        - name: recruitingAgencyId\n          in: path\n          type: string\n          required: true\n          description: Recruiting agency Workday ID\n        body:\n          type: json\n\
  \          data:\n            candidate: '{{tools.candidate}}'\n            jobRequisition: '{{tools.jobRequisition}}'\n            agencyUser: '{{tools.agencyUser}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applicants\n      path: /applicants\n      description: Applicant collection\n      operations:\n      - name: list-applicants\n        method: GET\n        description: Retrieve pre-hire and applicant records\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applicants-import\n      path: /applicants/import\n\
  \      description: Bulk applicant import\n      operations:\n      - name: import-applicants\n        method: POST\n        description: High-volume applicant import for asynchronous bulk loading\n        body:\n          type: json\n          data:\n            applicants: '{{tools.applicants}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: positions\n      path: /positions\n      description: Position management\n      operations:\n      - name: list-positions\n        method: GET\n        description: Retrieve position management positions\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-position\n        method: POST\n        description: Create and open a new position\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            jobProfile: '{{tools.jobProfile}}'\n            supervisoryOrganization: '{{tools.supervisoryOrganization}}'\n            location: '{{tools.location}}'\n            workerType: '{{tools.workerType}}'\n            timeType: '{{tools.timeType}}'\n            availableDate: '{{tools.availableDate}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-posting-sites\n      path: /jobPostingSites\n      description: Job posting site configuration\n      operations:\n      - name: list-job-posting-sites\n        method: GET\n        description: Retrieve available job posting sites\n        inputParameters:\n        - name: limit\n\
  \          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: questionnaires\n      path: /questionnaires\n      description: Recruiting questionnaires\n      operations:\n      - name: list-questionnaires\n        method: GET\n        description: Retrieve recruiting questionnaires for screening and assessment\n        inputParameters:\n \n\n# --- truncated at 32 KB (45 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/workday-recruiting/refs/heads/main/capabilities/candidate-pipeline.yaml\n"
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
