---
categories: []
consumed_apis:
- appsumo
description: Workflow capability for managing AppSumo marketplace licenses within a SaaS partner application. Enables validating purchases, activating licenses, and managing customer access for products sold through the AppSumo marketplace.
layout: capability
name: AppSumo License Management
operations: []
personas: []
provider_name: AppSumo
provider_slug: appsumo
search_terms:
- validate license
- check partner profile
- appsumo
- checks the appsumo partner profile and integration configuration
- managing license activation and status for appsumo purchases
- software deals
- activate customer license
- saas partners
- marketplace
- licensing
- validate and activate appsumo licenses for newly onboarded customers
- configuring and managing the appsumo marketplace partnership
- validates and retrieves details for an appsumo license key
- saas
- developer integrating appsumo licensing into their product
- activates an appsumo license for a newly onboarded customer
- appsumo customer activating a purchased license
slug: license-management
source_filename: license-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: AppSumo License Management\n  description: >-\n    Workflow capability for managing AppSumo marketplace licenses within a SaaS partner\n    application. Enables validating purchases, activating licenses, and managing customer\n    access for products sold through the AppSumo marketplace.\n  tags:\n    - AppSumo\n    - Licensing\n    - Marketplace\n    - SaaS Partners\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      APPSUMO_API_KEY: APPSUMO_API_KEY\n\ncapability:\n  consumes:\n    - import: appsumo\n      location: ./shared/appsumo-api.yaml\n\n  exposes:\n    - type: mcp\n      port: 9090\n      namespace: license-management-mcp\n      transport: http\n      description: MCP server for AI-assisted AppSumo license management in SaaS products.\n      tools:\n        - name: validate-license\n          description: Validates and retrieves details for an AppSumo license key\n     \
  \     hints:\n            readOnly: true\n            idempotent: true\n          call: \"appsumo.get-license\"\n          with:\n            licenseKey: \"tools.licenseKey\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: activate-customer-license\n          description: Activates an AppSumo license for a newly onboarded customer\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"appsumo.activate-license\"\n          with:\n            licenseKey: \"tools.licenseKey\"\n            userId: \"tools.userId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: check-partner-profile\n          description: Checks the AppSumo partner profile and integration configuration\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"appsumo.get-profile\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/appsumo/refs/heads/main/capabilities/license-management.yaml
tags:
- AppSumo
- Licensing
- Marketplace
- SaaS Partners
tools:
- description: Validates and retrieves details for an AppSumo license key
  hints:
    idempotent: true
    readOnly: true
  name: validate-license
- description: Activates an AppSumo license for a newly onboarded customer
  hints:
    destructive: false
    readOnly: false
  name: activate-customer-license
- description: Checks the AppSumo partner profile and integration configuration
  hints:
    idempotent: true
    readOnly: true
  name: check-partner-profile
---
