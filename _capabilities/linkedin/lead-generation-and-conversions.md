---
categories: []
consumed_apis: []
description: Unified workflow for demand generation managers to capture leads, sync lead data, track conversions, and measure attribution -- combining lead sync and conversions APIs.
layout: capability
name: LinkedIn Lead Generation And Conversions
operations:
- description: Get lead forms for a sponsored account.
  method: GET
  name: get-lead-forms
  path: /v1/lead-forms
- description: Pull lead form responses.
  method: GET
  name: get-lead-form-responses
  path: /v1/lead-form-responses
- description: Fetch full lead data by ID.
  method: GET
  name: get-lead-by-id
  path: /v1/lead-form-responses/{lead_id}
- description: Subscribe for lead notification webhooks.
  method: POST
  name: subscribe-lead-notifications
  path: /v1/lead-notifications
- description: Fetch existing conversion rules.
  method: GET
  name: get-conversion-rules
  path: /v1/conversions
- description: Create a new conversion rule.
  method: POST
  name: create-conversion-rule
  path: /v1/conversions
- description: Stream conversion events.
  method: POST
  name: stream-conversion-events
  path: /v1/conversion-events
personas: []
provider_name: LinkedIn
provider_slug: linkedin
search_terms:
- get lead forms for a sponsored account.
- tracks employee learning activity and completions.
- social media
- uses sales navigator for lead generation and crm sync.
- create conversion rule
- create a new conversion rule.
- get lead by id
- professional networking
- validate organization role
- get conversion rules
- subscribe lead notifications
- integrates linkedin authentication and sharing into applications.
- linkedin
- employee development tracking and content access.
- business
- validate user's organization role for lead access.
- job posting, recruiting, and applicant tracking.
- data portability and advertiser transparency for dma.
- sales intelligence, lead management, and crm integration.
- message archiving and regulatory communications governance.
- recruiting
- archives communications for regulatory compliance.
- posts jobs and manages candidates through ats integrations.
- get lead forms
- careers
- subscribe for lead notification webhooks.
- stream conversion events
- fetch full lead data by id.
- b2b advertising, audience targeting, and campaign analytics.
- get the user's sponsored accounts.
- marketing
- demand generation
- get lead form responses
- get sponsored accounts
- manages b2b ad campaigns and audience targeting on linkedin.
- pull lead form responses.
- authentication, sharing, and verification for consumer apps.
- lead generation
- stream conversion events.
- conversions
- fetch existing conversion rules.
slug: lead-generation-and-conversions
source_filename: lead-generation-and-conversions.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: LinkedIn Lead Generation And Conversions\n  description: Unified workflow for demand generation managers to capture leads, sync lead data, track conversions, and measure\n    attribution -- combining lead sync and conversions APIs.\n  tags:\n  - LinkedIn\n  - Lead Generation\n  - Conversions\n  - Demand Generation\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    LINKEDIN_OAUTH_TOKEN: LINKEDIN_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: marketing-leads\n    baseUri: https://api.linkedin.com\n    description: LinkedIn Lead Sync API.\n    authentication:\n      type: bearer\n      token: '{{LINKEDIN_OAUTH_TOKEN}}'\n    resources:\n    - name: organization-acls\n      path: /organizationAcls\n      description: Validate user's organization role.\n      operations:\n      - name: validate-organization-role\n        method: GET\n        description: Validate the user's organization\
  \ role for lead access.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Query type\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: State filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lead-forms\n      path: /leadForms\n      description: Lead generation form management.\n      operations:\n      - name: get-lead-forms\n        method: GET\n        description: Get forms for a sponsored account.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Query type\n        - name: owner\n          in: query\n          type: string\n          required: false\n          description: Owner URN\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: lead-form-responses\n      path: /leadFormResponses\n      description: Lead form response management.\n      operations:\n      - name: get-lead-form-responses\n        method: GET\n        description: Schedule periodic form response pulls.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Query type\n        - name: owner\n          in: query\n          type: string\n          required: false\n          description: Owner URN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lead-form-response-by-id\n      path: /leadFormResponses/{lead_id}\n      description: Individual lead form response.\n      operations:\n      - name: get-lead-by-id\n        method: GET\n        description: Fetch full lead data by ID.\n        inputParameters:\n\
  \        - name: lead_id\n          in: path\n          type: string\n          required: true\n          description: Lead ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lead-notifications\n      path: /leadNotifications\n      description: Lead notification webhook management.\n      operations:\n      - name: subscribe-lead-notifications\n        method: POST\n        description: Subscribe for lead notification webhooks.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ad-accounts\n      path: /adAccounts\n      description: Ad account retrieval for lead sync.\n      operations:\n      - name: get-sponsored-accounts\n        method: GET\n        description: Get the user's sponsored accounts.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required:\
  \ false\n          description: Query type\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search criteria\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: marketing-conversions\n    baseUri: https://api.linkedin.com\n    description: LinkedIn Conversions API.\n    authentication:\n      type: bearer\n      token: '{{LINKEDIN_OAUTH_TOKEN}}'\n    resources:\n    - name: ad-account-users\n      path: /adAccountUsers\n      description: Retrieve ad account users.\n      operations:\n      - name: get-ad-account-users\n        method: GET\n        description: Retrieve authenticated user's sponsored ad accounts.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Query type\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: conversions\n      path: /conversions\n      description: Conversion rule management.\n      operations:\n      - name: get-conversion-rules\n        method: GET\n        description: Fetch existing conversion rules for an ad account.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Query type\n        - name: account\n          in: query\n          type: string\n          required: false\n          description: Sponsored account URN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-conversion-rule\n        method: POST\n        description: Create a new conversion rule.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: conversion-events\n\
  \      path: /conversionEvents\n      description: Conversion event streaming.\n      operations:\n      - name: stream-conversion-events\n        method: POST\n        description: Stream multiple conversion events.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: lead-gen-conversions-api\n    description: Unified REST API for LinkedIn lead generation and conversion tracking.\n    resources:\n    - path: /v1/lead-forms\n      name: lead-forms\n      operations:\n      - method: GET\n        name: get-lead-forms\n        description: Get lead forms for a sponsored account.\n        call: marketing-leads.get-lead-forms\n    - path: /v1/lead-form-responses\n      name: lead-form-responses\n      operations:\n      - method: GET\n        name: get-lead-form-responses\n        description: Pull lead form responses.\n        call: marketing-leads.get-lead-form-responses\n\
  \    - path: /v1/lead-form-responses/{lead_id}\n      name: lead-by-id\n      operations:\n      - method: GET\n        name: get-lead-by-id\n        description: Fetch full lead data by ID.\n        call: marketing-leads.get-lead-by-id\n    - path: /v1/lead-notifications\n      name: lead-notifications\n      operations:\n      - method: POST\n        name: subscribe-lead-notifications\n        description: Subscribe for lead notification webhooks.\n        call: marketing-leads.subscribe-lead-notifications\n    - path: /v1/conversions\n      name: conversions\n      operations:\n      - method: GET\n        name: get-conversion-rules\n        description: Fetch existing conversion rules.\n        call: marketing-conversions.get-conversion-rules\n      - method: POST\n        name: create-conversion-rule\n        description: Create a new conversion rule.\n        call: marketing-conversions.create-conversion-rule\n    - path: /v1/conversion-events\n      name: conversion-events\n   \
  \   operations:\n      - method: POST\n        name: stream-conversion-events\n        description: Stream conversion events.\n        call: marketing-conversions.stream-conversion-events\n  - type: mcp\n    port: 9092\n    namespace: lead-gen-conversions-mcp\n    transport: http\n    description: MCP server for AI-assisted LinkedIn lead generation and conversion tracking.\n    tools:\n    - name: validate-organization-role\n      description: Validate user's organization role for lead access.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marketing-leads.validate-organization-role\n    - name: get-sponsored-accounts\n      description: Get the user's sponsored accounts.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marketing-leads.get-sponsored-accounts\n    - name: get-lead-forms\n      description: Get lead forms for a sponsored account.\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: marketing-leads.get-lead-forms\n    - name: get-lead-form-responses\n      description: Pull lead form responses.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marketing-leads.get-lead-form-responses\n    - name: get-lead-by-id\n      description: Fetch full lead data by ID.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marketing-leads.get-lead-by-id\n    - name: subscribe-lead-notifications\n      description: Subscribe for lead notification webhooks.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: marketing-leads.subscribe-lead-notifications\n    - name: get-conversion-rules\n      description: Fetch existing conversion rules.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: marketing-conversions.get-conversion-rules\n\
  \    - name: create-conversion-rule\n      description: Create a new conversion rule.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: marketing-conversions.create-conversion-rule\n    - name: stream-conversion-events\n      description: Stream conversion events.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: marketing-conversions.stream-conversion-events\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/linkedin/refs/heads/main/capabilities/lead-generation-and-conversions.yaml
tags:
- LinkedIn
- Lead Generation
- Conversions
- Demand Generation
tools:
- description: Validate user's organization role for lead access.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: validate-organization-role
- description: Get the user's sponsored accounts.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-sponsored-accounts
- description: Get lead forms for a sponsored account.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-lead-forms
- description: Pull lead form responses.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-lead-form-responses
- description: Fetch full lead data by ID.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-lead-by-id
- description: Subscribe for lead notification webhooks.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: subscribe-lead-notifications
- description: Fetch existing conversion rules.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-conversion-rules
- description: Create a new conversion rule.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-conversion-rule
- description: Stream conversion events.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stream-conversion-events
---
