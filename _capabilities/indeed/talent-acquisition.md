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
- register candidate sync
- create an employer entity on indeed.
- create employer
- job search
- hiring
- candidate management.
- register employer for candidate sync.
- recruiting
- jobs
- job posting management.
- get candidate
- list jobs
- get job posting
- get employer
- list candidates for an employer.
- list job postings for an employer.
- job postings
- update a job posting.
- create a job posting on indeed.
- careers
- create job posting
- create job
- update candidate disposition status.
- indeed
- update employer details.
- get job posting details.
- get candidate details.
- talent acquisition
- update disposition
- get employer details.
- list candidates
- list employer jobs
- expire job posting
- create an employer entity.
- individual employer management.
- employment
- update job posting
- update employer
- employer management.
- create a job posting.
- list job postings.
- expire a job posting.
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
