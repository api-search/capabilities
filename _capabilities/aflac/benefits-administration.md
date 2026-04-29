---
categories: []
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
- list aflac supplemental insurance claims.
- list aflac supplemental insurance benefit enrollments for a group or employee.
- list claims.
- create enrollment
- enrollment
- verify employee eligibility.
- specific enrollment operations.
- benefits
- active supplemental insurance policy tracking.
- submit a claim.
- benefit enrollment management.
- list claims
- eligibility verification.
- verify eligibility
- hr or benefits team member managing employee enrollment, claims, and eligibility for supplemental insurance.
- employee enrollment in supplemental insurance products.
- submit claim
- submit an aflac supplemental insurance claim for a qualifying event.
- full supplemental insurance benefits lifecycle from enrollment through claims and eligibility verification.
- claims management.
- create a new enrollment.
- enroll an employee in an aflac supplemental insurance product.
- backend developer integrating aflac supplemental insurance enrollment into an hr or benefits administration platform.
- benefits administrator
- claims
- list benefit enrollments.
- aflac
- hr platform engineer
- verify an employee's eligibility for an aflac supplemental insurance product.
- retrieve an enrollment.
- get enrollment
- insurance
- claim submission and tracking for qualifying health events.
- list enrollments
- real-time eligibility verification for supplemental insurance products.
- retrieve a specific aflac enrollment record.
slug: benefits-administration
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Aflac Benefits Administration\"\n  description: \"Unified workflow capability for Aflac supplemental insurance benefits administration covering enrollment, claims, eligibility, and policy management. Used by HR platform engineers and benefits administrators.\"\n  tags:\n    - Aflac\n    - Benefits\n    - Insurance\n    - Enrollment\n    - Claims\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AFLAC_CLIENT_ID: AFLAC_CLIENT_ID\n      AFLAC_CLIENT_SECRET: AFLAC_CLIENT_SECRET\n      AFLAC_ACCESS_TOKEN: AFLAC_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: aflac-enterprise-connect\n      location: ./shared/enterprise-connect.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: aflac-benefits-api\n      description: \"Unified REST API for Aflac supplemental insurance benefits administration.\"\n      resources:\n        - path: /v1/enrollments\n      \
  \    name: enrollments\n          description: \"Benefit enrollment management.\"\n          operations:\n            - method: GET\n              name: list-enrollments\n              description: \"List benefit enrollments.\"\n              call: \"aflac-enterprise-connect.list-enrollments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-enrollment\n              description: \"Create a new enrollment.\"\n              call: \"aflac-enterprise-connect.create-enrollment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/enrollments/{enrollment_id}\n          name: enrollment-by-id\n          description: \"Specific enrollment operations.\"\n          operations:\n            - method: GET\n              name: get-enrollment\n              description: \"Retrieve an enrollment.\"\n              call: \"aflac-enterprise-connect.get-enrollment\"\
  \n              with:\n                enrollment_id: \"rest.enrollment_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/claims\n          name: claims\n          description: \"Claims management.\"\n          operations:\n            - method: GET\n              name: list-claims\n              description: \"List claims.\"\n              call: \"aflac-enterprise-connect.list-claims\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: submit-claim\n              description: \"Submit a claim.\"\n              call: \"aflac-enterprise-connect.submit-claim\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/eligibility/verify\n          name: eligibility\n          description: \"Eligibility verification.\"\n          operations:\n            -\
  \ method: POST\n              name: verify-eligibility\n              description: \"Verify employee eligibility.\"\n              call: \"aflac-enterprise-connect.verify-eligibility\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: aflac-benefits-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Aflac supplemental insurance benefits administration.\"\n      tools:\n        - name: list-enrollments\n          description: \"List Aflac supplemental insurance benefit enrollments for a group or employee.\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"aflac-enterprise-connect.list-enrollments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-enrollment\n          description: \"Enroll an employee in an Aflac supplemental insurance product.\"\n \
  \         hints:\n            readOnly: false\n            destructive: false\n          call: \"aflac-enterprise-connect.create-enrollment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-enrollment\n          description: \"Retrieve a specific Aflac enrollment record.\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"aflac-enterprise-connect.get-enrollment\"\n          with:\n            enrollment_id: \"tools.enrollment_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-claims\n          description: \"List Aflac supplemental insurance claims.\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"aflac-enterprise-connect.list-claims\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-claim\n          description:\
  \ \"Submit an Aflac supplemental insurance claim for a qualifying event.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"aflac-enterprise-connect.submit-claim\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: verify-eligibility\n          description: \"Verify an employee's eligibility for an Aflac supplemental insurance product.\"\n          hints:\n            readOnly: true\n            destructive: false\n          call: \"aflac-enterprise-connect.verify-eligibility\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
