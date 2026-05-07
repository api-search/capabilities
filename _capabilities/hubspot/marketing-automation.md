---
categories:
- messaging
consumed_apis: []
description: Marketing automation workflow combining email campaigns and analytics events.
layout: capability
name: HubSpot Marketing Automation
operations: []
personas: []
provider_name: HubSpot
provider_slug: hubspot
search_terms:
- analytics
- hubspot
- hubspot reset smtp token password
- operations
- getsmtptokenbyid
- hubspot get an smtp token by id
- hubspot delete an smtp token
- hubspot list all smtp tokens
- resetsmtptokenpassword
- deletesmtptoken
- hubspot create an smtp token
- crm
- geteventinstances
- content
- createsmtptoken
- email
- sendtransactionalemail
- hubspot send a transactional email
- hubspot retrieve available event types
- listsmtptokens
- hubspot retrieve event instances
- marketing
- sales
- geteventtypes
- customer service
- marketing automation
- commerce
- email marketing
slug: marketing-automation
source_filename: marketing-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: HubSpot Marketing Automation\n  description: Marketing automation workflow combining email campaigns and analytics events.\n  tags:\n  - HubSpot\n  - Marketing\n  - Email\n  - Analytics\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    HUBSPOT_ACCESS_TOKEN: HUBSPOT_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: marketing-emal-api\n    baseUri: https://api.hubapi.com\n    description: 'The HubSpot Marketing Transactional Email API enables you to send transactional emails and manage SMTP tokens.\n\n\n      Use this API to:\n\n      - Create and manage SMTP API tokens for sending transactional emails\n\n      - '\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: smtp-tokens\n      path: /smtp-tokens\n      description: smtp-tokens operations\n      operations:\n      - name: listsmtptokens\n        method: GET\n  \
  \      description: HubSpot List All SMTP Tokens\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsmtptoken\n        method: POST\n        description: HubSpot Create an SMTP Token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getsmtptokenbyid\n        method: GET\n        description: HubSpot Get an SMTP Token by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesmtptoken\n        method: DELETE\n        description: HubSpot Delete an SMTP Token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: password-reset\n      path: /password-reset\n      description: password-reset operations\n      operations:\n  \
  \    - name: resetsmtptokenpassword\n        method: POST\n        description: HubSpot Reset SMTP Token Password\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: send\n      path: /send\n      description: send operations\n      operations:\n      - name: sendtransactionalemail\n        method: POST\n        description: HubSpot Send a Transactional Email\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: analytics-events-api\n    baseUri: https://api.hubapi.com\n    description: \"The HubSpot Analytics Events API allows you to retrieve event completion data \\nfrom your HubSpot account.\\\n      \\ Use this API to query event instances associated with \\nCRM objects, filter by event types, and\"\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n\
  \    - name: events\n      path: /events\n      description: events operations\n      operations:\n      - name: geteventinstances\n        method: GET\n        description: HubSpot Retrieve Event Instances\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-types\n      path: /event-types\n      description: event-types operations\n      operations:\n      - name: geteventtypes\n        method: GET\n        description: HubSpot Retrieve Available Event Types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: mcp\n    port: 9092\n    namespace: marketing-automation-mcp\n    transport: http\n    description: MCP server for AI-assisted HubSpot Marketing Automation.\n    tools:\n    - name: listsmtptokens\n      description: HubSpot List All SMTP Tokens\n      hints:\n        readOnly: true\n      call:\
  \ marketing-emal-api.listsmtptokens\n    - name: createsmtptoken\n      description: HubSpot Create an SMTP Token\n      hints:\n        readOnly: false\n      call: marketing-emal-api.createsmtptoken\n    - name: getsmtptokenbyid\n      description: HubSpot Get an SMTP Token by ID\n      hints:\n        readOnly: true\n      call: marketing-emal-api.getsmtptokenbyid\n    - name: deletesmtptoken\n      description: HubSpot Delete an SMTP Token\n      hints:\n        destructive: true\n      call: marketing-emal-api.deletesmtptoken\n    - name: resetsmtptokenpassword\n      description: HubSpot Reset SMTP Token Password\n      hints:\n        readOnly: false\n      call: marketing-emal-api.resetsmtptokenpassword\n    - name: sendtransactionalemail\n      description: HubSpot Send a Transactional Email\n      hints:\n        readOnly: false\n      call: marketing-emal-api.sendtransactionalemail\n    - name: geteventinstances\n      description: HubSpot Retrieve Event Instances\n      hints:\n\
  \        readOnly: true\n      call: analytics-events-api.geteventinstances\n    - name: geteventtypes\n      description: HubSpot Retrieve Available Event Types\n      hints:\n        readOnly: true\n      call: analytics-events-api.geteventtypes\n"
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
