---
categories: []
consumed_apis:
- backupify-saas-api
description: SaaS backup management workflow for Backupify (Datto), covering domain administration and seat licensing for Microsoft 365 and Google Workspace. Serves MSPs and IT administrators managing cloud-to-cloud backup coverage.
layout: capability
name: Backupify SaaS Backup Management
operations:
- description: List all backup customer domains
  method: GET
  name: list-domains
  path: /v1/domains
- description: List seats for a customer
  method: GET
  name: list-seats
  path: /v1/customers/{saasCustomerId}/seats
- description: Bulk license/unlicense/pause seats
  method: PUT
  name: bulk-seat-change
  path: /v1/customers/{saasCustomerId}/seats/bulk
personas: []
provider_name: Backupify
provider_slug: backupify
search_terms:
- backupify
- list backup domains
- MSP Technician
- msp
- list backup seats
- google workspace
- customer backup seats
- bulk change seat licenses
- datto
- list seats
- managed service provider technician managing backup coverage across customer accounts
- data protection
- IT Administrator
- saas backup domains
- cloud backup
- bulk seat management
- bulk seat change
- domain and seat management for backupify cloud-to-cloud backup
- enterprise it admin managing backup seat coverage for microsoft 365 or google workspace
- bulk license/unlicense/pause seats
- list all backup seats (users, mailboxes, sites, teams) for a specific customer
- license, unlicense, or pause up to 100 backup seats for a customer in a single operation
- microsoft 365
- list all backup customer domains
- saas backup
- list domains
- list all backupify saas backup domains with customer ids and subscription information
- cloud-to-cloud backup and recovery for saas platforms
- list seats for a customer
slug: saas-backup-management
source_filename: saas-backup-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Backupify SaaS Backup Management\"\n  description: >-\n    SaaS backup management workflow for Backupify (Datto), covering domain administration\n    and seat licensing for Microsoft 365 and Google Workspace. Serves MSPs and IT administrators\n    managing cloud-to-cloud backup coverage.\n  tags:\n    - Backupify\n    - Datto\n    - SaaS Backup\n    - Data Protection\n    - MSP\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      BACKUPIFY_API_KEY: BACKUPIFY_API_KEY\n      BACKUPIFY_API_SECRET: BACKUPIFY_API_SECRET\n\ncapability:\n  consumes:\n    - import: backupify-saas-api\n      location: ./shared/saas-protection-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: backupify-backup-api\n      description: \"Unified REST API for Backupify SaaS backup management.\"\n      resources:\n        - path: /v1/domains\n          name: domains\n          description:\
  \ SaaS backup domains\n          operations:\n            - method: GET\n              name: list-domains\n              description: List all backup customer domains\n              call: \"backupify-saas-api.list-domains\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/customers/{saasCustomerId}/seats\n          name: seats\n          description: Customer backup seats\n          operations:\n            - method: GET\n              name: list-seats\n              description: List seats for a customer\n              call: \"backupify-saas-api.list-seats\"\n              with:\n                saasCustomerId: \"rest.saasCustomerId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/customers/{saasCustomerId}/seats/bulk\n          name: bulk-seats\n          description: Bulk seat management\n          operations:\n            - method: PUT\n\
  \              name: bulk-seat-change\n              description: Bulk license/unlicense/pause seats\n              call: \"backupify-saas-api.bulk-seat-change\"\n              with:\n                saasCustomerId: \"rest.saasCustomerId\"\n                seats: \"rest.seats\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: backupify-backup-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Backupify SaaS backup management.\"\n      tools:\n        - name: list-backup-domains\n          description: List all Backupify SaaS backup domains with customer IDs and subscription information\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"backupify-saas-api.list-domains\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-backup-seats\n          description:\
  \ List all backup seats (users, mailboxes, sites, teams) for a specific customer\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"backupify-saas-api.list-seats\"\n          with:\n            saasCustomerId: \"tools.saasCustomerId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: bulk-change-seat-licenses\n          description: License, unlicense, or pause up to 100 backup seats for a customer in a single operation\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"backupify-saas-api.bulk-seat-change\"\n          with:\n            saasCustomerId: \"tools.saasCustomerId\"\n            seats: \"tools.seats\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/backupify/refs/heads/main/capabilities/saas-backup-management.yaml
tags:
- Backupify
- Datto
- SaaS Backup
- Data Protection
- MSP
tools:
- description: List all Backupify SaaS backup domains with customer IDs and subscription information
  hints:
    openWorld: false
    readOnly: true
  name: list-backup-domains
- description: List all backup seats (users, mailboxes, sites, teams) for a specific customer
  hints:
    openWorld: false
    readOnly: true
  name: list-backup-seats
- description: License, unlicense, or pause up to 100 backup seats for a customer in a single operation
  hints:
    idempotent: true
    readOnly: false
  name: bulk-change-seat-licenses
---
