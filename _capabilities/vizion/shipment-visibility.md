---
categories: []
consumed_apis: []
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
- container tracking
- logistics
- get reference
- container tracking subscriptions.
- cancel tracking and remove reference.
- create reference
- subscribe to tracking for a container.
- 'retrieve all tracking milestone events for a container: loading, departure, transshipment, arrival, customs clearance, and delivery events.'
- list container subscriptions
- cancel container tracking
- list tracking events
- supply chain
- individual container reference details.
- get container status
- list all active container tracking subscriptions in the account.
- container tracking milestone events.
- vizion
- ocean freight
- list all active container tracking references.
- webhooks
- delete reference
- track container
- get shipment milestones
- retrieve all tracking events for a container.
- get reference status and metadata.
- subscribe to real-time tracking for a container. provide the container id and carrier scac code (e.g. mscu for msc, maeu for maersk). optionally supply a webhook url for push updates.
- list references
- shipping
- cancel tracking for a container and remove the reference. no further updates will be sent.
- get the current tracking status for a specific container reference, including whether it is actively receiving updates.
slug: shipment-visibility
source_filename: shipment-visibility.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Vizion Shipment Visibility Workflow\n  description: Workflow capability for supply chain and logistics teams needing end-to-end container shipment visibility.\n    Combines the Vizion Container Tracking API to manage subscriptions, monitor milestone events, and surface estimated and\n    actual arrival/departure times. Supports both real-time webhook and polling-based integration patterns.\n  tags:\n  - Vizion\n  - Container Tracking\n  - Logistics\n  - Ocean Freight\n  - Shipping\n  - Supply Chain\n  - Webhooks\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VIZION_API_KEY: VIZION_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: vizion\n    baseUri: https://prod.vizionapi.com\n    description: Vizion Container Tracking REST API.\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{VIZION_API_KEY}}'\n      placement: header\n    resources:\n    - name:\
  \ references\n      path: /references\n      description: Container tracking subscription management.\n      operations:\n      - name: list-references\n        method: GET\n        description: List all active container tracking references.\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-reference\n        method: POST\n        description: Subscribe to tracking updates for a container.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            container_id: '{{tools.container_id}}'\n\
  \            carrier_code: '{{tools.carrier_code}}'\n            callback_url: '{{tools.callback_url}}'\n    - name: reference-detail\n      path: /references/{reference_id}\n      description: Individual container tracking reference.\n      operations:\n      - name: get-reference\n        method: GET\n        description: Get status and metadata for a specific reference.\n        inputParameters:\n        - name: reference_id\n          in: path\n          type: string\n          required: true\n          description: Reference ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-reference\n        method: DELETE\n        description: Cancel tracking and delete a container reference.\n        inputParameters:\n        - name: reference_id\n          in: path\n          type: string\n          required: true\n          description: Reference ID\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: reference-updates\n      path: /references/{reference_id}/updates\n      description: Tracking event updates for a reference (polling).\n      operations:\n      - name: list-reference-updates\n        method: GET\n        description: List all tracking milestone events for a container reference.\n        inputParameters:\n        - name: reference_id\n          in: path\n          type: string\n          required: true\n          description: Reference ID\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace:\
  \ vizion-shipment-api\n    description: Unified REST API for container shipment visibility workflows.\n    resources:\n    - path: /v1/references\n      name: references\n      description: Container tracking subscriptions.\n      operations:\n      - method: GET\n        name: list-references\n        description: List all active container tracking references.\n        call: vizion.list-references\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-reference\n        description: Subscribe to tracking for a container.\n        call: vizion.create-reference\n        with:\n          container_id: rest.container_id\n          carrier_code: rest.carrier_code\n          callback_url: rest.callback_url\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/references/{reference_id}\n      name: reference-detail\n      description: Individual container reference details.\n      operations:\n\
  \      - method: GET\n        name: get-reference\n        description: Get reference status and metadata.\n        call: vizion.get-reference\n        with:\n          reference_id: rest.reference_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-reference\n        description: Cancel tracking and remove reference.\n        call: vizion.delete-reference\n        with:\n          reference_id: rest.reference_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/references/{reference_id}/updates\n      name: tracking-events\n      description: Container tracking milestone events.\n      operations:\n      - method: GET\n        name: list-tracking-events\n        description: Retrieve all tracking events for a container.\n        call: vizion.list-reference-updates\n        with:\n          reference_id: rest.reference_id\n        outputParameters:\n        - type: object\n \
  \         mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: vizion-shipment-mcp\n    transport: http\n    description: MCP server for AI-assisted container shipment visibility and logistics workflows.\n    tools:\n    - name: list-container-subscriptions\n      description: List all active container tracking subscriptions in the account.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vizion.list-references\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: track-container\n      description: Subscribe to real-time tracking for a container. Provide the container ID and carrier SCAC code (e.g. MSCU\n        for MSC, MAEU for Maersk). Optionally supply a webhook URL for push updates.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: vizion.create-reference\n      with:\n        container_id: tools.container_id\n        carrier_code: tools.carrier_code\n        callback_url: tools.callback_url\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-container-status\n      description: Get the current tracking status for a specific container reference, including whether it is actively receiving\n        updates.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vizion.get-reference\n      with:\n        reference_id: tools.reference_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-shipment-milestones\n      description: 'Retrieve all tracking milestone events for a container: loading, departure, transshipment, arrival, customs\n        clearance, and delivery events.'\n      hints:\n        readOnly: true\n        idempotent: true\n      call: vizion.list-reference-updates\n      with:\n        reference_id: tools.reference_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-container-tracking\n      description: Cancel tracking for a container\
  \ and remove the reference. No further updates will be sent.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: vizion.delete-reference\n      with:\n        reference_id: tools.reference_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
