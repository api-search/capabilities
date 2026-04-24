---
consumed_apis:
- aflac-enterprise-connect
description: Unified workflow capability for Aflac supplemental insurance benefits administration covering enrollment, claims, eligibility, and policy management. Used by HR platform engineers and benefits administrators.
layout: capability
name: Aflac Benefits Administration
operations:
- description: List benefit enrollments.
  method: GET
  name: list-enrollments
  path: /v1/enrollments
- description: Create a new enrollment.
  method: POST
  name: create-enrollment
  path: /v1/enrollments
- description: Retrieve an enrollment.
  method: GET
  name: get-enrollment
  path: /v1/enrollments/{enrollment_id}
- description: List claims.
  method: GET
  name: list-claims
  path: /v1/claims
- description: Submit a claim.
  method: POST
  name: submit-claim
  path: /v1/claims
- description: Verify employee eligibility.
  method: POST
  name: verify-eligibility
  path: /v1/eligibility/verify
personas:
- description: Backend developer integrating Aflac supplemental insurance enrollment into an HR or benefits administration platform.
  id: hr-platform-engineer
  name: HR Platform Engineer
- description: HR or benefits team member managing employee enrollment, claims, and eligibility for supplemental insurance.
  id: benefits-administrator
  name: Benefits Administrator
provider_name: aflac
provider_slug: aflac
search_terms:
- eligibility verification.
- full supplemental insurance benefits lifecycle from enrollment through claims and eligibility verification.
- verify employee eligibility.
- claims management.
- insurance
- get enrollment
- real-time eligibility verification for supplemental insurance products.
- benefit enrollment management.
- create enrollment
- employee enrollment in supplemental insurance products.
- claims
- list enrollments
- submit a claim.
- aflac
- active supplemental insurance policy tracking.
- benefits
- verify eligibility
- list aflac supplemental insurance claims.
- list benefit enrollments.
- list claims.
- benefits administrator
- enroll an employee in an aflac supplemental insurance product.
- list aflac supplemental insurance benefit enrollments for a group or employee.
- submit an aflac supplemental insurance claim for a qualifying event.
- list claims
- retrieve a specific aflac enrollment record.
- claim submission and tracking for qualifying health events.
- retrieve an enrollment.
- verify an employee's eligibility for an aflac supplemental insurance product.
- hr platform engineer
- submit claim
- specific enrollment operations.
- create a new enrollment.
- enrollment
- backend developer integrating aflac supplemental insurance enrollment into an hr or benefits administration platform.
- hr or benefits team member managing employee enrollment, claims, and eligibility for supplemental insurance.
slug: benefits-administration
tags:
- Aflac
- Benefits
- Insurance
- Enrollment
- Claims
tools:
- description: List Aflac supplemental insurance benefit enrollments for a group or employee.
  hints:
    destructive: false
    readOnly: true
  name: list-enrollments
- description: Enroll an employee in an Aflac supplemental insurance product.
  hints:
    destructive: false
    readOnly: false
  name: create-enrollment
- description: Retrieve a specific Aflac enrollment record.
  hints:
    destructive: false
    readOnly: true
  name: get-enrollment
- description: List Aflac supplemental insurance claims.
  hints:
    destructive: false
    readOnly: true
  name: list-claims
- description: Submit an Aflac supplemental insurance claim for a qualifying event.
  hints:
    destructive: false
    readOnly: false
  name: submit-claim
- description: Verify an employee's eligibility for an Aflac supplemental insurance product.
  hints:
    destructive: false
    readOnly: true
  name: verify-eligibility
---
