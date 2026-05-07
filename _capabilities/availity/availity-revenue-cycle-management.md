---
categories: []
consumed_apis: []
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
- claim status tracking and attachment submission
- lookup supported payers
- list payers
- check if authorization is required
- oversees end-to-end revenue cycle including authorization, eligibility, and claim adjudication
- claims
- supported health plan payers
- revenue cycle
- get claim detail
- determine if a payer requires prior authorization before service delivery
- verify patient insurance eligibility and benefits before service delivery
- unified workflow combining eligibility, claims, and authorization for rcm teams
- prior authorization requests
- availity
- submit claim status inquiry
- search claims summary
- get detailed claim information including adjudication and payment amounts
- check prior auth required
- submit prior authorization request
- verify member insurance coverage and benefits
- healthcare
- track the status of a submitted prior authorization request
- check claim status
- member eligibility verification
- eligibility
- track authorization status
- check auth required
- list previous eligibility inquiries for audit and follow-up
- manages claim submission, status tracking, and patient billing
- list eligibilities
- list claim statuses
- list claim status inquiries
- service review and authorization request management
- verify eligibility
- list eligibility inquiries
- verify member eligibility
- search claims by service date or member id for revenue tracking
- claim status inquiries
- submit authorization
- integrates availity apis into electronic health record and practice management systems
- Billing Specialist
- real-time insurance coverage and benefits verification
- list supported payers
- Revenue Cycle Manager
- submit prior authorization
- list eligibility history
- patient cost estimation and price transparency
- submit a prior authorization request for a scheduled procedure
- find health plan payers available for transactions
- submit a claim status inquiry to check adjudication status
slug: availity-revenue-cycle-management
source_filename: availity-revenue-cycle-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Availity Healthcare Revenue Cycle Management\n  description: Unified workflow for revenue cycle management combining eligibility verification, claim status tracking, and\n    prior authorization. Used by billing departments and revenue cycle teams to streamline patient encounter workflows.\n  tags:\n  - Availity\n  - Revenue Cycle\n  - Healthcare\n  - Claims\n  - Eligibility\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AVAILITY_CLIENT_ID: AVAILITY_CLIENT_ID\n    AVAILITY_CLIENT_SECRET: AVAILITY_CLIENT_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: availity-eligibility\n    baseUri: https://api.availity.com\n    description: Availity Eligibility & Benefits API\n    authentication:\n      type: bearer\n      token: '{{AVAILITY_TOKEN}}'\n    resources:\n    - name: eligibilities\n      path: /availity/intelligent-payer-network/v1/eligibilities\n      description: Member eligibility\
  \ inquiries\n      operations:\n      - name: check-eligibility\n        method: POST\n        description: Submit real-time eligibility and benefits inquiry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-eligibilities\n        method: GET\n        description: List previous eligibility inquiries\n        inputParameters:\n        - name: fromDate\n          in: query\n          type: string\n          required: false\n          description: Start date filter\n        - name: toDate\n          in: query\n          type: string\n          required: false\n          description: End date filter\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-eligibility\n        method: GET\n        description: Get specific eligibility inquiry by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Eligibility transaction ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payers\n      path: /availity/intelligent-payer-network/v1/payers\n      description: Supported health plan payers\n      operations:\n      - name: list-payers\n        method: GET\n        description: List supported payers\n        inputParameters:\n        - name: supportedTransaction\n          in: query\n          type: string\n          required: false\n          description: Filter by transaction type\n        outputRawFormat: json\n        outputParameters:\n    \
  \    - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: availity-claims\n    baseUri: https://api.availity.com\n    description: Availity Claim Status API\n    authentication:\n      type: bearer\n      token: '{{AVAILITY_TOKEN}}'\n    resources:\n    - name: claim-statuses\n      path: /availity/intelligent-payer-network/v1/claim-statuses\n      description: Claim status inquiries\n      operations:\n      - name: create-claim-status-inquiry\n        method: POST\n        description: Submit a claim status inquiry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-claim-status-inquiries\n        method: GET\n        description: List previous claim status inquiries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: enhanced-claim-status\n      path: /clmsmgmt/claim-status/claim-status/v1/status\n\
  \      description: Enhanced claim status with summary and detail search\n      operations:\n      - name: summary-search-claims\n        method: POST\n        description: High-level claim search by service date or member ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: detail-search-claim\n        method: POST\n        description: Detailed claim lookup by claim number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: availity-auth\n    baseUri: https://api.availity.com\n    description: Availity Service Reviews and Prior Authorization API\n    authentication:\n      type: bearer\n      token: '{{AVAILITY_TOKEN}}'\n    resources:\n    - name: service-reviews\n      path: /availity/intelligent-payer-network/v1/service-reviews\n      description: Prior authorization and service review\
  \ requests\n      operations:\n      - name: create-service-review\n        method: POST\n        description: Submit a prior authorization request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-service-reviews\n        method: GET\n        description: List previous service review submissions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-service-review\n        method: GET\n        description: Get specific service review by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Service review ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: is-auth-required\n      path: /value-adds/v1/isauthrequired\n      description:\
  \ Check if authorization is required before submission\n      operations:\n      - name: check-is-auth-required\n        method: POST\n        description: Query if payer requires prior authorization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: availity-rcm-api\n    description: Unified REST API for healthcare revenue cycle management.\n    resources:\n    - path: /v1/eligibilities\n      name: eligibilities\n      description: Member eligibility verification\n      operations:\n      - method: POST\n        name: verify-eligibility\n        description: Verify member insurance coverage and benefits\n        call: availity-eligibility.check-eligibility\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-eligibilities\n        description: List eligibility inquiries\n        call: availity-eligibility.list-eligibilities\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payers\n      name: payers\n      description: Supported health plan payers\n      operations:\n      - method: GET\n        name: list-payers\n        description: List supported payers\n        call: availity-eligibility.list-payers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/claim-statuses\n      name: claim-statuses\n      description: Claim status inquiries\n      operations:\n      - method: POST\n        name: check-claim-status\n        description: Submit claim status inquiry\n        call: availity-claims.create-claim-status-inquiry\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-claim-statuses\n        description: List claim status inquiries\n        call: availity-claims.list-claim-status-inquiries\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/prior-authorizations\n      name: prior-authorizations\n      description: Prior authorization requests\n      operations:\n      - method: POST\n        name: check-auth-required\n        description: Check if authorization is required\n        call: availity-auth.check-is-auth-required\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: submit-authorization\n        description: Submit prior authorization request\n        call: availity-auth.create-service-review\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: availity-rcm-mcp\n    transport: http\n    description: MCP server for AI-assisted healthcare revenue cycle management.\n    tools:\n    - name: verify-member-eligibility\n      description: Verify patient insurance eligibility and benefits before service delivery\n      hints:\n        readOnly: false\n        openWorld: true\n  \
  \    call: availity-eligibility.check-eligibility\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-eligibility-history\n      description: List previous eligibility inquiries for audit and follow-up\n      hints:\n        readOnly: true\n        openWorld: true\n      call: availity-eligibility.list-eligibilities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookup-supported-payers\n      description: Find health plan payers available for transactions\n      hints:\n        readOnly: true\n        openWorld: true\n      call: availity-eligibility.list-payers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-claim-status-inquiry\n      description: Submit a claim status inquiry to check adjudication status\n      hints:\n        readOnly: false\n        openWorld: true\n      call: availity-claims.create-claim-status-inquiry\n      outputParameters:\n      - type: object\n     \
  \   mapping: $.\n    - name: search-claims-summary\n      description: Search claims by service date or member ID for revenue tracking\n      hints:\n        readOnly: true\n        openWorld: true\n      call: availity-claims.summary-search-claims\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-claim-detail\n      description: Get detailed claim information including adjudication and payment amounts\n      hints:\n        readOnly: true\n        openWorld: true\n      call: availity-claims.detail-search-claim\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-prior-auth-required\n      description: Determine if a payer requires prior authorization before service delivery\n      hints:\n        readOnly: true\n        openWorld: true\n      call: availity-auth.check-is-auth-required\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-prior-authorization\n      description: Submit\
  \ a prior authorization request for a scheduled procedure\n      hints:\n        readOnly: false\n        openWorld: true\n      call: availity-auth.create-service-review\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: track-authorization-status\n      description: Track the status of a submitted prior authorization request\n      hints:\n        readOnly: true\n        openWorld: true\n      call: availity-auth.get-service-review\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
