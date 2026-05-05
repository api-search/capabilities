---
categories: []
consumed_apis:
- wbd-content
description: Unified workflow for Warner Bros. Discovery content delivery operations. Enables content partners to submit media deliveries, validate metadata against MMC specifications, track delivery status, and manage media assets through WBD's media supply chain for distribution across Max, HBO, Warner Bros., Discovery, CNN, and other WBD brands.
layout: capability
name: WBD Content Delivery Workflow
operations:
- description: List all media content deliveries
  method: GET
  name: list-deliveries
  path: /v1/deliveries
- description: Submit a new content delivery
  method: POST
  name: create-delivery
  path: /v1/deliveries
- description: Get processing status for a delivery
  method: GET
  name: get-delivery-status
  path: /v1/deliveries/{deliveryId}/status
- description: Validate MMC metadata before submission
  method: POST
  name: validate-metadata
  path: /v1/metadata/validate
- description: List media assets
  method: GET
  name: list-assets
  path: /v1/assets
personas: []
provider_name: Warner Bros. Discovery
provider_slug: warner-bros-discovery
search_terms:
- get processing status for a delivery
- validate metadata
- media asset management
- delivery processing status
- list deliveries
- list assets
- list all media content deliveries in the wbd partner supply chain
- submit a new media content delivery to wbd supply chain
- validate mmc metadata before submission
- metadata
- validate mmc metadata against wbd specifications before submission
- content delivery management
- streaming
- list media assets associated with wbd deliveries
- submit metadata
- create delivery
- warner bros. discovery
- entertainment
- media supply chain
- television
- media
- list media assets
- get delivery status
- list all media content deliveries
- content
- film
- get the current processing status of a wbd content delivery
- submit movielabs mmc metadata for a content delivery
- content delivery
- metadata validation
- submit a new content delivery
slug: content-delivery
source_filename: content-delivery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"WBD Content Delivery Workflow\"\n  description: >-\n    Unified workflow for Warner Bros. Discovery content delivery operations.\n    Enables content partners to submit media deliveries, validate metadata against\n    MMC specifications, track delivery status, and manage media assets through\n    WBD's media supply chain for distribution across Max, HBO, Warner Bros.,\n    Discovery, CNN, and other WBD brands.\n  tags:\n    - Warner Bros. Discovery\n    - Content Delivery\n    - Media Supply Chain\n    - Metadata\n    - Entertainment\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WBD_ACCESS_TOKEN: WBD_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: wbd-content\n      location: ./shared/content-partner.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: wbd-delivery-api\n      description: \"Unified REST API for WBD content delivery and media supply\
  \ chain operations.\"\n      resources:\n        - path: /v1/deliveries\n          name: deliveries\n          description: Content delivery management\n          operations:\n            - method: GET\n              name: list-deliveries\n              description: List all media content deliveries\n              call: \"wbd-content.list-deliveries\"\n              with:\n                status: \"rest.status\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-delivery\n              description: Submit a new content delivery\n              call: \"wbd-content.create-delivery\"\n              with:\n                title: \"rest.title\"\n                contentType: \"rest.contentType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/deliveries/{deliveryId}/status\n  \
  \        name: delivery-status\n          description: Delivery processing status\n          operations:\n            - method: GET\n              name: get-delivery-status\n              description: Get processing status for a delivery\n              call: \"wbd-content.get-delivery-status\"\n              with:\n                deliveryId: \"rest.deliveryId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/metadata/validate\n          name: metadata-validation\n          description: Metadata validation\n          operations:\n            - method: POST\n              name: validate-metadata\n              description: Validate MMC metadata before submission\n              call: \"wbd-content.validate-metadata\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/assets\n          name: assets\n          description: Media asset management\n\
  \          operations:\n            - method: GET\n              name: list-assets\n              description: List media assets\n              call: \"wbd-content.list-assets\"\n              with:\n                deliveryId: \"rest.deliveryId\"\n                assetType: \"rest.assetType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: wbd-delivery-mcp\n      transport: http\n      description: \"MCP server for AI-assisted WBD content delivery and supply chain operations.\"\n      tools:\n        - name: list-deliveries\n          description: List all media content deliveries in the WBD partner supply chain\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wbd-content.list-deliveries\"\n          with:\n            status: \"tools.status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n  \
  \      - name: create-delivery\n          description: Submit a new media content delivery to WBD supply chain\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"wbd-content.create-delivery\"\n          with:\n            title: \"tools.title\"\n            contentType: \"tools.contentType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-delivery-status\n          description: Get the current processing status of a WBD content delivery\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wbd-content.get-delivery-status\"\n          with:\n            deliveryId: \"tools.deliveryId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: validate-metadata\n          description: Validate MMC metadata against WBD specifications before submission\n          hints:\n\
  \            readOnly: true\n            openWorld: false\n          call: \"wbd-content.validate-metadata\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-metadata\n          description: Submit MovieLabs MMC metadata for a content delivery\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"wbd-content.submit-metadata\"\n          with:\n            deliveryId: \"tools.deliveryId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-assets\n          description: List media assets associated with WBD deliveries\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wbd-content.list-assets\"\n          with:\n            deliveryId: \"tools.deliveryId\"\n            assetType: \"tools.assetType\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/warner-bros-discovery/refs/heads/main/capabilities/content-delivery.yaml
tags:
- Warner Bros. Discovery
- Content Delivery
- Media Supply Chain
- Metadata
- Entertainment
tools:
- description: List all media content deliveries in the WBD partner supply chain
  hints:
    openWorld: false
    readOnly: true
  name: list-deliveries
- description: Submit a new media content delivery to WBD supply chain
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-delivery
- description: Get the current processing status of a WBD content delivery
  hints:
    openWorld: false
    readOnly: true
  name: get-delivery-status
- description: Validate MMC metadata against WBD specifications before submission
  hints:
    openWorld: false
    readOnly: true
  name: validate-metadata
- description: Submit MovieLabs MMC metadata for a content delivery
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submit-metadata
- description: List media assets associated with WBD deliveries
  hints:
    openWorld: false
    readOnly: true
  name: list-assets
---
