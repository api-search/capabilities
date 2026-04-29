---
categories:
- recruiting-ats
consumed_apis:
- indeed
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
- list employer jobs
- update job posting
- expire a job posting.
- employment
- indeed
- employer management.
- update a job posting.
- list job postings for an employer.
- update disposition
- job search
- talent acquisition
- list candidates
- create job
- list job postings.
- candidate management.
- get job posting
- expire job posting
- careers
- update candidate disposition status.
- create an employer entity on indeed.
- hiring
- get employer
- create employer
- get employer details.
- job posting management.
- create a job posting.
- job postings
- create an employer entity.
- individual employer management.
- create a job posting on indeed.
- update employer
- register employer for candidate sync.
- get job posting details.
- list jobs
- create job posting
- jobs
- register candidate sync
- get candidate
- update employer details.
- get candidate details.
- recruiting
- list candidates for an employer.
slug: talent-acquisition
source_filename: talent-acquisition.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Indeed Talent Acquisition\"\n  description: \"Unified workflow for managing the hiring pipeline including employer setup, job posting, candidate retrieval, and disposition tracking. Used by ATS partners and hiring platform developers.\"\n  tags:\n    - Indeed\n    - Talent Acquisition\n    - Hiring\n    - Job Postings\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      INDEED_ACCESS_TOKEN: INDEED_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: indeed\n      location: ./shared/employer-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: indeed-talent-api\n      description: \"Unified REST API for Indeed talent acquisition workflows.\"\n      resources:\n        - path: /v1/employers\n          name: employers\n          description: \"Employer management.\"\n          operations:\n            - method: POST\n              name: create-employer\n\
  \              description: \"Create an employer entity.\"\n              call: \"indeed.create-employer\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/employers/{id}\n          name: employer-details\n          description: \"Individual employer management.\"\n          operations:\n            - method: GET\n              name: get-employer\n              description: \"Get employer details.\"\n              call: \"indeed.get-employer\"\n              with:\n                employerId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-employer\n              description: \"Update employer details.\"\n              call: \"indeed.update-employer\"\n              with:\n                employerId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n        - path: /v1/employers/{id}/candidates\n          name: candidates\n          description: \"Candidate management.\"\n          operations:\n            - method: GET\n              name: list-candidates\n              description: \"List candidates for an employer.\"\n              call: \"indeed.list-candidates\"\n              with:\n                employerId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/employers/{id}/jobs\n          name: jobs\n          description: \"Job posting management.\"\n          operations:\n            - method: GET\n              name: list-jobs\n              description: \"List job postings.\"\n              call: \"indeed.list-employer-jobs\"\n              with:\n                employerId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name:\
  \ create-job\n              description: \"Create a job posting.\"\n              call: \"indeed.create-job-posting\"\n              with:\n                employerId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: indeed-talent-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Indeed talent acquisition.\"\n      tools:\n        - name: create-employer\n          description: \"Create an employer entity on Indeed.\"\n          hints:\n            readOnly: false\n          call: \"indeed.create-employer\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-employer\n          description: \"Get employer details.\"\n          hints:\n            readOnly: true\n          call: \"indeed.get-employer\"\n          with:\n            employerId: \"tools.employerId\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: update-employer\n          description: \"Update employer details.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"indeed.update-employer\"\n          with:\n            employerId: \"tools.employerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: register-candidate-sync\n          description: \"Register employer for candidate sync.\"\n          hints:\n            readOnly: false\n          call: \"indeed.register-employer-candidate-sync\"\n          with:\n            employerId: \"tools.employerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-candidates\n          description: \"List candidates for an employer.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"indeed.list-candidates\"\n  \
  \        with:\n            employerId: \"tools.employerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-candidate\n          description: \"Get candidate details.\"\n          hints:\n            readOnly: true\n          call: \"indeed.get-candidate\"\n          with:\n            employerId: \"tools.employerId\"\n            candidateId: \"tools.candidateId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-disposition\n          description: \"Update candidate disposition status.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"indeed.update-candidate-disposition\"\n          with:\n            employerId: \"tools.employerId\"\n            candidateId: \"tools.candidateId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-job-posting\n          description:\
  \ \"Create a job posting on Indeed.\"\n          hints:\n            readOnly: false\n          call: \"indeed.create-job-posting\"\n          with:\n            employerId: \"tools.employerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-employer-jobs\n          description: \"List job postings for an employer.\"\n          hints:\n            readOnly: true\n          call: \"indeed.list-employer-jobs\"\n          with:\n            employerId: \"tools.employerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-job-posting\n          description: \"Get job posting details.\"\n          hints:\n            readOnly: true\n          call: \"indeed.get-job-posting\"\n          with:\n            employerId: \"tools.employerId\"\n            jobId: \"tools.jobId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        -\
  \ name: update-job-posting\n          description: \"Update a job posting.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"indeed.update-job-posting\"\n          with:\n            employerId: \"tools.employerId\"\n            jobId: \"tools.jobId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: expire-job-posting\n          description: \"Expire a job posting.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"indeed.expire-job-posting\"\n          with:\n            employerId: \"tools.employerId\"\n            jobId: \"tools.jobId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
