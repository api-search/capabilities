---
api_specs:
- filename: sendoso-api-openapi.yml
  format: yaml
  label: sendoso-api
  slug: sendoso-api
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/sendoso/refs/heads/main/openapi/sendoso-api-openapi.yml
categories: []
consumed_apis:
- sendoso-api
description: Unified capability for corporate gifting and direct mail workflows using the Sendoso platform. Enables sales and marketing teams to send physical gifts, e-gift cards, swag, and direct mail to prospects and customers. Integrates CRM attribution for campaign reporting.
layout: capability
name: Sendoso Gift Sending
operations:
- description: List sends with filtering by status and date range
  method: GET
  name: list-sends
  path: /v1/sends
- description: Create a new gift send to a recipient
  method: POST
  name: create-send
  path: /v1/sends
- description: Get send details and tracking status
  method: GET
  name: retrieve-send
  path: /v1/sends/{send_id}
- description: Cancel a pending send
  method: DELETE
  name: cancel-send
  path: /v1/sends/{send_id}
- description: List recipient contacts
  method: GET
  name: list-recipients
  path: /v1/recipients
- description: Add a new recipient contact
  method: POST
  name: create-recipient
  path: /v1/recipients
- description: List available inventory items by type
  method: GET
  name: list-inventory
  path: /v1/inventory
- description: Get team budget balance and remaining spend
  method: GET
  name: get-team-budget
  path: /v1/teams/budget
- description: Get aggregated sending analytics by date range
  method: GET
  name: get-sends-report
  path: /v1/reports/sends
personas: []
provider_name: Sendoso
provider_slug: sendoso
search_terms:
- list sends with filtering by status and date range
- list inventory
- get sends report
- get sending analytics for a date range. use group_by to aggregate by day, week, month, user, or team. returns totals and time-series data.
- add a new recipient contact with name, email, and optional address
- get the current status and tracking details for a specific send
- send a gift to a recipient. provide recipient_id and item_id from inventory. optionally add a personalized message and crm attribution (crm_id, crm_type) for salesforce/hubspot reporting.
- list available inventory items by type
- monitor team budget
- sales engagement
- create send
- marketing automation
- create and manage gift sends
- 'browse available gifts and products. filter by type: egift (digital gift cards), physical (shipped products), swag (branded merchandise), direct_mail, or charity.'
- search for recipient contacts by name or email. use before creating a send to find an existing recipient_id.
- list recipient contacts
- get send details and tracking status
- retrieve send
- add a new recipient contact
- list gift sends with optional filtering by status (pending, shipped, delivered, failed) and date range. use to check on pending sends or review recent gifting activity.
- get team budget
- crm integration
- list recipients
- cancel a pending send
- manage gift recipients
- list sends
- direct mail
- sending analytics
- cancel a pending send that has not yet been processed for shipment
- browse available gifts and products
- cancel send
- retrieve or cancel a specific send
- corporate gifting
- check the team's remaining gift sending budget and billing period
- create a new gift send to a recipient
- get aggregated sending analytics by date range
- create recipient
- get team budget balance and remaining spend
slug: gift-sending
source_filename: gift-sending.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sendoso Gift Sending\"\n  description: >-\n    Unified capability for corporate gifting and direct mail workflows using\n    the Sendoso platform. Enables sales and marketing teams to send physical\n    gifts, e-gift cards, swag, and direct mail to prospects and customers.\n    Integrates CRM attribution for campaign reporting.\n  tags:\n    - Corporate Gifting\n    - Direct Mail\n    - Sales Engagement\n    - Marketing Automation\n    - CRM Integration\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SENDOSO_API_KEY: SENDOSO_API_KEY\n\ncapability:\n  consumes:\n    - import: sendoso-api\n      location: ./shared/sendoso-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sendoso-gift-sending-api\n      description: \"Unified REST API for Sendoso corporate gifting and direct mail workflows.\"\n      resources:\n        - path: /v1/sends\n          name:\
  \ sends\n          description: \"Create and manage gift sends\"\n          operations:\n            - method: GET\n              name: list-sends\n              description: \"List sends with filtering by status and date range\"\n              call: \"sendoso-api.list-sends\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-send\n              description: \"Create a new gift send to a recipient\"\n              call: \"sendoso-api.create-send\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/sends/{send_id}\n          name: send\n          description: \"Retrieve or cancel a specific send\"\n          operations:\n            - method: GET\n              name: retrieve-send\n              description: \"Get send details and tracking status\"\n              call: \"sendoso-api.retrieve-send\"\n           \
  \   with:\n                send_id: \"rest.send_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: cancel-send\n              description: \"Cancel a pending send\"\n              call: \"sendoso-api.cancel-send\"\n              with:\n                send_id: \"rest.send_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/recipients\n          name: recipients\n          description: \"Manage gift recipients\"\n          operations:\n            - method: GET\n              name: list-recipients\n              description: \"List recipient contacts\"\n              call: \"sendoso-api.list-recipients\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-recipient\n              description: \"Add a new recipient\
  \ contact\"\n              call: \"sendoso-api.create-recipient\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/inventory\n          name: inventory\n          description: \"Browse available gifts and products\"\n          operations:\n            - method: GET\n              name: list-inventory\n              description: \"List available inventory items by type\"\n              call: \"sendoso-api.list-inventory\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/teams/budget\n          name: team-budget\n          description: \"Monitor team budget\"\n          operations:\n            - method: GET\n              name: get-team-budget\n              description: \"Get team budget balance and remaining spend\"\n              call: \"sendoso-api.get-team-budget\"\n              outputParameters:\n                - type: object\n     \
  \             mapping: \"$.\"\n\n        - path: /v1/reports/sends\n          name: sends-report\n          description: \"Sending analytics\"\n          operations:\n            - method: GET\n              name: get-sends-report\n              description: \"Get aggregated sending analytics by date range\"\n              call: \"sendoso-api.get-sends-report\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sendoso-gift-sending-mcp\n      transport: http\n      description: \"MCP server for AI-assisted corporate gifting and sales engagement workflows.\"\n      tools:\n        - name: list-sends\n          description: >-\n            List gift sends with optional filtering by status (pending, shipped,\n            delivered, failed) and date range. Use to check on pending sends or\n            review recent gifting activity.\n          hints:\n            readOnly: true\n       \
  \     idempotent: true\n          call: \"sendoso-api.list-sends\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-send\n          description: >-\n            Send a gift to a recipient. Provide recipient_id and item_id from\n            inventory. Optionally add a personalized message and CRM attribution\n            (crm_id, crm_type) for Salesforce/HubSpot reporting.\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"sendoso-api.create-send\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: retrieve-send\n          description: \"Get the current status and tracking details for a specific send\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sendoso-api.retrieve-send\"\n          with:\n            send_id: \"tools.send_id\"\n          outputParameters:\n            -\
  \ type: object\n              mapping: \"$.\"\n\n        - name: cancel-send\n          description: \"Cancel a pending send that has not yet been processed for shipment\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"sendoso-api.cancel-send\"\n          with:\n            send_id: \"tools.send_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-recipients\n          description: >-\n            Search for recipient contacts by name or email. Use before creating\n            a send to find an existing recipient_id.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sendoso-api.list-recipients\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-recipient\n          description: \"Add a new recipient contact with name, email, and optional\
  \ address\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"sendoso-api.create-recipient\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-inventory\n          description: >-\n            Browse available gifts and products. Filter by type: egift (digital\n            gift cards), physical (shipped products), swag (branded merchandise),\n            direct_mail, or charity.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sendoso-api.list-inventory\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-team-budget\n          description: \"Check the team's remaining gift sending budget and billing period\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sendoso-api.get-team-budget\"\n          outputParameters:\n            -\
  \ type: object\n              mapping: \"$.\"\n\n        - name: get-sends-report\n          description: >-\n            Get sending analytics for a date range. Use group_by to aggregate\n            by day, week, month, user, or team. Returns totals and time-series data.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"sendoso-api.get-sends-report\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sendoso/refs/heads/main/capabilities/gift-sending.yaml
tags:
- Corporate Gifting
- Direct Mail
- Sales Engagement
- Marketing Automation
- CRM Integration
tools:
- description: List gift sends with optional filtering by status (pending, shipped, delivered, failed) and date range. Use to check on pending sends or review recent gifting activity.
  hints:
    idempotent: true
    readOnly: true
  name: list-sends
- description: Send a gift to a recipient. Provide recipient_id and item_id from inventory. Optionally add a personalized message and CRM attribution (crm_id, crm_type) for Salesforce/HubSpot reporting.
  hints:
    idempotent: false
    readOnly: false
  name: create-send
- description: Get the current status and tracking details for a specific send
  hints:
    idempotent: true
    readOnly: true
  name: retrieve-send
- description: Cancel a pending send that has not yet been processed for shipment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-send
- description: Search for recipient contacts by name or email. Use before creating a send to find an existing recipient_id.
  hints:
    idempotent: true
    readOnly: true
  name: list-recipients
- description: Add a new recipient contact with name, email, and optional address
  hints:
    idempotent: false
    readOnly: false
  name: create-recipient
- description: 'Browse available gifts and products. Filter by type: egift (digital gift cards), physical (shipped products), swag (branded merchandise), direct_mail, or charity.'
  hints:
    idempotent: true
    readOnly: true
  name: list-inventory
- description: Check the team's remaining gift sending budget and billing period
  hints:
    idempotent: true
    readOnly: true
  name: get-team-budget
- description: Get sending analytics for a date range. Use group_by to aggregate by day, week, month, user, or team. Returns totals and time-series data.
  hints:
    idempotent: true
    readOnly: true
  name: get-sends-report
---
