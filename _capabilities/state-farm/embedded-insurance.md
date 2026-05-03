---
categories: []
consumed_apis:
- state-farm-renters
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
provider_name: State Farm
provider_slug: state-farm
search_terms:
- get the current status, coverage details, and premium information for an active state farm renters insurance policy.
- insurance
- get renters policy
- create renters quote
- get renters policy status
- renters insurance quote operations
- convert an accepted state farm renters insurance quote into an active policy. specify the quote id, payment method, and payment frequency to complete policy binding.
- embedded insurance
- policy status and details
- get renters insurance policy status and coverage
- bind a renters insurance policy from a quote
- create a state farm renters insurance quote for a tenant given their property address, personal information, and desired coverage selections. returns the quoted premium and coverage summary.
- retrieve the details and status of a previously created state farm renters insurance quote by its quote id.
- available coverage options for tenants
- create a renters insurance quote for a tenant
- quote retrieval
- renters insurance
- get available renters insurance coverage options by state
- property management
- list renters coverage options
- list available state farm renters insurance coverage options and limits for a specific us state, including personal property limits, liability limits, deductible choices, and optional coverages.
- partner
- get renters quote
- retrieve a renters insurance quote
- list coverage options
- bind renters policy
- renters insurance policy binding
slug: embedded-insurance
source_filename: embedded-insurance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"State Farm Embedded Insurance\"\n  description: >-\n    Workflow capability for State Farm embedded insurance integrations. Enables property\n    management platforms, real estate applications, and partner aggregators to embed\n    State Farm renters insurance quoting and policy binding directly into their tenant\n    onboarding and lease workflows. Supports AI-assisted insurance recommendation,\n    coverage configuration, and policy management.\n  tags:\n    - Insurance\n    - Renters Insurance\n    - Embedded Insurance\n    - Partner\n    - Property Management\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STATE_FARM_CLIENT_ID: STATE_FARM_CLIENT_ID\n      STATE_FARM_CLIENT_SECRET: STATE_FARM_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: state-farm-renters\n      location: ./shared/renters-insurance.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n    \
  \  namespace: state-farm-embedded-insurance-api\n      description: \"Unified REST API for State Farm embedded insurance partner workflows.\"\n      resources:\n        - path: /v1/renters/coverage-options\n          name: coverage-options\n          description: \"Available coverage options for tenants\"\n          operations:\n            - method: GET\n              name: list-coverage-options\n              description: \"Get available renters insurance coverage options by state\"\n              call: \"state-farm-renters.list-coverage-options\"\n              with:\n                state: \"rest.state\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/renters/quotes\n          name: renters-quotes\n          description: \"Renters insurance quote operations\"\n          operations:\n            - method: POST\n              name: create-renters-quote\n              description: \"Create a renters insurance quote\
  \ for a tenant\"\n              call: \"state-farm-renters.create-renters-quote\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/renters/quotes/{quoteId}\n          name: renters-quote-detail\n          description: \"Quote retrieval\"\n          operations:\n            - method: GET\n              name: get-renters-quote\n              description: \"Retrieve a renters insurance quote\"\n              call: \"state-farm-renters.get-renters-quote\"\n              with:\n                quoteId: \"rest.quoteId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/renters/policies\n          name: renters-policies\n          description: \"Renters insurance policy binding\"\n          operations:\n            - method: POST\n              name: bind-renters-policy\n              description: \"Bind a renters insurance policy from a quote\"\n\
  \              call: \"state-farm-renters.create-renters-policy\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/renters/policies/{policyNumber}\n          name: renters-policy-detail\n          description: \"Policy status and details\"\n          operations:\n            - method: GET\n              name: get-renters-policy\n              description: \"Get renters insurance policy status and coverage\"\n              call: \"state-farm-renters.get-renters-policy\"\n              with:\n                policyNumber: \"rest.policyNumber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: state-farm-embedded-insurance-mcp\n      transport: http\n      description: \"MCP server for AI-assisted State Farm embedded insurance workflows for property management platforms.\"\n      tools:\n        - name: list-renters-coverage-options\n\
  \          description: >-\n            List available State Farm renters insurance coverage options and limits\n            for a specific US state, including personal property limits, liability\n            limits, deductible choices, and optional coverages.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"state-farm-renters.list-coverage-options\"\n          with:\n            state: \"tools.state\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-renters-quote\n          description: >-\n            Create a State Farm renters insurance quote for a tenant given their\n            property address, personal information, and desired coverage selections.\n            Returns the quoted premium and coverage summary.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"state-farm-renters.create-renters-quote\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: get-renters-quote\n          description: >-\n            Retrieve the details and status of a previously created State Farm\n            renters insurance quote by its quote ID.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"state-farm-renters.get-renters-quote\"\n          with:\n            quoteId: \"tools.quoteId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: bind-renters-policy\n          description: >-\n            Convert an accepted State Farm renters insurance quote into an active\n            policy. Specify the quote ID, payment method, and payment frequency\n            to complete policy binding.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"state-farm-renters.create-renters-policy\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: get-renters-policy-status\n          description: >-\n            Get the current status, coverage details, and premium information\n            for an active State Farm renters insurance policy.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"state-farm-renters.get-renters-policy\"\n          with:\n            policyNumber: \"tools.policyNumber\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/state-farm/refs/heads/main/capabilities/embedded-insurance.yaml
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
