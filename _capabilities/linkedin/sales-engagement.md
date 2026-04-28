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
- recruiting
- job posting, recruiting, and applicant tracking.
- employee development tracking and content access.
- sales intelligence, lead management, and crm integration.
- careers
- get crm data validation export job status.
- fetch export job status.
- batch fetch profile associations.
- marketing
- business
- create export job
- data portability and advertiser transparency for dma.
- get contracts
- create crm data validation job.
- manages b2b ad campaigns and audience targeting on linkedin.
- message archiving and regulatory communications governance.
- get sales access token
- uses sales navigator for lead generation and crm sync.
- crm integration
- fetch sales analytics export job by id.
- professional networking
- retrieve sales access token.
- sales navigator
- get export job
- create crm data validation export job.
- tracks employee learning activity and completions.
- integrates linkedin authentication and sharing into applications.
- posts jobs and manages candidates through ats integrations.
- get crm validation job
- batch get profile associations
- get crm validation job status.
- sales
- create new sales analytics export job.
- create sales analytics export job.
- authentication, sharing, and verification for consumer apps.
- batch fetch profile associations from crm records.
- get sales access token.
- archives communications for regulatory compliance.
- create crm validation job
- b2b advertising, audience targeting, and campaign analytics.
- social media
- find all contracts where user has an active seat.
- linkedin
slug: sales-engagement
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
