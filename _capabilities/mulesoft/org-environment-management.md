---
categories: []
consumed_apis: []
description: Discover and manage Anypoint Platform organizations and environments
layout: capability
name: Org Environment Management
operations:
- description: ''
  method: GET
  name: ''
  path: /organizations
- description: ''
  method: GET
  name: ''
  path: /organizations/{orgId}
- description: ''
  method: GET
  name: ''
  path: /organizations/{orgId}/environments
- description: ''
  method: GET
  name: ''
  path: /organizations/{orgId}/environments/{envId}
personas: []
provider_name: MuleSoft
provider_slug: mulesoft
search_terms:
- list environments within an organization
- get details for a specific organization
- list all environments (production, sandbox, design) within an anypoint organization
- api gateway
- create a new environment within a mulesoft anypoint organization
- api management
- list all accessible anypoint platform organizations
- get details for a specific anypoint environment including type and client id
- get details for a specific environment
- list all mulesoft anypoint organizations accessible to the authenticated user
- create environment
- enterprise
- get details for a specific anypoint organization including entitlements and settings
- integration
- get organization
- get environment
- list organizations
- list environments
slug: org-environment-management
source_filename: org-environment-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  name: MuleSoft Organization and Environment Management\n  description: Discover and manage Anypoint Platform organizations and environments\n  version: 1.0.0\n\nimport:\n  - name: accounts\n    location: shared/accounts.yaml\n\ncapability:\n  exposes:\n    - type: rest\n      port: 8112\n      namespace: mulesoft-org-env-rest\n      resources:\n        - path: \"/organizations\"\n          name: organizations\n          label: \"List Organizations\"\n          description: \"List all accessible Anypoint Platform organizations\"\n          operations:\n            - method: GET\n              call: accounts.listOrganizations\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n                  items:\n                    type: object\n\n        - path: \"/organizations/{orgId}\"\n          name: organization\n          label: \"Get Organization\"\n          description: \"Get details for a\
  \ specific organization\"\n          operations:\n            - method: GET\n              call: accounts.getOrganization\n              inputParameters:\n                - name: orgId\n                  in: path\n                  type: string\n                  required: true\n                  description: \"Organization ID\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: \"/organizations/{orgId}/environments\"\n          name: environments\n          label: \"List Environments\"\n          description: \"List environments within an organization\"\n          operations:\n            - method: GET\n              call: accounts.listEnvironments\n              inputParameters:\n                - name: orgId\n                  in: path\n                  type: string\n                  required: true\n                  description: \"Organization ID\"\n              outputParameters:\n                - type: array\n\
  \                  mapping: \"$.\"\n                  items:\n                    type: object\n\n        - path: \"/organizations/{orgId}/environments/{envId}\"\n          name: environment\n          label: \"Get Environment\"\n          description: \"Get details for a specific environment\"\n          operations:\n            - method: GET\n              call: accounts.getEnvironment\n              inputParameters:\n                - name: orgId\n                  in: path\n                  type: string\n                  required: true\n                  description: \"Organization ID\"\n                - name: envId\n                  in: path\n                  type: string\n                  required: true\n                  description: \"Environment ID\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      address: \"0.0.0.0\"\n      port: 9112\n      namespace: mulesoft-org-env\n      description: \"MuleSoft\
  \ Anypoint organization and environment management — discover orgs, list environments, inspect configuration\"\n      tools:\n        - name: list-organizations\n          description: \"List all MuleSoft Anypoint organizations accessible to the authenticated user\"\n          hints:\n            readOnly: true\n          call: accounts.listOrganizations\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n              items:\n                type: object\n\n        - name: get-organization\n          description: \"Get details for a specific Anypoint organization including entitlements and settings\"\n          hints:\n            readOnly: true\n          call: accounts.getOrganization\n          inputParameters:\n            - name: orgId\n              type: string\n              required: true\n              description: \"Organization ID\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name:\
  \ list-environments\n          description: \"List all environments (production, sandbox, design) within an Anypoint organization\"\n          hints:\n            readOnly: true\n          call: accounts.listEnvironments\n          inputParameters:\n            - name: orgId\n              type: string\n              required: true\n              description: \"Organization ID\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n              items:\n                type: object\n\n        - name: get-environment\n          description: \"Get details for a specific Anypoint environment including type and client ID\"\n          hints:\n            readOnly: true\n          call: accounts.getEnvironment\n          inputParameters:\n            - name: orgId\n              type: string\n              required: true\n              description: \"Organization ID\"\n            - name: envId\n              type: string\n              required: true\n    \
  \          description: \"Environment ID\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-environment\n          description: \"Create a new environment within a MuleSoft Anypoint organization\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: accounts.createEnvironment\n          inputParameters:\n            - name: orgId\n              type: string\n              required: true\n              description: \"Organization ID\"\n            - name: body\n              type: object\n              required: true\n              description: \"Environment definition including name and type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mulesoft/refs/heads/main/capabilities/org-environment-management.yaml
tags: []
tools:
- description: List all MuleSoft Anypoint organizations accessible to the authenticated user
  hints:
    readOnly: true
  name: list-organizations
- description: Get details for a specific Anypoint organization including entitlements and settings
  hints:
    readOnly: true
  name: get-organization
- description: List all environments (production, sandbox, design) within an Anypoint organization
  hints:
    readOnly: true
  name: list-environments
- description: Get details for a specific Anypoint environment including type and client ID
  hints:
    readOnly: true
  name: get-environment
- description: Create a new environment within a MuleSoft Anypoint organization
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-environment
---
