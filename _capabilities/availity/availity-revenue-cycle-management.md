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
- list previous eligibility inquiries for audit and follow-up
- verify member eligibility
- check if authorization is required
- list eligibility inquiries
- patient cost estimation and price transparency
- check auth required
- search claims summary
- verify patient insurance eligibility and benefits before service delivery
- list eligibility history
- get claim detail
- list eligibilities
- manages claim submission, status tracking, and patient billing
- submit prior authorization request
- determine if a payer requires prior authorization before service delivery
- Billing Specialist
- submit prior authorization
- submit a claim status inquiry to check adjudication status
- unified workflow combining eligibility, claims, and authorization for rcm teams
- search claims by service date or member id for revenue tracking
- healthcare
- prior authorization requests
- real-time insurance coverage and benefits verification
- check claim status
- service review and authorization request management
- check prior auth required
- revenue cycle
- claim status inquiries
- eligibility
- list claim status inquiries
- member eligibility verification
- lookup supported payers
- supported health plan payers
- find health plan payers available for transactions
- availity
- claim status tracking and attachment submission
- track authorization status
- integrates availity apis into electronic health record and practice management systems
- oversees end-to-end revenue cycle including authorization, eligibility, and claim adjudication
- claims
- submit claim status inquiry
- get detailed claim information including adjudication and payment amounts
- submit authorization
- list payers
- submit a prior authorization request for a scheduled procedure
- Revenue Cycle Manager
- verify member insurance coverage and benefits
- verify eligibility
- track the status of a submitted prior authorization request
- list supported payers
- list claim statuses
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
