---
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
- update employer details.
- candidate management.
- get job posting details.
- list jobs
- expire a job posting.
- jobs
- employment
- list candidates
- get employer
- create job posting
- job search
- update employer
- list candidates for an employer.
- list job postings.
- create employer
- list job postings for an employer.
- list employer jobs
- careers
- register candidate sync
- get candidate
- create an employer entity on indeed.
- update a job posting.
- indeed
- create a job posting.
- create job
- create a job posting on indeed.
- expire job posting
- talent acquisition
- get candidate details.
- update candidate disposition status.
- employer management.
- update job posting
- create an employer entity.
- get job posting
- individual employer management.
- hiring
- job postings
- job posting management.
- update disposition
- recruiting
- register employer for candidate sync.
- get employer details.
slug: talent-acquisition
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
