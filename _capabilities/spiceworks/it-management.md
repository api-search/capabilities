---
categories: []
consumed_apis:
- spiceworks
description: Workflow capability for IT professionals using Spiceworks to manage help desk ticketing, device inventory, and user administration. Combines ticket lifecycle management with device inventory lookup for unified IT operations workflows. Suitable for IT managers, technicians, and help desk administrators who need to correlate support requests with asset information.
layout: capability
name: Spiceworks IT Management
operations:
- description: List all Help Desk tickets
  method: GET
  name: list-tickets
  path: /v1/tickets
- description: Create a new Help Desk ticket
  method: POST
  name: create-ticket
  path: /v1/tickets
- description: Get full ticket details including comments
  method: GET
  name: get-ticket
  path: /v1/tickets/{id}
- description: Update ticket status, priority, or assignee
  method: PUT
  name: update-ticket
  path: /v1/tickets/{id}
- description: List all comments on a ticket
  method: GET
  name: list-comments
  path: /v1/tickets/{id}/comments
- description: Add a comment to a ticket
  method: POST
  name: add-comment
  path: /v1/tickets/{id}/comments
- description: List all managed IT devices
  method: GET
  name: list-devices
  path: /v1/devices
- description: Get device hardware, software, and network details
  method: GET
  name: get-device
  path: /v1/devices/{id}
- description: List platform users and technicians
  method: GET
  name: list-users
  path: /v1/users
personas: []
provider_name: Spiceworks
provider_slug: spiceworks
search_terms:
- get device
- list spiceworks users and technicians
- community
- list comments
- list users
- it operations
- help desk
- it device inventory
- get full details of a help desk ticket including all comments
- list help desk tickets, optionally filtered by status or assignee
- individual ticket operations
- enterprise it
- add comment
- it management
- create a new help desk ticket
- get full ticket details including comments
- create a new help desk support ticket
- add a public or internal comment to a help desk ticket
- help desk ticket management
- create ticket
- list devices
- list all help desk tickets
- individual device details
- list all managed it devices from the spiceworks inventory
- add a comment to a ticket
- get ticket
- update ticket
- get device hardware, software, and network details
- spiceworks
- list all comments on a ticket
- ticket comment management
- inventory
- ticketing
- list tickets
- list all managed it devices
- add ticket comment
- update ticket status, priority, or assignee
- get hardware specs, software inventory, and network details for a device
- user and technician management
- list platform users and technicians
slug: it-management
source_filename: it-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Spiceworks IT Management\"\n  description: >-\n    Workflow capability for IT professionals using Spiceworks to manage help desk\n    ticketing, device inventory, and user administration. Combines ticket lifecycle\n    management with device inventory lookup for unified IT operations workflows.\n    Suitable for IT managers, technicians, and help desk administrators who need\n    to correlate support requests with asset information.\n  tags:\n    - Spiceworks\n    - Help Desk\n    - IT Management\n    - Ticketing\n    - Inventory\n    - IT Operations\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SPICEWORKS_OAUTH_TOKEN: SPICEWORKS_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: spiceworks\n      location: ./shared/cloud-apps.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: spiceworks-it-management-api\n      description: \"Unified REST API for\
  \ Spiceworks IT management workflows.\"\n      resources:\n        - path: /v1/tickets\n          name: tickets\n          description: \"Help Desk ticket management\"\n          operations:\n            - method: GET\n              name: list-tickets\n              description: \"List all Help Desk tickets\"\n              call: \"spiceworks.list-tickets\"\n              with:\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-ticket\n              description: \"Create a new Help Desk ticket\"\n              call: \"spiceworks.create-ticket\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tickets/{id}\n          name: ticket\n          description: \"Individual ticket operations\"\n          operations:\n            - method: GET\n              name: get-ticket\n    \
  \          description: \"Get full ticket details including comments\"\n              call: \"spiceworks.get-ticket\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-ticket\n              description: \"Update ticket status, priority, or assignee\"\n              call: \"spiceworks.update-ticket\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tickets/{id}/comments\n          name: ticket-comments\n          description: \"Ticket comment management\"\n          operations:\n            - method: GET\n              name: list-comments\n              description: \"List all comments on a ticket\"\n              call: \"spiceworks.list-comments\"\n              with:\n                ticket_id: \"rest.id\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: add-comment\n              description: \"Add a comment to a ticket\"\n              call: \"spiceworks.add-comment\"\n              with:\n                ticket_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/devices\n          name: devices\n          description: \"IT device inventory\"\n          operations:\n            - method: GET\n              name: list-devices\n              description: \"List all managed IT devices\"\n              call: \"spiceworks.list-devices\"\n              with:\n                type: \"rest.type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/devices/{id}\n          name: device\n          description: \"Individual device details\"\n    \
  \      operations:\n            - method: GET\n              name: get-device\n              description: \"Get device hardware, software, and network details\"\n              call: \"spiceworks.get-device\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users\n          name: users\n          description: \"User and technician management\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List platform users and technicians\"\n              call: \"spiceworks.list-users\"\n              with:\n                role: \"rest.role\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: spiceworks-it-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted IT help desk and inventory\
  \ management.\"\n      tools:\n        - name: list-tickets\n          description: \"List Help Desk tickets, optionally filtered by status or assignee\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spiceworks.list-tickets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-ticket\n          description: \"Get full details of a Help Desk ticket including all comments\"\n          hints:\n            readOnly: true\n          call: \"spiceworks.get-ticket\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-ticket\n          description: \"Create a new Help Desk support ticket\"\n          hints:\n            readOnly: false\n          call: \"spiceworks.create-ticket\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-ticket\n\
  \          description: \"Update ticket status, priority, or assignee\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"spiceworks.update-ticket\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-ticket-comment\n          description: \"Add a public or internal comment to a Help Desk ticket\"\n          hints:\n            readOnly: false\n          call: \"spiceworks.add-comment\"\n          with:\n            ticket_id: \"tools.ticket_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-devices\n          description: \"List all managed IT devices from the Spiceworks inventory\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spiceworks.list-devices\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: get-device\n          description: \"Get hardware specs, software inventory, and network details for a device\"\n          hints:\n            readOnly: true\n          call: \"spiceworks.get-device\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-users\n          description: \"List Spiceworks users and technicians\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spiceworks.list-users\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spiceworks/refs/heads/main/capabilities/it-management.yaml
tags:
- Spiceworks
- Help Desk
- IT Management
- Ticketing
- Inventory
- IT Operations
tools:
- description: List Help Desk tickets, optionally filtered by status or assignee
  hints:
    openWorld: true
    readOnly: true
  name: list-tickets
- description: Get full details of a Help Desk ticket including all comments
  hints:
    readOnly: true
  name: get-ticket
- description: Create a new Help Desk support ticket
  hints:
    readOnly: false
  name: create-ticket
- description: Update ticket status, priority, or assignee
  hints:
    idempotent: true
    readOnly: false
  name: update-ticket
- description: Add a public or internal comment to a Help Desk ticket
  hints:
    readOnly: false
  name: add-ticket-comment
- description: List all managed IT devices from the Spiceworks inventory
  hints:
    openWorld: true
    readOnly: true
  name: list-devices
- description: Get hardware specs, software inventory, and network details for a device
  hints:
    readOnly: true
  name: get-device
- description: List Spiceworks users and technicians
  hints:
    openWorld: true
    readOnly: true
  name: list-users
---
