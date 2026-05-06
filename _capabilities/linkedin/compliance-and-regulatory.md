---
categories:
- compliance
consumed_apis: []
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
- get posts for data portability.
- check member compliance monitoring status.
- tracks employee learning activity and completions.
- get dma comments
- get dma posts
- recruiting
- careers
- authentication, sharing, and verification for consumer apps.
- batch get organizations
- opt in member
- linkedin
- marketing
- professional networking
- data portability and advertiser transparency for dma.
- batch get organizations for data portability.
- compliance
- get lead gen responses for data portability.
- get advertiser transparency data for a sponsored account.
- business
- get organization
- regulatory
- get page content analytics for data portability.
- get business manager relationships
- employee development tracking and content access.
- sales intelligence, lead management, and crm integration.
- check member status
- message archiving and regulatory communications governance.
- get organization by id.
- get comments for data portability.
- get organization by id for data portability.
- data portability
- b2b advertising, audience targeting, and campaign analytics.
- get business manager account relationships.
- get compliance events
- retrieve compliance events for a regulated member.
- get page content analytics
- manages b2b ad campaigns and audience targeting on linkedin.
- get advertiser transparency data.
- get events for data portability.
- get organization acls
- posts jobs and manages candidates through ats integrations.
- job posting, recruiting, and applicant tracking.
- retrieve compliance events.
- social media
- get organization acls for data portability.
- opt out member
- uses sales navigator for lead generation and crm sync.
- integrates linkedin authentication and sharing into applications.
- opt in a member for compliance monitoring.
- opt out a member from compliance monitoring.
- get reactions for data portability.
- get dma events
- get dma lead gen responses
- archives communications for regulatory compliance.
- get dma reactions
- get advertiser transparency
slug: compliance-and-regulatory
source_filename: compliance-and-regulatory.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: LinkedIn Compliance And Regulatory\n  description: Unified workflow for compliance officers to monitor regulated communications, export data for portability compliance,\n    and access ads transparency data -- combining compliance events, data portability, and ads transparency APIs.\n  tags:\n  - LinkedIn\n  - Compliance\n  - Regulatory\n  - Data Portability\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    LINKEDIN_OAUTH_TOKEN: LINKEDIN_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: compliance-events\n    baseUri: https://api.linkedin.com\n    description: LinkedIn Compliance Events API for monitoring and archiving communications.\n    authentication:\n      type: bearer\n      token: '{{LINKEDIN_OAUTH_TOKEN}}'\n    resources:\n    - name: compliance-authorizations\n      path: /v2/memberComplianceAuthorizations\n      description: Manage compliance monitoring authorizations\
  \ for members.\n      operations:\n      - name: opt-in-member\n        method: POST\n        description: Opt in a member for compliance monitoring.\n        inputParameters:\n        - name: member\n          in: body\n          type: string\n          required: true\n          description: URN of the member to regulate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            member: '{{tools.member}}'\n      - name: check-member-status\n        method: GET\n        description: Check if a member is currently opted in for compliance monitoring.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Query type for member lookup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: compliance-authorization-by-key\n\
  \      path: /v2/memberComplianceAuthorizations/developerApplication=urn:li:developerApplication:{DeveloperApplicationId}&member=urn:li:person:{PersonId}\n      description: Manage compliance authorization by composite key.\n      operations:\n      - name: opt-out-member\n        method: DELETE\n        description: Opt out a member from compliance monitoring.\n        inputParameters:\n        - name: DeveloperApplicationId\n          in: path\n          type: string\n          required: true\n          description: Developer application ID\n        - name: PersonId\n          in: path\n          type: string\n          required: true\n          description: Person ID of the member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: compliance-events\n      path: /v2/complianceEvents\n      description: Retrieve compliance events for regulated members.\n      operations:\n      - name: get-compliance-events\n\
  \        method: GET\n        description: Retrieve compliance events for a regulated member.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Query type\n        - name: projection\n          in: query\n          type: string\n          required: false\n          description: Fields to include in the response\n        - name: startTime\n          in: query\n          type: integer\n          required: false\n          description: Start time in milliseconds since epoch\n        - name: count\n          in: query\n          type: integer\n          required: false\n          description: Number of events to retrieve\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: data-portability\n    baseUri: https://api.linkedin.com\n    description: LinkedIn Pages Data Portability API.\n    authentication:\n\
  \      type: bearer\n      token: '{{LINKEDIN_OAUTH_TOKEN}}'\n    resources:\n    - name: dma-organizations\n      path: /rest/dmaOrganizations\n      description: DMA organization data.\n      operations:\n      - name: batch-get-organizations\n        method: GET\n        description: Batch get organizations for data portability.\n        inputParameters:\n        - name: ids\n          in: query\n          type: string\n          required: true\n          description: Organization IDs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dma-organization-by-id\n      path: /rest/dmaOrganizations/{organizationId}\n      description: Individual organization data.\n      operations:\n      - name: get-organization\n        method: GET\n        description: Get organization by ID.\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required:\
  \ true\n          description: Organization ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dma-organization-acls\n      path: /rest/dmaOrganizationAcls\n      description: Organization access controls.\n      operations:\n      - name: get-organization-acls\n        method: GET\n        description: Get organization ACLs.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Query type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dma-page-analytics\n      path: /rest/dmaOrganizationalPageContentAnalytics\n      description: Page content analytics.\n      operations:\n      - name: get-page-content-analytics\n        method: GET\n        description: Get page content analytics.\n        inputParameters:\n        -\
  \ name: q\n          in: query\n          type: string\n          required: true\n          description: Query type\n        - name: organizationUrn\n          in: query\n          type: string\n          required: true\n          description: Organization URN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dma-posts\n      path: /rest/dmaPosts\n      description: DMA posts.\n      operations:\n      - name: get-posts\n        method: GET\n        description: Get posts for data portability.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Query type\n        - name: author\n          in: query\n          type: string\n          required: true\n          description: Author URN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \   - name: dma-reactions\n      path: /rest/dmaReactions\n      description: DMA reactions.\n      operations:\n      - name: get-reactions\n        method: GET\n        description: Get reactions for data portability.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Query type\n        - name: activityUrn\n          in: query\n          type: string\n          required: true\n          description: Activity URN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dma-comments\n      path: /rest/dmaComments\n      description: DMA comments.\n      operations:\n      - name: get-comments\n        method: GET\n        description: Get comments for data portability.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Query type\n\
  \        - name: activityUrn\n          in: query\n          type: string\n          required: true\n          description: Activity URN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dma-lead-gen-responses\n      path: /rest/dmaLeadGenResponses\n      description: DMA lead generation responses.\n      operations:\n      - name: get-lead-gen-responses\n        method: GET\n        description: Get lead gen responses for data portability.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Query type\n        - name: owner\n          in: query\n          type: string\n          required: true\n          description: Owner URN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dma-events\n      path: /rest/dmaEvents\n    \
  \  description: DMA events.\n      operations:\n      - name: get-events\n        method: GET\n        description: Get events for data portability.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Query type\n        - name: organizer\n          in: query\n          type: string\n          required: true\n          description: Organizer URN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dma-business-manager\n      path: /rest/dmaBusinessManagerAccountRelationships\n      description: Business manager relationships.\n      operations:\n      - name: get-business-manager-relationships\n        method: GET\n        description: Get business manager account relationships.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description:\
  \ Query type\n        - name: businessManagerAccount\n          in: query\n          type: string\n          required: true\n          description: Business manager account URN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: ads-transparency\n    baseUri: https://api.linkedin.com\n    description: LinkedIn Ads Transparency API.\n    authentication:\n      type: bearer\n      token: '{{LINKEDIN_OAUTH_TOKEN}}'\n    resources:\n    - name: advertiser-transparency\n      path: /rest/advertiserTransparencyData/urn:li:sponsoredAccount:{sponsoredaccount_id}\n      description: Advertiser transparency data.\n      operations:\n      - name: get-advertiser-transparency\n        method: GET\n        description: Get advertiser transparency data for a sponsored account.\n        inputParameters:\n        - name: sponsoredaccount_id\n          in: path\n          type: string\n          required:\
  \ true\n          description: Sponsored account ID\n        - name: month\n          in: query\n          type: integer\n          required: false\n          description: Month in YYYYMM format\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8086\n    namespace: compliance-regulatory-api\n    description: Unified REST API for LinkedIn compliance and regulatory workflows.\n    resources:\n    - path: /v1/compliance-authorizations\n      name: compliance-authorizations\n      operations:\n      - method: POST\n        name: opt-in-member\n        description: Opt in a member for compliance monitoring.\n        call: compliance-events.opt-in-member\n      - method: GET\n        name: check-member-status\n        description: Check member compliance monitoring status.\n        call: compliance-events.check-member-status\n    - path: /v1/compliance-events\n      name: compliance-events\n\
  \      operations:\n      - method: GET\n        name: get-compliance-events\n        description: Retrieve compliance events.\n        call: compliance-events.get-compliance-events\n    - path: /v1/dma-organizations\n      name: dma-organizations\n      operations:\n      - method: GET\n        name: batch-get-organizations\n        description: Batch get organizations for data portability.\n        call: data-portability.batch-get-organizations\n    - path: /v1/dma-organizations/{organizationId}\n      name: dma-organization-by-id\n      operations:\n      - method: GET\n        name: get-organization\n        description: Get organization by ID.\n        call: data-portability.get-organization\n    - path: /v1/dma-posts\n      name: dma-posts\n      operations:\n      - method: GET\n        name: get-dma-posts\n        description: Get posts for data portability.\n        call: data-portability.get-posts\n    - path: /v1/dma-reactions\n      name: dma-reactions\n      operations:\n\
  \      - method: GET\n        name: get-dma-reactions\n        description: Get reactions for data portability.\n        call: data-portability.get-reactions\n    - path: /v1/dma-comments\n      name: dma-comments\n      operations:\n      - method: GET\n        name: get-dma-comments\n        description: Get comments for data portability.\n        call: data-portability.get-comments\n    - path: /v1/dma-events\n      name: dma-events\n      operations:\n      - method: GET\n        name: get-dma-events\n        description: Get events for data portability.\n        call: data-portability.get-events\n    - path: /v1/advertiser-transparency/{sponsoredaccount_id}\n      name: advertiser-transparency\n      operations:\n      - method: GET\n        name: get-advertiser-transparency\n        description: Get advertiser transparency data.\n        call: ads-transparency.get-advertiser-transparency\n  - type: mcp\n    port: 9096\n    namespace: compliance-regulatory-mcp\n    transport: http\n\
  \    description: MCP server for AI-assisted LinkedIn compliance and regulatory workflows.\n    tools:\n    - name: opt-in-member\n      description: Opt in a member for compliance monitoring.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: compliance-events.opt-in-member\n    - name: check-member-status\n      description: Check member compliance monitoring status.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: compliance-events.check-member-status\n    - name: opt-out-member\n      description: Opt out a member from compliance monitoring.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: compliance-events.opt-out-member\n    - name: get-compliance-events\n      description: Retrieve compliance events for a regulated member.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n\
  \      call: compliance-events.get-compliance-events\n    - name: batch-get-organizations\n      description: Batch get organizations for data portability.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: data-portability.batch-get-organizations\n    - name: get-organization\n      description: Get organization by ID for data portability.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: data-portability.get-organization\n    - name: get-organization-acls\n      description: Get organization ACLs for data portability.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: data-portability.get-organization-acls\n    - name: get-page-content-analytics\n      description: Get page content analytics for data portability.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: data-portability.get-page-content-analytics\n\
  \    - name: get-dma-posts\n      description: Get posts for data portability.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: data-portability.get-posts\n    - name: get-dma-reactions\n      description: Get reactions for data portability.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: data-portability.get-reactions\n    - name: get-dma-comments\n      description: Get comments for data portability.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: data-portability.get-comments\n    - name: get-dma-lead-gen-responses\n      description: Get lead gen responses for data portability.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: data-portability.get-lead-gen-responses\n    - name: get-dma-events\n      description: Get events for data portability.\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: data-portability.get-events\n    - name: get-business-manager-relationships\n      description: Get business manager account relationships.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: data-portability.get-business-manager-relationships\n    - name: get-advertiser-transparency\n      description: Get advertiser transparency data for a sponsored account.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: ads-transparency.get-advertiser-transparency\n"
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
