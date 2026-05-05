---
categories: []
consumed_apis:
- vizion
description: Workflow capability for supply chain and logistics teams needing end-to-end container shipment visibility. Combines the Vizion Container Tracking API to manage subscriptions, monitor milestone events, and surface estimated and actual arrival/departure times. Supports both real-time webhook and polling-based integration patterns.
layout: capability
name: Vizion Shipment Visibility Workflow
operations:
- description: List all active container tracking references.
  method: GET
  name: list-references
  path: /v1/references
- description: Subscribe to tracking for a container.
  method: POST
  name: create-reference
  path: /v1/references
- description: Get reference status and metadata.
  method: GET
  name: get-reference
  path: /v1/references/{reference_id}
- description: Cancel tracking and remove reference.
  method: DELETE
  name: delete-reference
  path: /v1/references/{reference_id}
- description: Retrieve all tracking events for a container.
  method: GET
  name: list-tracking-events
  path: /v1/references/{reference_id}/updates
personas: []
provider_name: Vizion
provider_slug: vizion
search_terms:
- vizion
- list references
- get shipment milestones
- webhooks
- cancel container tracking
- delete reference
- get container status
- list all active container tracking references.
- list container subscriptions
- cancel tracking for a container and remove the reference. no further updates will be sent.
- 'retrieve all tracking milestone events for a container: loading, departure, transshipment, arrival, customs clearance, and delivery events.'
- list all active container tracking subscriptions in the account.
- individual container reference details.
- subscribe to real-time tracking for a container. provide the container id and carrier scac code (e.g. mscu for msc, maeu for maersk). optionally supply a webhook url for push updates.
- container tracking milestone events.
- list tracking events
- container tracking subscriptions.
- subscribe to tracking for a container.
- retrieve all tracking events for a container.
- supply chain
- container tracking
- logistics
- get reference status and metadata.
- get the current tracking status for a specific container reference, including whether it is actively receiving updates.
- cancel tracking and remove reference.
- get reference
- ocean freight
- shipping
- create reference
- track container
slug: shipment-visibility
source_filename: shipment-visibility.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Vizion Shipment Visibility Workflow\"\n  description: >-\n    Workflow capability for supply chain and logistics teams needing end-to-end\n    container shipment visibility. Combines the Vizion Container Tracking API\n    to manage subscriptions, monitor milestone events, and surface estimated\n    and actual arrival/departure times. Supports both real-time webhook and\n    polling-based integration patterns.\n  tags:\n    - Vizion\n    - Container Tracking\n    - Logistics\n    - Ocean Freight\n    - Shipping\n    - Supply Chain\n    - Webhooks\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      VIZION_API_KEY: VIZION_API_KEY\n\ncapability:\n  consumes:\n    - import: vizion\n      location: ./shared/container-tracking.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: vizion-shipment-api\n      description: \"Unified REST API for container shipment visibility\
  \ workflows.\"\n      resources:\n        - path: /v1/references\n          name: references\n          description: \"Container tracking subscriptions.\"\n          operations:\n            - method: GET\n              name: list-references\n              description: \"List all active container tracking references.\"\n              call: \"vizion.list-references\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-reference\n              description: \"Subscribe to tracking for a container.\"\n              call: \"vizion.create-reference\"\n              with:\n                container_id: \"rest.container_id\"\n                carrier_code: \"rest.carrier_code\"\n                callback_url: \"rest.callback_url\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/references/{reference_id}\n          name:\
  \ reference-detail\n          description: \"Individual container reference details.\"\n          operations:\n            - method: GET\n              name: get-reference\n              description: \"Get reference status and metadata.\"\n              call: \"vizion.get-reference\"\n              with:\n                reference_id: \"rest.reference_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-reference\n              description: \"Cancel tracking and remove reference.\"\n              call: \"vizion.delete-reference\"\n              with:\n                reference_id: \"rest.reference_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/references/{reference_id}/updates\n          name: tracking-events\n          description: \"Container tracking milestone events.\"\n          operations:\n\
  \            - method: GET\n              name: list-tracking-events\n              description: \"Retrieve all tracking events for a container.\"\n              call: \"vizion.list-reference-updates\"\n              with:\n                reference_id: \"rest.reference_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: vizion-shipment-mcp\n      transport: http\n      description: \"MCP server for AI-assisted container shipment visibility and logistics workflows.\"\n      tools:\n        - name: list-container-subscriptions\n          description: \"List all active container tracking subscriptions in the account.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vizion.list-references\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: track-container\n          description:\
  \ \"Subscribe to real-time tracking for a container. Provide the container ID and carrier SCAC code (e.g. MSCU for MSC, MAEU for Maersk). Optionally supply a webhook URL for push updates.\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"vizion.create-reference\"\n          with:\n            container_id: \"tools.container_id\"\n            carrier_code: \"tools.carrier_code\"\n            callback_url: \"tools.callback_url\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-container-status\n          description: \"Get the current tracking status for a specific container reference, including whether it is actively receiving updates.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vizion.get-reference\"\n          with:\n            reference_id: \"tools.reference_id\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: get-shipment-milestones\n          description: \"Retrieve all tracking milestone events for a container: loading, departure, transshipment, arrival, customs clearance, and delivery events.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"vizion.list-reference-updates\"\n          with:\n            reference_id: \"tools.reference_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: cancel-container-tracking\n          description: \"Cancel tracking for a container and remove the reference. No further updates will be sent.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"vizion.delete-reference\"\n          with:\n            reference_id: \"tools.reference_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/vizion/refs/heads/main/capabilities/shipment-visibility.yaml
tags:
- Vizion
- Container Tracking
- Logistics
- Ocean Freight
- Shipping
- Supply Chain
- Webhooks
tools:
- description: List all active container tracking subscriptions in the account.
  hints:
    idempotent: true
    readOnly: true
  name: list-container-subscriptions
- description: Subscribe to real-time tracking for a container. Provide the container ID and carrier SCAC code (e.g. MSCU for MSC, MAEU for Maersk). Optionally supply a webhook URL for push updates.
  hints:
    idempotent: false
    readOnly: false
  name: track-container
- description: Get the current tracking status for a specific container reference, including whether it is actively receiving updates.
  hints:
    idempotent: true
    readOnly: true
  name: get-container-status
- description: 'Retrieve all tracking milestone events for a container: loading, departure, transshipment, arrival, customs clearance, and delivery events.'
  hints:
    idempotent: true
    readOnly: true
  name: get-shipment-milestones
- description: Cancel tracking for a container and remove the reference. No further updates will be sent.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-container-tracking
---
