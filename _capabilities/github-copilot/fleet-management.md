---
categories:
- platform
- developer-experience
consumed_apis:
- github-copilot-business
description: Enterprise Copilot rollout governance — seat assignment, usage telemetry, billing rollups, and policy controls for an organization running Copilot across thousands of developer teams. Provides a FinOps and platform-engineering view of Copilot fleet health so security, finance, and engineering leaders can govern scale without spreadsheet sprawl.
layout: capability
name: GitHub Copilot Fleet Management
operations:
- description: List Copilot seat assignments across an enterprise
  method: GET
  name: list-seat-assignments
  path: /enterprises/{enterprise}/copilot/billing/seats
- description: Assign Copilot seats to users in an organization
  method: POST
  name: assign-seats
  path: /orgs/{org}/copilot/billing/selected_users
- description: Revoke Copilot seats from users in an organization
  method: DELETE
  name: revoke-seats
  path: /orgs/{org}/copilot/billing/selected_users
- description: List Copilot usage metrics broken down by user for the organization
  method: GET
  name: list-usage-by-user
  path: /orgs/{org}/copilot/usage
- description: Get the Copilot billing summary and seat counts for an organization
  method: GET
  name: get-billing-summary
  path: /orgs/{org}/copilot/billing
- description: List Copilot policy settings configured for the enterprise
  method: GET
  name: list-policies
  path: /enterprises/{enterprise}/copilot/billing
personas:
- Engineering Manager
- Platform Engineer
provider_name: GitHub Copilot
provider_slug: github-copilot
search_terms:
- list copilot seat assignments across an enterprise
- assign copilot seats to users in an org
- revoke copilot seats
- list copilot usage by user
- get copilot billing summary
- list copilot policies
- enterprise copilot rollout governance
- copilot finops view
- copilot fleet management for thousands of developers
- ford-style enterprise copilot governance
- platform engineering for copilot
- security policy review for copilot
- copilot seat lifecycle
- copilot telemetry rollup
- engineering leader copilot dashboard
- Engineering Manager
- Platform Engineer
- copilot business api
- bulk seat assignment
- bulk seat revocation
- per-user copilot usage
- copilot billing api
- enterprise copilot policies
slug: fleet-management
tags:
- GitHub Copilot
- Fleet Management
- Enterprise
- FinOps
- Platform Engineering
tools:
- description: List Copilot seat assignments across the entire enterprise so platform teams can audit who has access
  hints:
    openWorld: false
    readOnly: true
  name: list-seat-assignments
- description: Assign Copilot seats to a set of users in an organization in bulk
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: assign-seats
- description: Revoke Copilot seats from a set of users in an organization in bulk
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: revoke-seats
- description: List Copilot usage metrics broken down by user to drive FinOps and adoption reporting
  hints:
    openWorld: false
    readOnly: true
  name: list-usage-by-user
- description: Get the Copilot billing summary and seat counts for an organization
  hints:
    openWorld: false
    readOnly: true
  name: get-billing-summary
- description: List Copilot policy settings configured for the enterprise so security teams can verify guardrails
  hints:
    openWorld: false
    readOnly: true
  name: list-policies
---
