---
categories: []
consumed_apis: []
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
- close a job requisition
- close a job requisition that has no pending events
- candidate-to-requisition links, stage progression, and offers.
- post job
- remove a job posting from career sites
- recruiter and sourcer workflow for managing candidates from sourcing through application progression, including profile management, assessments, referrals, stage moves, offers, bulk applicant import, and agency candidate submissions.
- freeze or unfreeze a job requisition to halt or resume hiring
- get details of a specific job requisition
- edit job requisition
- create a position
- get details of a specific evergreen requisition
- worker assigned to evaluate candidates — submits interview feedback with competency ratings and hiring recommendations.
- create a new evergreen requisition for ongoing hiring needs
- list job requisitions with optional filters by status, organization, or update date
- list position management positions and their fill status
- hiring manager
- hiring needs, evergreen requisitions, and position management.
- manage job requisition freeze
- create a job requisition
- create a new job requisition for an open position
- job requisitions
- get a job requisition
- close job requisition
- list evergreen requisitions
- list job requisitions
- positions
- recruiter and hiring manager workflow for scheduling interviews, collecting interviewer feedback, and running pre-hire background screening.
- builds candidate pipelines from external sourcing tools and job boards into workday requisitions.
- post a job to internal and external career sites
- unpost a job from career sites
- get evergreen requisition
- get job posting
- workday
- compliance analyst
- recruiter
- drives the day-to-day hiring process — manages requisitions, progresses candidates through stages, schedules interviews, and coordinates screening.
- get job requisition
- list evergreen requisitions used for ongoing hiring needs
- update job posting
- recruiting
- individual evergreen requisition
- eeo, ofccp, and veteran self-identification reference values.
- create an evergreen requisition
- owns hiring decisions for a team — opens and edits requisitions, reviews finalists, and approves offers.
- configures recruiting reference data — career sites, questionnaires, and reference values used across the recruiting workflows.
- create evergreen requisition
- get a job posting
- post a job to career sites
- individual job posting
- edit an open job requisition
- pre-hire records and high-volume bulk applicant import.
- interview scheduling and interviewer feedback collection.
- edit a job requisition
- freeze or unfreeze a job requisition
- recruiting agency
- saas
- job postings
- hcm
- update a job posting
- external agency relationships and candidate submissions.
- recruiting administrator workflow for retrieving recruiting configuration and reference data — job posting sites, screening questionnaires, and veteran status values for eeo and ofccp compliance.
- get an evergreen requisition
- recruiting configuration and reference data.
- recruiting admin
- close an evergreen requisition
- evergreen requisitions
- close evergreen requisition
- hiring manager and recruiter workflow for opening, modifying, freezing, and closing job requisitions and evergreen requisitions, creating positions, and posting jobs to career sites.
- update an existing job posting (start/end dates)
- pre-hire background screening and check packages.
- close an evergreen requisition with no pending events
- public publication of requisitions to internal and external career sites.
- create job requisition
- create position
- talent acquisition
- get details of a specific job posting
- interviewer
- create and open a new position in the position management staffing model
- individual job requisition
- unpost job
- list job postings
- human resources
- candidate profiles, attachments, photos, assessments, and referrals.
- pulls eeo, ofccp, and veteran self-identification reference data for regulatory reporting.
- external staffing partner that submits candidates against open requisitions through the agency portal.
- sourcer
- list job postings with optional filters by requisition or posting site
- list positions
slug: requisition-management
source_filename: requisition-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Workday Recruiting Requisition Management\n  description: Hiring manager and recruiter workflow for opening, modifying, freezing, and closing job requisitions and evergreen\n    requisitions, creating positions in the position management staffing model, and posting jobs to internal and external\n    career sites.\n  tags:\n  - Workday\n  - Recruiting\n  - Job Requisitions\n  - Job Postings\n  - Positions\n  - HCM\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WORKDAY_RECRUITING_TOKEN: WORKDAY_RECRUITING_TOKEN\n    WORKDAY_TENANT: WORKDAY_TENANT\ncapability:\n  consumes:\n  - type: http\n    namespace: recruiting\n    baseUri: https://{{WORKDAY_TENANT}}.workday.com/ccx/api/recruiting/v41.2\n    description: Workday Recruiting REST API for managing the full hiring lifecycle.\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_RECRUITING_TOKEN}}'\n    resources:\n    - name: job-requisitions\n\
  \      path: /jobRequisitions\n      description: Job requisition collection\n      operations:\n      - name: list-job-requisitions\n        method: GET\n        description: Retrieve a collection of job requisitions with optional filters\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status (Open, Filled, Frozen, Closed, Draft)\n        - name: supervisoryOrganization\n          in: query\n          type: string\n          required: false\n          description: Filter by supervisory organization Workday ID\n        - name: updatedFrom\n          in: query\n          type: string\n          required:\
  \ false\n          description: Return requisitions updated on or after this date-time\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-job-requisition\n        method: POST\n        description: Create a new job requisition for a position\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            jobProfile: '{{tools.jobProfile}}'\n            position: '{{tools.position}}'\n            supervisoryOrganization: '{{tools.supervisoryOrganization}}'\n            hiringManager: '{{tools.hiringManager}}'\n            recruiter: '{{tools.recruiter}}'\n            numberOfOpenings: '{{tools.numberOfOpenings}}'\n            location: '{{tools.location}}'\n            workerType: '{{tools.workerType}}'\n            timeType: '{{tools.timeType}}'\n            targetHireDate: '{{tools.targetHireDate}}'\n            jobDescription: '{{tools.jobDescription}}'\n\
  \            qualifications: '{{tools.qualifications}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-requisition-by-id\n      path: /jobRequisitions/{jobRequisitionId}\n      description: Individual job requisition\n      operations:\n      - name: get-job-requisition\n        method: GET\n        description: Retrieve details of a specific job requisition\n        inputParameters:\n        - name: jobRequisitionId\n          in: path\n          type: string\n          required: true\n          description: Job requisition Workday ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: edit-job-requisition\n        method: PATCH\n        description: Update an open job requisition\n        inputParameters:\n        - name: jobRequisitionId\n          in: path\n          type: string\n          required:\
  \ true\n          description: Job requisition Workday ID\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            jobProfile: '{{tools.jobProfile}}'\n            numberOfOpenings: '{{tools.numberOfOpenings}}'\n            location: '{{tools.location}}'\n            workerType: '{{tools.workerType}}'\n            timeType: '{{tools.timeType}}'\n            targetHireDate: '{{tools.targetHireDate}}'\n            jobDescription: '{{tools.jobDescription}}'\n            qualifications: '{{tools.qualifications}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-requisition-close\n      path: /jobRequisitions/{jobRequisitionId}/close\n      description: Close a job requisition\n      operations:\n      - name: close-job-requisition\n        method: POST\n        description: Close a job requisition that has no pending events\n        inputParameters:\n\
  \        - name: jobRequisitionId\n          in: path\n          type: string\n          required: true\n          description: Job requisition Workday ID\n        body:\n          type: json\n          data:\n            closeReason: '{{tools.closeReason}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-requisition-freeze\n      path: /jobRequisitions/{jobRequisitionId}/freeze\n      description: Freeze or unfreeze a job requisition\n      operations:\n      - name: manage-job-requisition-freeze\n        method: POST\n        description: Freeze or unfreeze a job requisition\n        inputParameters:\n        - name: jobRequisitionId\n          in: path\n          type: string\n          required: true\n          description: Job requisition Workday ID\n        body:\n          type: json\n          data:\n            freeze: '{{tools.freeze}}'\n            reason: '{{tools.reason}}'\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: evergreen-requisitions\n      path: /evergreenRequisitions\n      description: Evergreen requisition collection\n      operations:\n      - name: list-evergreen-requisitions\n        method: GET\n        description: Retrieve a collection of evergreen requisitions\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-evergreen-requisition\n        method: POST\n        description: Create a new evergreen requisition for ongoing hiring needs\n        body:\n\
  \          type: json\n          data:\n            title: '{{tools.title}}'\n            jobProfile: '{{tools.jobProfile}}'\n            supervisoryOrganization: '{{tools.supervisoryOrganization}}'\n            hiringManager: '{{tools.hiringManager}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: evergreen-requisition-by-id\n      path: /evergreenRequisitions/{evergreenRequisitionId}\n      description: Individual evergreen requisition\n      operations:\n      - name: get-evergreen-requisition\n        method: GET\n        description: Retrieve details of a specific evergreen requisition\n        inputParameters:\n        - name: evergreenRequisitionId\n          in: path\n          type: string\n          required: true\n          description: Evergreen requisition Workday ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n        \
  \  value: $.\n    - name: evergreen-requisition-close\n      path: /evergreenRequisitions/{evergreenRequisitionId}/close\n      description: Close an evergreen requisition\n      operations:\n      - name: close-evergreen-requisition\n        method: POST\n        description: Close an evergreen requisition with no pending events\n        inputParameters:\n        - name: evergreenRequisitionId\n          in: path\n          type: string\n          required: true\n          description: Evergreen requisition Workday ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidates\n      path: /candidates\n      description: Candidate collection\n      operations:\n      - name: list-candidates\n        method: GET\n        description: Retrieve a collection of candidates with optional filters\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required:\
  \ false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: updatedFrom\n          in: query\n          type: string\n          required: false\n          description: Return candidates updated on or after this date-time\n        - name: name\n          in: query\n          type: string\n          required: false\n          description: Filter candidates by name (partial match)\n        - name: email\n          in: query\n          type: string\n          required: false\n          description: Filter candidates by email address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-candidate\n        method: POST\n        description: Create a new candidate record\n        body:\n          type: json\n          data:\n            firstName:\
  \ '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            email: '{{tools.email}}'\n            phone: '{{tools.phone}}'\n            address: '{{tools.address}}'\n            source: '{{tools.source}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidate-by-id\n      path: /candidates/{candidateId}\n      description: Individual candidate\n      operations:\n      - name: get-candidate\n        method: GET\n        description: Retrieve details of a specific candidate\n        inputParameters:\n        - name: candidateId\n          in: path\n          type: string\n          required: true\n          description: Candidate Workday ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-candidate\n        method: PATCH\n        description: Update an existing candidate record\n\
  \        inputParameters:\n        - name: candidateId\n          in: path\n          type: string\n          required: true\n          description: Candidate Workday ID\n        body:\n          type: json\n          data:\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            email: '{{tools.email}}'\n            phone: '{{tools.phone}}'\n            address: '{{tools.address}}'\n            source: '{{tools.source}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidate-attachments\n      path: /candidates/{candidateId}/attachments\n      description: Candidate attachments\n      operations:\n      - name: list-candidate-attachments\n        method: GET\n        description: Retrieve attachments for a candidate\n        inputParameters:\n        - name: candidateId\n          in: path\n          type: string\n          required: true\n     \
  \     description: Candidate Workday ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-candidate-attachment\n        method: POST\n        description: Upload an attachment to a candidate record\n        inputParameters:\n        - name: candidateId\n          in: path\n          type: string\n          required: true\n          description: Candidate Workday ID\n        body:\n          type: multipart\n          data:\n            file: '{{tools.file}}'\n            category: '{{tools.category}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidate-photo\n      path: /candidates/{candidateId}/photo\n      description: Candidate photo\n      operations:\n      - name: get-candidate-photo\n        method: GET\n        description: Retrieve the candidate photo\n        inputParameters:\n      \
  \  - name: candidateId\n          in: path\n          type: string\n          required: true\n          description: Candidate Workday ID\n        outputRawFormat: binary\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-candidate-photo\n        method: PUT\n        description: Upload or replace the candidate photo\n        inputParameters:\n        - name: candidateId\n          in: path\n          type: string\n          required: true\n          description: Candidate Workday ID\n        body:\n          type: binary\n          data:\n            file: '{{tools.file}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidate-assess\n      path: /candidates/{candidateId}/assess\n      description: Candidate assessment\n      operations:\n      - name: assess-candidate\n        method: POST\n        description: Create or modify\
  \ a candidate assessment\n        inputParameters:\n        - name: candidateId\n          in: path\n          type: string\n          required: true\n          description: Candidate Workday ID\n        body:\n          type: json\n          data:\n            assessmentCategory: '{{tools.assessmentCategory}}'\n            result: '{{tools.result}}'\n            score: '{{tools.score}}'\n            comments: '{{tools.comments}}'\n            assessedOn: '{{tools.assessedOn}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidate-refer\n      path: /candidates/{candidateId}/refer\n      description: Candidate referral\n      operations:\n      - name: refer-candidate\n        method: POST\n        description: Submit a candidate referral from an existing worker\n        inputParameters:\n        - name: candidateId\n          in: path\n          type: string\n          required: true\n    \
  \      description: Candidate Workday ID\n        body:\n          type: json\n          data:\n            jobRequisition: '{{tools.jobRequisition}}'\n            referrer: '{{tools.referrer}}'\n            referralComments: '{{tools.referralComments}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-applications\n      path: /jobApplications\n      description: Job application collection\n      operations:\n      - name: list-job-applications\n        method: GET\n        description: Retrieve a collection of job applications with optional filters\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: jobRequisition\n   \
  \       in: query\n          type: string\n          required: false\n          description: Filter by job requisition Workday ID\n        - name: candidate\n          in: query\n          type: string\n          required: false\n          description: Filter by candidate Workday ID\n        - name: stage\n          in: query\n          type: string\n          required: false\n          description: Filter by recruiting stage\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-application-by-id\n      path: /jobApplications/{jobApplicationId}\n      description: Individual job application\n      operations:\n      - name: get-job-application\n        method: GET\n        description: Retrieve details of a specific job application\n        inputParameters:\n        - name: jobApplicationId\n          in: path\n          type: string\n          required: true\n          description: Job application\
  \ Workday ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-application-move\n      path: /jobApplications/{jobApplicationId}/move\n      description: Move candidate to a different stage\n      operations:\n      - name: move-candidate-stage\n        method: POST\n        description: Move a candidate to a different recruiting or disposition stage\n        inputParameters:\n        - name: jobApplicationId\n          in: path\n          type: string\n          required: true\n          description: Job application Workday ID\n        body:\n          type: json\n          data:\n            stage: '{{tools.stage}}'\n            reason: '{{tools.reason}}'\n            comments: '{{tools.comments}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-application-offer\n      path: /jobApplications/{jobApplicationId}/offer\n\
  \      description: Initiate an employment offer\n      operations:\n      - name: initiate-offer\n        method: POST\n        description: Initiate an employment offer for a job application\n        inputParameters:\n        - name: jobApplicationId\n          in: path\n          type: string\n          required: true\n          description: Job application Workday ID\n        body:\n          type: json\n          data:\n            proposedStartDate: '{{tools.proposedStartDate}}'\n            compensationAmount: '{{tools.compensationAmount}}'\n            compensationFrequency: '{{tools.compensationFrequency}}'\n            currency: '{{tools.currency}}'\n            expirationDate: '{{tools.expirationDate}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-postings\n      path: /jobPostings\n      description: Job posting collection\n      operations:\n      - name: list-job-postings\n\
  \        method: GET\n        description: Retrieve a collection of job postings with optional filters\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: jobRequisition\n          in: query\n          type: string\n          required: false\n          description: Filter by job requisition Workday ID\n        - name: postingSite\n          in: query\n          type: string\n          required: false\n          description: Filter by posting site Workday ID\n        - name: active\n          in: query\n          type: boolean\n          required: false\n          description: Filter by active posting status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n    - name: job-posting-by-id\n      path: /jobPostings/{jobPostingId}\n      description: Individual job posting\n      operations:\n      - name: get-job-posting\n        method: GET\n        description: Retrieve details of a specific job posting\n        inputParameters:\n        - name: jobPostingId\n          in: path\n          type: string\n          required: true\n          description: Job posting Workday ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-job-posting\n        method: PATCH\n        description: Update an existing job posting\n        inputParameters:\n        - name: jobPostingId\n          in: path\n          type: string\n          required: true\n          description: Job posting Workday ID\n        body:\n          type: json\n          data:\n            startDate: '{{tools.startDate}}'\n            endDate: '{{tools.endDate}}'\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-posting-post\n      path: /jobPostings/{jobPostingId}/post\n      description: Post a job to career sites\n      operations:\n      - name: post-job\n        method: POST\n        description: Post a job to internal and external career sites\n        inputParameters:\n        - name: jobPostingId\n          in: path\n          type: string\n          required: true\n          description: Job posting Workday ID\n        body:\n          type: json\n          data:\n            postingSites: '{{tools.postingSites}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-posting-unpost\n      path: /jobPostings/{jobPostingId}/unpost\n      description: Unpost a job from career sites\n      operations:\n      - name: unpost-job\n        method: POST\n        description:\
  \ Remove a job posting from career sites\n        inputParameters:\n        - name: jobPostingId\n          in: path\n          type: string\n          required: true\n          description: Job posting Workday ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: interviews\n      path: /interviews\n      description: Interview collection\n      operations:\n      - name: list-interviews\n        method: GET\n        description: Retrieve a collection of scheduled interviews with optional filters\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: jobApplication\n          in: query\n          type: string\n          required:\
  \ false\n          description: Filter by job application Workday ID\n        - name: dateFrom\n          in: query\n          type: string\n          required: false\n          description: Return interviews scheduled on or after this date\n        - name: dateTo\n          in: query\n          type: string\n          required: false\n          description: Return interviews scheduled on or before this date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: schedule-interview\n        method: POST\n        description: Schedule a new interview for a job application\n        body:\n          type: json\n          data:\n            jobApplication: '{{tools.jobApplication}}'\n            interviewType: '{{tools.interviewType}}'\n            scheduledDate: '{{tools.scheduledDate}}'\n            startTime: '{{tools.startTime}}'\n            endTime: '{{tools.endTime}}'\n            interviewers: '{{tools.interviewers}}'\n\
  \            location: '{{tools.location}}'\n            webConferenceUrl: '{{tools.webConferenceUrl}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: interview-by-id\n      path: /interviews/{interviewId}\n      description: Individual interview\n      operations:\n      - name: get-interview\n        method: GET\n        description: Retrieve details of a specific interview\n        inputParameters:\n        - name: interviewId\n          in: path\n          type: string\n          required: true\n          description: Interview Workday ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: interview-feedback\n      path: /interviews/{interviewId}/feedback\n      description: Interview feedback\n      operations:\n      - name: list-interview-feedback\n        method: GET\n        description: Retrieve feedback\
  \ submitted for an interview\n        inputParameters:\n        - name: interviewId\n          in: path\n          type: string\n          required: true\n          description: Interview Workday ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: submit-interview-feedback\n        method: POST\n        description: Submit feedback for a completed interview\n        inputParameters:\n        - name: interviewId\n          in: path\n          type: string\n          required: true\n          description: Interview Workday ID\n        body:\n          type: json\n          data:\n            overallRating: '{{tools.overallRating}}'\n            competencyRatings: '{{tools.competencyRatings}}'\n            comments: '{{tools.comments}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: background-checks\n   \
  \   path: /backgroundChecks\n      description: Background check collection\n      operations:\n      - name: list-background-checks\n        method: GET\n        description: Retrieve a collection of background check results\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: candidate\n          in: query\n          type: string\n          required: false\n          description: Filter by candidate Workday ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: submit-background-check\n        method: POST\n        description: Load background check results from an external provider\n        body:\n          type: json\n    \
  \      data:\n            candidate: '{{tools.candidate}}'\n            jobApplication: '{{tools.jobApplication}}'\n            package: '{{tools.package}}'\n            status: '{{tools.status}}'\n            result: '{{tools.result}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: background-check-packages\n      path: /backgroundCheckPackages\n      description: Background check package collection\n      operations:\n      - name: list-background-check-packages\n        method: GET\n        description: Retrieve available background check packages\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recruiting-agencies\n      path: /recruitingAgencies\n      description: Recruiting agency collection\n      operations:\n      - name: list-recruiting-agencies\n        method: GET\n        description: Retrieve a collection of recruiting agencies\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recruiting-agency-by-id\n      path: /recruitingAgencies/{recruitingAgencyId}\n      description: Individual recruiting agency\n      operations:\n      - name: get-recruiting-agency\n        method:\
  \ GET\n        description: Retrieve details of a specific recruiting agency\n        inputParameters:\n        - name: recruitingAgencyId\n          in: path\n          type: string\n          required: true\n          description: Recruiting agency Workday ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recruiting-agency-candidates\n      path: /recruitingAgencies/{recruitingAgencyId}/candidates\n      description: Submit candidates from a recruiting agency\n      operations:\n      - name: submit-agency-candidate\n        method: POST\n        description: Submit a candidate from a recruiting agency for a job requisition\n        inputParameters:\n        - name: recruitingAgencyId\n          in: path\n          type: string\n          required: true\n          description: Recruiting agency Workday ID\n        body:\n          type: json\n          data:\n            candidate: '{{tools.candidate}}'\n\
  \            jobRequisition: '{{tools.jobRequisition}}'\n            agencyUser: '{{tools.agencyUser}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applicants\n      path: /applicants\n      description: Applicant collection\n      operations:\n      - name: list-applicants\n        method: GET\n        description: Retrieve pre-hire and applicant records\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applicants-import\n      path: /applicants/import\n      description: Bulk applicant import\n \
  \     operations:\n      - name: import-applicants\n        method: POST\n        description: High-volume applicant import for asynchronous bulk loading\n        body:\n          type: json\n          data:\n            applicants: '{{tools.applicants}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: positions\n      path: /positions\n      description: Position management\n      operations:\n      - name: list-positions\n        method: GET\n        description: Retrieve position management positions\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n    \
  \      type: object\n          value: $.\n      - name: create-position\n        method: POST\n        description: Create and open a new position\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            jobProfile: '{{tools.jobProfile}}'\n            supervisoryOrganization: '{{tools.supervisoryOrganization}}'\n            location: '{{tools.location}}'\n            workerType: '{{tools.workerType}}'\n            timeType: '{{tools.timeType}}'\n            availableDate: '{{tools.availableDate}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-posting-sites\n      path: /jobPostingSites\n      description: Job posting site configuration\n      operations:\n      - name: list-job-posting-sites\n        method: GET\n        description: Retrieve available job posting sites\n        inputParameters:\n        - name: limit\n          in: query\n \
  \         type: integer\n          required: false\n          description: Maximum number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: questionnaires\n      path: /questionnaires\n      description: Recruiting questionnaires\n      operations:\n      - name: list-questionnaires\n        method: GET\n        description: Retrieve recruiting questionnaires for screening and assessment\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n         \n\n# --- truncated at 32 KB (44 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/workday-recruiting/refs/heads/main/capabilities/requisition-management.yaml\n"
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
