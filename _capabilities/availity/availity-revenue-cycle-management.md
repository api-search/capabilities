---
categories: []
consumed_apis:
- availity-eligibility
- availity-claims
- availity-auth
description: Unified workflow for revenue cycle management combining eligibility verification, claim status tracking, and prior authorization. Used by billing departments and revenue cycle teams to streamline patient encounter workflows.
layout: capability
name: Availity Healthcare Revenue Cycle Management
operations:
- description: Verify member insurance coverage and benefits
  method: POST
  name: verify-eligibility
  path: /v1/eligibilities
- description: List eligibility inquiries
  method: GET
  name: list-eligibilities
  path: /v1/eligibilities
- description: List supported payers
  method: GET
  name: list-payers
  path: /v1/payers
- description: Submit claim status inquiry
  method: POST
  name: check-claim-status
  path: /v1/claim-statuses
- description: List claim status inquiries
  method: GET
  name: list-claim-statuses
  path: /v1/claim-statuses
- description: Check if authorization is required
  method: POST
  name: check-auth-required
  path: /v1/prior-authorizations
- description: Submit prior authorization request
  method: POST
  name: submit-authorization
  path: /v1/prior-authorizations
personas: []
provider_name: availity
provider_slug: availity
search_terms:
- Revenue Cycle Manager
- search claims by service date or member id for revenue tracking
- track the status of a submitted prior authorization request
- claim status tracking and attachment submission
- supported health plan payers
- search claims summary
- revenue cycle
- list claim statuses
- Billing Specialist
- list payers
- healthcare
- submit claim status inquiry
- verify patient insurance eligibility and benefits before service delivery
- patient cost estimation and price transparency
- eligibility
- submit authorization
- list eligibility inquiries
- manages claim submission, status tracking, and patient billing
- real-time insurance coverage and benefits verification
- check if authorization is required
- verify eligibility
- prior authorization requests
- list eligibility history
- submit prior authorization request
- determine if a payer requires prior authorization before service delivery
- submit prior authorization
- check claim status
- track authorization status
- submit a claim status inquiry to check adjudication status
- list claim status inquiries
- oversees end-to-end revenue cycle including authorization, eligibility, and claim adjudication
- lookup supported payers
- submit a prior authorization request for a scheduled procedure
- list supported payers
- member eligibility verification
- service review and authorization request management
- verify member insurance coverage and benefits
- list previous eligibility inquiries for audit and follow-up
- find health plan payers available for transactions
- unified workflow combining eligibility, claims, and authorization for rcm teams
- integrates availity apis into electronic health record and practice management systems
- check prior auth required
- get detailed claim information including adjudication and payment amounts
- claims
- get claim detail
- list eligibilities
- claim status inquiries
- verify member eligibility
- availity
- check auth required
slug: availity-revenue-cycle-management
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Availity Healthcare Revenue Cycle Management\n  description: Unified workflow for revenue cycle management combining eligibility verification, claim status tracking, and prior authorization. Used by billing departments and revenue cycle teams to \n    streamline patient encounter workflows.\n  tags:\n  - Availity\n  - Revenue Cycle\n  - Healthcare\n  - Claims\n  - Eligibility\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AVAILITY_CLIENT_ID: AVAILITY_CLIENT_ID\n    AVAILITY_CLIENT_SECRET: AVAILITY_CLIENT_SECRET\ncapability:\n  consumes:\n  - import: availity-eligibility\n    location: ./shared/eligibility.yaml\n  - import: availity-claims\n    location: ./shared/claim-status.yaml\n  - import: availity-auth\n    location: ./shared/service-reviews.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: availity-rcm-api\n    description: Unified REST API for healthcare revenue cycle management.\n\
  \    resources:\n    - path: /v1/eligibilities\n      name: eligibilities\n      description: Member eligibility verification\n      operations:\n      - method: POST\n        name: verify-eligibility\n        description: Verify member insurance coverage and benefits\n        call: availity-eligibility.check-eligibility\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-eligibilities\n        description: List eligibility inquiries\n        call: availity-eligibility.list-eligibilities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payers\n      name: payers\n      description: Supported health plan payers\n      operations:\n      - method: GET\n        name: list-payers\n        description: List supported payers\n        call: availity-eligibility.list-payers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/claim-statuses\n      name:\
  \ claim-statuses\n      description: Claim status inquiries\n      operations:\n      - method: POST\n        name: check-claim-status\n        description: Submit claim status inquiry\n        call: availity-claims.create-claim-status-inquiry\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-claim-statuses\n        description: List claim status inquiries\n        call: availity-claims.list-claim-status-inquiries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/prior-authorizations\n      name: prior-authorizations\n      description: Prior authorization requests\n      operations:\n      - method: POST\n        name: check-auth-required\n        description: Check if authorization is required\n        call: availity-auth.check-is-auth-required\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: submit-authorization\n   \
  \     description: Submit prior authorization request\n        call: availity-auth.create-service-review\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: availity-rcm-mcp\n    transport: http\n    description: MCP server for AI-assisted healthcare revenue cycle management.\n    tools:\n    - name: verify-member-eligibility\n      description: Verify patient insurance eligibility and benefits before service delivery\n      hints:\n        readOnly: false\n        openWorld: true\n      call: availity-eligibility.check-eligibility\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-eligibility-history\n      description: List previous eligibility inquiries for audit and follow-up\n      hints:\n        readOnly: true\n        openWorld: true\n      call: availity-eligibility.list-eligibilities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-supported-payers\n\
  \      description: Find health plan payers available for transactions\n      hints:\n        readOnly: true\n        openWorld: true\n      call: availity-eligibility.list-payers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-claim-status-inquiry\n      description: Submit a claim status inquiry to check adjudication status\n      hints:\n        readOnly: false\n        openWorld: true\n      call: availity-claims.create-claim-status-inquiry\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-claims-summary\n      description: Search claims by service date or member ID for revenue tracking\n      hints:\n        readOnly: true\n        openWorld: true\n      call: availity-claims.summary-search-claims\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-claim-detail\n      description: Get detailed claim information including adjudication and payment amounts\n      hints:\n  \
  \      readOnly: true\n        openWorld: true\n      call: availity-claims.detail-search-claim\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-prior-auth-required\n      description: Determine if a payer requires prior authorization before service delivery\n      hints:\n        readOnly: true\n        openWorld: true\n      call: availity-auth.check-is-auth-required\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-prior-authorization\n      description: Submit a prior authorization request for a scheduled procedure\n      hints:\n        readOnly: false\n        openWorld: true\n      call: availity-auth.create-service-review\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: track-authorization-status\n      description: Track the status of a submitted prior authorization request\n      hints:\n        readOnly: true\n        openWorld: true\n      call: availity-auth.get-service-review\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/availity/refs/heads/main/capabilities/availity-revenue-cycle-management.yaml
tags:
- Availity
- Revenue Cycle
- Healthcare
- Claims
- Eligibility
tools:
- description: Verify patient insurance eligibility and benefits before service delivery
  hints:
    openWorld: true
    readOnly: false
  name: verify-member-eligibility
- description: List previous eligibility inquiries for audit and follow-up
  hints:
    openWorld: true
    readOnly: true
  name: list-eligibility-history
- description: Find health plan payers available for transactions
  hints:
    openWorld: true
    readOnly: true
  name: lookup-supported-payers
- description: Submit a claim status inquiry to check adjudication status
  hints:
    openWorld: true
    readOnly: false
  name: submit-claim-status-inquiry
- description: Search claims by service date or member ID for revenue tracking
  hints:
    openWorld: true
    readOnly: true
  name: search-claims-summary
- description: Get detailed claim information including adjudication and payment amounts
  hints:
    openWorld: true
    readOnly: true
  name: get-claim-detail
- description: Determine if a payer requires prior authorization before service delivery
  hints:
    openWorld: true
    readOnly: true
  name: check-prior-auth-required
- description: Submit a prior authorization request for a scheduled procedure
  hints:
    openWorld: true
    readOnly: false
  name: submit-prior-authorization
- description: Track the status of a submitted prior authorization request
  hints:
    openWorld: true
    readOnly: true
  name: track-authorization-status
---
