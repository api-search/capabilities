---
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
- email campaign management
- crm, pipeline management, and revenue operations
- sync a contact's data to activecampaign, creating or updating as needed
- sync contact
- list contacts
- list automations
- activecampaign
- Revenue Operations
- create a new contact tag in activecampaign
- Sales Representative
- list contact lists
- Account Manager
- marketing automation workflows
- email, sms, and multi-channel marketing automation
- list all contact lists
- list all campaigns
- list lists
- list all contact tags in activecampaign
- orchestrate contact journeys, campaigns, automations, and list management
- list all email campaigns in activecampaign
- create tag
- customer experience
- list campaigns
- list all marketing automations in activecampaign
- manage sales pipeline, deals, accounts, and tasks
- create a new contact in activecampaign
- marketing automation
- campaigns
- Marketing Manager
- manages email campaigns, automations, and contact segmentation
- contact lifecycle management
- list and search activecampaign contacts by email, name, or other criteria
- Email Marketer
- contact list management
- builds integrations, automation workflows, and uses the api directly
- list all contact lists in activecampaign
- create a new contact
- list and search contacts
- list all tags
- create contact
- create list
- Growth Engineer
- contacts
- list all automations
- create a new contact list
- contact tag management
- tracks deals, manages accounts, and uses crm features
- cross-channel contact engagement and personalization
- sales automation
- list tags
- crm
- email marketing
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
