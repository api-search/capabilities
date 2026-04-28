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
- get crm validation job
- archives communications for regulatory compliance.
- crm integration
- careers
- create crm data validation export job.
- get export job
- uses sales navigator for lead generation and crm sync.
- tracks employee learning activity and completions.
- professional networking
- get crm data validation export job status.
- message archiving and regulatory communications governance.
- social media
- create crm validation job
- authentication, sharing, and verification for consumer apps.
- find all contracts where user has an active seat.
- b2b advertising, audience targeting, and campaign analytics.
- linkedin
- employee development tracking and content access.
- fetch export job status.
- get sales access token
- marketing
- sales intelligence, lead management, and crm integration.
- recruiting
- get sales access token.
- create export job
- fetch sales analytics export job by id.
- business
- create crm data validation job.
- job posting, recruiting, and applicant tracking.
- get crm validation job status.
- sales navigator
- create sales analytics export job.
- create new sales analytics export job.
- posts jobs and manages candidates through ats integrations.
- integrates linkedin authentication and sharing into applications.
- data portability and advertiser transparency for dma.
- sales
- batch fetch profile associations from crm records.
- get contracts
- manages b2b ad campaigns and audience targeting on linkedin.
- batch get profile associations
- batch fetch profile associations.
- retrieve sales access token.
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
