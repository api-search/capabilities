---
categories:
- customer-engagement
consumed_apis:
- activecampaign-v3
description: Unified workflow capability for marketing automation, contact management, campaign execution, and list segmentation. Used by marketing teams and growth engineers to orchestrate multi-channel customer journeys.
layout: capability
name: ActiveCampaign Marketing Automation
operations:
- description: List and search contacts
  method: GET
  name: list-contacts
  path: /v1/contacts
- description: Create a new contact
  method: POST
  name: create-contact
  path: /v1/contacts
- description: List all campaigns
  method: GET
  name: list-campaigns
  path: /v1/campaigns
- description: List all automations
  method: GET
  name: list-automations
  path: /v1/automations
- description: List all contact lists
  method: GET
  name: list-lists
  path: /v1/lists
- description: Create a new contact list
  method: POST
  name: create-list
  path: /v1/lists
- description: List all tags
  method: GET
  name: list-tags
  path: /v1/tags
personas: []
provider_name: ActiveCampaign
provider_slug: activecampaign
search_terms:
- marketing automation workflows
- list all marketing automations in activecampaign
- list all email campaigns in activecampaign
- email, sms, and multi-channel marketing automation
- builds integrations, automation workflows, and uses the api directly
- list all contact lists
- orchestrate contact journeys, campaigns, automations, and list management
- manages email campaigns, automations, and contact segmentation
- list and search activecampaign contacts by email, name, or other criteria
- list all campaigns
- Sales Representative
- campaigns
- create list
- email campaign management
- list and search contacts
- email marketing
- Account Manager
- contacts
- Email Marketer
- create a new contact in activecampaign
- activecampaign
- tracks deals, manages accounts, and uses crm features
- marketing automation
- create tag
- sync contact
- customer experience
- list all tags
- list lists
- list automations
- list tags
- list contact lists
- Revenue Operations
- Marketing Manager
- contact lifecycle management
- list campaigns
- contact list management
- create a new contact list
- cross-channel contact engagement and personalization
- contact tag management
- list all automations
- sync a contact's data to activecampaign, creating or updating as needed
- create a new contact tag in activecampaign
- create a new contact
- manage sales pipeline, deals, accounts, and tasks
- create contact
- Growth Engineer
- list all contact lists in activecampaign
- sales automation
- crm
- crm, pipeline management, and revenue operations
- list contacts
- list all contact tags in activecampaign
slug: marketing-automation
tags:
- ActiveCampaign
- Marketing Automation
- Email Marketing
- Contacts
- Campaigns
tools:
- description: List and search ActiveCampaign contacts by email, name, or other criteria
  hints:
    openWorld: true
    readOnly: true
  name: list-contacts
- description: Create a new contact in ActiveCampaign
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-contact
- description: Sync a contact's data to ActiveCampaign, creating or updating as needed
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: sync-contact
- description: List all email campaigns in ActiveCampaign
  hints:
    openWorld: true
    readOnly: true
  name: list-campaigns
- description: List all marketing automations in ActiveCampaign
  hints:
    openWorld: true
    readOnly: true
  name: list-automations
- description: List all contact lists in ActiveCampaign
  hints:
    openWorld: true
    readOnly: true
  name: list-contact-lists
- description: List all contact tags in ActiveCampaign
  hints:
    openWorld: true
    readOnly: true
  name: list-tags
- description: Create a new contact tag in ActiveCampaign
  hints:
    destructive: false
    readOnly: false
  name: create-tag
---
