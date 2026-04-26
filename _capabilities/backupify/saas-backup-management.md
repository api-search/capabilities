---
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
- list domains
- bulk seat change
- list seats
- microsoft 365
- customer backup seats
- list all backup seats (users, mailboxes, sites, teams) for a specific customer
- managed service provider technician managing backup coverage across customer accounts
- IT Administrator
- saas backup domains
- enterprise it admin managing backup seat coverage for microsoft 365 or google workspace
- msp
- list seats for a customer
- google workspace
- data protection
- list backup domains
- cloud backup
- MSP Technician
- bulk license/unlicense/pause seats
- domain and seat management for backupify cloud-to-cloud backup
- backupify
- bulk change seat licenses
- saas backup
- license, unlicense, or pause up to 100 backup seats for a customer in a single operation
- cloud-to-cloud backup and recovery for saas platforms
- list all backup customer domains
- list all backupify saas backup domains with customer ids and subscription information
- datto
- list backup seats
- bulk seat management
slug: saas-backup-management
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
