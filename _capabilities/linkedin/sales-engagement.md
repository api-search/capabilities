---
categories:
- crm-sales
consumed_apis:
- sales-navigator
description: Unified workflow for sales representatives to manage Sales Navigator contracts, export analytics, associate CRM profiles, and validate CRM data.
layout: capability
name: LinkedIn Sales Engagement
operations:
- description: Find all contracts where user has an active seat.
  method: GET
  name: get-contracts
  path: /v1/sales-contracts
- description: Create sales analytics export job.
  method: POST
  name: create-export-job
  path: /v1/sales-analytics-export-jobs
- description: Fetch export job status.
  method: GET
  name: get-export-job
  path: /v1/sales-analytics-export-jobs/{JobId}
- description: Get sales access token.
  method: GET
  name: get-sales-access-token
  path: /v1/sales-access-tokens
- description: Batch fetch profile associations.
  method: GET
  name: batch-get-profile-associations
  path: /v1/profile-associations
- description: Create CRM data validation job.
  method: POST
  name: create-crm-validation-job
  path: /v1/crm-validation-jobs
- description: Get CRM validation job status.
  method: GET
  name: get-crm-validation-job
  path: /v1/crm-validation-jobs/{JobId}
personas: []
provider_name: LinkedIn
provider_slug: linkedin
search_terms:
- batch fetch profile associations.
- retrieve sales access token.
- professional networking
- create export job
- create crm data validation export job.
- authentication, sharing, and verification for consumer apps.
- fetch sales analytics export job by id.
- get sales access token
- archives communications for regulatory compliance.
- sales intelligence, lead management, and crm integration.
- data portability and advertiser transparency for dma.
- marketing
- get crm validation job status.
- linkedin
- batch fetch profile associations from crm records.
- employee development tracking and content access.
- get export job
- create crm data validation job.
- posts jobs and manages candidates through ats integrations.
- sales navigator
- get contracts
- b2b advertising, audience targeting, and campaign analytics.
- fetch export job status.
- careers
- get crm data validation export job status.
- social media
- crm integration
- batch get profile associations
- manages b2b ad campaigns and audience targeting on linkedin.
- job posting, recruiting, and applicant tracking.
- message archiving and regulatory communications governance.
- create new sales analytics export job.
- recruiting
- create crm validation job
- uses sales navigator for lead generation and crm sync.
- find all contracts where user has an active seat.
- create sales analytics export job.
- sales
- get sales access token.
- get crm validation job
- tracks employee learning activity and completions.
- business
- integrates linkedin authentication and sharing into applications.
slug: sales-engagement
source_filename: sales-engagement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"LinkedIn Sales Engagement\"\n  description: \"Unified workflow for sales representatives to manage Sales Navigator contracts, export analytics, associate CRM profiles, and validate CRM data.\"\n  tags:\n    - LinkedIn\n    - Sales Navigator\n    - CRM Integration\n    - Sales\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      LINKEDIN_OAUTH_TOKEN: LINKEDIN_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: sales-navigator\n      location: ./shared/sales-navigator.yaml\n\n  exposes:\n    - type: rest\n      port: 8084\n      namespace: sales-engagement-api\n      description: \"Unified REST API for LinkedIn sales engagement workflows.\"\n      resources:\n        - path: /v1/sales-contracts\n          name: sales-contracts\n          operations:\n            - method: GET\n              name: get-contracts\n              description: \"Find all contracts where user has an active\
  \ seat.\"\n              call: \"sales-navigator.get-contracts\"\n        - path: /v1/sales-analytics-export-jobs\n          name: sales-analytics-export-jobs\n          operations:\n            - method: POST\n              name: create-export-job\n              description: \"Create sales analytics export job.\"\n              call: \"sales-navigator.create-export-job\"\n        - path: /v1/sales-analytics-export-jobs/{JobId}\n          name: export-job-by-id\n          operations:\n            - method: GET\n              name: get-export-job\n              description: \"Fetch export job status.\"\n              call: \"sales-navigator.get-export-job\"\n        - path: /v1/sales-access-tokens\n          name: sales-access-tokens\n          operations:\n            - method: GET\n              name: get-sales-access-token\n              description: \"Get sales access token.\"\n              call: \"sales-navigator.get-sales-access-token\"\n        - path: /v1/profile-associations\n\
  \          name: profile-associations\n          operations:\n            - method: GET\n              name: batch-get-profile-associations\n              description: \"Batch fetch profile associations.\"\n              call: \"sales-navigator.batch-get-profile-associations\"\n        - path: /v1/crm-validation-jobs\n          name: crm-validation-jobs\n          operations:\n            - method: POST\n              name: create-crm-validation-job\n              description: \"Create CRM data validation job.\"\n              call: \"sales-navigator.create-crm-validation-job\"\n        - path: /v1/crm-validation-jobs/{JobId}\n          name: crm-validation-job-by-id\n          operations:\n            - method: GET\n              name: get-crm-validation-job\n              description: \"Get CRM validation job status.\"\n              call: \"sales-navigator.get-crm-validation-job\"\n\n    - type: mcp\n      port: 9094\n      namespace: sales-engagement-mcp\n      transport: http\n  \
  \    description: \"MCP server for AI-assisted LinkedIn sales engagement.\"\n      tools:\n        - name: get-contracts\n          description: \"Find all contracts where user has an active seat.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"sales-navigator.get-contracts\"\n        - name: create-export-job\n          description: \"Create new sales analytics export job.\"\n          hints: { readOnly: false, destructive: false, idempotent: false }\n          call: \"sales-navigator.create-export-job\"\n        - name: get-export-job\n          description: \"Fetch sales analytics export job by ID.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"sales-navigator.get-export-job\"\n        - name: get-sales-access-token\n          description: \"Retrieve sales access token.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"sales-navigator.get-sales-access-token\"\
  \n        - name: batch-get-profile-associations\n          description: \"Batch fetch profile associations from CRM records.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"sales-navigator.batch-get-profile-associations\"\n        - name: create-crm-validation-job\n          description: \"Create CRM data validation export job.\"\n          hints: { readOnly: false, destructive: false, idempotent: false }\n          call: \"sales-navigator.create-crm-validation-job\"\n        - name: get-crm-validation-job\n          description: \"Get CRM data validation export job status.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"sales-navigator.get-crm-validation-job\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/linkedin/refs/heads/main/capabilities/sales-engagement.yaml
tags:
- LinkedIn
- Sales Navigator
- CRM Integration
- Sales
tools:
- description: Find all contracts where user has an active seat.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-contracts
- description: Create new sales analytics export job.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-export-job
- description: Fetch sales analytics export job by ID.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-export-job
- description: Retrieve sales access token.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-sales-access-token
- description: Batch fetch profile associations from CRM records.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: batch-get-profile-associations
- description: Create CRM data validation export job.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-crm-validation-job
- description: Get CRM data validation export job status.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-crm-validation-job
---
