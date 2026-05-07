---
categories: []
consumed_apis: []
description: Workflow capability for managing AppSumo marketplace licenses within a SaaS partner application. Enables validating purchases, activating licenses, and managing customer access for products sold through the AppSumo marketplace.
layout: capability
name: AppSumo License Management
operations: []
personas: []
provider_name: AppSumo
provider_slug: appsumo
search_terms:
- validate license
- configuring and managing the appsumo marketplace partnership
- appsumo
- saas
- marketplace
- validates and retrieves details for an appsumo license key
- checks the appsumo partner profile and integration configuration
- developer integrating appsumo licensing into their product
- validate and activate appsumo licenses for newly onboarded customers
- appsumo customer activating a purchased license
- activates an appsumo license for a newly onboarded customer
- licensing
- software deals
- check partner profile
- managing license activation and status for appsumo purchases
- activate customer license
- saas partners
slug: license-management
source_filename: license-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AppSumo License Management\n  description: Workflow capability for managing AppSumo marketplace licenses within a SaaS partner application. Enables validating\n    purchases, activating licenses, and managing customer access for products sold through the AppSumo marketplace.\n  tags:\n  - AppSumo\n  - Licensing\n  - Marketplace\n  - SaaS Partners\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    APPSUMO_API_KEY: APPSUMO_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: appsumo\n    baseUri: https://appsumo.com/api/v2\n    description: AppSumo Licensing API\n    authentication:\n      type: apikey\n      header: X-AppSumo-API-Key\n      key: '{{APPSUMO_API_KEY}}'\n    resources:\n    - name: licenses\n      path: /licenses/{licenseKey}\n      description: License management\n      operations:\n      - name: get-license\n        method: GET\n        description: Returns license details\
  \ for a key\n        inputParameters:\n        - name: licenseKey\n          in: path\n          type: string\n          required: true\n          description: License key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: activate-license\n        method: POST\n        description: Activates a license key\n        inputParameters:\n        - name: licenseKey\n          in: path\n          type: string\n          required: true\n          description: License key to activate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            userId: '{{tools.userId}}'\n    - name: profile\n      path: /profile\n      description: Partner profile\n      operations:\n      - name: get-profile\n        method: GET\n        description: Returns partner profile information\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: mcp\n    port: 9090\n    namespace: license-management-mcp\n    transport: http\n    description: MCP server for AI-assisted AppSumo license management in SaaS products.\n    tools:\n    - name: validate-license\n      description: Validates and retrieves details for an AppSumo license key\n      hints:\n        readOnly: true\n        idempotent: true\n      call: appsumo.get-license\n      with:\n        licenseKey: tools.licenseKey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: activate-customer-license\n      description: Activates an AppSumo license for a newly onboarded customer\n      hints:\n        readOnly: false\n        destructive: false\n      call: appsumo.activate-license\n      with:\n        licenseKey: tools.licenseKey\n        userId: tools.userId\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: check-partner-profile\n      description: Checks the AppSumo partner profile and integration configuration\n      hints:\n        readOnly: true\n        idempotent: true\n      call: appsumo.get-profile\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
