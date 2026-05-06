---
categories: []
consumed_apis: []
description: Workflow capability for healthcare providers using UnitedHealthcare APIs to verify member eligibility, manage claims, check prior authorizations, and access the provider directory. Supports revenue cycle management, point-of-care eligibility, and clinical workflow automation for practices, hospitals, and health IT systems.
layout: capability
name: UnitedHealthcare Provider Operations
operations:
- description: Check member eligibility.
  method: POST
  name: check-eligibility
  path: /v1/eligibility
- description: Check patient benefit details.
  method: POST
  name: check-benefit
  path: /v1/eligibility
- description: Inquire claim status.
  method: POST
  name: inquire-claim
  path: /v1/claims
- description: Check prior auth requirements.
  method: POST
  name: check-prior-auth
  path: /v1/prior-auth
- description: Get provider demographics.
  method: GET
  name: get-provider
  path: /v1/providers
personas: []
provider_name: UnitedHealthcare
provider_slug: unitedhealthcare
search_terms:
- verify unitedhealthcare member eligibility and coverage details at point of care including deductible, copay, and network status.
- fhir
- check prior auth
- get provider
- inquire claim
- eligibility
- get provider demographics.
- get claim status
- health app developer
- revenue cycle
- healthcare provider
- clinical staff coordinating prior authorization requests and tracking approval status
- claims management
- check eligibility
- healthcare
- billing specialist
- fhir-based patient data access workflow for claims history, coverage, and provider directory
- healthcare provider workflow for eligibility, claims, prior authorization, and provider directory
- developer building patient-facing applications using fhir interoperability apis
- claims submission, eligibility verification, and payment management workflows
- check prior auth requirements.
- check patient-specific benefit details for a service code including whether authorization is required and estimated cost-sharing.
- health insurance
- check member eligibility.
- provider directory.
- care management professional accessing member health history for care coordination
- look up unitedhealthcare claim status, payment details, and denial reasons by claim number or member id.
- member eligibility verification.
- check prior authorization
- search unitedhealthcare provider directory for in-network physicians and organizations by npi or state.
- physician or clinical staff verifying eligibility and managing prior authorizations at point of care
- find provider
- check patient benefit
- prior auth coordinator
- unitedhealthcare
- patient
- prior authorization
- check patient benefit details.
- check benefit
- care coordinator
- determine if prior authorization is required for a procedure and check current authorization status to prevent avoidable denials.
- inquire claim status.
- claims management.
- prior authorization management.
- fhir-based interoperability for health information exchange
- unitedhealthcare member accessing their health data through patient portals or apps
- prior authorization, provider directory, and point-of-care clinical support
- medical billing staff managing claim submission, status inquiry, and revenue cycle workflows
- claims
- verify member eligibility
- member-facing health data access and patient portal integration
slug: provider-operations
source_filename: provider-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: UnitedHealthcare Provider Operations\n  description: Workflow capability for healthcare providers using UnitedHealthcare APIs to verify member eligibility, manage\n    claims, check prior authorizations, and access the provider directory. Supports revenue cycle management, point-of-care\n    eligibility, and clinical workflow automation for practices, hospitals, and health IT systems.\n  tags:\n  - UnitedHealthcare\n  - Healthcare Provider\n  - Eligibility\n  - Claims Management\n  - Prior Authorization\n  - Revenue Cycle\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UHC_BEARER_TOKEN: UHC_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: uhc-provider\n    baseUri: https://api.uhcprovider.com\n    description: UnitedHealthcare Provider API.\n    authentication:\n      type: bearer\n      token: '{{UHC_BEARER_TOKEN}}'\n    resources:\n    - name: eligibility\n      path: /eligibility/v1/real-time\n\
  \      description: Real-time eligibility verification.\n      operations:\n      - name: check-eligibility\n        method: POST\n        description: Verify member eligibility and benefits in real time.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            memberId: '{{tools.memberId}}'\n            dateOfBirth: '{{tools.dateOfBirth}}'\n            serviceType: '{{tools.serviceType}}'\n            dateOfService: '{{tools.dateOfService}}'\n            npi: '{{tools.npi}}'\n    - name: benefit-check\n      path: /eligibility/v1/patient-benefit-check\n      description: Patient-specific benefit check.\n      operations:\n      - name: check-patient-benefit\n        method: POST\n        description: Check patient benefit and cost-sharing details for a service.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n        body:\n          type: json\n          data:\n            memberId: '{{tools.memberId}}'\n            serviceCode: '{{tools.serviceCode}}'\n            dateOfService: '{{tools.dateOfService}}'\n            npi: '{{tools.npi}}'\n    - name: claims\n      path: /claims/v1/inquiry\n      description: Claim status inquiry.\n      operations:\n      - name: inquire-claim\n        method: POST\n        description: Check claim status and payment details.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            claimNumber: '{{tools.claimNumber}}'\n            npi: '{{tools.npi}}'\n            memberId: '{{tools.memberId}}'\n    - name: prior-auth\n      path: /prior-auth/v1/check\n      description: Prior authorization requirement check.\n      operations:\n      - name: check-prior-auth\n        method: POST\n\
  \        description: Check if prior authorization is required for a procedure.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            memberId: '{{tools.memberId}}'\n            npi: '{{tools.npi}}'\n            serviceCode: '{{tools.serviceCode}}'\n    - name: providers\n      path: /providers/v1/demographics\n      description: Provider demographics and directory.\n      operations:\n      - name: get-provider-demographics\n        method: GET\n        description: Get provider demographic and credentialing information.\n        inputParameters:\n        - name: npi\n          in: query\n          type: string\n          required: true\n          description: Provider NPI.\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: State filter.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: provider-operations-api\n    description: Unified REST API for UnitedHealthcare provider operations.\n    resources:\n    - path: /v1/eligibility\n      name: eligibility\n      description: Member eligibility verification.\n      operations:\n      - method: POST\n        name: check-eligibility\n        description: Check member eligibility.\n        call: uhc-provider.check-eligibility\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: check-benefit\n        description: Check patient benefit details.\n        call: uhc-provider.check-patient-benefit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/claims\n      name: claims\n      description: Claims management.\n      operations:\n      - method: POST\n        name: inquire-claim\n        description: Inquire\
  \ claim status.\n        call: uhc-provider.inquire-claim\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/prior-auth\n      name: prior-auth\n      description: Prior authorization management.\n      operations:\n      - method: POST\n        name: check-prior-auth\n        description: Check prior auth requirements.\n        call: uhc-provider.check-prior-auth\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/providers\n      name: providers\n      description: Provider directory.\n      operations:\n      - method: GET\n        name: get-provider\n        description: Get provider demographics.\n        call: uhc-provider.get-provider-demographics\n        with:\n          npi: rest.npi\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: provider-operations-mcp\n    transport: http\n    description: MCP server for AI-assisted UnitedHealthcare\
  \ provider operations.\n    tools:\n    - name: verify-member-eligibility\n      description: Verify UnitedHealthcare member eligibility and coverage details at point of care including deductible,\n        copay, and network status.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: uhc-provider.check-eligibility\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-patient-benefit\n      description: Check patient-specific benefit details for a service code including whether authorization is required and\n        estimated cost-sharing.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: uhc-provider.check-patient-benefit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-claim-status\n      description: Look up UnitedHealthcare claim status, payment details, and denial reasons by claim number or member ID.\n  \
  \    hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: uhc-provider.inquire-claim\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-prior-authorization\n      description: Determine if prior authorization is required for a procedure and check current authorization status to\n        prevent avoidable denials.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: uhc-provider.check-prior-auth\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-provider\n      description: Search UnitedHealthcare provider directory for in-network physicians and organizations by NPI or state.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: uhc-provider.get-provider-demographics\n      with:\n        npi: tools.npi\n        state: tools.state\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/unitedhealthcare/refs/heads/main/capabilities/provider-operations.yaml
tags:
- UnitedHealthcare
- Healthcare Provider
- Eligibility
- Claims Management
- Prior Authorization
- Revenue Cycle
tools:
- description: Verify UnitedHealthcare member eligibility and coverage details at point of care including deductible, copay, and network status.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: verify-member-eligibility
- description: Check patient-specific benefit details for a service code including whether authorization is required and estimated cost-sharing.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: check-patient-benefit
- description: Look up UnitedHealthcare claim status, payment details, and denial reasons by claim number or member ID.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: get-claim-status
- description: Determine if prior authorization is required for a procedure and check current authorization status to prevent avoidable denials.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: check-prior-authorization
- description: Search UnitedHealthcare provider directory for in-network physicians and organizations by NPI or state.
  hints:
    openWorld: true
    readOnly: true
  name: find-provider
---
