---
consumed_apis:
- hunter
description: Unified workflow for sales prospecting including email discovery, verification, enrichment, lead management, and outreach campaigns. Used by sales development representatives and marketing teams.
layout: capability
name: Hunter Sales Prospecting
operations:
- description: Search for emails by domain.
  method: GET
  name: domain-search
  path: /v1/domain-search
- description: Find email for a person.
  method: GET
  name: find-email
  path: /v1/email-finder
- description: Verify email deliverability.
  method: GET
  name: verify-email
  path: /v1/email-verifier
- description: List all leads.
  method: GET
  name: list-leads
  path: /v1/leads
- description: Create a lead.
  method: POST
  name: create-lead
  path: /v1/leads
- description: Get lead details.
  method: GET
  name: get-lead
  path: /v1/leads/{id}
- description: Update a lead.
  method: PUT
  name: update-lead
  path: /v1/leads/{id}
- description: Delete a lead.
  method: DELETE
  name: delete-lead
  path: /v1/leads/{id}
- description: Enrich personal data from email.
  method: GET
  name: enrich-email
  path: /v1/enrichment/email
- description: Enrich company data from domain.
  method: GET
  name: enrich-company
  path: /v1/enrichment/company
- description: Discover companies.
  method: GET
  name: discover-companies
  path: /v1/discover
personas: []
provider_name: Hunter
provider_slug: hunter
search_terms:
- hunter
- update a lead.
- create lead
- contact discovery
- list all email campaigns.
- delete a lead.
- count emails for a domain.
- email outreach
- search for email addresses by domain.
- update lead
- delete lead
- delete a lead list.
- delete leads list
- get combined person and company data.
- email
- sales intelligence
- get lead list details.
- verify email
- discover companies matching criteria.
- list campaigns
- find email for a person.
- list all leads.
- search emails by domain.
- discover companies.
- get lead
- update a lead list.
- search for emails by domain.
- individual lead management.
- company enrichment.
- enrich company data from domain.
- prospecting
- lead generation
- enrich email
- create a new lead list.
- enrich combined
- domain search
- find email addresses.
- count emails
- get leads list
- list leads
- update leads list
- enrich company
- discover companies
- email verification
- verify email deliverability.
- create a lead.
- get lead details.
- verify emails.
- enrich personal data from email.
- create a new lead.
- sales prospecting
- get account
- get account information and usage.
- list all lead lists.
- email enrichment.
- find email
- list leads lists
- create leads list
- find the most likely email for a person at a company.
- enrich personal data from email address.
- company discovery.
- lead management.
slug: sales-prospecting
tags:
- Hunter
- Sales Prospecting
- Lead Generation
- Email Outreach
tools:
- description: Search for email addresses by domain.
  hints:
    openWorld: true
    readOnly: true
  name: domain-search
- description: Find the most likely email for a person at a company.
  hints:
    readOnly: true
  name: find-email
- description: Verify email deliverability.
  hints:
    readOnly: true
  name: verify-email
- description: Count emails for a domain.
  hints:
    readOnly: true
  name: count-emails
- description: Get account information and usage.
  hints:
    readOnly: true
  name: get-account
- description: List all leads.
  hints:
    openWorld: true
    readOnly: true
  name: list-leads
- description: Create a new lead.
  hints:
    readOnly: false
  name: create-lead
- description: Get lead details.
  hints:
    readOnly: true
  name: get-lead
- description: Update a lead.
  hints:
    idempotent: true
    readOnly: false
  name: update-lead
- description: Delete a lead.
  hints:
    destructive: true
    idempotent: true
  name: delete-lead
- description: List all lead lists.
  hints:
    readOnly: true
  name: list-leads-lists
- description: Create a new lead list.
  hints:
    readOnly: false
  name: create-leads-list
- description: Get lead list details.
  hints:
    readOnly: true
  name: get-leads-list
- description: Update a lead list.
  hints:
    idempotent: true
    readOnly: false
  name: update-leads-list
- description: Delete a lead list.
  hints:
    destructive: true
    idempotent: true
  name: delete-leads-list
- description: Discover companies matching criteria.
  hints:
    openWorld: true
    readOnly: true
  name: discover-companies
- description: Enrich personal data from email address.
  hints:
    readOnly: true
  name: enrich-email
- description: Enrich company data from domain.
  hints:
    readOnly: true
  name: enrich-company
- description: Get combined person and company data.
  hints:
    readOnly: true
  name: enrich-combined
- description: List all email campaigns.
  hints:
    readOnly: true
  name: list-campaigns
---
