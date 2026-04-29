---
categories: []
consumed_apis:
- marketing-leads
- marketing-conversions
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
- archives communications for regulatory compliance.
- validate organization role
- lead generation
- get lead form responses
- stream conversion events.
- social media
- create conversion rule
- manages b2b ad campaigns and audience targeting on linkedin.
- stream conversion events
- get lead forms for a sponsored account.
- get lead by id
- subscribe lead notifications
- marketing
- professional networking
- get lead forms
- b2b advertising, audience targeting, and campaign analytics.
- job posting, recruiting, and applicant tracking.
- subscribe for lead notification webhooks.
- get sponsored accounts
- get conversion rules
- demand generation
- recruiting
- employee development tracking and content access.
- business
- posts jobs and manages candidates through ats integrations.
- uses sales navigator for lead generation and crm sync.
- linkedin
- get the user's sponsored accounts.
- conversions
- sales intelligence, lead management, and crm integration.
- fetch full lead data by id.
- data portability and advertiser transparency for dma.
- pull lead form responses.
- careers
- create a new conversion rule.
- fetch existing conversion rules.
- validate user's organization role for lead access.
- tracks employee learning activity and completions.
- authentication, sharing, and verification for consumer apps.
- integrates linkedin authentication and sharing into applications.
- message archiving and regulatory communications governance.
slug: lead-generation-and-conversions
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"LinkedIn Lead Generation And Conversions\"\n  description: \"Unified workflow for demand generation managers to capture leads, sync lead data, track conversions, and measure attribution -- combining lead sync and conversions APIs.\"\n  tags:\n    - LinkedIn\n    - Lead Generation\n    - Conversions\n    - Demand Generation\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      LINKEDIN_OAUTH_TOKEN: LINKEDIN_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: marketing-leads\n      location: ./shared/marketing-leads.yaml\n    - import: marketing-conversions\n      location: ./shared/marketing-conversions.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: lead-gen-conversions-api\n      description: \"Unified REST API for LinkedIn lead generation and conversion tracking.\"\n      resources:\n        - path: /v1/lead-forms\n          name: lead-forms\n      \
  \    operations:\n            - method: GET\n              name: get-lead-forms\n              description: \"Get lead forms for a sponsored account.\"\n              call: \"marketing-leads.get-lead-forms\"\n        - path: /v1/lead-form-responses\n          name: lead-form-responses\n          operations:\n            - method: GET\n              name: get-lead-form-responses\n              description: \"Pull lead form responses.\"\n              call: \"marketing-leads.get-lead-form-responses\"\n        - path: /v1/lead-form-responses/{lead_id}\n          name: lead-by-id\n          operations:\n            - method: GET\n              name: get-lead-by-id\n              description: \"Fetch full lead data by ID.\"\n              call: \"marketing-leads.get-lead-by-id\"\n        - path: /v1/lead-notifications\n          name: lead-notifications\n          operations:\n            - method: POST\n              name: subscribe-lead-notifications\n              description: \"Subscribe\
  \ for lead notification webhooks.\"\n              call: \"marketing-leads.subscribe-lead-notifications\"\n        - path: /v1/conversions\n          name: conversions\n          operations:\n            - method: GET\n              name: get-conversion-rules\n              description: \"Fetch existing conversion rules.\"\n              call: \"marketing-conversions.get-conversion-rules\"\n            - method: POST\n              name: create-conversion-rule\n              description: \"Create a new conversion rule.\"\n              call: \"marketing-conversions.create-conversion-rule\"\n        - path: /v1/conversion-events\n          name: conversion-events\n          operations:\n            - method: POST\n              name: stream-conversion-events\n              description: \"Stream conversion events.\"\n              call: \"marketing-conversions.stream-conversion-events\"\n\n    - type: mcp\n      port: 9092\n      namespace: lead-gen-conversions-mcp\n      transport: http\n\
  \      description: \"MCP server for AI-assisted LinkedIn lead generation and conversion tracking.\"\n      tools:\n        - name: validate-organization-role\n          description: \"Validate user's organization role for lead access.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-leads.validate-organization-role\"\n        - name: get-sponsored-accounts\n          description: \"Get the user's sponsored accounts.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-leads.get-sponsored-accounts\"\n        - name: get-lead-forms\n          description: \"Get lead forms for a sponsored account.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-leads.get-lead-forms\"\n        - name: get-lead-form-responses\n          description: \"Pull lead form responses.\"\n          hints: { readOnly: true, destructive: false, idempotent:\
  \ true }\n          call: \"marketing-leads.get-lead-form-responses\"\n        - name: get-lead-by-id\n          description: \"Fetch full lead data by ID.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-leads.get-lead-by-id\"\n        - name: subscribe-lead-notifications\n          description: \"Subscribe for lead notification webhooks.\"\n          hints: { readOnly: false, destructive: false, idempotent: false }\n          call: \"marketing-leads.subscribe-lead-notifications\"\n        - name: get-conversion-rules\n          description: \"Fetch existing conversion rules.\"\n          hints: { readOnly: true, destructive: false, idempotent: true }\n          call: \"marketing-conversions.get-conversion-rules\"\n        - name: create-conversion-rule\n          description: \"Create a new conversion rule.\"\n          hints: { readOnly: false, destructive: false, idempotent: false }\n          call: \"marketing-conversions.create-conversion-rule\"\
  \n        - name: stream-conversion-events\n          description: \"Stream conversion events.\"\n          hints: { readOnly: false, destructive: false, idempotent: false }\n          call: \"marketing-conversions.stream-conversion-events\"\n"
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
