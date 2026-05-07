---
categories: []
consumed_apis: []
description: Workflow capability that wraps the Email Verifier API 16-point verification engine. Used by growth, marketing, and lead-generation teams to validate email addresses at signup, before a marketing send, and during list cleanup. Exposes a single normalized verify-email operation as a REST resource and an MCP tool, with credit-balance awareness so AI agents can budget verification work against the customer's remaining credits.
layout: capability
name: Email Verifier API Email Verification
operations:
- description: Verify an email address and return the deliverability verdict, event code, and intelligence flags.
  method: GET
  name: verify-email
  path: /v1/verify
personas: []
provider_name: Email Verifier API
provider_slug: email-verifier-api
search_terms:
- catch-all detection
- bounce prevention
- role account detection
- 'verify whether an email address is deliverable using the email verifier api 16-point engine.

  returns a top-level status (passed / failed / unknown / transient), a granular event code

  (mailboxexists, mailboxdoesnotexist, iscatchall, isgreylisting, etc.), and intelligence

  flags such as isdisposable, isroleaccount, isfreeservice, and isgibberish. the response

  includes the customer''s remaining credit balance so the agent can budget further work.'
- deliverability
- email verification
- typo suggestion
- b2b lead scoring
- spam trap detection
- verify a single email address.
- verify an email address and return the deliverability verdict, event code, and intelligence flags.
- greylisting
- disposable detection
- lead validation
- smtp check
- verify email
slug: email-verification
source_filename: email-verification.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Email Verifier API Email Verification\n  description: |-\n    Workflow capability that wraps the Email Verifier API 16-point verification engine. Used by\n    growth, marketing, and lead-generation teams to validate email addresses at signup, before\n    a marketing send, and during list cleanup. Exposes a single normalized verify-email\n    operation as a REST resource and an MCP tool, with credit-balance awareness so AI agents\n    can budget verification work against the customer's remaining credits.\n  tags:\n    - Email Verification\n    - Deliverability\n    - SMTP Check\n    - Bounce Prevention\n    - Lead Validation\n  created: '2026-05-06'\n  modified: '2026-05-06'\nbinds:\n  - namespace: env\n    keys:\n      EMAIL_VERIFIER_API_KEY: EMAIL_VERIFIER_API_KEY\ncapability:\n  consumes:\n    - type: http\n      namespace: email-verifier\n      baseUri: https://emailverifierapi.com/v2\n      description: Email Verifier API real-time\
  \ verification endpoint.\n      authentication:\n        type: apiKey\n        in: query\n        name: apiKey\n        token: '{{EMAIL_VERIFIER_API_KEY}}'\n      resources:\n        - name: verification\n          path: /\n          description: Real-time email verification.\n          operations:\n            - name: verify-email\n              method: GET\n              description: Verify a single email address.\n              inputParameters:\n                - name: email\n                  in: query\n                  type: string\n                  required: true\n                  description: Email address to verify.\n                - name: xml\n                  in: query\n                  type: boolean\n                  required: false\n                  description: Return XML payload instead of JSON.\n              outputRawFormat: json\n              outputParameters:\n                - name: status\n                  type: string\n                  value: $.status\n\
  \                - name: event\n                  type: string\n                  value: $.event\n                - name: details\n                  type: string\n                  value: $.details\n                - name: emailSuggested\n                  type: string\n                  value: $.emailSuggested\n                - name: isDisposable\n                  type: boolean\n                  value: $.isDisposable\n                - name: isRoleAccount\n                  type: boolean\n                  value: $.isRoleAccount\n                - name: isFreeService\n                  type: boolean\n                  value: $.isFreeService\n                - name: remaining\n                  type: string\n                  value: $.remaining\n                - name: result\n                  type: object\n                  value: $.\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: email-verifier-rest\n      description: Normalized REST surface for the Email Verifier\
  \ API.\n      resources:\n        - path: /v1/verify\n          name: verify\n          description: Verify a single email address.\n          operations:\n            - method: GET\n              name: verify-email\n              description: Verify an email address and return the deliverability verdict, event code, and intelligence flags.\n              call: email-verifier.verify-email\n              with:\n                email: rest.email\n              outputParameters:\n                - type: object\n                  mapping: $.\n    - type: mcp\n      port: 9090\n      namespace: email-verifier-mcp\n      transport: http\n      description: MCP server exposing the Email Verifier API verification engine to AI agents.\n      tools:\n        - name: verify-email\n          description: |-\n            Verify whether an email address is deliverable using the Email Verifier API 16-point engine.\n            Returns a top-level status (passed / failed / unknown / transient), a granular\
  \ event code\n            (mailboxExists, mailboxDoesNotExist, isCatchall, isGreylisting, etc.), and intelligence\n            flags such as isDisposable, isRoleAccount, isFreeService, and isGibberish. The response\n            includes the customer's remaining credit balance so the agent can budget further work.\n          hints:\n            readOnly: true\n            idempotent: true\n            openWorld: true\n          call: email-verifier.verify-email\n          with:\n            email: tools.email\n          outputParameters:\n            - type: object\n              mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/email-verifier-api/refs/heads/main/capabilities/email-verification.yaml
tags:
- Email Verification
- Deliverability
- SMTP Check
- Bounce Prevention
- Lead Validation
tools:
- description: Verify whether an email address is deliverable using the Email Verifier API 16-point engine. Returns a top-level status (passed / failed / unknown / transient), a granular event code (mailboxExists, mailboxDoesNotExist, isCatchall, isGreylisting, etc.), and intelligence flags such as isDisposable, isRoleAccount, isFreeService, and isGibberish. The response includes the customer's remaining credit balance so the agent can budget further work.
  hints:
    idempotent: true
    openWorld: true
    readOnly: true
  name: verify-email
---
