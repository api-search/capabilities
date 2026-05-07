---
categories:
- recruiting-ats
consumed_apis: []
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
- get customer integrations
- get exported candidates
- provision a child application.
- tracks employee learning activity and completions.
- social media
- retrieve candidate matches.
- provision child application
- sync candidates to linkedin.
- delete synced applications.
- get exported candidate profiles.
- get child application
- uses sales navigator for lead generation and crm sync.
- get customer ats integration details.
- update customer integrations
- delete candidates
- talent acquisition
- professional networking
- create resume upload url.
- integrates linkedin authentication and sharing into applications.
- linkedin
- create or update job posting
- employee development tracking and content access.
- create resume upload url
- create or update a job posting.
- sync job applications.
- job posting, recruiting, and applicant tracking.
- business
- upsert entity acl
- data portability and advertiser transparency for dma.
- sales intelligence, lead management, and crm integration.
- message archiving and regulatory communications governance.
- update customer ats integrations.
- recruiting
- archives communications for regulatory compliance.
- get seatholders
- posts jobs and manages candidates through ats integrations.
- create or update entity acl.
- careers
- delete synced candidates.
- b2b advertising, audience targeting, and campaign analytics.
- marketing
- delete applications
- sync applications
- manages b2b ad campaigns and audience targeting on linkedin.
- authentication, sharing, and verification for consumer apps.
- job posting
- get candidate matches
- check job posting task status.
- sync candidates
- get job posting task status
- get child application credentials.
- retrieve recruiter seatholders.
slug: talent-acquisition
source_filename: talent-acquisition.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: LinkedIn Talent Acquisition\n  description: Unified workflow for recruiters to post jobs, sync candidates and applications via ATS, manage recruiter integrations,\n    and provision partner applications -- combining job posting, RSC, and provisioning APIs.\n  tags:\n  - LinkedIn\n  - Talent Acquisition\n  - Recruiting\n  - Job Posting\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    LINKEDIN_OAUTH_TOKEN: LINKEDIN_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: talent-job-posting\n    baseUri: https://api.linkedin.com\n    description: LinkedIn Job Posting API.\n    authentication:\n      type: bearer\n      token: '{{LINKEDIN_OAUTH_TOKEN}}'\n    resources:\n    - name: simple-job-postings\n      path: /v2/simpleJobPostings\n      description: Apply Connect job posting management.\n      operations:\n      - name: create-or-update-job-posting\n        method: POST\n       \
  \ description: Create or update an Apply Connect job posting.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: simple-job-posting-tasks\n      path: /v2/simpleJobPostingTasks\n      description: Job posting task status.\n      operations:\n      - name: get-job-posting-task-status\n        method: GET\n        description: Check job posting task status.\n        inputParameters:\n        - name: ids\n          in: query\n          type: string\n          required: true\n          description: Task URN(s)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ats-integrations\n      path: /v2/atsIntegrations\n      description: ATS integration management.\n      operations:\n      - name: update-customer-integrations\n        method: POST\n        description: Update customer ATS integrations.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-customer-integrations\n        method: GET\n        description: Get customer ATS integration details.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: talent-rsc\n    baseUri: https://api.linkedin.com\n    description: LinkedIn Recruiter System Connect API.\n    authentication:\n      type: bearer\n      token: '{{LINKEDIN_OAUTH_TOKEN}}'\n    resources:\n    - name: ats-integrations\n      path: /v2/atsIntegrations\n      description: ATS integration configuration.\n      operations:\n      - name: update-ats-integration\n        method: POST\n        description: Update customer ATS integration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-integration-notification\n\
  \        method: GET\n        description: Get integration status change notification.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Query type\n        - name: requestId\n          in: query\n          type: string\n          required: true\n          description: Request ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ats-candidates\n      path: /v2/atsCandidates\n      description: Candidate synchronization.\n      operations:\n      - name: sync-candidates\n        method: PUT\n        description: Sync candidates to LinkedIn.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-candidate-matches\n        method: GET\n        description: Retrieve candidate matches.\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-candidates\n        method: DELETE\n        description: Delete synced candidates.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ats-applications\n      path: /v2/atsApplications\n      description: Application synchronization.\n      operations:\n      - name: sync-applications\n        method: PUT\n        description: Sync job applications.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-applications\n        method: DELETE\n        description: Delete synced applications.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resume-upload\n      path: /v2/hireMediaUrl\n      description: Resume upload\
  \ management.\n      operations:\n      - name: create-resume-upload-url\n        method: POST\n        description: Create resume upload URL.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: exported-candidates\n      path: /v2/exportedCandidates\n      description: Exported candidate retrieval.\n      operations:\n      - name: get-exported-candidates\n        method: GET\n        description: Get exported candidate profile.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Query type\n        - name: requestId\n          in: query\n          type: string\n          required: true\n          description: Request ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: seats\n      path: /v2/seats\n      description: Recruiter\
  \ seatholders.\n      operations:\n      - name: get-seatholders\n        method: GET\n        description: Retrieve recruiter seatholders.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Query type\n        - name: contracts\n          in: query\n          type: string\n          required: true\n          description: Contract URN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ats-entity-acls\n      path: /v2/atsEntityAcls\n      description: Entity ACL management.\n      operations:\n      - name: upsert-entity-acl\n        method: PUT\n        description: Create or update entity ACL.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-entity-acl\n        method: GET\n        description: Retrieve entity ACL.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-entity-acl\n        method: DELETE\n        description: Delete entity ACL.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: talent-learning-parent-app\n    baseUri: https://api.linkedin.com\n    description: LinkedIn Parent Application Management API.\n    authentication:\n      type: bearer\n      token: '{{LINKEDIN_OAUTH_TOKEN}}'\n    resources:\n    - name: provisioned-applications\n      path: /v2/provisionedApplications\n      description: Child application provisioning.\n      operations:\n      - name: provision-child-application\n        method: POST\n        description: Provision a new child application for a customer.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: get-child-application\n        method: GET\n        description: Get child application credentials.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Query type\n        - name: uniqueForeignId\n          in: query\n          type: string\n          required: true\n          description: Partner's unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: provisioned-application-by-urn\n      path: /v2/provisionedApplications/{customer_application_urn}\n      description: Update child application.\n      operations:\n      - name: update-callback-urls\n        method: POST\n        description: Update OAuth 2.0 callback URLs for a child application.\n        inputParameters:\n        - name: customer_application_urn\n          in: path\n          type: string\n   \
  \       required: true\n          description: Customer application URN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8085\n    namespace: talent-acquisition-api\n    description: Unified REST API for LinkedIn talent acquisition workflows.\n    resources:\n    - path: /v1/job-postings\n      name: job-postings\n      operations:\n      - method: POST\n        name: create-or-update-job-posting\n        description: Create or update a job posting.\n        call: talent-job-posting.create-or-update-job-posting\n    - path: /v1/job-posting-tasks\n      name: job-posting-tasks\n      operations:\n      - method: GET\n        name: get-job-posting-task-status\n        description: Check job posting task status.\n        call: talent-job-posting.get-job-posting-task-status\n    - path: /v1/ats-integrations\n      name: ats-integrations\n      operations:\n      - method: POST\n\
  \        name: update-customer-integrations\n        description: Update customer ATS integrations.\n        call: talent-job-posting.update-customer-integrations\n      - method: GET\n        name: get-customer-integrations\n        description: Get customer ATS integration details.\n        call: talent-job-posting.get-customer-integrations\n    - path: /v1/candidates\n      name: candidates\n      operations:\n      - method: PUT\n        name: sync-candidates\n        description: Sync candidates to LinkedIn.\n        call: talent-rsc.sync-candidates\n      - method: GET\n        name: get-candidate-matches\n        description: Retrieve candidate matches.\n        call: talent-rsc.get-candidate-matches\n      - method: DELETE\n        name: delete-candidates\n        description: Delete synced candidates.\n        call: talent-rsc.delete-candidates\n    - path: /v1/applications\n      name: applications\n      operations:\n      - method: PUT\n        name: sync-applications\n   \
  \     description: Sync job applications.\n        call: talent-rsc.sync-applications\n      - method: DELETE\n        name: delete-applications\n        description: Delete synced applications.\n        call: talent-rsc.delete-applications\n    - path: /v1/exported-candidates\n      name: exported-candidates\n      operations:\n      - method: GET\n        name: get-exported-candidates\n        description: Get exported candidate profiles.\n        call: talent-rsc.get-exported-candidates\n    - path: /v1/seatholders\n      name: seatholders\n      operations:\n      - method: GET\n        name: get-seatholders\n        description: Retrieve recruiter seatholders.\n        call: talent-rsc.get-seatholders\n    - path: /v1/provisioned-applications\n      name: provisioned-applications\n      operations:\n      - method: POST\n        name: provision-child-application\n        description: Provision a child application.\n        call: talent-learning-parent-app.provision-child-application\n\
  \      - method: GET\n        name: get-child-application\n        description: Get child application credentials.\n        call: talent-learning-parent-app.get-child-application\n  - type: mcp\n    port: 9095\n    namespace: talent-acquisition-mcp\n    transport: http\n    description: MCP server for AI-assisted LinkedIn talent acquisition.\n    tools:\n    - name: create-or-update-job-posting\n      description: Create or update a job posting.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: talent-job-posting.create-or-update-job-posting\n    - name: get-job-posting-task-status\n      description: Check job posting task status.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: talent-job-posting.get-job-posting-task-status\n    - name: update-customer-integrations\n      description: Update customer ATS integrations.\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: true\n      call: talent-job-posting.update-customer-integrations\n    - name: get-customer-integrations\n      description: Get customer ATS integration details.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: talent-job-posting.get-customer-integrations\n    - name: sync-candidates\n      description: Sync candidates to LinkedIn.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: talent-rsc.sync-candidates\n    - name: get-candidate-matches\n      description: Retrieve candidate matches.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: talent-rsc.get-candidate-matches\n    - name: delete-candidates\n      description: Delete synced candidates.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: talent-rsc.delete-candidates\n    - name: sync-applications\n\
  \      description: Sync job applications.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: talent-rsc.sync-applications\n    - name: delete-applications\n      description: Delete synced applications.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: talent-rsc.delete-applications\n    - name: create-resume-upload-url\n      description: Create resume upload URL.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: talent-rsc.create-resume-upload-url\n    - name: get-exported-candidates\n      description: Get exported candidate profiles.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: talent-rsc.get-exported-candidates\n    - name: get-seatholders\n      description: Retrieve recruiter seatholders.\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: talent-rsc.get-seatholders\n    - name: upsert-entity-acl\n      description: Create or update entity ACL.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: talent-rsc.upsert-entity-acl\n    - name: provision-child-application\n      description: Provision a child application.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: talent-learning-parent-app.provision-child-application\n    - name: get-child-application\n      description: Get child application credentials.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: talent-learning-parent-app.get-child-application\n"
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
