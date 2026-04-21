---
consumed_apis:
- activecampaign-v3
description: Workflow capability for CRM and sales pipeline management including deals, accounts, tasks, and pipeline stages. Used by sales teams and revenue operations to track and advance deals.
layout: capability
name: ActiveCampaign CRM and Sales
operations:
- description: List all deals
  method: GET
  name: list-deals
  path: /v1/deals
- description: Create a new deal
  method: POST
  name: create-deal
  path: /v1/deals
- description: List all accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: Create a new account
  method: POST
  name: create-account
  path: /v1/accounts
personas: []
provider_name: ActiveCampaign
provider_slug: activecampaign
search_terms:
- Sales Representative
- get deal
- deals
- create account
- crm
- list deals
- create a new account
- manages email campaigns, automations, and contact segmentation
- activecampaign
- company account management
- Growth Engineer
- create a new company account in activecampaign crm
- Email Marketer
- sales deal management
- Marketing Manager
- sales
- email marketing
- retrieve a specific deal by id
- list all sales deals in activecampaign crm
- list accounts
- list all accounts
- manage sales pipeline, deals, accounts, and tasks
- create deal
- crm, pipeline management, and revenue operations
- create a new sales deal in activecampaign crm
- create a new deal
- sales automation
- accounts
- list all company accounts in activecampaign crm
- cross-channel contact engagement and personalization
- orchestrate contact journeys, campaigns, automations, and list management
- Revenue Operations
- builds integrations, automation workflows, and uses the api directly
- customer experience
- email, sms, and multi-channel marketing automation
- marketing automation
- tracks deals, manages accounts, and uses crm features
- Account Manager
- list all deals
slug: crm-sales
tags:
- ActiveCampaign
- CRM
- Sales
- Deals
- Accounts
tools:
- description: List all sales deals in ActiveCampaign CRM
  hints:
    openWorld: true
    readOnly: true
  name: list-deals
- description: Create a new sales deal in ActiveCampaign CRM
  hints:
    destructive: false
    readOnly: false
  name: create-deal
- description: Retrieve a specific deal by ID
  hints:
    openWorld: false
    readOnly: true
  name: get-deal
- description: List all company accounts in ActiveCampaign CRM
  hints:
    openWorld: true
    readOnly: true
  name: list-accounts
- description: Create a new company account in ActiveCampaign CRM
  hints:
    destructive: false
    readOnly: false
  name: create-account
---
