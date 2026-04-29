---
categories:
- messaging
consumed_apis:
- marketing-emal-api
- analytics-events-api
description: Marketing automation workflow combining email campaigns and analytics events.
layout: capability
name: HubSpot Marketing Automation
operations: []
personas: []
provider_name: HubSpot
provider_slug: hubspot
search_terms:
- hubspot create an smtp token
- resetsmtptokenpassword
- analytics
- geteventinstances
- marketing automation
- hubspot retrieve available event types
- hubspot list all smtp tokens
- listsmtptokens
- hubspot reset smtp token password
- marketing
- customer service
- geteventtypes
- sales
- content
- hubspot delete an smtp token
- deletesmtptoken
- hubspot get an smtp token by id
- operations
- crm
- hubspot send a transactional email
- hubspot
- email marketing
- commerce
- createsmtptoken
- sendtransactionalemail
- email
- getsmtptokenbyid
- hubspot retrieve event instances
slug: marketing-automation
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: HubSpot Marketing Automation\n  description: Marketing automation workflow combining email campaigns and analytics events.\n  tags:\n  - HubSpot\n  - Marketing\n  - Email\n  - Analytics\n  created: '2026-04-18'\n  modified: '2026-04-18'\nbinds:\n- namespace: env\n  keys:\n    HUBSPOT_ACCESS_TOKEN: HUBSPOT_ACCESS_TOKEN\ncapability:\n  consumes:\n  - import: marketing-emal-api\n    location: ./shared/marketing-emal-api.yaml\n  - import: analytics-events-api\n    location: ./shared/analytics-events-api.yaml\n  exposes:\n  - type: mcp\n    port: 9092\n    namespace: marketing-automation-mcp\n    transport: http\n    description: MCP server for AI-assisted HubSpot Marketing Automation.\n    tools:\n    - name: listsmtptokens\n      description: HubSpot List All SMTP Tokens\n      hints:\n        readOnly: true\n      call: marketing-emal-api.listsmtptokens\n    - name: createsmtptoken\n      description: HubSpot Create an SMTP Token\n     \
  \ hints:\n        readOnly: false\n      call: marketing-emal-api.createsmtptoken\n    - name: getsmtptokenbyid\n      description: HubSpot Get an SMTP Token by ID\n      hints:\n        readOnly: true\n      call: marketing-emal-api.getsmtptokenbyid\n    - name: deletesmtptoken\n      description: HubSpot Delete an SMTP Token\n      hints:\n        destructive: true\n      call: marketing-emal-api.deletesmtptoken\n    - name: resetsmtptokenpassword\n      description: HubSpot Reset SMTP Token Password\n      hints:\n        readOnly: false\n      call: marketing-emal-api.resetsmtptokenpassword\n    - name: sendtransactionalemail\n      description: HubSpot Send a Transactional Email\n      hints:\n        readOnly: false\n      call: marketing-emal-api.sendtransactionalemail\n    - name: geteventinstances\n      description: HubSpot Retrieve Event Instances\n      hints:\n        readOnly: true\n      call: analytics-events-api.geteventinstances\n    - name: geteventtypes\n      description:\
  \ HubSpot Retrieve Available Event Types\n      hints:\n        readOnly: true\n      call: analytics-events-api.geteventtypes\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hubspot/refs/heads/main/capabilities/marketing-automation.yaml
tags:
- HubSpot
- Marketing
- Email
- Analytics
tools:
- description: HubSpot List All SMTP Tokens
  hints:
    readOnly: true
  name: listsmtptokens
- description: HubSpot Create an SMTP Token
  hints:
    readOnly: false
  name: createsmtptoken
- description: HubSpot Get an SMTP Token by ID
  hints:
    readOnly: true
  name: getsmtptokenbyid
- description: HubSpot Delete an SMTP Token
  hints:
    destructive: true
  name: deletesmtptoken
- description: HubSpot Reset SMTP Token Password
  hints:
    readOnly: false
  name: resetsmtptokenpassword
- description: HubSpot Send a Transactional Email
  hints:
    readOnly: false
  name: sendtransactionalemail
- description: HubSpot Retrieve Event Instances
  hints:
    readOnly: true
  name: geteventinstances
- description: HubSpot Retrieve Available Event Types
  hints:
    readOnly: true
  name: geteventtypes
---
