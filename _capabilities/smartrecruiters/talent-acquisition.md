---
categories: []
consumed_apis:
- smartrecruiters-jobs
- smartrecruiters-candidates
- smartrecruiters-posting
description: Unified workflow for end-to-end talent acquisition combining job management, candidate tracking, and application processing. Used by recruiters and hiring managers to manage the full recruiting lifecycle from job creation through hire.
layout: capability
name: SmartRecruiters Talent Acquisition
operations:
- description: List all jobs with optional filters
  method: GET
  name: list-jobs
  path: /v1/jobs
- description: Create a new job opening
  method: POST
  name: create-job
  path: /v1/jobs
- description: Get job details
  method: GET
  name: get-job
  path: /v1/jobs/{jobId}
- description: List candidates for a job
  method: GET
  name: list-job-candidates
  path: /v1/jobs/{jobId}/candidates
- description: List public job postings
  method: GET
  name: list-postings
  path: /v1/postings
- description: Get a specific job posting
  method: GET
  name: get-posting
  path: /v1/postings/{postingId}
- description: Submit a job application
  method: POST
  name: submit-application
  path: /v1/postings/{postingId}/applications
- description: List candidate profiles
  method: GET
  name: list-candidates
  path: /v1/candidates
- description: Get a candidate profile
  method: GET
  name: get-candidate
  path: /v1/candidates/{candidateId}
personas: []
provider_name: SmartRecruiters
provider_slug: smartrecruiters
search_terms:
- list candidate profiles
- list open positions with optional filtering by status or keyword
- list candidates
- get the recruiting team assigned to a job
- candidate application submission
- smartrecruiters
- individual public job posting
- check the current status of a candidate's application
- applicant tracking
- list jobs
- create a new job opening in smartrecruiters
- list postings
- candidates
- human resources
- candidates for a job
- create job
- get a candidate's full profile including contact info and history
- get a candidate profile
- submit a job application
- submit a candidate application for a job posting
- search and list candidate profiles in the system
- get application status
- create a new job opening
- list all jobs with optional filters
- get job details
- update job status
- talent acquisition
- list all job applications associated with a candidate
- public job postings for career sites
- get job hiring team
- list job candidates
- move a job to a new status in the hiring workflow
- import a new candidate profile into smartrecruiters
- get job
- jobs
- recruiting
- job lifecycle management
- list candidates for a job
- get posting
- list public job postings
- individual job management
- candidate profile management
- get detailed information about a specific job opening
- browse public job postings on the career site
- get the full details of a public job posting
- individual candidate profile
- list candidates who applied for a specific job
- add candidate note
- list candidate applications
- get a specific job posting
- create candidate
- hr technology
- submit application
- get candidate
- add a recruiter note to a candidate profile
slug: talent-acquisition
source_filename: talent-acquisition.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: SmartRecruiters Talent Acquisition\n  description: >-\n    Unified workflow for end-to-end talent acquisition combining job management,\n    candidate tracking, and application processing. Used by recruiters and hiring\n    managers to manage the full recruiting lifecycle from job creation through hire.\n  tags:\n    - SmartRecruiters\n    - Talent Acquisition\n    - Recruiting\n    - Human Resources\n    - Jobs\n    - Candidates\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SMARTRECRUITERS_API_KEY: SMARTRECRUITERS_API_KEY\n\ncapability:\n  consumes:\n    - import: smartrecruiters-jobs\n      location: ./shared/jobs-api.yaml\n    - import: smartrecruiters-candidates\n      location: ./shared/candidates-api.yaml\n    - import: smartrecruiters-posting\n      location: ./shared/posting-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: talent-acquisition-api\n\
  \      description: Unified REST API for end-to-end talent acquisition workflows.\n      resources:\n        - path: /v1/jobs\n          name: jobs\n          description: Job lifecycle management\n          operations:\n            - method: GET\n              name: list-jobs\n              description: List all jobs with optional filters\n              call: \"smartrecruiters-jobs.list-jobs\"\n              with:\n                q: \"rest.q\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-job\n              description: Create a new job opening\n              call: \"smartrecruiters-jobs.create-job\"\n              with:\n                title: \"rest.title\"\n                department: \"rest.department\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/jobs/{jobId}\n\
  \          name: job\n          description: Individual job management\n          operations:\n            - method: GET\n              name: get-job\n              description: Get job details\n              call: \"smartrecruiters-jobs.get-job\"\n              with:\n                jobId: \"rest.jobId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/jobs/{jobId}/candidates\n          name: job-candidates\n          description: Candidates for a job\n          operations:\n            - method: GET\n              name: list-job-candidates\n              description: List candidates for a job\n              call: \"smartrecruiters-jobs.list-job-candidates\"\n              with:\n                jobId: \"rest.jobId\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/postings\n          name: postings\n\
  \          description: Public job postings for career sites\n          operations:\n            - method: GET\n              name: list-postings\n              description: List public job postings\n              call: \"smartrecruiters-posting.list-postings\"\n              with:\n                companyIdentifier: \"rest.companyIdentifier\"\n                q: \"rest.q\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/postings/{postingId}\n          name: posting\n          description: Individual public job posting\n          operations:\n            - method: GET\n              name: get-posting\n              description: Get a specific job posting\n              call: \"smartrecruiters-posting.get-posting\"\n              with:\n                companyIdentifier: \"rest.companyIdentifier\"\n                postingId: \"rest.postingId\"\n              outputParameters:\n                - type: object\n     \
  \             mapping: \"$.\"\n        - path: /v1/postings/{postingId}/applications\n          name: applications\n          description: Candidate application submission\n          operations:\n            - method: POST\n              name: submit-application\n              description: Submit a job application\n              call: \"smartrecruiters-posting.submit-application\"\n              with:\n                companyIdentifier: \"rest.companyIdentifier\"\n                postingId: \"rest.postingId\"\n                firstName: \"rest.firstName\"\n                lastName: \"rest.lastName\"\n                email: \"rest.email\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/candidates\n          name: candidates\n          description: Candidate profile management\n          operations:\n            - method: GET\n              name: list-candidates\n              description: List candidate profiles\n\
  \              call: \"smartrecruiters-candidates.list-candidates\"\n              with:\n                q: \"rest.q\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/candidates/{candidateId}\n          name: candidate\n          description: Individual candidate profile\n          operations:\n            - method: GET\n              name: get-candidate\n              description: Get a candidate profile\n              call: \"smartrecruiters-candidates.get-candidate\"\n              with:\n                candidateId: \"rest.candidateId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: talent-acquisition-mcp\n      transport: http\n      description: MCP server for AI-assisted talent acquisition and recruiting workflows.\n      tools:\n        - name: list-jobs\n          description: List open positions with\
  \ optional filtering by status or keyword\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smartrecruiters-jobs.list-jobs\"\n          with:\n            q: \"tools.q\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-job\n          description: Get detailed information about a specific job opening\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smartrecruiters-jobs.get-job\"\n          with:\n            jobId: \"tools.jobId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-job\n          description: Create a new job opening in SmartRecruiters\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"smartrecruiters-jobs.create-job\"\n          with:\n            title: \"tools.title\"\n        \
  \    department: \"tools.department\"\n            location: \"tools.location\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-job-status\n          description: Move a job to a new status in the hiring workflow\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"smartrecruiters-jobs.update-job-status\"\n          with:\n            jobId: \"tools.jobId\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-job-hiring-team\n          description: Get the recruiting team assigned to a job\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smartrecruiters-jobs.get-job-hiring-team\"\n          with:\n            jobId: \"tools.jobId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-job-candidates\n\
  \          description: List candidates who applied for a specific job\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smartrecruiters-jobs.list-job-candidates\"\n          with:\n            jobId: \"tools.jobId\"\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-postings\n          description: Browse public job postings on the career site\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smartrecruiters-posting.list-postings\"\n          with:\n            companyIdentifier: \"tools.companyIdentifier\"\n            q: \"tools.q\"\n            country: \"tools.country\"\n            department: \"tools.department\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-posting\n          description: Get the full details of a public job posting\n\
  \          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smartrecruiters-posting.get-posting\"\n          with:\n            companyIdentifier: \"tools.companyIdentifier\"\n            postingId: \"tools.postingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-application\n          description: Submit a candidate application for a job posting\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"smartrecruiters-posting.submit-application\"\n          with:\n            companyIdentifier: \"tools.companyIdentifier\"\n            postingId: \"tools.postingId\"\n            firstName: \"tools.firstName\"\n            lastName: \"tools.lastName\"\n            email: \"tools.email\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-application-status\n          description: Check the current\
  \ status of a candidate's application\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smartrecruiters-posting.get-application-status\"\n          with:\n            companyIdentifier: \"tools.companyIdentifier\"\n            postingId: \"tools.postingId\"\n            candidateId: \"tools.candidateId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-candidates\n          description: Search and list candidate profiles in the system\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smartrecruiters-candidates.list-candidates\"\n          with:\n            q: \"tools.q\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-candidate\n          description: Get a candidate's full profile including contact info and history\n          hints:\n            readOnly: true\n            openWorld:\
  \ true\n          call: \"smartrecruiters-candidates.get-candidate\"\n          with:\n            candidateId: \"tools.candidateId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-candidate\n          description: Import a new candidate profile into SmartRecruiters\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"smartrecruiters-candidates.create-candidate\"\n          with:\n            firstName: \"tools.firstName\"\n            lastName: \"tools.lastName\"\n            email: \"tools.email\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-candidate-applications\n          description: List all job applications associated with a candidate\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smartrecruiters-candidates.list-candidate-applications\"\n          with:\n    \
  \        candidateId: \"tools.candidateId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-candidate-note\n          description: Add a recruiter note to a candidate profile\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"smartrecruiters-candidates.create-candidate-message\"\n          with:\n            candidateId: \"tools.candidateId\"\n            message: \"tools.message\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/smartrecruiters/refs/heads/main/capabilities/talent-acquisition.yaml
tags:
- SmartRecruiters
- Talent Acquisition
- Recruiting
- Human Resources
- Jobs
- Candidates
tools:
- description: List open positions with optional filtering by status or keyword
  hints:
    openWorld: true
    readOnly: true
  name: list-jobs
- description: Get detailed information about a specific job opening
  hints:
    openWorld: true
    readOnly: true
  name: get-job
- description: Create a new job opening in SmartRecruiters
  hints:
    destructive: false
    readOnly: false
  name: create-job
- description: Move a job to a new status in the hiring workflow
  hints:
    idempotent: true
    readOnly: false
  name: update-job-status
- description: Get the recruiting team assigned to a job
  hints:
    openWorld: true
    readOnly: true
  name: get-job-hiring-team
- description: List candidates who applied for a specific job
  hints:
    openWorld: true
    readOnly: true
  name: list-job-candidates
- description: Browse public job postings on the career site
  hints:
    openWorld: true
    readOnly: true
  name: list-postings
- description: Get the full details of a public job posting
  hints:
    openWorld: true
    readOnly: true
  name: get-posting
- description: Submit a candidate application for a job posting
  hints:
    destructive: false
    readOnly: false
  name: submit-application
- description: Check the current status of a candidate's application
  hints:
    openWorld: true
    readOnly: true
  name: get-application-status
- description: Search and list candidate profiles in the system
  hints:
    openWorld: true
    readOnly: true
  name: list-candidates
- description: Get a candidate's full profile including contact info and history
  hints:
    openWorld: true
    readOnly: true
  name: get-candidate
- description: Import a new candidate profile into SmartRecruiters
  hints:
    destructive: false
    readOnly: false
  name: create-candidate
- description: List all job applications associated with a candidate
  hints:
    openWorld: true
    readOnly: true
  name: list-candidate-applications
- description: Add a recruiter note to a candidate profile
  hints:
    destructive: false
    readOnly: false
  name: add-candidate-note
---
