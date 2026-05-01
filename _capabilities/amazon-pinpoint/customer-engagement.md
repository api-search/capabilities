---
api_specs:
- filename: amazon-pinpoint-openapi.yml
  format: yaml
  label: amazon-pinpoint
  slug: amazon-pinpoint
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/amazon-pinpoint/refs/heads/main/openapi/amazon-pinpoint-openapi.yml
categories:
- customer-engagement
consumed_apis:
- amazon-pinpoint
description: Workflow capability for multi-channel customer engagement using Amazon Pinpoint. Combines campaign management, audience segmentation, customer journeys, and transactional messaging for marketing teams and growth engineers.
layout: capability
name: Amazon Pinpoint Customer Engagement
operations:
- description: List all Pinpoint applications
  method: GET
  name: list-apps
  path: /v1/apps
- description: Create a new Pinpoint application
  method: POST
  name: create-app
  path: /v1/apps
- description: List campaigns for an application
  method: GET
  name: list-campaigns
  path: /v1/campaigns
- description: Create a new marketing campaign
  method: POST
  name: create-campaign
  path: /v1/campaigns
- description: List audience segments
  method: GET
  name: list-segments
  path: /v1/audiences
- description: Create a new audience segment
  method: POST
  name: create-segment
  path: /v1/audiences
- description: List customer journeys
  method: GET
  name: list-journeys
  path: /v1/journeys
- description: Create a new customer journey
  method: POST
  name: create-journey
  path: /v1/journeys
- description: Send transactional messages to customer endpoints
  method: POST
  name: send-messages
  path: /v1/messages
personas: []
provider_name: Amazon Pinpoint
provider_slug: amazon-pinpoint
search_terms:
- create a new marketing campaign
- create a new pinpoint application for customer engagement
- voice
- pinpoint application management
- audience segment management
- create a new customer journey
- amazon
- campaigns
- send transactional messages
- send messages
- communications
- send transactional messages (confirmations, alerts, notifications) to customer endpoints
- analytics
- push notifications
- create a new customer audience segment based on attributes or imported data
- create audience segment
- list campaigns
- customer journey workflow management
- create segment
- list audience segments
- sms
- marketing
- journeys
- Marketing Manager
- aws
- create a multi-step automated customer engagement journey
- list audience segments for targeting campaigns and journeys
- create campaign
- manages campaigns, segments, and journeys
- create a new pinpoint application
- marketing campaign management
- customer engagement
- multi-channel customer engagement workflow
- messaging
- list automated customer journey workflows
- create a new multi-channel marketing campaign
- list marketing campaigns for a pinpoint application
- Growth Engineer
- list journeys
- list apps
- list all pinpoint applications
- email
- integrates messaging apis and manages endpoints
- list campaigns for an application
- segmentation
- create journey
- send transactional messages to customer endpoints
- create a new audience segment
- list customer journeys
- list segments
- create app
slug: customer-engagement
source_filename: customer-engagement.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Amazon Pinpoint Customer Engagement\n  description: Workflow capability for multi-channel customer engagement using Amazon Pinpoint. Combines campaign management, audience segmentation, customer journeys, and transactional messaging for marketing teams and growth engineers.\n  tags:\n    - Amazon\n    - AWS\n    - Marketing\n    - Customer Engagement\n    - Campaigns\n    - Journeys\n    - Segmentation\n    - Messaging\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: amazon-pinpoint\n      location: ./shared/amazon-pinpoint.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: customer-engagement-api\n      description: Unified REST API for Amazon Pinpoint customer engagement workflows.\n      resources:\n\
  \        - path: /v1/apps\n          name: apps\n          description: Pinpoint application management\n          operations:\n            - method: GET\n              name: list-apps\n              description: List all Pinpoint applications\n              call: \"amazon-pinpoint.get-apps\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-app\n              description: Create a new Pinpoint application\n              call: \"amazon-pinpoint.create-app\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/campaigns\n          name: campaigns\n          description: Marketing campaign management\n          operations:\n            - method: GET\n              name: list-campaigns\n              description: List campaigns for an application\n              call: \"amazon-pinpoint.get-campaigns\"\n             \
  \ with:\n                application-id: \"rest.application_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-campaign\n              description: Create a new marketing campaign\n              call: \"amazon-pinpoint.create-campaign\"\n              with:\n                application-id: \"rest.application_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/audiences\n          name: audiences\n          description: Audience segment management\n          operations:\n            - method: GET\n              name: list-segments\n              description: List audience segments\n              call: \"amazon-pinpoint.get-segments\"\n              with:\n                application-id: \"rest.application_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"\
  $.\"\n            - method: POST\n              name: create-segment\n              description: Create a new audience segment\n              call: \"amazon-pinpoint.create-segment\"\n              with:\n                application-id: \"rest.application_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/journeys\n          name: journeys\n          description: Customer journey workflow management\n          operations:\n            - method: GET\n              name: list-journeys\n              description: List customer journeys\n              call: \"amazon-pinpoint.list-journeys\"\n              with:\n                application-id: \"rest.application_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-journey\n              description: Create a new customer journey\n              call: \"amazon-pinpoint.create-journey\"\
  \n              with:\n                application-id: \"rest.application_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/messages\n          name: messages\n          description: Send transactional messages\n          operations:\n            - method: POST\n              name: send-messages\n              description: Send transactional messages to customer endpoints\n              call: \"amazon-pinpoint.send-messages\"\n              with:\n                application-id: \"rest.application_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: customer-engagement-mcp\n      transport: http\n      description: MCP server for AI-assisted customer engagement workflows with Amazon Pinpoint.\n      tools:\n        - name: list-apps\n          description: List all Pinpoint applications\n          hints:\n\
  \            readOnly: true\n            openWorld: true\n          call: \"amazon-pinpoint.get-apps\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-app\n          description: Create a new Pinpoint application for customer engagement\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"amazon-pinpoint.create-app\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-campaigns\n          description: List marketing campaigns for a Pinpoint application\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"amazon-pinpoint.get-campaigns\"\n          with:\n            application-id: \"tools.application_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-campaign\n\
  \          description: Create a new multi-channel marketing campaign\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"amazon-pinpoint.create-campaign\"\n          with:\n            application-id: \"tools.application_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-audience-segments\n          description: List audience segments for targeting campaigns and journeys\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"amazon-pinpoint.get-segments\"\n          with:\n            application-id: \"tools.application_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-audience-segment\n          description: Create a new customer audience segment based on attributes or imported data\n          hints:\n            readOnly: false\n            destructive: false\n     \
  \     call: \"amazon-pinpoint.create-segment\"\n          with:\n            application-id: \"tools.application_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-journeys\n          description: List automated customer journey workflows\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"amazon-pinpoint.list-journeys\"\n          with:\n            application-id: \"tools.application_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-journey\n          description: Create a multi-step automated customer engagement journey\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"amazon-pinpoint.create-journey\"\n          with:\n            application-id: \"tools.application_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n\
  \        - name: send-transactional-messages\n          description: Send transactional messages (confirmations, alerts, notifications) to customer endpoints\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"amazon-pinpoint.send-messages\"\n          with:\n            application-id: \"tools.application_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-pinpoint/refs/heads/main/capabilities/customer-engagement.yaml
tags:
- Amazon
- AWS
- Marketing
- Customer Engagement
- Campaigns
- Journeys
- Segmentation
- Messaging
tools:
- description: List all Pinpoint applications
  hints:
    openWorld: true
    readOnly: true
  name: list-apps
- description: Create a new Pinpoint application for customer engagement
  hints:
    destructive: false
    readOnly: false
  name: create-app
- description: List marketing campaigns for a Pinpoint application
  hints:
    openWorld: true
    readOnly: true
  name: list-campaigns
- description: Create a new multi-channel marketing campaign
  hints:
    destructive: false
    readOnly: false
  name: create-campaign
- description: List audience segments for targeting campaigns and journeys
  hints:
    openWorld: true
    readOnly: true
  name: list-audience-segments
- description: Create a new customer audience segment based on attributes or imported data
  hints:
    destructive: false
    readOnly: false
  name: create-audience-segment
- description: List automated customer journey workflows
  hints:
    openWorld: true
    readOnly: true
  name: list-journeys
- description: Create a multi-step automated customer engagement journey
  hints:
    destructive: false
    readOnly: false
  name: create-journey
- description: Send transactional messages (confirmations, alerts, notifications) to customer endpoints
  hints:
    destructive: false
    readOnly: false
  name: send-transactional-messages
---
