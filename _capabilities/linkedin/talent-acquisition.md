---
consumed_apis:
- talent-job-posting
- talent-rsc
- talent-learning-parent-app
description: Unified workflow for recruiters to post jobs, sync candidates and applications via ATS, manage recruiter integrations, and provision partner applications -- combining job posting, RSC, and provisioning APIs.
layout: capability
name: LinkedIn Talent Acquisition
operations:
- description: Create or update a job posting.
  method: POST
  name: create-or-update-job-posting
  path: /v1/job-postings
- description: Check job posting task status.
  method: GET
  name: get-job-posting-task-status
  path: /v1/job-posting-tasks
- description: Update customer ATS integrations.
  method: POST
  name: update-customer-integrations
  path: /v1/ats-integrations
- description: Get customer ATS integration details.
  method: GET
  name: get-customer-integrations
  path: /v1/ats-integrations
- description: Sync candidates to LinkedIn.
  method: PUT
  name: sync-candidates
  path: /v1/candidates
- description: Retrieve candidate matches.
  method: GET
  name: get-candidate-matches
  path: /v1/candidates
- description: Delete synced candidates.
  method: DELETE
  name: delete-candidates
  path: /v1/candidates
- description: Sync job applications.
  method: PUT
  name: sync-applications
  path: /v1/applications
- description: Delete synced applications.
  method: DELETE
  name: delete-applications
  path: /v1/applications
- description: Get exported candidate profiles.
  method: GET
  name: get-exported-candidates
  path: /v1/exported-candidates
- description: Retrieve recruiter seatholders.
  method: GET
  name: get-seatholders
  path: /v1/seatholders
- description: Provision a child application.
  method: POST
  name: provision-child-application
  path: /v1/provisioned-applications
- description: Get child application credentials.
  method: GET
  name: get-child-application
  path: /v1/provisioned-applications
personas: []
provider_name: LinkedIn
provider_slug: linkedin
search_terms:
- delete synced applications.
- upsert entity acl
- archives communications for regulatory compliance.
- sales intelligence, lead management, and crm integration.
- sync candidates to linkedin.
- marketing
- delete candidates
- authentication, sharing, and verification for consumer apps.
- social media
- recruiting
- get exported candidates
- create or update entity acl.
- retrieve candidate matches.
- manages b2b ad campaigns and audience targeting on linkedin.
- employee development tracking and content access.
- get customer integrations
- provision a child application.
- update customer integrations
- get child application credentials.
- sync applications
- careers
- provision child application
- update customer ats integrations.
- delete applications
- create or update a job posting.
- create resume upload url
- business
- talent acquisition
- create resume upload url.
- linkedin
- get customer ats integration details.
- sync candidates
- posts jobs and manages candidates through ats integrations.
- job posting
- integrates linkedin authentication and sharing into applications.
- get child application
- b2b advertising, audience targeting, and campaign analytics.
- uses sales navigator for lead generation and crm sync.
- message archiving and regulatory communications governance.
- check job posting task status.
- retrieve recruiter seatholders.
- professional networking
- delete synced candidates.
- create or update job posting
- get job posting task status
- tracks employee learning activity and completions.
- get candidate matches
- get seatholders
- job posting, recruiting, and applicant tracking.
- data portability and advertiser transparency for dma.
- get exported candidate profiles.
- sync job applications.
slug: talent-acquisition
tags:
- LinkedIn
- Talent Acquisition
- Recruiting
- Job Posting
tools:
- description: Create or update a job posting.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-or-update-job-posting
- description: Check job posting task status.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-job-posting-task-status
- description: Update customer ATS integrations.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-customer-integrations
- description: Get customer ATS integration details.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-customer-integrations
- description: Sync candidates to LinkedIn.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: sync-candidates
- description: Retrieve candidate matches.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-candidate-matches
- description: Delete synced candidates.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-candidates
- description: Sync job applications.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: sync-applications
- description: Delete synced applications.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-applications
- description: Create resume upload URL.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-resume-upload-url
- description: Get exported candidate profiles.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-exported-candidates
- description: Retrieve recruiter seatholders.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-seatholders
- description: Create or update entity ACL.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: upsert-entity-acl
- description: Provision a child application.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: provision-child-application
- description: Get child application credentials.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-child-application
---
