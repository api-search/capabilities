---
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
- getsmtptokenbyid
- hubspot retrieve available event types
- email
- hubspot create an smtp token
- crm
- hubspot send a transactional email
- marketing automation
- createsmtptoken
- operations
- customer service
- sendtransactionalemail
- hubspot reset smtp token password
- hubspot list all smtp tokens
- resetsmtptokenpassword
- sales
- commerce
- hubspot get an smtp token by id
- email marketing
- content
- deletesmtptoken
- hubspot
- geteventtypes
- analytics
- listsmtptokens
- geteventinstances
- marketing
- hubspot retrieve event instances
- hubspot delete an smtp token
slug: marketing-automation
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
