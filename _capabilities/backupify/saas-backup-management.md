---
categories: []
consumed_apis: []
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
- microsoft 365
- google workspace
- IT Administrator
- cloud backup
- bulk license/unlicense/pause seats
- saas backup domains
- saas backup
- data protection
- customer backup seats
- msp
- list backup domains
- list seats
- license, unlicense, or pause up to 100 backup seats for a customer in a single operation
- backupify
- datto
- MSP Technician
- managed service provider technician managing backup coverage across customer accounts
- cloud-to-cloud backup and recovery for saas platforms
- domain and seat management for backupify cloud-to-cloud backup
- list backup seats
- bulk seat management
- list domains
- list seats for a customer
- enterprise it admin managing backup seat coverage for microsoft 365 or google workspace
- list all backupify saas backup domains with customer ids and subscription information
- list all backup customer domains
- bulk seat change
- list all backup seats (users, mailboxes, sites, teams) for a specific customer
- bulk change seat licenses
slug: saas-backup-management
source_filename: saas-backup-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Backupify SaaS Backup Management\n  description: SaaS backup management workflow for Backupify (Datto), covering domain administration and seat licensing for\n    Microsoft 365 and Google Workspace. Serves MSPs and IT administrators managing cloud-to-cloud backup coverage.\n  tags:\n  - Backupify\n  - Datto\n  - SaaS Backup\n  - Data Protection\n  - MSP\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    BACKUPIFY_API_KEY: BACKUPIFY_API_KEY\n    BACKUPIFY_API_SECRET: BACKUPIFY_API_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: backupify-saas-api\n    baseUri: https://api.datto.com\n    description: Backupify SaaS Protection API v1\n    authentication:\n      type: basic\n      username: '{{BACKUPIFY_API_KEY}}'\n      password: '{{BACKUPIFY_API_SECRET}}'\n    resources:\n    - name: domains\n      path: /v1/saas/domains\n      description: SaaS customer domain listing\n      operations:\n\
  \      - name: list-domains\n        method: GET\n        description: List all SaaS customer domains with IDs and subscription info\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: seats\n      path: /v1/saas/{saasCustomerId}/seats\n      description: Seat listing for a customer\n      operations:\n      - name: list-seats\n        method: GET\n        description: List seats for a given SaaS customer\n        inputParameters:\n        - name: saasCustomerId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bulk-seat-change\n      path: /v1/saas/{saasCustomerId}/externalSubscriptionId/bulkSeatChange\n      description: Bulk seat licensing management\n      operations:\n      - name: bulk-seat-change\n        method: PUT\n        description:\
  \ License, unlicense, or pause up to 100 seats at once\n        inputParameters:\n        - name: saasCustomerId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            seats: '{{tools.seats}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: backupify-backup-api\n    description: Unified REST API for Backupify SaaS backup management.\n    resources:\n    - path: /v1/domains\n      name: domains\n      description: SaaS backup domains\n      operations:\n      - method: GET\n        name: list-domains\n        description: List all backup customer domains\n        call: backupify-saas-api.list-domains\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customers/{saasCustomerId}/seats\n      name: seats\n      description: Customer\
  \ backup seats\n      operations:\n      - method: GET\n        name: list-seats\n        description: List seats for a customer\n        call: backupify-saas-api.list-seats\n        with:\n          saasCustomerId: rest.saasCustomerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/customers/{saasCustomerId}/seats/bulk\n      name: bulk-seats\n      description: Bulk seat management\n      operations:\n      - method: PUT\n        name: bulk-seat-change\n        description: Bulk license/unlicense/pause seats\n        call: backupify-saas-api.bulk-seat-change\n        with:\n          saasCustomerId: rest.saasCustomerId\n          seats: rest.seats\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: backupify-backup-mcp\n    transport: http\n    description: MCP server for AI-assisted Backupify SaaS backup management.\n    tools:\n    - name: list-backup-domains\n      description:\
  \ List all Backupify SaaS backup domains with customer IDs and subscription information\n      hints:\n        readOnly: true\n        openWorld: false\n      call: backupify-saas-api.list-domains\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-backup-seats\n      description: List all backup seats (users, mailboxes, sites, teams) for a specific customer\n      hints:\n        readOnly: true\n        openWorld: false\n      call: backupify-saas-api.list-seats\n      with:\n        saasCustomerId: tools.saasCustomerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: bulk-change-seat-licenses\n      description: License, unlicense, or pause up to 100 backup seats for a customer in a single operation\n      hints:\n        readOnly: false\n        idempotent: true\n      call: backupify-saas-api.bulk-seat-change\n      with:\n        saasCustomerId: tools.saasCustomerId\n        seats: tools.seats\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n"
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
