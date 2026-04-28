---
categories: []
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
- email
- get leads list
- hunter
- delete a lead.
- email verification
- update a lead.
- company enrichment.
- get account
- discover companies.
- count emails
- verify emails.
- delete leads list
- get lead list details.
- update lead
- enrich company
- sales prospecting
- delete lead
- enrich company data from domain.
- enrich email
- search for emails by domain.
- get lead
- sales intelligence
- lead management.
- discover companies
- delete a lead list.
- create a lead.
- list leads
- find email addresses.
- email enrichment.
- create lead
- count emails for a domain.
- enrich personal data from email.
- domain search
- company discovery.
- list leads lists
- prospecting
- list campaigns
- discover companies matching criteria.
- list all email campaigns.
- find email for a person.
- search emails by domain.
- list all lead lists.
- get combined person and company data.
- get account information and usage.
- email outreach
- get lead details.
- individual lead management.
- update leads list
- create a new lead list.
- verify email
- find the most likely email for a person at a company.
- enrich personal data from email address.
- contact discovery
- update a lead list.
- create leads list
- lead generation
- list all leads.
- create a new lead.
- search for email addresses by domain.
- find email
- enrich combined
- verify email deliverability.
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
