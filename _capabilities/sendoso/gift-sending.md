---
categories: []
consumed_apis: []
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
- list inventory
- add a new recipient contact with name, email, and optional address
- sending analytics
- get aggregated sending analytics by date range
- get sends report
- check the team's remaining gift sending budget and billing period
- create a new gift send to a recipient
- direct mail
- create recipient
- crm integration
- list recipients
- cancel a pending send
- get team budget balance and remaining spend
- monitor team budget
- list gift sends with optional filtering by status (pending, shipped, delivered, failed) and date range. use to check on pending sends or review recent gifting activity.
- list sends with filtering by status and date range
- get sending analytics for a date range. use group_by to aggregate by day, week, month, user, or team. returns totals and time-series data.
- sales engagement
- retrieve send
- list recipient contacts
- get the current status and tracking details for a specific send
- list sends
- get send details and tracking status
- search for recipient contacts by name or email. use before creating a send to find an existing recipient_id.
- manage gift recipients
- retrieve or cancel a specific send
- cancel send
- add a new recipient contact
- cancel a pending send that has not yet been processed for shipment
- 'browse available gifts and products. filter by type: egift (digital gift cards), physical (shipped products), swag (branded merchandise), direct_mail, or charity.'
- browse available gifts and products
- create send
- create and manage gift sends
- get team budget
- send a gift to a recipient. provide recipient_id and item_id from inventory. optionally add a personalized message and crm attribution (crm_id, crm_type) for salesforce/hubspot reporting.
- marketing automation
- list available inventory items by type
- corporate gifting
slug: gift-sending
source_filename: gift-sending.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sendoso Gift Sending\n  description: Unified capability for corporate gifting and direct mail workflows using the Sendoso platform. Enables sales\n    and marketing teams to send physical gifts, e-gift cards, swag, and direct mail to prospects and customers. Integrates\n    CRM attribution for campaign reporting.\n  tags:\n  - Corporate Gifting\n  - Direct Mail\n  - Sales Engagement\n  - Marketing Automation\n  - CRM Integration\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SENDOSO_API_KEY: SENDOSO_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: sendoso-api\n    baseUri: https://app.sendoso.com/api/v2\n    description: Sendoso Sending Platform API\n    authentication:\n      type: apikey\n      key: X-Api-Key\n      value: '{{SENDOSO_API_KEY}}'\n      placement: header\n    resources:\n    - name: sends\n      path: /sends\n      description: Create and manage gift sends\n\
  \      operations:\n      - name: list-sends\n        method: GET\n        description: Returns a paginated list of sends\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by send status\n        - name: start_date\n          in: query\n          type: string\n          required: false\n          description: Filter sends created on or after this date\n        - name: end_date\n          in: query\n          type: string\n          required: false\n          description: Filter sends created on or before this date\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: create-send\n        method: POST\n        description: Initiates a new gift send to a recipient\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            recipient_id: '{{tools.recipient_id}}'\n            item_id: '{{tools.item_id}}'\n            message: '{{tools.message}}'\n            crm_id: '{{tools.crm_id}}'\n            crm_type: '{{tools.crm_type}}'\n    - name: send\n      path: /sends/{send_id}\n      description: Retrieve or cancel a specific send\n      operations:\n      - name: retrieve-send\n        method: GET\n        description: Returns details for a specific send\n        inputParameters:\n        - name: send_id\n          in: path\n          type: string\n          required: true\n          description: Send ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: cancel-send\n        method: DELETE\n        description: Cancels a pending send\n        inputParameters:\n        - name: send_id\n          in: path\n          type: string\n          required: true\n          description: Send ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recipients\n      path: /recipients\n      description: Manage recipient contacts\n      operations:\n      - name: list-recipients\n        method: GET\n        description: Returns a paginated list of recipient contacts\n        inputParameters:\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search by name or email\n        - name: page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: create-recipient\n        method: POST\n        description: Creates a new recipient contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            first_name: '{{tools.first_name}}'\n            last_name: '{{tools.last_name}}'\n            email: '{{tools.email}}'\n            company: '{{tools.company}}'\n    - name: inventory\n      path: /inventory\n      description: Browse available gifts and products\n      operations:\n      - name: list-inventory\n        method: GET\n        description: Returns available items in the team inventory\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Filter by item type (physical, egift, swag, direct_mail, charity)\n        - name: page\n          in: query\n\
  \          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: team-budget\n      path: /teams/budget\n      description: Team budget management\n      operations:\n      - name: get-team-budget\n        method: GET\n        description: Returns the team budget balance and allocation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sends-report\n      path: /reports/sends\n      description: Sending analytics and reports\n      operations:\n      - name: get-sends-report\n        method: GET\n        description: Returns aggregated sending analytics for a date range\n        inputParameters:\n        - name: start_date\n          in: query\n          type: string\n          required: true\n          description: Report start date (YYYY-MM-DD)\n        - name: end_date\n\
  \          in: query\n          type: string\n          required: true\n          description: Report end date (YYYY-MM-DD)\n        - name: group_by\n          in: query\n          type: string\n          required: false\n          description: Aggregation dimension (day, week, month, user, team)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sendoso-gift-sending-api\n    description: Unified REST API for Sendoso corporate gifting and direct mail workflows.\n    resources:\n    - path: /v1/sends\n      name: sends\n      description: Create and manage gift sends\n      operations:\n      - method: GET\n        name: list-sends\n        description: List sends with filtering by status and date range\n        call: sendoso-api.list-sends\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-send\n\
  \        description: Create a new gift send to a recipient\n        call: sendoso-api.create-send\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sends/{send_id}\n      name: send\n      description: Retrieve or cancel a specific send\n      operations:\n      - method: GET\n        name: retrieve-send\n        description: Get send details and tracking status\n        call: sendoso-api.retrieve-send\n        with:\n          send_id: rest.send_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: cancel-send\n        description: Cancel a pending send\n        call: sendoso-api.cancel-send\n        with:\n          send_id: rest.send_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/recipients\n      name: recipients\n      description: Manage gift recipients\n      operations:\n      - method: GET\n        name: list-recipients\n      \
  \  description: List recipient contacts\n        call: sendoso-api.list-recipients\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-recipient\n        description: Add a new recipient contact\n        call: sendoso-api.create-recipient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/inventory\n      name: inventory\n      description: Browse available gifts and products\n      operations:\n      - method: GET\n        name: list-inventory\n        description: List available inventory items by type\n        call: sendoso-api.list-inventory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/teams/budget\n      name: team-budget\n      description: Monitor team budget\n      operations:\n      - method: GET\n        name: get-team-budget\n        description: Get team budget balance and remaining spend\n        call: sendoso-api.get-team-budget\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports/sends\n      name: sends-report\n      description: Sending analytics\n      operations:\n      - method: GET\n        name: get-sends-report\n        description: Get aggregated sending analytics by date range\n        call: sendoso-api.get-sends-report\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sendoso-gift-sending-mcp\n    transport: http\n    description: MCP server for AI-assisted corporate gifting and sales engagement workflows.\n    tools:\n    - name: list-sends\n      description: List gift sends with optional filtering by status (pending, shipped, delivered, failed) and date range.\n        Use to check on pending sends or review recent gifting activity.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sendoso-api.list-sends\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n    - name: create-send\n      description: Send a gift to a recipient. Provide recipient_id and item_id from inventory. Optionally add a personalized\n        message and CRM attribution (crm_id, crm_type) for Salesforce/HubSpot reporting.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: sendoso-api.create-send\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrieve-send\n      description: Get the current status and tracking details for a specific send\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sendoso-api.retrieve-send\n      with:\n        send_id: tools.send_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-send\n      description: Cancel a pending send that has not yet been processed for shipment\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: sendoso-api.cancel-send\n\
  \      with:\n        send_id: tools.send_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-recipients\n      description: Search for recipient contacts by name or email. Use before creating a send to find an existing recipient_id.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sendoso-api.list-recipients\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-recipient\n      description: Add a new recipient contact with name, email, and optional address\n      hints:\n        readOnly: false\n        idempotent: false\n      call: sendoso-api.create-recipient\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-inventory\n      description: 'Browse available gifts and products. Filter by type: egift (digital gift cards), physical (shipped products),\n        swag (branded merchandise), direct_mail, or charity.'\n      hints:\n        readOnly: true\n \
  \       idempotent: true\n      call: sendoso-api.list-inventory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-team-budget\n      description: Check the team's remaining gift sending budget and billing period\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sendoso-api.get-team-budget\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-sends-report\n      description: Get sending analytics for a date range. Use group_by to aggregate by day, week, month, user, or team. Returns\n        totals and time-series data.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: sendoso-api.get-sends-report\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
