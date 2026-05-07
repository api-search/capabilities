---
categories: []
consumed_apis: []
description: Workflow capability for State Farm embedded insurance integrations. Enables property management platforms, real estate applications, and partner aggregators to embed State Farm renters insurance quoting and policy binding directly into their tenant onboarding and lease workflows. Supports AI-assisted insurance recommendation, coverage configuration, and policy management.
layout: capability
name: State Farm Embedded Insurance
operations:
- description: Get available renters insurance coverage options by state
  method: GET
  name: list-coverage-options
  path: /v1/renters/coverage-options
- description: Create a renters insurance quote for a tenant
  method: POST
  name: create-renters-quote
  path: /v1/renters/quotes
- description: Retrieve a renters insurance quote
  method: GET
  name: get-renters-quote
  path: /v1/renters/quotes/{quoteId}
- description: Bind a renters insurance policy from a quote
  method: POST
  name: bind-renters-policy
  path: /v1/renters/policies
- description: Get renters insurance policy status and coverage
  method: GET
  name: get-renters-policy
  path: /v1/renters/policies/{policyNumber}
personas: []
provider_name: State Farm Insurance Companies
provider_slug: state-farm-insurance-cos
search_terms:
- list available state farm renters insurance coverage options and limits for a specific us state, including personal property limits, liability limits, deductible choices, and optional coverages.
- create a renters insurance quote for a tenant
- policy status and details
- create renters quote
- bind renters policy
- list renters coverage options
- quote retrieval
- embedded insurance
- get renters insurance policy status and coverage
- partner
- renters insurance policy binding
- get the current status, coverage details, and premium information for an active state farm renters insurance policy.
- renters insurance
- retrieve the details and status of a previously created state farm renters insurance quote by its quote id.
- property management
- bind a renters insurance policy from a quote
- create a state farm renters insurance quote for a tenant given their property address, personal information, and desired coverage selections. returns the quoted premium and coverage summary.
- convert an accepted state farm renters insurance quote into an active policy. specify the quote id, payment method, and payment frequency to complete policy binding.
- get renters policy status
- get available renters insurance coverage options by state
- available coverage options for tenants
- list coverage options
- get renters policy
- renters insurance quote operations
- get renters quote
- insurance
- retrieve a renters insurance quote
slug: embedded-insurance
source_filename: embedded-insurance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: State Farm Embedded Insurance\n  description: Workflow capability for State Farm embedded insurance integrations. Enables property management platforms,\n    real estate applications, and partner aggregators to embed State Farm renters insurance quoting and policy binding directly\n    into their tenant onboarding and lease workflows. Supports AI-assisted insurance recommendation, coverage configuration,\n    and policy management.\n  tags:\n  - Insurance\n  - Renters Insurance\n  - Embedded Insurance\n  - Partner\n  - Property Management\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STATE_FARM_CLIENT_ID: STATE_FARM_CLIENT_ID\n    STATE_FARM_CLIENT_SECRET: STATE_FARM_CLIENT_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: state-farm-renters\n    baseUri: https://api.statefarm.com/v1\n    description: State Farm Renters Insurance API\n    authentication:\n      type: bearer\n\
  \      token: '{{STATE_FARM_ACCESS_TOKEN}}'\n    resources:\n    - name: renters-quotes\n      path: /renters/quotes\n      description: Renters insurance quote operations\n      operations:\n      - name: create-renters-quote\n        method: POST\n        description: Create a renters insurance quote\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            propertyAddress: '{{tools.propertyAddress}}'\n            tenantInfo: '{{tools.tenantInfo}}'\n            coverageOptions: '{{tools.coverageOptions}}'\n            effectiveDate: '{{tools.effectiveDate}}'\n    - name: renters-quote-detail\n      path: /renters/quotes/{quoteId}\n      description: Individual quote operations\n      operations:\n      - name: get-renters-quote\n        method: GET\n        description: Get renters insurance quote by ID\n        inputParameters:\n        - name: quoteId\n\
  \          in: path\n          type: string\n          required: true\n          description: Quote identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: renters-policies\n      path: /renters/policies\n      description: Renters insurance policy operations\n      operations:\n      - name: create-renters-policy\n        method: POST\n        description: Bind a renters insurance policy from a quote\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            quoteId: '{{tools.quoteId}}'\n            paymentMethod: '{{tools.paymentMethod}}'\n            paymentFrequency: '{{tools.paymentFrequency}}'\n            effectiveDate: '{{tools.effectiveDate}}'\n    - name: renters-policy-detail\n      path: /renters/policies/{policyNumber}\n      description: Individual\
  \ policy operations\n      operations:\n      - name: get-renters-policy\n        method: GET\n        description: Get renters insurance policy details\n        inputParameters:\n        - name: policyNumber\n          in: path\n          type: string\n          required: true\n          description: Policy number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: coverage-options\n      path: /renters/coverage-options\n      description: Available coverage options\n      operations:\n      - name: list-coverage-options\n        method: GET\n        description: List available coverage options and limits\n        inputParameters:\n        - name: state\n          in: query\n          type: string\n          required: false\n          description: US state code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n\
  \  - type: rest\n    port: 8080\n    namespace: state-farm-embedded-insurance-api\n    description: Unified REST API for State Farm embedded insurance partner workflows.\n    resources:\n    - path: /v1/renters/coverage-options\n      name: coverage-options\n      description: Available coverage options for tenants\n      operations:\n      - method: GET\n        name: list-coverage-options\n        description: Get available renters insurance coverage options by state\n        call: state-farm-renters.list-coverage-options\n        with:\n          state: rest.state\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/renters/quotes\n      name: renters-quotes\n      description: Renters insurance quote operations\n      operations:\n      - method: POST\n        name: create-renters-quote\n        description: Create a renters insurance quote for a tenant\n        call: state-farm-renters.create-renters-quote\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /v1/renters/quotes/{quoteId}\n      name: renters-quote-detail\n      description: Quote retrieval\n      operations:\n      - method: GET\n        name: get-renters-quote\n        description: Retrieve a renters insurance quote\n        call: state-farm-renters.get-renters-quote\n        with:\n          quoteId: rest.quoteId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/renters/policies\n      name: renters-policies\n      description: Renters insurance policy binding\n      operations:\n      - method: POST\n        name: bind-renters-policy\n        description: Bind a renters insurance policy from a quote\n        call: state-farm-renters.create-renters-policy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/renters/policies/{policyNumber}\n      name: renters-policy-detail\n      description: Policy status and details\n      operations:\n     \
  \ - method: GET\n        name: get-renters-policy\n        description: Get renters insurance policy status and coverage\n        call: state-farm-renters.get-renters-policy\n        with:\n          policyNumber: rest.policyNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: state-farm-embedded-insurance-mcp\n    transport: http\n    description: MCP server for AI-assisted State Farm embedded insurance workflows for property management platforms.\n    tools:\n    - name: list-renters-coverage-options\n      description: List available State Farm renters insurance coverage options and limits for a specific US state, including\n        personal property limits, liability limits, deductible choices, and optional coverages.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: state-farm-renters.list-coverage-options\n      with:\n        state: tools.state\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: create-renters-quote\n      description: Create a State Farm renters insurance quote for a tenant given their property address, personal information,\n        and desired coverage selections. Returns the quoted premium and coverage summary.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: state-farm-renters.create-renters-quote\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-renters-quote\n      description: Retrieve the details and status of a previously created State Farm renters insurance quote by its quote\n        ID.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: state-farm-renters.get-renters-quote\n      with:\n        quoteId: tools.quoteId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: bind-renters-policy\n      description: Convert an accepted State Farm renters insurance quote into an active policy. Specify\
  \ the quote ID, payment\n        method, and payment frequency to complete policy binding.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: state-farm-renters.create-renters-policy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-renters-policy-status\n      description: Get the current status, coverage details, and premium information for an active State Farm renters insurance\n        policy.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: state-farm-renters.get-renters-policy\n      with:\n        policyNumber: tools.policyNumber\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/state-farm-insurance-cos/refs/heads/main/capabilities/embedded-insurance.yaml
tags:
- Insurance
- Renters Insurance
- Embedded Insurance
- Partner
- Property Management
tools:
- description: List available State Farm renters insurance coverage options and limits for a specific US state, including personal property limits, liability limits, deductible choices, and optional coverages.
  hints:
    openWorld: true
    readOnly: true
  name: list-renters-coverage-options
- description: Create a State Farm renters insurance quote for a tenant given their property address, personal information, and desired coverage selections. Returns the quoted premium and coverage summary.
  hints:
    openWorld: false
    readOnly: false
  name: create-renters-quote
- description: Retrieve the details and status of a previously created State Farm renters insurance quote by its quote ID.
  hints:
    openWorld: false
    readOnly: true
  name: get-renters-quote
- description: Convert an accepted State Farm renters insurance quote into an active policy. Specify the quote ID, payment method, and payment frequency to complete policy binding.
  hints:
    openWorld: false
    readOnly: false
  name: bind-renters-policy
- description: Get the current status, coverage details, and premium information for an active State Farm renters insurance policy.
  hints:
    openWorld: false
    readOnly: true
  name: get-renters-policy-status
---
