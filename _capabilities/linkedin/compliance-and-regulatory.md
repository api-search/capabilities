---
consumed_apis:
- compliance-events
- data-portability
- ads-transparency
description: Unified workflow for compliance officers to monitor regulated communications, export data for portability compliance, and access ads transparency data -- combining compliance events, data portability, and ads transparency APIs.
layout: capability
name: LinkedIn Compliance And Regulatory
operations:
- description: Opt in a member for compliance monitoring.
  method: POST
  name: opt-in-member
  path: /v1/compliance-authorizations
- description: Check member compliance monitoring status.
  method: GET
  name: check-member-status
  path: /v1/compliance-authorizations
- description: Retrieve compliance events.
  method: GET
  name: get-compliance-events
  path: /v1/compliance-events
- description: Batch get organizations for data portability.
  method: GET
  name: batch-get-organizations
  path: /v1/dma-organizations
- description: Get organization by ID.
  method: GET
  name: get-organization
  path: /v1/dma-organizations/{organizationId}
- description: Get posts for data portability.
  method: GET
  name: get-dma-posts
  path: /v1/dma-posts
- description: Get reactions for data portability.
  method: GET
  name: get-dma-reactions
  path: /v1/dma-reactions
- description: Get comments for data portability.
  method: GET
  name: get-dma-comments
  path: /v1/dma-comments
- description: Get events for data portability.
  method: GET
  name: get-dma-events
  path: /v1/dma-events
- description: Get advertiser transparency data.
  method: GET
  name: get-advertiser-transparency
  path: /v1/advertiser-transparency/{sponsoredaccount_id}
personas: []
provider_name: LinkedIn
provider_slug: linkedin
search_terms:
- get organization
- get business manager relationships
- archives communications for regulatory compliance.
- sales intelligence, lead management, and crm integration.
- retrieve compliance events for a regulated member.
- retrieve compliance events.
- marketing
- get dma events
- authentication, sharing, and verification for consumer apps.
- social media
- recruiting
- get lead gen responses for data portability.
- get organization acls
- manages b2b ad campaigns and audience targeting on linkedin.
- employee development tracking and content access.
- opt out member
- get business manager account relationships.
- get dma posts
- careers
- get reactions for data portability.
- opt out a member from compliance monitoring.
- compliance
- business
- get organization by id.
- get posts for data portability.
- linkedin
- get organization by id for data portability.
- posts jobs and manages candidates through ats integrations.
- get page content analytics for data portability.
- get page content analytics
- integrates linkedin authentication and sharing into applications.
- b2b advertising, audience targeting, and campaign analytics.
- data portability
- get compliance events
- get dma lead gen responses
- get events for data portability.
- uses sales navigator for lead generation and crm sync.
- get advertiser transparency data for a sponsored account.
- message archiving and regulatory communications governance.
- professional networking
- batch get organizations
- get comments for data portability.
- tracks employee learning activity and completions.
- get organization acls for data portability.
- batch get organizations for data portability.
- check member compliance monitoring status.
- get dma comments
- job posting, recruiting, and applicant tracking.
- data portability and advertiser transparency for dma.
- check member status
- get dma reactions
- get advertiser transparency
- opt in a member for compliance monitoring.
- opt in member
- regulatory
- get advertiser transparency data.
slug: compliance-and-regulatory
tags:
- LinkedIn
- Compliance
- Regulatory
- Data Portability
tools:
- description: Opt in a member for compliance monitoring.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: opt-in-member
- description: Check member compliance monitoring status.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: check-member-status
- description: Opt out a member from compliance monitoring.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: opt-out-member
- description: Retrieve compliance events for a regulated member.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-compliance-events
- description: Batch get organizations for data portability.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: batch-get-organizations
- description: Get organization by ID for data portability.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-organization
- description: Get organization ACLs for data portability.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-organization-acls
- description: Get page content analytics for data portability.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-page-content-analytics
- description: Get posts for data portability.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-dma-posts
- description: Get reactions for data portability.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-dma-reactions
- description: Get comments for data portability.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-dma-comments
- description: Get lead gen responses for data portability.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-dma-lead-gen-responses
- description: Get events for data portability.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-dma-events
- description: Get business manager account relationships.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-business-manager-relationships
- description: Get advertiser transparency data for a sponsored account.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-advertiser-transparency
---
