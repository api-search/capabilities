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
- microsoft 365
- customer backup seats
- IT Administrator
- list domains
- saas backup
- saas backup domains
- datto
- list seats
- data protection
- backupify
- cloud-to-cloud backup and recovery for saas platforms
- list seats for a customer
- list all backup seats (users, mailboxes, sites, teams) for a specific customer
- domain and seat management for backupify cloud-to-cloud backup
- MSP Technician
- cloud backup
- msp
- list backup domains
- managed service provider technician managing backup coverage across customer accounts
- google workspace
- list all backup customer domains
- bulk seat management
- list all backupify saas backup domains with customer ids and subscription information
- bulk change seat licenses
- bulk seat change
- bulk license/unlicense/pause seats
- list backup seats
- license, unlicense, or pause up to 100 backup seats for a customer in a single operation
- enterprise it admin managing backup seat coverage for microsoft 365 or google workspace
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
