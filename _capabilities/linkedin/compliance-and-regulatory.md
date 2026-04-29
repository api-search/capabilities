---
categories:
- compliance
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
- batch get organizations
- authentication, sharing, and verification for consumer apps.
- marketing
- get advertiser transparency data.
- integrates linkedin authentication and sharing into applications.
- get organization acls
- get business manager account relationships.
- check member status
- get organization acls for data portability.
- get advertiser transparency data for a sponsored account.
- business
- careers
- linkedin
- opt out a member from compliance monitoring.
- message archiving and regulatory communications governance.
- opt in a member for compliance monitoring.
- get dma posts
- get page content analytics
- employee development tracking and content access.
- uses sales navigator for lead generation and crm sync.
- data portability
- compliance
- get comments for data portability.
- archives communications for regulatory compliance.
- posts jobs and manages candidates through ats integrations.
- job posting, recruiting, and applicant tracking.
- manages b2b ad campaigns and audience targeting on linkedin.
- regulatory
- get reactions for data portability.
- retrieve compliance events for a regulated member.
- get organization
- tracks employee learning activity and completions.
- get compliance events
- get posts for data portability.
- check member compliance monitoring status.
- get dma reactions
- opt out member
- get dma events
- get organization by id for data portability.
- get page content analytics for data portability.
- batch get organizations for data portability.
- b2b advertising, audience targeting, and campaign analytics.
- get organization by id.
- retrieve compliance events.
- recruiting
- data portability and advertiser transparency for dma.
- get dma lead gen responses
- get events for data portability.
- get lead gen responses for data portability.
- professional networking
- social media
- get dma comments
- opt in member
- get advertiser transparency
- get business manager relationships
- sales intelligence, lead management, and crm integration.
slug: compliance-and-regulatory
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"LinkedIn Compliance And Regulatory\"\n  description: \"Unified workflow for compliance officers to monitor regulated communications, export data for portability compliance, and access ads transparency data -- combining compliance events, data portability, and ads transparency APIs.\"\n  tags:\n    - LinkedIn\n    - Compliance\n    - Regulatory\n    - Data Portability\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      LINKEDIN_OAUTH_TOKEN: LINKEDIN_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: compliance-events\n      location: ./shared/compliance-events.yaml\n    - import: data-portability\n      location: ./shared/data-portability.yaml\n    - import: ads-transparency\n      location: ./shared/ads-transparency.yaml\n\n  exposes:\n    - type: rest\n      port: 8086\n      namespace: compliance-regulatory-api\n      description: \"Unified REST API for LinkedIn compliance\
  \ and regulatory workflows.\"\n      resources:\n        - path: /v1/compliance-authorizations\n          name: compliance-authorizations\n          operations:\n            - method: POST\n              name: opt-in-member\n              description: \"Opt in a member for compliance monitoring.\"\n              call: \"compliance-events.opt-in-member\"\n            - method: GET\n              name: check-member-status\n              description: \"Check member compliance monitoring status.\"\n              call: \"compliance-events.check-member-status\"\n        - path: /v1/compliance-events\n          name: compliance-events\n          operations:\n            - method: GET\n              name: get-compliance-events\n              description: \"Retrieve compliance events.\"\n              call: \"compliance-events.get-compliance-events\"\n        - path: /v1/dma-organizations\n          name: dma-organizations\n          operations:\n            - method: GET\n              name: batch-get-organizations\n\
  \              description: \"Batch get organizations for data portability.\"\n              call: \"data-portability.batch-get-organizations\"\n        - path: /v1/dma-organizations/{organizationId}\n          name: dma-organization-by-id\n          operations:\n            - method: GET\n              name: get-organization\n              description: \"Get organization by ID.\"\n              call: \"data-portability.get-organization\"\n        - path: /v1/dma-posts\n          name: dma-posts\n          operations:\n            - method: GET\n              name: get-dma-posts\n              description: \"Get posts for data portability.\"\n              call: \"data-portability.get-posts\"\n        - path: /v1/dma-reactions\n          name: dma-reactions\n          operations:\n            - method: GET\n              name: get-dma-reactions\n              description: \"Get reactions for data portability.\"\n              call: \"data-portability.get-reactions\"\n        - path: /v1/dma-comments\n\
  \          name: dma-comments\n          operations:\n            - method: GET\n              name: get-dma-comments\n              description: \"Get comments for data portability.\"\n              call: \"data-portability.get-comments\"\n        - path: /v1/dma-events\n          name: dma-events\n          operations:\n            - method: GET\n              name: get-dma-events\n              description: \"Get events for data portability.\"\n              call: \"data-portability.get-events\"\n        - path: /v1/advertiser-transparency/{sponsoredaccount_id}\n          name: advertiser-transparency\n          operations:\n            - method: GET\n              name: get-advertiser-transparency\n              description: \"Get advertiser transparency data.\"\n              call: \"ads-transparency.get-advertiser-transparency\"\n\n    - type: mcp\n      port: 9096\n      namespace: compliance-regulatory-mcp\n      transport: http\n      description: \"MCP server for AI-assisted\
  \ LinkedIn compliance and regulatory workflows.\"\n      tools:\n        - name: opt-in-member\n          description: \"Opt in a member for compliance monitoring.\"\n          hints: { readOnly: false, destructive: false, idempotent: false }\n          call: \"compliance-events.opt-in-member\"\n        - name: check-member-status\n          description: \"Check member compliance monitoring status.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"compliance-events.check-member-status\"\n        - name: opt-out-member\n          description: \"Opt out a member from compliance monitoring.\"\n          hints: { readOnly: false, destructive: true, idempotent: true }\n          call: \"compliance-events.opt-out-member\"\n        - name: get-compliance-events\n          description: \"Retrieve compliance events for a regulated member.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"compliance-events.get-compliance-events\"\
  \n        - name: batch-get-organizations\n          description: \"Batch get organizations for data portability.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"data-portability.batch-get-organizations\"\n        - name: get-organization\n          description: \"Get organization by ID for data portability.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"data-portability.get-organization\"\n        - name: get-organization-acls\n          description: \"Get organization ACLs for data portability.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"data-portability.get-organization-acls\"\n        - name: get-page-content-analytics\n          description: \"Get page content analytics for data portability.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"data-portability.get-page-content-analytics\"\n \
  \       - name: get-dma-posts\n          description: \"Get posts for data portability.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"data-portability.get-posts\"\n        - name: get-dma-reactions\n          description: \"Get reactions for data portability.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"data-portability.get-reactions\"\n        - name: get-dma-comments\n          description: \"Get comments for data portability.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"data-portability.get-comments\"\n        - name: get-dma-lead-gen-responses\n          description: \"Get lead gen responses for data portability.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"data-portability.get-lead-gen-responses\"\n        - name: get-dma-events\n          description: \"Get events for data portability.\"\
  \n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"data-portability.get-events\"\n        - name: get-business-manager-relationships\n          description: \"Get business manager account relationships.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"data-portability.get-business-manager-relationships\"\n        - name: get-advertiser-transparency\n          description: \"Get advertiser transparency data for a sponsored account.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"ads-transparency.get-advertiser-transparency\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/linkedin/refs/heads/main/capabilities/compliance-and-regulatory.yaml
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
