---
api_specs:
- filename: travelers-openapi.yml
  format: yaml
  label: travelers
  slug: travelers
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/travelers/refs/heads/main/openapi/travelers-openapi.yml
categories: []
consumed_apis:
- travelers
description: 'Workflow capability for commercial insurance agents, brokers, and enterprise clients integrating with Travelers Insurance. Covers the full commercial insurance lifecycle: obtaining quotes, managing policies, reporting claims, and tracking claim status across property, casualty, workers compensation, and commercial auto lines.'
layout: capability
name: Travelers Commercial Insurance Workflow
operations:
- description: Request a commercial lines insurance quote
  method: POST
  name: request-quote
  path: /v1/quotes
- description: Retrieve a previously generated quote
  method: GET
  name: get-quote
  path: /v1/quotes
- description: List all commercial insurance policies
  method: GET
  name: list-policies
  path: /v1/policies
- description: Get details of a specific policy
  method: GET
  name: get-policy
  path: /v1/policies
- description: List business insurance claims
  method: GET
  name: list-claims
  path: /v1/claims
- description: Submit a new business insurance claim
  method: POST
  name: report-claim
  path: /v1/claims
- description: Get the status and details of a specific claim
  method: GET
  name: get-claim
  path: /v1/claims
personas: []
provider_name: Travelers
provider_slug: travelers
search_terms:
- retrieve a previously generated commercial insurance quote
- list policies
- insurance
- list business insurance claims with optional status and date filtering
- commercial insurance
- get policy
- request a commercial insurance quote for business owner policy or workers compensation
- get details of a specific commercial insurance policy
- retrieve a previously generated quote
- submit a new business insurance claim
- get the status and details of a specific claim
- policy management
- business insurance claims management
- claims
- get details of a specific policy
- get claim
- request a commercial lines insurance quote
- list commercial insurance policies for the organization
- check the status and details of an existing insurance claim
- quoting
- property casualty
- commercial insurance quoting
- request quote
- get quote
- list all commercial insurance policies
- get claim status
- commercial insurance policy management
- report insurance claim
- submit a new business insurance claim to travelers
- request commercial quote
- fintech
- list claims
- fortune 500
- report claim
- list business insurance claims
slug: commercial-insurance-workflow
source_filename: commercial-insurance-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Travelers Commercial Insurance Workflow\"\n  description: >-\n    Workflow capability for commercial insurance agents, brokers, and\n    enterprise clients integrating with Travelers Insurance. Covers the\n    full commercial insurance lifecycle: obtaining quotes, managing policies,\n    reporting claims, and tracking claim status across property, casualty,\n    workers compensation, and commercial auto lines.\n  tags:\n    - Insurance\n    - Property Casualty\n    - Claims\n    - Commercial Insurance\n    - Quoting\n    - Policy Management\n    - Fortune 500\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TRAVELERS_CLIENT_ID: TRAVELERS_CLIENT_ID\n      TRAVELERS_CLIENT_SECRET: TRAVELERS_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: travelers\n      location: ./shared/travelers.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: commercial-insurance-api\n\
  \      description: \"Unified REST API for commercial insurance quoting, policy management, and claims.\"\n      resources:\n        - path: /v1/quotes\n          name: quotes\n          description: \"Commercial insurance quoting\"\n          operations:\n            - method: POST\n              name: request-quote\n              description: \"Request a commercial lines insurance quote\"\n              call: \"travelers.request-quote\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-quote\n              description: \"Retrieve a previously generated quote\"\n              call: \"travelers.get-quote\"\n              with:\n                quote_id: \"rest.quote_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/policies\n          name: policies\n          description: \"Commercial insurance policy management\"\
  \n          operations:\n            - method: GET\n              name: list-policies\n              description: \"List all commercial insurance policies\"\n              call: \"travelers.list-policies\"\n              with:\n                status: \"rest.status\"\n                policy_type: \"rest.policy_type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-policy\n              description: \"Get details of a specific policy\"\n              call: \"travelers.get-policy\"\n              with:\n                policy_number: \"rest.policy_number\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/claims\n          name: claims\n          description: \"Business insurance claims management\"\n          operations:\n            - method: GET\n              name: list-claims\n              description: \"List\
  \ business insurance claims\"\n              call: \"travelers.list-claims\"\n              with:\n                status: \"rest.status\"\n                policy_type: \"rest.policy_type\"\n                start_date: \"rest.start_date\"\n                end_date: \"rest.end_date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: report-claim\n              description: \"Submit a new business insurance claim\"\n              call: \"travelers.report-claim\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-claim\n              description: \"Get the status and details of a specific claim\"\n              call: \"travelers.get-claim\"\n              with:\n                claim_number: \"rest.claim_number\"\n              outputParameters:\n                - type: object\n             \
  \     mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: commercial-insurance-mcp\n      transport: http\n      description: \"MCP server for AI-assisted commercial insurance quoting and claims management.\"\n      tools:\n        - name: request-commercial-quote\n          description: \"Request a commercial insurance quote for Business Owner Policy or Workers Compensation\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"travelers.request-quote\"\n          with:\n            product_type: \"tools.product_type\"\n            business_info: \"tools.business_info\"\n            effective_date: \"tools.effective_date\"\n            coverage_options: \"tools.coverage_options\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-quote\n          description: \"Retrieve a previously generated commercial insurance quote\"\n          hints:\n            readOnly: true\n\
  \            openWorld: false\n          call: \"travelers.get-quote\"\n          with:\n            quote_id: \"tools.quote_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-policies\n          description: \"List commercial insurance policies for the organization\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"travelers.list-policies\"\n          with:\n            status: \"tools.status\"\n            policy_type: \"tools.policy_type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-policy\n          description: \"Get details of a specific commercial insurance policy\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"travelers.get-policy\"\n          with:\n            policy_number: \"tools.policy_number\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: report-insurance-claim\n          description: \"Submit a new business insurance claim to Travelers\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"travelers.report-claim\"\n          with:\n            policy_number: \"tools.policy_number\"\n            policy_type: \"tools.policy_type\"\n            loss_date: \"tools.loss_date\"\n            description: \"tools.description\"\n            loss_location: \"tools.loss_location\"\n            claimant: \"tools.claimant\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-claim-status\n          description: \"Check the status and details of an existing insurance claim\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"travelers.get-claim\"\n          with:\n            claim_number: \"tools.claim_number\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: list-claims\n          description: \"List business insurance claims with optional status and date filtering\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"travelers.list-claims\"\n          with:\n            status: \"tools.status\"\n            policy_type: \"tools.policy_type\"\n            start_date: \"tools.start_date\"\n            end_date: \"tools.end_date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/travelers/refs/heads/main/capabilities/commercial-insurance-workflow.yaml
tags:
- Insurance
- Property Casualty
- Claims
- Commercial Insurance
- Quoting
- Policy Management
- Fortune 500
tools:
- description: Request a commercial insurance quote for Business Owner Policy or Workers Compensation
  hints:
    openWorld: false
    readOnly: false
  name: request-commercial-quote
- description: Retrieve a previously generated commercial insurance quote
  hints:
    openWorld: false
    readOnly: true
  name: get-quote
- description: List commercial insurance policies for the organization
  hints:
    openWorld: false
    readOnly: true
  name: list-policies
- description: Get details of a specific commercial insurance policy
  hints:
    openWorld: false
    readOnly: true
  name: get-policy
- description: Submit a new business insurance claim to Travelers
  hints:
    openWorld: false
    readOnly: false
  name: report-insurance-claim
- description: Check the status and details of an existing insurance claim
  hints:
    openWorld: false
    readOnly: true
  name: get-claim-status
- description: List business insurance claims with optional status and date filtering
  hints:
    openWorld: false
    readOnly: true
  name: list-claims
---
