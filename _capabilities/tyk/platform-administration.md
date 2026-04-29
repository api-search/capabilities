---
categories: []
consumed_apis:
- tyk-dashboard-admin
- tyk-mdcb
description: Platform administration workflow combining Dashboard Admin and MDCB APIs for platform administrators to manage organizations, multi-data center deployments, and system diagnostics.
layout: capability
name: Tyk Platform Administration
operations:
- description: List all organizations
  method: GET
  name: list-organizations
  path: /v1/organizations
- description: Create a new organization
  method: POST
  name: create-organization
  path: /v1/organizations
- description: List admin users
  method: GET
  name: list-admin-users
  path: /v1/admin-users
- description: List all connected data planes
  method: GET
  name: list-dataplanes
  path: /v1/dataplanes
- description: Check MDCB health
  method: GET
  name: check-mdcb-health
  path: /v1/health
personas: []
provider_name: Tyk
provider_slug: tyk
search_terms:
- update organization
- delete an organization
- get pprof diagnostic data from mdcb
- list all connected data plane nodes
- platform
- list all tyk organizations
- graphql
- mdcb
- list all connected data planes
- import system
- api management
- open source
- update an organization
- check mdcb health
- api gateway
- list all admin users
- administration
- create an admin user
- list all organizations
- import system configuration
- mdcb health
- organization management
- data plane monitoring
- get details for a specific data plane
- create organization
- admin user management
- delete organization
- export system configuration
- get dataplane
- create admin user
- list dataplanes
- create a new organization
- list organizations
- list admin users
- get diagnostics
- export system
- tyk
slug: platform-administration
source_filename: platform-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Tyk Platform Administration\"\n  description: \"Platform administration workflow combining Dashboard Admin and MDCB APIs for platform administrators to manage organizations, multi-data center deployments, and system diagnostics.\"\n  tags:\n    - Administration\n    - MDCB\n    - Platform\n    - Tyk\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      TYK_ADMIN_SECRET: TYK_ADMIN_SECRET\n      TYK_MDCB_API_KEY: TYK_MDCB_API_KEY\n\ncapability:\n  consumes:\n    - import: tyk-dashboard-admin\n      location: ./shared/dashboard-admin.yaml\n    - import: tyk-mdcb\n      location: ./shared/mdcb.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: tyk-platform-admin-api\n      description: \"Unified REST API for Tyk platform administration.\"\n      resources:\n        - path: /v1/organizations\n          name: organizations\n          description: \"Organization management\"\
  \n          operations:\n            - method: GET\n              name: list-organizations\n              description: \"List all organizations\"\n              call: \"tyk-dashboard-admin.list-organizations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-organization\n              description: \"Create a new organization\"\n              call: \"tyk-dashboard-admin.create-organization\"\n              with:\n                org: \"rest.org\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/admin-users\n          name: admin-users\n          description: \"Admin user management\"\n          operations:\n            - method: GET\n              name: list-admin-users\n              description: \"List admin users\"\n              call: \"tyk-dashboard-admin.list-admin-users\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/dataplanes\n          name: dataplanes\n          description: \"Data plane monitoring\"\n          operations:\n            - method: GET\n              name: list-dataplanes\n              description: \"List all connected data planes\"\n              call: \"tyk-mdcb.list-dataplanes\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/health\n          name: health\n          description: \"MDCB health\"\n          operations:\n            - method: GET\n              name: check-mdcb-health\n              description: \"Check MDCB health\"\n              call: \"tyk-mdcb.check-health\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: tyk-platform-admin-mcp\n      transport: http\n      description: \"MCP server for AI-assisted\
  \ Tyk platform administration.\"\n      tools:\n        - name: list-organizations\n          description: \"List all Tyk organizations\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tyk-dashboard-admin.list-organizations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-organization\n          description: \"Create a new organization\"\n          hints:\n            readOnly: false\n          call: \"tyk-dashboard-admin.create-organization\"\n          with:\n            org: \"tools.org\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-organization\n          description: \"Update an organization\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"tyk-dashboard-admin.update-organization\"\n          with:\n            orgID: \"tools.orgID\"\n            org: \"tools.org\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-organization\n          description: \"Delete an organization\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"tyk-dashboard-admin.delete-organization\"\n          with:\n            orgID: \"tools.orgID\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-admin-users\n          description: \"List all admin users\"\n          hints:\n            readOnly: true\n          call: \"tyk-dashboard-admin.list-admin-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-admin-user\n          description: \"Create an admin user\"\n          hints:\n            readOnly: false\n          call: \"tyk-dashboard-admin.create-admin-user\"\n          with:\n            user: \"tools.user\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: export-system\n          description: \"Export system configuration\"\n          hints:\n            readOnly: true\n          call: \"tyk-dashboard-admin.export-system\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: import-system\n          description: \"Import system configuration\"\n          hints:\n            readOnly: false\n          call: \"tyk-dashboard-admin.import-system\"\n          with:\n            data: \"tools.data\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-dataplanes\n          description: \"List all connected data plane nodes\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"tyk-mdcb.list-dataplanes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-dataplane\n\
  \          description: \"Get details for a specific data plane\"\n          hints:\n            readOnly: true\n          call: \"tyk-mdcb.get-dataplane\"\n          with:\n            dataplaneID: \"tools.dataplaneID\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-mdcb-health\n          description: \"Check MDCB health\"\n          hints:\n            readOnly: true\n          call: \"tyk-mdcb.check-health\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-diagnostics\n          description: \"Get pprof diagnostic data from MDCB\"\n          hints:\n            readOnly: true\n          call: \"tyk-mdcb.get-profile\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tyk/refs/heads/main/capabilities/platform-administration.yaml
tags:
- Administration
- MDCB
- Platform
- Tyk
tools:
- description: List all Tyk organizations
  hints:
    openWorld: true
    readOnly: true
  name: list-organizations
- description: Create a new organization
  hints:
    readOnly: false
  name: create-organization
- description: Update an organization
  hints:
    idempotent: true
    readOnly: false
  name: update-organization
- description: Delete an organization
  hints:
    destructive: true
    idempotent: true
  name: delete-organization
- description: List all admin users
  hints:
    readOnly: true
  name: list-admin-users
- description: Create an admin user
  hints:
    readOnly: false
  name: create-admin-user
- description: Export system configuration
  hints:
    readOnly: true
  name: export-system
- description: Import system configuration
  hints:
    readOnly: false
  name: import-system
- description: List all connected data plane nodes
  hints:
    openWorld: true
    readOnly: true
  name: list-dataplanes
- description: Get details for a specific data plane
  hints:
    readOnly: true
  name: get-dataplane
- description: Check MDCB health
  hints:
    readOnly: true
  name: check-mdcb-health
- description: Get pprof diagnostic data from MDCB
  hints:
    readOnly: true
  name: get-diagnostics
---
