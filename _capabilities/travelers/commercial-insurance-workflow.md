---
categories: []
consumed_apis: []
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
- policy management
- check the status and details of an existing insurance claim
- quoting
- commercial insurance
- get policy
- request commercial quote
- list claims
- submit a new business insurance claim
- get claim status
- request quote
- claims
- fintech
- get quote
- get details of a specific policy
- list business insurance claims
- list commercial insurance policies for the organization
- report insurance claim
- get the status and details of a specific claim
- request a commercial lines insurance quote
- commercial insurance quoting
- submit a new business insurance claim to travelers
- request a commercial insurance quote for business owner policy or workers compensation
- list all commercial insurance policies
- get claim
- retrieve a previously generated commercial insurance quote
- business insurance claims management
- list policies
- commercial insurance policy management
- list business insurance claims with optional status and date filtering
- property casualty
- insurance
- retrieve a previously generated quote
- fortune 500
- get details of a specific commercial insurance policy
- report claim
slug: commercial-insurance-workflow
source_filename: commercial-insurance-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Travelers Commercial Insurance Workflow\n  description: 'Workflow capability for commercial insurance agents, brokers, and enterprise clients integrating with Travelers\n    Insurance. Covers the full commercial insurance lifecycle: obtaining quotes, managing policies, reporting claims, and\n    tracking claim status across property, casualty, workers compensation, and commercial auto lines.'\n  tags:\n  - Insurance\n  - Property Casualty\n  - Claims\n  - Commercial Insurance\n  - Quoting\n  - Policy Management\n  - Fortune 500\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TRAVELERS_CLIENT_ID: TRAVELERS_CLIENT_ID\n    TRAVELERS_CLIENT_SECRET: TRAVELERS_CLIENT_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: travelers\n    baseUri: https://api.travelers.com/v1\n    description: Travelers business insurance claims, quoting, and policy APIs.\n    authentication:\n      type: bearer\n\
  \      token: '{{TRAVELERS_OAUTH_TOKEN}}'\n    resources:\n    - name: claims\n      path: /claims\n      description: Business insurance claims management\n      operations:\n      - name: list-claims\n        method: GET\n        description: List business insurance claims\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by claim status\n        - name: policy_type\n          in: query\n          type: string\n          required: false\n          description: Filter by policy type\n        - name: start_date\n          in: query\n          type: string\n          required: false\n          description: Filter from date\n        - name: end_date\n          in: query\n          type: string\n          required: false\n          description: Filter to date\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: report-claim\n        method: POST\n        description: Submit a new business insurance claim\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            policy_number: '{{tools.policy_number}}'\n            policy_type: '{{tools.policy_type}}'\n            loss_date: '{{tools.loss_date}}'\n            description: '{{tools.description}}'\n    - name: claims-by-number\n      path: /claims/{claim_number}\n      description: Individual claim operations\n      operations:\n      - name: get-claim\n        method: GET\n        description: Get details of a specific claim\n        inputParameters:\n        - name: claim_number\n          in: path\n          type: string\n          required: true\n          description:\
  \ Claim number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: quotes\n      path: /quotes\n      description: Commercial insurance quoting\n      operations:\n      - name: request-quote\n        method: POST\n        description: Request a commercial insurance quote\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            product_type: '{{tools.product_type}}'\n            business_info: '{{tools.business_info}}'\n            effective_date: '{{tools.effective_date}}'\n    - name: quotes-by-id\n      path: /quotes/{quote_id}\n      description: Individual quote retrieval\n      operations:\n      - name: get-quote\n        method: GET\n        description: Retrieve a previously generated quote\n        inputParameters:\n        - name: quote_id\n          in:\
  \ path\n          type: string\n          required: true\n          description: Quote ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: policies\n      path: /policies\n      description: Policy information\n      operations:\n      - name: list-policies\n        method: GET\n        description: List commercial insurance policies\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by policy status\n        - name: policy_type\n          in: query\n          type: string\n          required: false\n          description: Filter by policy type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: policies-by-number\n      path: /policies/{policy_number}\n      description: Individual policy retrieval\n      operations:\n\
  \      - name: get-policy\n        method: GET\n        description: Get details of a specific policy\n        inputParameters:\n        - name: policy_number\n          in: path\n          type: string\n          required: true\n          description: Policy number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: commercial-insurance-api\n    description: Unified REST API for commercial insurance quoting, policy management, and claims.\n    resources:\n    - path: /v1/quotes\n      name: quotes\n      description: Commercial insurance quoting\n      operations:\n      - method: POST\n        name: request-quote\n        description: Request a commercial lines insurance quote\n        call: travelers.request-quote\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-quote\n        description:\
  \ Retrieve a previously generated quote\n        call: travelers.get-quote\n        with:\n          quote_id: rest.quote_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/policies\n      name: policies\n      description: Commercial insurance policy management\n      operations:\n      - method: GET\n        name: list-policies\n        description: List all commercial insurance policies\n        call: travelers.list-policies\n        with:\n          status: rest.status\n          policy_type: rest.policy_type\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-policy\n        description: Get details of a specific policy\n        call: travelers.get-policy\n        with:\n          policy_number: rest.policy_number\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/claims\n      name: claims\n      description: Business insurance claims management\n\
  \      operations:\n      - method: GET\n        name: list-claims\n        description: List business insurance claims\n        call: travelers.list-claims\n        with:\n          status: rest.status\n          policy_type: rest.policy_type\n          start_date: rest.start_date\n          end_date: rest.end_date\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: report-claim\n        description: Submit a new business insurance claim\n        call: travelers.report-claim\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-claim\n        description: Get the status and details of a specific claim\n        call: travelers.get-claim\n        with:\n          claim_number: rest.claim_number\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: commercial-insurance-mcp\n    transport: http\n    description:\
  \ MCP server for AI-assisted commercial insurance quoting and claims management.\n    tools:\n    - name: request-commercial-quote\n      description: Request a commercial insurance quote for Business Owner Policy or Workers Compensation\n      hints:\n        readOnly: false\n        openWorld: false\n      call: travelers.request-quote\n      with:\n        product_type: tools.product_type\n        business_info: tools.business_info\n        effective_date: tools.effective_date\n        coverage_options: tools.coverage_options\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-quote\n      description: Retrieve a previously generated commercial insurance quote\n      hints:\n        readOnly: true\n        openWorld: false\n      call: travelers.get-quote\n      with:\n        quote_id: tools.quote_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-policies\n      description: List commercial insurance policies for\
  \ the organization\n      hints:\n        readOnly: true\n        openWorld: false\n      call: travelers.list-policies\n      with:\n        status: tools.status\n        policy_type: tools.policy_type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-policy\n      description: Get details of a specific commercial insurance policy\n      hints:\n        readOnly: true\n        openWorld: false\n      call: travelers.get-policy\n      with:\n        policy_number: tools.policy_number\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: report-insurance-claim\n      description: Submit a new business insurance claim to Travelers\n      hints:\n        readOnly: false\n        openWorld: false\n      call: travelers.report-claim\n      with:\n        policy_number: tools.policy_number\n        policy_type: tools.policy_type\n        loss_date: tools.loss_date\n        description: tools.description\n        loss_location: tools.loss_location\n\
  \        claimant: tools.claimant\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-claim-status\n      description: Check the status and details of an existing insurance claim\n      hints:\n        readOnly: true\n        openWorld: false\n      call: travelers.get-claim\n      with:\n        claim_number: tools.claim_number\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-claims\n      description: List business insurance claims with optional status and date filtering\n      hints:\n        readOnly: true\n        openWorld: false\n      call: travelers.list-claims\n      with:\n        status: tools.status\n        policy_type: tools.policy_type\n        start_date: tools.start_date\n        end_date: tools.end_date\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
