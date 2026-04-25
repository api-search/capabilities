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
- oversees end-to-end revenue cycle including authorization, eligibility, and claim adjudication
- search claims by service date or member id for revenue tracking
- patient cost estimation and price transparency
- list claim status inquiries
- track authorization status
- check auth required
- submit authorization
- get detailed claim information including adjudication and payment amounts
- list claim statuses
- check prior auth required
- submit prior authorization request
- find health plan payers available for transactions
- verify member insurance coverage and benefits
- get claim detail
- search claims summary
- list previous eligibility inquiries for audit and follow-up
- list supported payers
- list eligibility history
- submit prior authorization
- list eligibilities
- claim status inquiries
- real-time insurance coverage and benefits verification
- service review and authorization request management
- verify patient insurance eligibility and benefits before service delivery
- revenue cycle
- list payers
- eligibility
- verify member eligibility
- submit a prior authorization request for a scheduled procedure
- member eligibility verification
- unified workflow combining eligibility, claims, and authorization for rcm teams
- manages claim submission, status tracking, and patient billing
- availity
- Billing Specialist
- check claim status
- track the status of a submitted prior authorization request
- submit claim status inquiry
- submit a claim status inquiry to check adjudication status
- list eligibility inquiries
- prior authorization requests
- integrates availity apis into electronic health record and practice management systems
- verify eligibility
- check if authorization is required
- lookup supported payers
- supported health plan payers
- determine if a payer requires prior authorization before service delivery
- claims
- claim status tracking and attachment submission
- healthcare
- Revenue Cycle Manager
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
