---
categories: []
consumed_apis: []
description: Unified capability for strategic sourcing and procurement workflows using the Workday Strategic Sourcing (Scout RFP) API. Enables procurement teams to manage the full sourcing lifecycle — from creating RFP events and inviting suppliers to collecting bids and making award decisions.
layout: capability
name: Strategic Sourcing and Procurement
operations:
- description: List all sourcing events
  method: GET
  name: list-events
  path: /v1/events
- description: Create a new sourcing event from a template
  method: POST
  name: create-event
  path: /v1/events
- description: Get event details
  method: GET
  name: get-event
  path: /v1/events/{id}
- description: Update event details
  method: PATCH
  name: update-event
  path: /v1/events/{id}
- description: Delete a sourcing event
  method: DELETE
  name: delete-event
  path: /v1/events/{id}
- description: List available event templates
  method: GET
  name: list-event-templates
  path: /v1/templates
- description: List worksheets for an event
  method: GET
  name: list-worksheets
  path: /v1/events/{event_id}/worksheets
- description: List line items for an event worksheet
  method: GET
  name: list-line-items
  path: /v1/events/{event_id}/line-items
- description: Add a line item to a worksheet
  method: POST
  name: create-line-item
  path: /v1/events/{event_id}/line-items
- description: List all bids for an event
  method: GET
  name: list-bids
  path: /v1/events/{event_id}/bids
- description: Get bid details
  method: GET
  name: get-bid
  path: /v1/events/{event_id}/bids/{id}
personas: []
provider_name: Scout RFP
provider_slug: scout-rfp
search_terms:
- create a new sourcing event from a template
- update sourcing event
- list worksheets
- list events
- delete event
- list event templates
- procurement
- supplier bids for rfp events
- list line items
- delete a sourcing event
- individual bid details
- get bid
- list all sourcing events
- sourcing events (rfps, rfis, auctions)
- list sourcing events
- list supplier bids submitted for an rfp event
- list worksheets within a sourcing event
- update event details
- workday
- get details of a specific supplier bid
- supply chain
- strategic sourcing
- list all sourcing events (rfps, rfis, auctions) with optional filtering
- add a line item to a worksheet
- create sourcing event
- list line items for an event worksheet
- worksheets within sourcing events
- list bids
- list line items (products/services being sourced) in an event worksheet
- get bid details
- get sourcing event
- get details of a specific sourcing event by id
- create event
- create line item
- list available event templates
- create a new sourcing event (rfp or rfi) from an existing template
- add a line item to a sourcing event worksheet
- get event details
- update properties of an existing sourcing event
- list available event templates for creating standardized rfps
- rfp
- list worksheets for an event
- event templates for creating standardized sourcing events
- get event
- supplier management
- individual event management
- update event
- line items within event worksheets
- list all bids for an event
- sourcing
slug: strategic-sourcing
source_filename: strategic-sourcing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Strategic Sourcing and Procurement\n  description: Unified capability for strategic sourcing and procurement workflows using the Workday Strategic Sourcing (Scout\n    RFP) API. Enables procurement teams to manage the full sourcing lifecycle — from creating RFP events and inviting suppliers\n    to collecting bids and making award decisions.\n  tags:\n  - Procurement\n  - Strategic Sourcing\n  - RFP\n  - Supplier Management\n  - Workday\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SCOUT_RFP_API_KEY: SCOUT_RFP_API_KEY\n    SCOUT_RFP_USER_TOKEN: SCOUT_RFP_USER_TOKEN\n    SCOUT_RFP_USER_EMAIL: SCOUT_RFP_USER_EMAIL\ncapability:\n  consumes:\n  - type: http\n    namespace: scout-rfp-events\n    baseUri: https://api.us.workdayspend.com/services/events/v1\n    description: Workday Strategic Sourcing Events API v1.3\n    authentication:\n      type: apikey\n      key: X-Api-Key\n      value: '{{SCOUT_RFP_API_KEY}}'\n\
  \      placement: header\n    resources:\n    - name: events\n      path: /events\n      description: Sourcing events management\n      operations:\n      - name: list-events\n        method: GET\n        description: List all sourcing events with filtering and pagination\n        inputParameters:\n        - name: page[size]\n          in: query\n          type: integer\n          required: false\n          description: Number of results per page (max 100)\n        - name: filter\n          in: query\n          type: string\n          required: false\n          description: Filter criteria\n        - name: include\n          in: query\n          type: string\n          required: false\n          description: Related resources to include\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-event\n        method: POST\n        description: Create a new sourcing event from a template\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            event_type: '{{tools.event_type}}'\n    - name: event-detail\n      path: /events/{id}\n      description: Individual event operations\n      operations:\n      - name: get-event\n        method: GET\n        description: Get details of a specific sourcing event\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Event identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-event\n        method: PATCH\n        description: Update an existing sourcing event\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description:\
  \ Event identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n      - name: delete-event\n        method: DELETE\n        description: Delete a sourcing event\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Event identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event-templates\n      path: /event_templates\n      description: Event template management\n      operations:\n      - name: list-event-templates\n        method: GET\n        description: List all available event templates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ get-event-template\n        method: GET\n        description: Get a specific event template\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Template identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: worksheets\n      path: /events/{event_id}/worksheets\n      description: Event worksheet management\n      operations:\n      - name: list-worksheets\n        method: GET\n        description: List worksheets for a sourcing event\n        inputParameters:\n        - name: event_id\n          in: path\n          type: string\n          required: true\n          description: Event identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-worksheet\n        method: GET\n        description: Get a specific\
  \ worksheet\n        inputParameters:\n        - name: event_id\n          in: path\n          type: string\n          required: true\n          description: Event identifier\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Worksheet identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: line-items\n      path: /events/{event_id}/worksheets/{worksheet_id}/line_items\n      description: Worksheet line item management\n      operations:\n      - name: list-line-items\n        method: GET\n        description: List line items for a worksheet\n        inputParameters:\n        - name: event_id\n          in: path\n          type: string\n          required: true\n          description: Event identifier\n        - name: worksheet_id\n          in: path\n          type: string\n          required: true\n          description: Worksheet\
  \ identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-line-item\n        method: POST\n        description: Create a line item in a worksheet\n        inputParameters:\n        - name: event_id\n          in: path\n          type: string\n          required: true\n          description: Event identifier\n        - name: worksheet_id\n          in: path\n          type: string\n          required: true\n          description: Worksheet identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            quantity: '{{tools.quantity}}'\n    - name: bids\n      path: /events/{event_id}/bids\n      description: Bid management for RFP events\n      operations:\n     \
  \ - name: list-bids\n        method: GET\n        description: List all bids for an event\n        inputParameters:\n        - name: event_id\n          in: path\n          type: string\n          required: true\n          description: Event identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-bid\n        method: GET\n        description: Get a specific bid\n        inputParameters:\n        - name: event_id\n          in: path\n          type: string\n          required: true\n          description: Event identifier\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Bid identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: strategic-sourcing-api\n    description: Unified REST API\
  \ for end-to-end strategic sourcing and procurement workflows.\n    resources:\n    - path: /v1/events\n      name: events\n      description: Sourcing events (RFPs, RFIs, auctions)\n      operations:\n      - method: GET\n        name: list-events\n        description: List all sourcing events\n        call: scout-rfp-events.list-events\n        with:\n          page_size: rest.page_size\n          filter: rest.filter\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-event\n        description: Create a new sourcing event from a template\n        call: scout-rfp-events.create-event\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events/{id}\n      name: event-detail\n      description: Individual event management\n      operations:\n      - method: GET\n        name: get-event\n        description: Get event details\n        call: scout-rfp-events.get-event\n        with:\n \
  \         id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-event\n        description: Update event details\n        call: scout-rfp-events.update-event\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-event\n        description: Delete a sourcing event\n        call: scout-rfp-events.delete-event\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/templates\n      name: templates\n      description: Event templates for creating standardized sourcing events\n      operations:\n      - method: GET\n        name: list-event-templates\n        description: List available event templates\n        call: scout-rfp-events.list-event-templates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events/{event_id}/worksheets\n\
  \      name: worksheets\n      description: Worksheets within sourcing events\n      operations:\n      - method: GET\n        name: list-worksheets\n        description: List worksheets for an event\n        call: scout-rfp-events.list-worksheets\n        with:\n          event_id: rest.event_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events/{event_id}/line-items\n      name: line-items\n      description: Line items within event worksheets\n      operations:\n      - method: GET\n        name: list-line-items\n        description: List line items for an event worksheet\n        call: scout-rfp-events.list-line-items\n        with:\n          event_id: rest.event_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-line-item\n        description: Add a line item to a worksheet\n        call: scout-rfp-events.create-line-item\n        with:\n          event_id: rest.event_id\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events/{event_id}/bids\n      name: bids\n      description: Supplier bids for RFP events\n      operations:\n      - method: GET\n        name: list-bids\n        description: List all bids for an event\n        call: scout-rfp-events.list-bids\n        with:\n          event_id: rest.event_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events/{event_id}/bids/{id}\n      name: bid-detail\n      description: Individual bid details\n      operations:\n      - method: GET\n        name: get-bid\n        description: Get bid details\n        call: scout-rfp-events.get-bid\n        with:\n          event_id: rest.event_id\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: strategic-sourcing-mcp\n    transport: http\n    description: MCP server for AI-assisted strategic\
  \ sourcing and procurement workflows.\n    tools:\n    - name: list-sourcing-events\n      description: List all sourcing events (RFPs, RFIs, auctions) with optional filtering\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scout-rfp-events.list-events\n      with:\n        page_size: tools.page_size\n        filter: tools.filter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-sourcing-event\n      description: Create a new sourcing event (RFP or RFI) from an existing template\n      hints:\n        readOnly: false\n      call: scout-rfp-events.create-event\n      with:\n        title: tools.title\n        event_type: tools.event_type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-sourcing-event\n      description: Get details of a specific sourcing event by ID\n      hints:\n        readOnly: true\n      call: scout-rfp-events.get-event\n      with:\n        id: tools.id\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: update-sourcing-event\n      description: Update properties of an existing sourcing event\n      hints:\n        readOnly: false\n        idempotent: true\n      call: scout-rfp-events.update-event\n      with:\n        id: tools.id\n        title: tools.title\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-event-templates\n      description: List available event templates for creating standardized RFPs\n      hints:\n        readOnly: true\n      call: scout-rfp-events.list-event-templates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-worksheets\n      description: List worksheets within a sourcing event\n      hints:\n        readOnly: true\n      call: scout-rfp-events.list-worksheets\n      with:\n        event_id: tools.event_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-line-items\n      description: List\
  \ line items (products/services being sourced) in an event worksheet\n      hints:\n        readOnly: true\n      call: scout-rfp-events.list-line-items\n      with:\n        event_id: tools.event_id\n        worksheet_id: tools.worksheet_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-line-item\n      description: Add a line item to a sourcing event worksheet\n      hints:\n        readOnly: false\n      call: scout-rfp-events.create-line-item\n      with:\n        event_id: tools.event_id\n        worksheet_id: tools.worksheet_id\n        name: tools.name\n        description: tools.description\n        quantity: tools.quantity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-bids\n      description: List supplier bids submitted for an RFP event\n      hints:\n        readOnly: true\n      call: scout-rfp-events.list-bids\n      with:\n        event_id: tools.event_id\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: get-bid\n      description: Get details of a specific supplier bid\n      hints:\n        readOnly: true\n      call: scout-rfp-events.get-bid\n      with:\n        event_id: tools.event_id\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/scout-rfp/refs/heads/main/capabilities/strategic-sourcing.yaml
tags:
- Procurement
- Strategic Sourcing
- RFP
- Supplier Management
- Workday
tools:
- description: List all sourcing events (RFPs, RFIs, auctions) with optional filtering
  hints:
    openWorld: true
    readOnly: true
  name: list-sourcing-events
- description: Create a new sourcing event (RFP or RFI) from an existing template
  hints:
    readOnly: false
  name: create-sourcing-event
- description: Get details of a specific sourcing event by ID
  hints:
    readOnly: true
  name: get-sourcing-event
- description: Update properties of an existing sourcing event
  hints:
    idempotent: true
    readOnly: false
  name: update-sourcing-event
- description: List available event templates for creating standardized RFPs
  hints:
    readOnly: true
  name: list-event-templates
- description: List worksheets within a sourcing event
  hints:
    readOnly: true
  name: list-worksheets
- description: List line items (products/services being sourced) in an event worksheet
  hints:
    readOnly: true
  name: list-line-items
- description: Add a line item to a sourcing event worksheet
  hints:
    readOnly: false
  name: create-line-item
- description: List supplier bids submitted for an RFP event
  hints:
    readOnly: true
  name: list-bids
- description: Get details of a specific supplier bid
  hints:
    readOnly: true
  name: get-bid
---
