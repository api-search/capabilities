---
categories:
- recruiting-ats
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
- linkedin
- create or update a job posting.
- update customer integrations
- authentication, sharing, and verification for consumer apps.
- create resume upload url.
- retrieve candidate matches.
- posts jobs and manages candidates through ats integrations.
- delete synced candidates.
- delete candidates
- provision a child application.
- professional networking
- create or update entity acl.
- create or update job posting
- uses sales navigator for lead generation and crm sync.
- update customer ats integrations.
- sync applications
- get seatholders
- retrieve recruiter seatholders.
- employee development tracking and content access.
- talent acquisition
- message archiving and regulatory communications governance.
- get child application
- tracks employee learning activity and completions.
- data portability and advertiser transparency for dma.
- integrates linkedin authentication and sharing into applications.
- sync candidates to linkedin.
- get job posting task status
- delete synced applications.
- get exported candidate profiles.
- recruiting
- get customer ats integration details.
- social media
- sales intelligence, lead management, and crm integration.
- get candidate matches
- get exported candidates
- job posting
- create resume upload url
- careers
- provision child application
- job posting, recruiting, and applicant tracking.
- b2b advertising, audience targeting, and campaign analytics.
- delete applications
- archives communications for regulatory compliance.
- get customer integrations
- sync candidates
- sync job applications.
- check job posting task status.
- manages b2b ad campaigns and audience targeting on linkedin.
- marketing
- get child application credentials.
- business
- upsert entity acl
slug: talent-acquisition
source_filename: talent-acquisition.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"LinkedIn Talent Acquisition\"\n  description: \"Unified workflow for recruiters to post jobs, sync candidates and applications via ATS, manage recruiter integrations, and provision partner applications -- combining job posting, RSC, and provisioning APIs.\"\n  tags:\n    - LinkedIn\n    - Talent Acquisition\n    - Recruiting\n    - Job Posting\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      LINKEDIN_OAUTH_TOKEN: LINKEDIN_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: talent-job-posting\n      location: ./shared/talent-job-posting.yaml\n    - import: talent-rsc\n      location: ./shared/talent-recruiter-system-connect.yaml\n    - import: talent-learning-parent-app\n      location: ./shared/talent-learning-parent-application.yaml\n\n  exposes:\n    - type: rest\n      port: 8085\n      namespace: talent-acquisition-api\n      description: \"Unified REST API for LinkedIn\
  \ talent acquisition workflows.\"\n      resources:\n        - path: /v1/job-postings\n          name: job-postings\n          operations:\n            - method: POST\n              name: create-or-update-job-posting\n              description: \"Create or update a job posting.\"\n              call: \"talent-job-posting.create-or-update-job-posting\"\n        - path: /v1/job-posting-tasks\n          name: job-posting-tasks\n          operations:\n            - method: GET\n              name: get-job-posting-task-status\n              description: \"Check job posting task status.\"\n              call: \"talent-job-posting.get-job-posting-task-status\"\n        - path: /v1/ats-integrations\n          name: ats-integrations\n          operations:\n            - method: POST\n              name: update-customer-integrations\n              description: \"Update customer ATS integrations.\"\n              call: \"talent-job-posting.update-customer-integrations\"\n            - method: GET\n\
  \              name: get-customer-integrations\n              description: \"Get customer ATS integration details.\"\n              call: \"talent-job-posting.get-customer-integrations\"\n        - path: /v1/candidates\n          name: candidates\n          operations:\n            - method: PUT\n              name: sync-candidates\n              description: \"Sync candidates to LinkedIn.\"\n              call: \"talent-rsc.sync-candidates\"\n            - method: GET\n              name: get-candidate-matches\n              description: \"Retrieve candidate matches.\"\n              call: \"talent-rsc.get-candidate-matches\"\n            - method: DELETE\n              name: delete-candidates\n              description: \"Delete synced candidates.\"\n              call: \"talent-rsc.delete-candidates\"\n        - path: /v1/applications\n          name: applications\n          operations:\n            - method: PUT\n              name: sync-applications\n              description: \"\
  Sync job applications.\"\n              call: \"talent-rsc.sync-applications\"\n            - method: DELETE\n              name: delete-applications\n              description: \"Delete synced applications.\"\n              call: \"talent-rsc.delete-applications\"\n        - path: /v1/exported-candidates\n          name: exported-candidates\n          operations:\n            - method: GET\n              name: get-exported-candidates\n              description: \"Get exported candidate profiles.\"\n              call: \"talent-rsc.get-exported-candidates\"\n        - path: /v1/seatholders\n          name: seatholders\n          operations:\n            - method: GET\n              name: get-seatholders\n              description: \"Retrieve recruiter seatholders.\"\n              call: \"talent-rsc.get-seatholders\"\n        - path: /v1/provisioned-applications\n          name: provisioned-applications\n          operations:\n            - method: POST\n              name: provision-child-application\n\
  \              description: \"Provision a child application.\"\n              call: \"talent-learning-parent-app.provision-child-application\"\n            - method: GET\n              name: get-child-application\n              description: \"Get child application credentials.\"\n              call: \"talent-learning-parent-app.get-child-application\"\n\n    - type: mcp\n      port: 9095\n      namespace: talent-acquisition-mcp\n      transport: http\n      description: \"MCP server for AI-assisted LinkedIn talent acquisition.\"\n      tools:\n        - name: create-or-update-job-posting\n          description: \"Create or update a job posting.\"\n          hints: { readOnly: false, destructive: false, idempotent: false }\n          call: \"talent-job-posting.create-or-update-job-posting\"\n        - name: get-job-posting-task-status\n          description: \"Check job posting task status.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"\
  talent-job-posting.get-job-posting-task-status\"\n        - name: update-customer-integrations\n          description: \"Update customer ATS integrations.\"\n          hints: { readOnly: false, destructive: false, idempotent: true }\n          call: \"talent-job-posting.update-customer-integrations\"\n        - name: get-customer-integrations\n          description: \"Get customer ATS integration details.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"talent-job-posting.get-customer-integrations\"\n        - name: sync-candidates\n          description: \"Sync candidates to LinkedIn.\"\n          hints: { readOnly: false, destructive: false, idempotent: true }\n          call: \"talent-rsc.sync-candidates\"\n        - name: get-candidate-matches\n          description: \"Retrieve candidate matches.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"talent-rsc.get-candidate-matches\"\n        -\
  \ name: delete-candidates\n          description: \"Delete synced candidates.\"\n          hints: { readOnly: false, destructive: true, idempotent: true }\n          call: \"talent-rsc.delete-candidates\"\n        - name: sync-applications\n          description: \"Sync job applications.\"\n          hints: { readOnly: false, destructive: false, idempotent: true }\n          call: \"talent-rsc.sync-applications\"\n        - name: delete-applications\n          description: \"Delete synced applications.\"\n          hints: { readOnly: false, destructive: true, idempotent: true }\n          call: \"talent-rsc.delete-applications\"\n        - name: create-resume-upload-url\n          description: \"Create resume upload URL.\"\n          hints: { readOnly: false, destructive: false, idempotent: false }\n          call: \"talent-rsc.create-resume-upload-url\"\n        - name: get-exported-candidates\n          description: \"Get exported candidate profiles.\"\n          hints: { readOnly: true,\
  \ destructive: false, idempotent: true }\n          call: \"talent-rsc.get-exported-candidates\"\n        - name: get-seatholders\n          description: \"Retrieve recruiter seatholders.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"talent-rsc.get-seatholders\"\n        - name: upsert-entity-acl\n          description: \"Create or update entity ACL.\"\n          hints: { readOnly: false, destructive: false, idempotent: true }\n          call: \"talent-rsc.upsert-entity-acl\"\n        - name: provision-child-application\n          description: \"Provision a child application.\"\n          hints: { readOnly: false, destructive: false, idempotent: false }\n          call: \"talent-learning-parent-app.provision-child-application\"\n        - name: get-child-application\n          description: \"Get child application credentials.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"talent-learning-parent-app.get-child-application\"\
  \n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/linkedin/refs/heads/main/capabilities/talent-acquisition.yaml
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
