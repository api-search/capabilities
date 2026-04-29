---
api_specs:
- filename: power-platform-api-openapi.json
  format: json
  label: power-platform-api
  slug: power-platform-api
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/power-platform/refs/heads/main/openapi/power-platform-api-openapi.json
categories: []
consumed_apis:
- power-platform-api
description: Unified workflow for Power Platform administrators to manage environments, deploy applications, monitor flow runs, and govern licensing across the tenant.
layout: capability
name: Microsoft Power Platform Administration
operations:
- description: List all environments
  method: GET
  name: list-environments
  path: /v1/environments
- description: Get environment details
  method: GET
  name: get-environment
  path: /v1/environments/{environmentId}
- description: Delete an environment
  method: DELETE
  name: delete-environment
  path: /v1/environments/{environmentId}
- description: List application packages for an environment
  method: GET
  name: list-packages
  path: /v1/environments/{environmentId}/packages
- description: List flow runs for an environment
  method: GET
  name: list-flow-runs
  path: /v1/environments/{environmentId}/flow-runs
- description: List all billing policies
  method: GET
  name: list-billing-policies
  path: /v1/billing-policies
- description: Create a billing policy
  method: POST
  name: create-billing-policy
  path: /v1/billing-policies
personas: []
provider_name: Microsoft Power Platform APIs
provider_slug: power-platform
search_terms:
- list application packages
- delete an environment
- microsoft
- list flow runs for an environment
- billing policy management
- list application packages available in an environment
- power pages
- list flow runs
- get environment details
- list all billing policies
- create a billing policy
- create a new billing policy linking azure subscription
- check the installation status of an application package
- no-code
- list packages
- list power automate flow runs by workflow id
- delete a power platform environment
- get billing policy
- get details for a specific billing policy
- copilot studio
- flow run monitoring
- list all environments
- application package management
- update an existing billing policy
- list application packages for an environment
- list tenant packages
- single environment operations
- administration
- install an application package in an environment
- install application package
- create billing policy
- update billing policy
- low-code
- get environment
- list all power platform environments in the tenant
- delete environment
- environment management
- list installable application packages for the tenant
- list billing policies
- list billing policies for the tenant
- governance
- dataverse
- power platform
- list environments
- get details for a specific power platform environment
- business applications
- get install status
slug: platform-administration
source_filename: platform-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Microsoft Power Platform Administration\"\n  description: \"Unified workflow for Power Platform administrators to manage environments, deploy applications, monitor flow runs, and govern licensing across the tenant.\"\n  tags:\n    - Microsoft\n    - Power Platform\n    - Administration\n    - Governance\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      POWER_PLATFORM_BEARER_TOKEN: POWER_PLATFORM_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: power-platform-api\n      location: ./shared/power-platform-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: power-platform-admin-api\n      description: \"Unified REST API for Power Platform administration.\"\n      resources:\n        - path: /v1/environments\n          name: environments\n          description: \"Environment management\"\n          operations:\n            - method: GET\n          \
  \    name: list-environments\n              description: \"List all environments\"\n              call: \"power-platform-api.list-environments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/environments/{environmentId}\n          name: environment-detail\n          description: \"Single environment operations\"\n          operations:\n            - method: GET\n              name: get-environment\n              description: \"Get environment details\"\n              call: \"power-platform-api.get-environment\"\n              with:\n                environmentId: \"rest.environmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-environment\n              description: \"Delete an environment\"\n              call: \"power-platform-api.delete-environment\"\n              with:\n                environmentId:\
  \ \"rest.environmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/environments/{environmentId}/packages\n          name: application-packages\n          description: \"Application package management\"\n          operations:\n            - method: GET\n              name: list-packages\n              description: \"List application packages for an environment\"\n              call: \"power-platform-api.get-environment-application-packages\"\n              with:\n                environmentId: \"rest.environmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/environments/{environmentId}/flow-runs\n          name: flow-runs\n          description: \"Flow run monitoring\"\n          operations:\n            - method: GET\n              name: list-flow-runs\n              description: \"List flow runs for an environment\"\n           \
  \   call: \"power-platform-api.list-flow-runs\"\n              with:\n                environmentId: \"rest.environmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/billing-policies\n          name: billing-policies\n          description: \"Billing policy management\"\n          operations:\n            - method: GET\n              name: list-billing-policies\n              description: \"List all billing policies\"\n              call: \"power-platform-api.list-billing-policies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-billing-policy\n              description: \"Create a billing policy\"\n              call: \"power-platform-api.create-billing-policy\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n \
  \     namespace: power-platform-admin-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Power Platform administration.\"\n      tools:\n        - name: list-environments\n          description: \"List all Power Platform environments in the tenant\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"power-platform-api.list-environments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-environment\n          description: \"Get details for a specific Power Platform environment\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"power-platform-api.get-environment\"\n          with:\n            environmentId: \"tools.environmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-environment\n          description: \"Delete a Power Platform environment\"\n\
  \          hints:\n            destructive: true\n            idempotent: true\n          call: \"power-platform-api.delete-environment\"\n          with:\n            environmentId: \"tools.environmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-application-packages\n          description: \"List application packages available in an environment\"\n          hints:\n            readOnly: true\n          call: \"power-platform-api.get-environment-application-packages\"\n          with:\n            environmentId: \"tools.environmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: install-application-package\n          description: \"Install an application package in an environment\"\n          hints:\n            readOnly: false\n          call: \"power-platform-api.install-application-package\"\n          with:\n            environmentId: \"tools.environmentId\"\
  \n            applicationPackageId: \"tools.applicationPackageId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-install-status\n          description: \"Check the installation status of an application package\"\n          hints:\n            readOnly: true\n          call: \"power-platform-api.get-install-status\"\n          with:\n            environmentId: \"tools.environmentId\"\n            operationId: \"tools.operationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-tenant-packages\n          description: \"List installable application packages for the tenant\"\n          hints:\n            readOnly: true\n          call: \"power-platform-api.get-tenant-application-packages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-flow-runs\n          description: \"List Power Automate flow runs by\
  \ workflow ID\"\n          hints:\n            readOnly: true\n          call: \"power-platform-api.list-flow-runs\"\n          with:\n            environmentId: \"tools.environmentId\"\n            workflowId: \"tools.workflowId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-billing-policies\n          description: \"List billing policies for the tenant\"\n          hints:\n            readOnly: true\n          call: \"power-platform-api.list-billing-policies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-billing-policy\n          description: \"Create a new billing policy linking Azure subscription\"\n          hints:\n            readOnly: false\n          call: \"power-platform-api.create-billing-policy\"\n          with:\n            name: \"tools.name\"\n            billingInstrument: \"tools.billingInstrument\"\n          outputParameters:\n       \
  \     - type: object\n              mapping: \"$.\"\n        - name: get-billing-policy\n          description: \"Get details for a specific billing policy\"\n          hints:\n            readOnly: true\n          call: \"power-platform-api.get-billing-policy\"\n          with:\n            billingPolicyId: \"tools.billingPolicyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-billing-policy\n          description: \"Update an existing billing policy\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"power-platform-api.update-billing-policy\"\n          with:\n            billingPolicyId: \"tools.billingPolicyId\"\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/power-platform/refs/heads/main/capabilities/platform-administration.yaml
tags:
- Microsoft
- Power Platform
- Administration
- Governance
tools:
- description: List all Power Platform environments in the tenant
  hints:
    openWorld: true
    readOnly: true
  name: list-environments
- description: Get details for a specific Power Platform environment
  hints:
    idempotent: true
    readOnly: true
  name: get-environment
- description: Delete a Power Platform environment
  hints:
    destructive: true
    idempotent: true
  name: delete-environment
- description: List application packages available in an environment
  hints:
    readOnly: true
  name: list-application-packages
- description: Install an application package in an environment
  hints:
    readOnly: false
  name: install-application-package
- description: Check the installation status of an application package
  hints:
    readOnly: true
  name: get-install-status
- description: List installable application packages for the tenant
  hints:
    readOnly: true
  name: list-tenant-packages
- description: List Power Automate flow runs by workflow ID
  hints:
    readOnly: true
  name: list-flow-runs
- description: List billing policies for the tenant
  hints:
    readOnly: true
  name: list-billing-policies
- description: Create a new billing policy linking Azure subscription
  hints:
    readOnly: false
  name: create-billing-policy
- description: Get details for a specific billing policy
  hints:
    readOnly: true
  name: get-billing-policy
- description: Update an existing billing policy
  hints:
    idempotent: true
    readOnly: false
  name: update-billing-policy
---
