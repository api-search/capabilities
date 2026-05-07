---
categories: []
consumed_apis: []
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
- list enrollments
- backend developer integrating aflac supplemental insurance enrollment into an hr or benefits administration platform.
- aflac
- submit an aflac supplemental insurance claim for a qualifying event.
- list claims
- get enrollment
- verify employee eligibility.
- create a new enrollment.
- claims
- list aflac supplemental insurance claims.
- submit claim
- claim submission and tracking for qualifying health events.
- submit a claim.
- retrieve a specific aflac enrollment record.
- list benefit enrollments.
- employee enrollment in supplemental insurance products.
- retrieve an enrollment.
- hr platform engineer
- specific enrollment operations.
- create enrollment
- verify eligibility
- enrollment
- benefits
- benefits administrator
- hr or benefits team member managing employee enrollment, claims, and eligibility for supplemental insurance.
- full supplemental insurance benefits lifecycle from enrollment through claims and eligibility verification.
- list claims.
- verify an employee's eligibility for an aflac supplemental insurance product.
- list aflac supplemental insurance benefit enrollments for a group or employee.
- real-time eligibility verification for supplemental insurance products.
- active supplemental insurance policy tracking.
- claims management.
- eligibility verification.
- insurance
- enroll an employee in an aflac supplemental insurance product.
- benefit enrollment management.
slug: benefits-administration
source_filename: benefits-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Aflac Benefits Administration\n  description: Unified workflow capability for Aflac supplemental insurance benefits administration covering enrollment, claims,\n    eligibility, and policy management. Used by HR platform engineers and benefits administrators.\n  tags:\n  - Aflac\n  - Benefits\n  - Insurance\n  - Enrollment\n  - Claims\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AFLAC_CLIENT_ID: AFLAC_CLIENT_ID\n    AFLAC_CLIENT_SECRET: AFLAC_CLIENT_SECRET\n    AFLAC_ACCESS_TOKEN: AFLAC_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: aflac-enterprise-connect\n    baseUri: https://api.enterprise-connect.aflac.com/v1\n    description: Aflac Enterprise Connect API for benefits enrollment and policy management.\n    authentication:\n      type: bearer\n      token: '{{AFLAC_ACCESS_TOKEN}}'\n    resources:\n    - name: enrollments\n      path: /enrollments\n      description:\
  \ Benefits enrollment management.\n      operations:\n      - name: list-enrollments\n        method: GET\n        description: List benefit enrollments.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-enrollment\n        method: POST\n        description: Create a new benefit enrollment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: enrollment-by-id\n      path: /enrollments/{enrollment_id}\n      description: Operations on a specific enrollment.\n      operations:\n      - name: get-enrollment\n        method: GET\n        description: Retrieve an enrollment by ID.\n        inputParameters:\n        - name: enrollment_id\n          in: path\n          type: string\n          required: true\n          description: Enrollment identifier.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: claims\n      path: /claims\n      description: Claims management.\n      operations:\n      - name: list-claims\n        method: GET\n        description: List claims.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: submit-claim\n        method: POST\n        description: Submit a new claim.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: eligibility\n      path: /eligibility/verify\n      description: Eligibility verification.\n      operations:\n      - name: verify-eligibility\n        method: POST\n        description: Verify employee eligibility for a supplemental insurance product.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n\
  \  - type: rest\n    port: 8080\n    namespace: aflac-benefits-api\n    description: Unified REST API for Aflac supplemental insurance benefits administration.\n    resources:\n    - path: /v1/enrollments\n      name: enrollments\n      description: Benefit enrollment management.\n      operations:\n      - method: GET\n        name: list-enrollments\n        description: List benefit enrollments.\n        call: aflac-enterprise-connect.list-enrollments\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-enrollment\n        description: Create a new enrollment.\n        call: aflac-enterprise-connect.create-enrollment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/enrollments/{enrollment_id}\n      name: enrollment-by-id\n      description: Specific enrollment operations.\n      operations:\n      - method: GET\n        name: get-enrollment\n        description: Retrieve an enrollment.\n\
  \        call: aflac-enterprise-connect.get-enrollment\n        with:\n          enrollment_id: rest.enrollment_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/claims\n      name: claims\n      description: Claims management.\n      operations:\n      - method: GET\n        name: list-claims\n        description: List claims.\n        call: aflac-enterprise-connect.list-claims\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: submit-claim\n        description: Submit a claim.\n        call: aflac-enterprise-connect.submit-claim\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/eligibility/verify\n      name: eligibility\n      description: Eligibility verification.\n      operations:\n      - method: POST\n        name: verify-eligibility\n        description: Verify employee eligibility.\n        call: aflac-enterprise-connect.verify-eligibility\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: aflac-benefits-mcp\n    transport: http\n    description: MCP server for AI-assisted Aflac supplemental insurance benefits administration.\n    tools:\n    - name: list-enrollments\n      description: List Aflac supplemental insurance benefit enrollments for a group or employee.\n      hints:\n        readOnly: true\n        destructive: false\n      call: aflac-enterprise-connect.list-enrollments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-enrollment\n      description: Enroll an employee in an Aflac supplemental insurance product.\n      hints:\n        readOnly: false\n        destructive: false\n      call: aflac-enterprise-connect.create-enrollment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-enrollment\n      description: Retrieve a specific Aflac enrollment record.\n      hints:\n\
  \        readOnly: true\n        destructive: false\n      call: aflac-enterprise-connect.get-enrollment\n      with:\n        enrollment_id: tools.enrollment_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-claims\n      description: List Aflac supplemental insurance claims.\n      hints:\n        readOnly: true\n        destructive: false\n      call: aflac-enterprise-connect.list-claims\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-claim\n      description: Submit an Aflac supplemental insurance claim for a qualifying event.\n      hints:\n        readOnly: false\n        destructive: false\n      call: aflac-enterprise-connect.submit-claim\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: verify-eligibility\n      description: Verify an employee's eligibility for an Aflac supplemental insurance product.\n      hints:\n        readOnly: true\n        destructive: false\n\
  \      call: aflac-enterprise-connect.verify-eligibility\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/aflac/refs/heads/main/capabilities/benefits-administration.yaml
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
