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
- Marketing Manager
- list all contact lists in activecampaign
- create a new contact
- list all campaigns
- list automations
- cross-channel contact engagement and personalization
- list all contact tags in activecampaign
- sales automation
- manages email campaigns, automations, and contact segmentation
- builds integrations, automation workflows, and uses the api directly
- list contact lists
- list and search contacts
- create a new contact list
- tracks deals, manages accounts, and uses crm features
- marketing automation workflows
- list campaigns
- create list
- Revenue Operations
- Growth Engineer
- list contacts
- list all tags
- marketing automation
- create contact
- contacts
- email, sms, and multi-channel marketing automation
- create a new contact in activecampaign
- crm
- contact list management
- email campaign management
- contact tag management
- manage sales pipeline, deals, accounts, and tasks
- crm, pipeline management, and revenue operations
- list all email campaigns in activecampaign
- list all marketing automations in activecampaign
- list lists
- create tag
- Account Manager
- Email Marketer
- orchestrate contact journeys, campaigns, automations, and list management
- list all automations
- activecampaign
- contact lifecycle management
- sync contact
- customer experience
- create a new contact tag in activecampaign
- email marketing
- list all contact lists
- list tags
- campaigns
- list and search activecampaign contacts by email, name, or other criteria
- sync a contact's data to activecampaign, creating or updating as needed
- Sales Representative
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
