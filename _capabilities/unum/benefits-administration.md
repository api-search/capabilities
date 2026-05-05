---
categories: []
consumed_apis:
- unum-hr-connect
description: Workflow capability for Unum benefits administration, combining eligibility management, enrollment processing, EOI handling, leave management, and billing operations. Designed for HR administrators, benefits coordinators, and HR technology integration partners who manage employee benefits lifecycle from onboarding through termination.
layout: capability
name: Unum Benefits Administration
operations:
- description: List eligible members for an employer group
  method: GET
  name: list-members
  path: /v1/members
- description: Submit member eligibility information
  method: POST
  name: create-member
  path: /v1/members
- description: Get eligibility details for a member
  method: GET
  name: get-member
  path: /v1/members/{memberId}
- description: Update eligibility for a member
  method: PUT
  name: update-member
  path: /v1/members/{memberId}
- description: Terminate member eligibility
  method: DELETE
  name: terminate-member
  path: /v1/members/{memberId}
- description: List enrollment elections for a group
  method: GET
  name: list-enrollments
  path: /v1/enrollments
- description: Submit a new enrollment election
  method: POST
  name: create-enrollment
  path: /v1/enrollments
- description: List leave requests for a group
  method: GET
  name: list-leave-requests
  path: /v1/leave-requests
- description: Submit a new leave request
  method: POST
  name: create-leave-request
  path: /v1/leave-requests
- description: Get leave request details
  method: GET
  name: get-leave-request
  path: /v1/leave-requests/{requestId}
- description: List EOI submissions for a group
  method: GET
  name: list-eoi-submissions
  path: /v1/eoi-submissions
- description: Submit a new EOI application
  method: POST
  name: create-eoi-submission
  path: /v1/eoi-submissions
- description: Get EOI submission status and details
  method: GET
  name: get-eoi-submission
  path: /v1/eoi-submissions/{submissionId}
- description: List billing invoices for an employer group
  method: GET
  name: list-billing-invoices
  path: /v1/billing-invoices
- description: Get billing invoice details
  method: GET
  name: get-billing-invoice
  path: /v1/billing-invoices/{invoiceId}
personas: []
provider_name: Unum
provider_slug: unum
search_terms:
- update member
- get leave request
- list eoi submissions for a group
- individual member operations
- update eligibility for a member
- individual billing invoice
- list leave requests for a group
- submit a new leave or absence request for a member
- list eligible members for an employer group
- submit new member eligibility to unum
- get details and status of a leave request
- get billing invoice
- list members
- get eoi submission
- unum
- individual leave request operations
- submit a new eoi application
- leave management
- list enrollments
- life insurance
- list benefit enrollment elections for a group
- create leave request
- get premium billing invoice details
- list evidence of insurability submissions for a group
- insurance
- create member
- hr integration
- get leave request details
- leave and absence requests
- list enrollment elections for a group
- terminate member
- list premium billing invoices for an employer group
- disability insurance
- create enrollment
- submit a new evidence of insurability application
- create eoi submission
- submit a new benefit enrollment election for a member
- get eoi submission status and details
- individual eoi submission
- list billing invoices for an employer group
- premium billing invoices
- submit member eligibility information
- list eoi submissions
- get billing invoice details
- member eligibility management
- terminate eligibility for a member
- benefit enrollment elections
- eligibility
- benefits administration
- list leave requests
- get eligibility details for a member
- update existing member eligibility information
- terminate member eligibility
- get eligibility details for a specific member
- evidence of insurability submissions
- get status and decision for an eoi submission
- list leave and absence requests for a group
- list billing invoices
- get member
- submit a new leave request
- submit a new enrollment election
slug: benefits-administration
source_filename: benefits-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Unum Benefits Administration\"\n  description: >-\n    Workflow capability for Unum benefits administration, combining eligibility\n    management, enrollment processing, EOI handling, leave management, and\n    billing operations. Designed for HR administrators, benefits coordinators,\n    and HR technology integration partners who manage employee benefits\n    lifecycle from onboarding through termination.\n  tags:\n    - Unum\n    - Benefits Administration\n    - HR Integration\n    - Insurance\n    - Leave Management\n    - Eligibility\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UNUM_CLIENT_ID: UNUM_CLIENT_ID\n      UNUM_CLIENT_SECRET: UNUM_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: unum-hr-connect\n      location: ./shared/hr-connect.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: unum-benefits-api\n      description: \"Unified\
  \ REST API for Unum benefits administration workflows.\"\n      resources:\n        - path: /v1/members\n          name: members\n          description: \"Member eligibility management\"\n          operations:\n            - method: GET\n              name: list-members\n              description: \"List eligible members for an employer group\"\n              call: \"unum-hr-connect.list-eligible-members\"\n              with:\n                groupId: \"rest.groupId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-member\n              description: \"Submit member eligibility information\"\n              call: \"unum-hr-connect.submit-member-eligibility\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/members/{memberId}\n          name: member\n          description: \"Individual member operations\"\n \
  \         operations:\n            - method: GET\n              name: get-member\n              description: \"Get eligibility details for a member\"\n              call: \"unum-hr-connect.get-member-eligibility\"\n              with:\n                memberId: \"rest.memberId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-member\n              description: \"Update eligibility for a member\"\n              call: \"unum-hr-connect.update-member-eligibility\"\n              with:\n                memberId: \"rest.memberId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: terminate-member\n              description: \"Terminate member eligibility\"\n              call: \"unum-hr-connect.terminate-member-eligibility\"\n              with:\n                memberId: \"rest.memberId\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/enrollments\n          name: enrollments\n          description: \"Benefit enrollment elections\"\n          operations:\n            - method: GET\n              name: list-enrollments\n              description: \"List enrollment elections for a group\"\n              call: \"unum-hr-connect.list-enrollment-elections\"\n              with:\n                groupId: \"rest.groupId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-enrollment\n              description: \"Submit a new enrollment election\"\n              call: \"unum-hr-connect.submit-enrollment-election\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/leave-requests\n          name: leave-requests\n          description:\
  \ \"Leave and absence requests\"\n          operations:\n            - method: GET\n              name: list-leave-requests\n              description: \"List leave requests for a group\"\n              call: \"unum-hr-connect.list-leave-requests\"\n              with:\n                groupId: \"rest.groupId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-leave-request\n              description: \"Submit a new leave request\"\n              call: \"unum-hr-connect.submit-leave-request\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/leave-requests/{requestId}\n          name: leave-request\n          description: \"Individual leave request operations\"\n          operations:\n            - method: GET\n              name: get-leave-request\n              description: \"Get leave request details\"\n  \
  \            call: \"unum-hr-connect.get-leave-request\"\n              with:\n                requestId: \"rest.requestId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/eoi-submissions\n          name: eoi-submissions\n          description: \"Evidence of insurability submissions\"\n          operations:\n            - method: GET\n              name: list-eoi-submissions\n              description: \"List EOI submissions for a group\"\n              call: \"unum-hr-connect.list-eoi-submissions\"\n              with:\n                groupId: \"rest.groupId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-eoi-submission\n              description: \"Submit a new EOI application\"\n              call: \"unum-hr-connect.submit-eoi\"\n              outputParameters:\n                - type: object\n    \
  \              mapping: \"$.\"\n\n        - path: /v1/eoi-submissions/{submissionId}\n          name: eoi-submission\n          description: \"Individual EOI submission\"\n          operations:\n            - method: GET\n              name: get-eoi-submission\n              description: \"Get EOI submission status and details\"\n              call: \"unum-hr-connect.get-eoi-submission\"\n              with:\n                submissionId: \"rest.submissionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/billing-invoices\n          name: billing-invoices\n          description: \"Premium billing invoices\"\n          operations:\n            - method: GET\n              name: list-billing-invoices\n              description: \"List billing invoices for an employer group\"\n              call: \"unum-hr-connect.list-billing-invoices\"\n              with:\n                groupId: \"rest.groupId\"\n          \
  \    outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/billing-invoices/{invoiceId}\n          name: billing-invoice\n          description: \"Individual billing invoice\"\n          operations:\n            - method: GET\n              name: get-billing-invoice\n              description: \"Get billing invoice details\"\n              call: \"unum-hr-connect.get-billing-invoice\"\n              with:\n                invoiceId: \"rest.invoiceId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: unum-benefits-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Unum benefits administration workflows.\"\n      tools:\n        - name: list-members\n          description: \"List eligible members for an employer group\"\n          hints:\n            readOnly: true\n            openWorld: false\n         \
  \ call: \"unum-hr-connect.list-eligible-members\"\n          with:\n            groupId: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-member\n          description: \"Get eligibility details for a specific member\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unum-hr-connect.get-member-eligibility\"\n          with:\n            memberId: \"tools.memberId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-member\n          description: \"Submit new member eligibility to Unum\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"unum-hr-connect.submit-member-eligibility\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-member\n          description: \"Update existing member eligibility information\"\
  \n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"unum-hr-connect.update-member-eligibility\"\n          with:\n            memberId: \"tools.memberId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: terminate-member\n          description: \"Terminate eligibility for a member\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"unum-hr-connect.terminate-member-eligibility\"\n          with:\n            memberId: \"tools.memberId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-enrollments\n          description: \"List benefit enrollment elections for a group\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unum-hr-connect.list-enrollment-elections\"\n          with:\n            groupId: \"tools.groupId\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-enrollment\n          description: \"Submit a new benefit enrollment election for a member\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"unum-hr-connect.submit-enrollment-election\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-leave-requests\n          description: \"List leave and absence requests for a group\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unum-hr-connect.list-leave-requests\"\n          with:\n            groupId: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-leave-request\n          description: \"Submit a new leave or absence request for a member\"\n          hints:\n            readOnly: false\n            openWorld:\
  \ false\n          call: \"unum-hr-connect.submit-leave-request\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-leave-request\n          description: \"Get details and status of a leave request\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unum-hr-connect.get-leave-request\"\n          with:\n            requestId: \"tools.requestId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-eoi-submissions\n          description: \"List evidence of insurability submissions for a group\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unum-hr-connect.list-eoi-submissions\"\n          with:\n            groupId: \"tools.groupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-eoi-submission\n          description:\
  \ \"Submit a new evidence of insurability application\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"unum-hr-connect.submit-eoi\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-eoi-submission\n          description: \"Get status and decision for an EOI submission\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unum-hr-connect.get-eoi-submission\"\n          with:\n            submissionId: \"tools.submissionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-billing-invoices\n          description: \"List premium billing invoices for an employer group\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unum-hr-connect.list-billing-invoices\"\n          with:\n            groupId: \"tools.groupId\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: get-billing-invoice\n          description: \"Get premium billing invoice details\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"unum-hr-connect.get-billing-invoice\"\n          with:\n            invoiceId: \"tools.invoiceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/unum/refs/heads/main/capabilities/benefits-administration.yaml
tags:
- Unum
- Benefits Administration
- HR Integration
- Insurance
- Leave Management
- Eligibility
tools:
- description: List eligible members for an employer group
  hints:
    openWorld: false
    readOnly: true
  name: list-members
- description: Get eligibility details for a specific member
  hints:
    openWorld: false
    readOnly: true
  name: get-member
- description: Submit new member eligibility to Unum
  hints:
    openWorld: false
    readOnly: false
  name: create-member
- description: Update existing member eligibility information
  hints:
    idempotent: true
    readOnly: false
  name: update-member
- description: Terminate eligibility for a member
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: terminate-member
- description: List benefit enrollment elections for a group
  hints:
    openWorld: false
    readOnly: true
  name: list-enrollments
- description: Submit a new benefit enrollment election for a member
  hints:
    openWorld: false
    readOnly: false
  name: create-enrollment
- description: List leave and absence requests for a group
  hints:
    openWorld: false
    readOnly: true
  name: list-leave-requests
- description: Submit a new leave or absence request for a member
  hints:
    openWorld: false
    readOnly: false
  name: create-leave-request
- description: Get details and status of a leave request
  hints:
    openWorld: false
    readOnly: true
  name: get-leave-request
- description: List evidence of insurability submissions for a group
  hints:
    openWorld: false
    readOnly: true
  name: list-eoi-submissions
- description: Submit a new evidence of insurability application
  hints:
    openWorld: false
    readOnly: false
  name: create-eoi-submission
- description: Get status and decision for an EOI submission
  hints:
    openWorld: false
    readOnly: true
  name: get-eoi-submission
- description: List premium billing invoices for an employer group
  hints:
    openWorld: false
    readOnly: true
  name: list-billing-invoices
- description: Get premium billing invoice details
  hints:
    openWorld: false
    readOnly: true
  name: get-billing-invoice
---
