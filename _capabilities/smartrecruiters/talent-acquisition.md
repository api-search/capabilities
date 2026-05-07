---
categories: []
consumed_apis: []
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
- get application status
- create job
- submit application
- list candidates
- submit a job application
- smartrecruiters
- job lifecycle management
- add candidate note
- get job details
- create candidate
- get job hiring team
- get job
- list open positions with optional filtering by status or keyword
- candidate application submission
- list job candidates
- get posting
- get the recruiting team assigned to a job
- candidate profile management
- move a job to a new status in the hiring workflow
- talent acquisition
- list public job postings
- individual candidate profile
- applicant tracking
- public job postings for career sites
- list all jobs with optional filters
- update job status
- submit a candidate application for a job posting
- list candidate applications
- list candidates for a job
- get a candidate's full profile including contact info and history
- recruiting
- create a new job opening
- get candidate
- browse public job postings on the career site
- get a specific job posting
- check the current status of a candidate's application
- import a new candidate profile into smartrecruiters
- hr technology
- human resources
- individual public job posting
- search and list candidate profiles in the system
- add a recruiter note to a candidate profile
- list all job applications associated with a candidate
- list jobs
- get the full details of a public job posting
- jobs
- candidates
- list postings
- individual job management
- get detailed information about a specific job opening
- create a new job opening in smartrecruiters
- get a candidate profile
- candidates for a job
- list candidates who applied for a specific job
- list candidate profiles
slug: talent-acquisition
source_filename: talent-acquisition.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SmartRecruiters Talent Acquisition\n  description: Unified workflow for end-to-end talent acquisition combining job management, candidate tracking, and application\n    processing. Used by recruiters and hiring managers to manage the full recruiting lifecycle from job creation through hire.\n  tags:\n  - SmartRecruiters\n  - Talent Acquisition\n  - Recruiting\n  - Human Resources\n  - Jobs\n  - Candidates\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SMARTRECRUITERS_API_KEY: SMARTRECRUITERS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: smartrecruiters-jobs\n    baseUri: https://api.smartrecruiters.com\n    description: SmartRecruiters Job API for job lifecycle management\n    authentication:\n      type: apikey\n      key: X-SmartToken\n      value: '{{SMARTRECRUITERS_API_KEY}}'\n      placement: header\n    resources:\n    - name: jobs\n      path: /jobs\n      description:\
  \ Job management\n      operations:\n      - name: list-jobs\n        method: GET\n        description: List jobs with optional filtering\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by job status\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-job\n        method: POST\n        description: Create a new job opening\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            department: '{{tools.department}}'\n            location: '{{tools.location}}'\n    - name: job\n      path: /jobs/{jobId}\n      description: Single job management\n      operations:\n      - name: get-job\n        method: GET\n        description: Get details for a specific job\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: The job ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-job\n        method: PATCH\n        description: Update properties of a job\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: The job ID\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n    - name: job-status\n      path: /jobs/{jobId}/status\n      description: Job status management\n      operations:\n      - name: update-job-status\n        method: PUT\n        description: Update the status of a job\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: The job ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            status: '{{tools.status}}'\n    - name: job-hiring-team\n      path: /jobs/{jobId}/hiring-team\n      description: Job hiring team management\n      operations:\n      - name: get-job-hiring-team\n        method: GET\n        description: Get\
  \ the hiring team for a job\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: The job ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job-candidates\n      path: /jobs/{jobId}/candidates\n      description: Candidates for a specific job\n      operations:\n      - name: list-job-candidates\n        method: GET\n        description: List candidates who applied to a job\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: The job ID\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by candidate status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n\
  \    namespace: smartrecruiters-candidates\n    baseUri: https://api.smartrecruiters.com\n    description: SmartRecruiters Candidate API for candidate profile management\n    authentication:\n      type: apikey\n      key: X-SmartToken\n      value: '{{SMARTRECRUITERS_API_KEY}}'\n      placement: header\n    resources:\n    - name: candidates\n      path: /candidates\n      description: Candidate profile management\n      operations:\n      - name: list-candidates\n        method: GET\n        description: List candidates with optional filtering\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search by name or email\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n      \
  \  outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-candidate\n        method: POST\n        description: Import a new candidate profile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            email: '{{tools.email}}'\n    - name: candidate\n      path: /candidates/{candidateId}\n      description: Individual candidate management\n      operations:\n      - name: get-candidate\n        method: GET\n        description: Get a candidate profile\n        inputParameters:\n        - name: candidateId\n          in: path\n          type: string\n          required: true\n          description: The candidate ID\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n      - name: update-candidate\n        method: PATCH\n        description: Update candidate profile properties\n        inputParameters:\n        - name: candidateId\n          in: path\n          type: string\n          required: true\n          description: The candidate ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n    - name: candidate-applications\n      path: /candidates/{candidateId}/applications\n      description: Candidate application history\n      operations:\n      - name: list-candidate-applications\n        method: GET\n        description: List all applications for a candidate\n        inputParameters:\n        - name: candidateId\n          in: path\n          type: string\n        \
  \  required: true\n          description: The candidate ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidate-messages\n      path: /candidates/{candidateId}/messages\n      description: Candidate notes and messages\n      operations:\n      - name: list-candidate-messages\n        method: GET\n        description: List notes and messages for a candidate\n        inputParameters:\n        - name: candidateId\n          in: path\n          type: string\n          required: true\n          description: The candidate ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-candidate-message\n        method: POST\n        description: Add a note or message to a candidate profile\n        inputParameters:\n        - name: candidateId\n          in: path\n          type: string\n          required: true\n\
  \          description: The candidate ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            message: '{{tools.message}}'\n    - name: candidate-documents\n      path: /candidates/{candidateId}/documents\n      description: Candidate document attachments\n      operations:\n      - name: list-candidate-documents\n        method: GET\n        description: List documents attached to a candidate\n        inputParameters:\n        - name: candidateId\n          in: path\n          type: string\n          required: true\n          description: The candidate ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: smartrecruiters-posting\n    baseUri: https://api.smartrecruiters.com\n    description: SmartRecruiters Posting API for career site and application\
  \ management\n    authentication:\n      type: apikey\n      key: X-SmartToken\n      value: '{{SMARTRECRUITERS_API_KEY}}'\n      placement: header\n    resources:\n    - name: postings\n      path: /v1/companies/{companyIdentifier}/postings\n      description: Job postings management\n      operations:\n      - name: list-postings\n        method: GET\n        description: List active job postings for a company\n        inputParameters:\n        - name: companyIdentifier\n          in: path\n          type: string\n          required: true\n          description: The company identifier\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Full-text search query\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Results\
  \ to skip for pagination\n        - name: country\n          in: query\n          type: string\n          required: false\n          description: Filter by country code\n        - name: department\n          in: query\n          type: string\n          required: false\n          description: Filter by department\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-posting\n        method: GET\n        description: Get detailed information for a specific job posting\n        inputParameters:\n        - name: companyIdentifier\n          in: path\n          type: string\n          required: true\n          description: The company identifier\n        - name: postingId\n          in: path\n          type: string\n          required: true\n          description: The posting ID or UUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n    - name: applications\n      path: /v1/companies/{companyIdentifier}/postings/{postingId}/candidates\n      description: Candidate application submission\n      operations:\n      - name: submit-application\n        method: POST\n        description: Submit a new candidate application for a job posting\n        inputParameters:\n        - name: companyIdentifier\n          in: path\n          type: string\n          required: true\n          description: The company identifier\n        - name: postingId\n          in: path\n          type: string\n          required: true\n          description: The posting ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            email: '{{tools.email}}'\n    - name: application-status\n      path: /v1/companies/{companyIdentifier}/postings/{postingId}/candidates/{candidateId}/status\n\
  \      description: Application status tracking\n      operations:\n      - name: get-application-status\n        method: GET\n        description: Get the application status for a specific candidate\n        inputParameters:\n        - name: companyIdentifier\n          in: path\n          type: string\n          required: true\n          description: The company identifier\n        - name: postingId\n          in: path\n          type: string\n          required: true\n          description: The posting ID\n        - name: candidateId\n          in: path\n          type: string\n          required: true\n          description: The candidate ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: talent-acquisition-api\n    description: Unified REST API for end-to-end talent acquisition workflows.\n    resources:\n    - path: /v1/jobs\n      name: jobs\n\
  \      description: Job lifecycle management\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List all jobs with optional filters\n        call: smartrecruiters-jobs.list-jobs\n        with:\n          q: rest.q\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-job\n        description: Create a new job opening\n        call: smartrecruiters-jobs.create-job\n        with:\n          title: rest.title\n          department: rest.department\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs/{jobId}\n      name: job\n      description: Individual job management\n      operations:\n      - method: GET\n        name: get-job\n        description: Get job details\n        call: smartrecruiters-jobs.get-job\n        with:\n          jobId: rest.jobId\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/jobs/{jobId}/candidates\n      name: job-candidates\n      description: Candidates for a job\n      operations:\n      - method: GET\n        name: list-job-candidates\n        description: List candidates for a job\n        call: smartrecruiters-jobs.list-job-candidates\n        with:\n          jobId: rest.jobId\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/postings\n      name: postings\n      description: Public job postings for career sites\n      operations:\n      - method: GET\n        name: list-postings\n        description: List public job postings\n        call: smartrecruiters-posting.list-postings\n        with:\n          companyIdentifier: rest.companyIdentifier\n          q: rest.q\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/postings/{postingId}\n      name: posting\n      description: Individual public job posting\n      operations:\n\
  \      - method: GET\n        name: get-posting\n        description: Get a specific job posting\n        call: smartrecruiters-posting.get-posting\n        with:\n          companyIdentifier: rest.companyIdentifier\n          postingId: rest.postingId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/postings/{postingId}/applications\n      name: applications\n      description: Candidate application submission\n      operations:\n      - method: POST\n        name: submit-application\n        description: Submit a job application\n        call: smartrecruiters-posting.submit-application\n        with:\n          companyIdentifier: rest.companyIdentifier\n          postingId: rest.postingId\n          firstName: rest.firstName\n          lastName: rest.lastName\n          email: rest.email\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/candidates\n      name: candidates\n      description: Candidate profile\
  \ management\n      operations:\n      - method: GET\n        name: list-candidates\n        description: List candidate profiles\n        call: smartrecruiters-candidates.list-candidates\n        with:\n          q: rest.q\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/candidates/{candidateId}\n      name: candidate\n      description: Individual candidate profile\n      operations:\n      - method: GET\n        name: get-candidate\n        description: Get a candidate profile\n        call: smartrecruiters-candidates.get-candidate\n        with:\n          candidateId: rest.candidateId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: talent-acquisition-mcp\n    transport: http\n    description: MCP server for AI-assisted talent acquisition and recruiting workflows.\n    tools:\n    - name: list-jobs\n      description: List open positions with optional filtering by status\
  \ or keyword\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smartrecruiters-jobs.list-jobs\n      with:\n        q: tools.q\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-job\n      description: Get detailed information about a specific job opening\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smartrecruiters-jobs.get-job\n      with:\n        jobId: tools.jobId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-job\n      description: Create a new job opening in SmartRecruiters\n      hints:\n        readOnly: false\n        destructive: false\n      call: smartrecruiters-jobs.create-job\n      with:\n        title: tools.title\n        department: tools.department\n        location: tools.location\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-job-status\n      description: Move a job\
  \ to a new status in the hiring workflow\n      hints:\n        readOnly: false\n        idempotent: true\n      call: smartrecruiters-jobs.update-job-status\n      with:\n        jobId: tools.jobId\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-job-hiring-team\n      description: Get the recruiting team assigned to a job\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smartrecruiters-jobs.get-job-hiring-team\n      with:\n        jobId: tools.jobId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-job-candidates\n      description: List candidates who applied for a specific job\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smartrecruiters-jobs.list-job-candidates\n      with:\n        jobId: tools.jobId\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-postings\n\
  \      description: Browse public job postings on the career site\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smartrecruiters-posting.list-postings\n      with:\n        companyIdentifier: tools.companyIdentifier\n        q: tools.q\n        country: tools.country\n        department: tools.department\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-posting\n      description: Get the full details of a public job posting\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smartrecruiters-posting.get-posting\n      with:\n        companyIdentifier: tools.companyIdentifier\n        postingId: tools.postingId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-application\n      description: Submit a candidate application for a job posting\n      hints:\n        readOnly: false\n        destructive: false\n      call: smartrecruiters-posting.submit-application\n\
  \      with:\n        companyIdentifier: tools.companyIdentifier\n        postingId: tools.postingId\n        firstName: tools.firstName\n        lastName: tools.lastName\n        email: tools.email\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-application-status\n      description: Check the current status of a candidate's application\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smartrecruiters-posting.get-application-status\n      with:\n        companyIdentifier: tools.companyIdentifier\n        postingId: tools.postingId\n        candidateId: tools.candidateId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-candidates\n      description: Search and list candidate profiles in the system\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smartrecruiters-candidates.list-candidates\n      with:\n        q: tools.q\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: get-candidate\n      description: Get a candidate's full profile including contact info and history\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smartrecruiters-candidates.get-candidate\n      with:\n        candidateId: tools.candidateId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-candidate\n      description: Import a new candidate profile into SmartRecruiters\n      hints:\n        readOnly: false\n        destructive: false\n      call: smartrecruiters-candidates.create-candidate\n      with:\n        firstName: tools.firstName\n        lastName: tools.lastName\n        email: tools.email\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-candidate-applications\n      description: List all job applications associated with a candidate\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smartrecruiters-candidates.list-candidate-applications\n\
  \      with:\n        candidateId: tools.candidateId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-candidate-note\n      description: Add a recruiter note to a candidate profile\n      hints:\n        readOnly: false\n        destructive: false\n      call: smartrecruiters-candidates.create-candidate-message\n      with:\n        candidateId: tools.candidateId\n        message: tools.message\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
