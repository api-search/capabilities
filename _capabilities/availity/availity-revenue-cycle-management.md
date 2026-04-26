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
- integrates availity apis into electronic health record and practice management systems
- service review and authorization request management
- get detailed claim information including adjudication and payment amounts
- availity
- verify member eligibility
- list eligibility history
- track the status of a submitted prior authorization request
- healthcare
- submit authorization
- submit a prior authorization request for a scheduled procedure
- submit prior authorization
- check if authorization is required
- check prior auth required
- manages claim submission, status tracking, and patient billing
- Revenue Cycle Manager
- member eligibility verification
- list eligibilities
- list supported payers
- submit claim status inquiry
- list claim statuses
- Billing Specialist
- patient cost estimation and price transparency
- real-time insurance coverage and benefits verification
- search claims summary
- verify member insurance coverage and benefits
- lookup supported payers
- unified workflow combining eligibility, claims, and authorization for rcm teams
- eligibility
- determine if a payer requires prior authorization before service delivery
- claim status tracking and attachment submission
- track authorization status
- get claim detail
- supported health plan payers
- revenue cycle
- list payers
- claim status inquiries
- list claim status inquiries
- oversees end-to-end revenue cycle including authorization, eligibility, and claim adjudication
- check claim status
- verify patient insurance eligibility and benefits before service delivery
- search claims by service date or member id for revenue tracking
- verify eligibility
- submit a claim status inquiry to check adjudication status
- find health plan payers available for transactions
- prior authorization requests
- claims
- list previous eligibility inquiries for audit and follow-up
- submit prior authorization request
- check auth required
- list eligibility inquiries
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
