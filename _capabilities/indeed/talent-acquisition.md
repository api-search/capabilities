---
categories:
- recruiting-ats
consumed_apis: []
description: Unified workflow for managing the hiring pipeline including employer setup, job posting, candidate retrieval, and disposition tracking. Used by ATS partners and hiring platform developers.
layout: capability
name: Indeed Talent Acquisition
operations:
- description: Create an employer entity.
  method: POST
  name: create-employer
  path: /v1/employers
- description: Get employer details.
  method: GET
  name: get-employer
  path: /v1/employers/{id}
- description: Update employer details.
  method: PATCH
  name: update-employer
  path: /v1/employers/{id}
- description: List candidates for an employer.
  method: GET
  name: list-candidates
  path: /v1/employers/{id}/candidates
- description: List job postings.
  method: GET
  name: list-jobs
  path: /v1/employers/{id}/jobs
- description: Create a job posting.
  method: POST
  name: create-job
  path: /v1/employers/{id}/jobs
personas: []
provider_name: Indeed
provider_slug: indeed
search_terms:
- list candidates for an employer.
- individual employer management.
- create job
- hiring
- register employer for candidate sync.
- list candidates
- expire job posting
- get employer details.
- create an employer entity on indeed.
- create an employer entity.
- update employer details.
- get job posting
- candidate management.
- update employer
- talent acquisition
- job postings
- expire a job posting.
- get candidate details.
- list employer jobs
- get employer
- update disposition
- get job posting details.
- list job postings.
- update job posting
- indeed
- recruiting
- employer management.
- create job posting
- get candidate
- employment
- create employer
- careers
- create a job posting on indeed.
- list jobs
- update a job posting.
- update candidate disposition status.
- create a job posting.
- jobs
- list job postings for an employer.
- job posting management.
- job search
- register candidate sync
slug: talent-acquisition
source_filename: talent-acquisition.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Indeed Talent Acquisition\n  description: Unified workflow for managing the hiring pipeline including employer setup, job posting, candidate retrieval,\n    and disposition tracking. Used by ATS partners and hiring platform developers.\n  tags:\n  - Indeed\n  - Talent Acquisition\n  - Hiring\n  - Job Postings\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    INDEED_ACCESS_TOKEN: INDEED_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: indeed\n    baseUri: https://apis.indeed.com\n    description: Indeed Employer REST API for managing employers, candidates, and jobs.\n    authentication:\n      type: bearer\n      token: '{{INDEED_ACCESS_TOKEN}}'\n    resources:\n    - name: employers\n      path: /v1/employers\n      description: Employer management.\n      operations:\n      - name: create-employer\n        method: POST\n        description: Create a new employer entity.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n    - name: employer-details\n      path: /v1/employers/{employerId}\n      description: Individual employer management.\n      operations:\n      - name: get-employer\n        method: GET\n        description: Get employer details.\n        inputParameters:\n        - name: employerId\n          in: path\n          type: string\n          required: true\n          description: Employer ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-employer\n        method: PATCH\n        description: Update employer details.\n        inputParameters:\n        - name: employerId\n          in: path\n          type: string\n          required: true\n\
  \          description: Employer ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: employer-registration\n      path: /v1/employers/{employerId}/candidate-sync\n      description: Candidate sync registration.\n      operations:\n      - name: register-employer-candidate-sync\n        method: POST\n        description: Register employer for candidate sync.\n        inputParameters:\n        - name: employerId\n          in: path\n          type: string\n          required: true\n          description: Employer ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidates\n      path: /v1/employers/{employerId}/candidates\n      description: Candidate management.\n      operations:\n      - name: list-candidates\n \
  \       method: GET\n        description: List candidates for an employer.\n        inputParameters:\n        - name: employerId\n          in: path\n          type: string\n          required: true\n          description: Employer ID.\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidate-details\n      path: /v1/employers/{employerId}/candidates/{candidateId}\n      description: Individual candidate management.\n      operations:\n      - name: get-candidate\n        method: GET\n        description: Get candidate details.\n        inputParameters:\n        - name: employerId\n          in: path\n          type: string\n          required: true\n          description: Employer ID.\n        - name: candidateId\n          in: path\n          type: string\n\
  \          required: true\n          description: Candidate ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidate-disposition\n      path: /v1/employers/{employerId}/candidates/{candidateId}/disposition\n      description: Candidate disposition tracking.\n      operations:\n      - name: update-candidate-disposition\n        method: PUT\n        description: Update candidate disposition status.\n        inputParameters:\n        - name: employerId\n          in: path\n          type: string\n          required: true\n          description: Employer ID.\n        - name: candidateId\n          in: path\n          type: string\n          required: true\n          description: Candidate ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            status: '{{tools.status}}'\n\
  \    - name: jobs\n      path: /v1/employers/{employerId}/jobs\n      description: Job posting management.\n      operations:\n      - name: create-job-posting\n        method: POST\n        description: Create a new job posting.\n        inputParameters:\n        - name: employerId\n          in: path\n          type: string\n          required: true\n          description: Employer ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            description: '{{tools.description}}'\n      - name: list-employer-jobs\n        method: GET\n        description: List job postings for an employer.\n        inputParameters:\n        - name: employerId\n          in: path\n          type: string\n          required: true\n          description: Employer ID.\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n    - name: job-details\n      path: /v1/employers/{employerId}/jobs/{jobId}\n      description: Individual job posting management.\n      operations:\n      - name: get-job-posting\n        method: GET\n        description: Get job posting details.\n        inputParameters:\n        - name: employerId\n          in: path\n          type: string\n          required: true\n          description: Employer ID.\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: Job ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-job-posting\n        method: PATCH\n        description: Update a job posting.\n        inputParameters:\n        - name: employerId\n          in: path\n          type: string\n          required: true\n          description: Employer ID.\n        - name:\
  \ jobId\n          in: path\n          type: string\n          required: true\n          description: Job ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n      - name: expire-job-posting\n        method: DELETE\n        description: Expire a job posting.\n        inputParameters:\n        - name: employerId\n          in: path\n          type: string\n          required: true\n          description: Employer ID.\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: Job ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: indeed-talent-api\n    description: Unified REST API for Indeed talent acquisition workflows.\n\
  \    resources:\n    - path: /v1/employers\n      name: employers\n      description: Employer management.\n      operations:\n      - method: POST\n        name: create-employer\n        description: Create an employer entity.\n        call: indeed.create-employer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/employers/{id}\n      name: employer-details\n      description: Individual employer management.\n      operations:\n      - method: GET\n        name: get-employer\n        description: Get employer details.\n        call: indeed.get-employer\n        with:\n          employerId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-employer\n        description: Update employer details.\n        call: indeed.update-employer\n        with:\n          employerId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/employers/{id}/candidates\n\
  \      name: candidates\n      description: Candidate management.\n      operations:\n      - method: GET\n        name: list-candidates\n        description: List candidates for an employer.\n        call: indeed.list-candidates\n        with:\n          employerId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/employers/{id}/jobs\n      name: jobs\n      description: Job posting management.\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List job postings.\n        call: indeed.list-employer-jobs\n        with:\n          employerId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-job\n        description: Create a job posting.\n        call: indeed.create-job-posting\n        with:\n          employerId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n\
  \    namespace: indeed-talent-mcp\n    transport: http\n    description: MCP server for AI-assisted Indeed talent acquisition.\n    tools:\n    - name: create-employer\n      description: Create an employer entity on Indeed.\n      hints:\n        readOnly: false\n      call: indeed.create-employer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-employer\n      description: Get employer details.\n      hints:\n        readOnly: true\n      call: indeed.get-employer\n      with:\n        employerId: tools.employerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-employer\n      description: Update employer details.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: indeed.update-employer\n      with:\n        employerId: tools.employerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: register-candidate-sync\n      description: Register employer for candidate\
  \ sync.\n      hints:\n        readOnly: false\n      call: indeed.register-employer-candidate-sync\n      with:\n        employerId: tools.employerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-candidates\n      description: List candidates for an employer.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: indeed.list-candidates\n      with:\n        employerId: tools.employerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-candidate\n      description: Get candidate details.\n      hints:\n        readOnly: true\n      call: indeed.get-candidate\n      with:\n        employerId: tools.employerId\n        candidateId: tools.candidateId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-disposition\n      description: Update candidate disposition status.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: indeed.update-candidate-disposition\n\
  \      with:\n        employerId: tools.employerId\n        candidateId: tools.candidateId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-job-posting\n      description: Create a job posting on Indeed.\n      hints:\n        readOnly: false\n      call: indeed.create-job-posting\n      with:\n        employerId: tools.employerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-employer-jobs\n      description: List job postings for an employer.\n      hints:\n        readOnly: true\n      call: indeed.list-employer-jobs\n      with:\n        employerId: tools.employerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-job-posting\n      description: Get job posting details.\n      hints:\n        readOnly: true\n      call: indeed.get-job-posting\n      with:\n        employerId: tools.employerId\n        jobId: tools.jobId\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n    - name: update-job-posting\n      description: Update a job posting.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: indeed.update-job-posting\n      with:\n        employerId: tools.employerId\n        jobId: tools.jobId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: expire-job-posting\n      description: Expire a job posting.\n      hints:\n        destructive: true\n        idempotent: true\n      call: indeed.expire-job-posting\n      with:\n        employerId: tools.employerId\n        jobId: tools.jobId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/indeed/refs/heads/main/capabilities/talent-acquisition.yaml
tags:
- Indeed
- Talent Acquisition
- Hiring
- Job Postings
tools:
- description: Create an employer entity on Indeed.
  hints:
    readOnly: false
  name: create-employer
- description: Get employer details.
  hints:
    readOnly: true
  name: get-employer
- description: Update employer details.
  hints:
    idempotent: true
    readOnly: false
  name: update-employer
- description: Register employer for candidate sync.
  hints:
    readOnly: false
  name: register-candidate-sync
- description: List candidates for an employer.
  hints:
    openWorld: true
    readOnly: true
  name: list-candidates
- description: Get candidate details.
  hints:
    readOnly: true
  name: get-candidate
- description: Update candidate disposition status.
  hints:
    idempotent: true
    readOnly: false
  name: update-disposition
- description: Create a job posting on Indeed.
  hints:
    readOnly: false
  name: create-job-posting
- description: List job postings for an employer.
  hints:
    readOnly: true
  name: list-employer-jobs
- description: Get job posting details.
  hints:
    readOnly: true
  name: get-job-posting
- description: Update a job posting.
  hints:
    idempotent: true
    readOnly: false
  name: update-job-posting
- description: Expire a job posting.
  hints:
    destructive: true
    idempotent: true
  name: expire-job-posting
---
