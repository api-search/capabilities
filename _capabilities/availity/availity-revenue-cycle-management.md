---
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
- lookup supported payers
- list previous eligibility inquiries for audit and follow-up
- submit a claim status inquiry to check adjudication status
- verify member eligibility
- claim status tracking and attachment submission
- find health plan payers available for transactions
- oversees end-to-end revenue cycle including authorization, eligibility, and claim adjudication
- Billing Specialist
- search claims by service date or member id for revenue tracking
- real-time insurance coverage and benefits verification
- check if authorization is required
- patient cost estimation and price transparency
- availity
- healthcare
- verify member insurance coverage and benefits
- list supported payers
- submit prior authorization
- get detailed claim information including adjudication and payment amounts
- check claim status
- get claim detail
- submit a prior authorization request for a scheduled procedure
- track the status of a submitted prior authorization request
- list claim statuses
- manages claim submission, status tracking, and patient billing
- list eligibility inquiries
- list claim status inquiries
- submit authorization
- submit claim status inquiry
- track authorization status
- supported health plan payers
- search claims summary
- check auth required
- list payers
- Revenue Cycle Manager
- service review and authorization request management
- verify patient insurance eligibility and benefits before service delivery
- unified workflow combining eligibility, claims, and authorization for rcm teams
- revenue cycle
- list eligibility history
- eligibility
- determine if a payer requires prior authorization before service delivery
- claims
- list eligibilities
- member eligibility verification
- verify eligibility
- claim status inquiries
- check prior auth required
- prior authorization requests
- submit prior authorization request
- integrates availity apis into electronic health record and practice management systems
slug: availity-revenue-cycle-management
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
