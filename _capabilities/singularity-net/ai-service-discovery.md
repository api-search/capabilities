---
api_specs:
- filename: singularitynet-marketplace-openapi.yml
  format: yaml
  label: singularitynet
  slug: singularitynet
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/singularity-net/refs/heads/main/openapi/singularitynet-marketplace-openapi.yml
categories: []
consumed_apis:
- singularitynet
description: Workflow capability for discovering, evaluating, and accessing AI services on the SingularityNET decentralized marketplace. Covers organization browsing, service discovery and metadata, endpoint retrieval, and payment channel management for service access.
layout: capability
name: SingularityNET AI Service Discovery
operations:
- description: List all AI service publishing organizations on the network.
  method: GET
  name: list-organizations
  path: /v1/organizations
- description: Get organization profile and contact information.
  method: GET
  name: get-organization
  path: /v1/organizations/{id}
- description: List all AI services published by a specific organization.
  method: GET
  name: list-org-services
  path: /v1/organizations/{id}/services
- description: Search and browse all AI services on the marketplace.
  method: GET
  name: list-services
  path: /v1/services
- description: Get full service metadata including pricing and gRPC endpoints.
  method: GET
  name: get-service
  path: /v1/organizations/{org_id}/services/{id}
- description: Get service endpoint groups and pricing.
  method: GET
  name: list-service-groups
  path: /v1/organizations/{org_id}/services/{id}/groups
- description: Open an MPE payment channel to fund AI service calls.
  method: POST
  name: open-payment-channel
  path: /v1/channels
- description: Get payment channel balance and expiration status.
  method: GET
  name: get-channel
  path: /v1/channels/{id}
- description: Add funds or extend channel expiration.
  method: POST
  name: extend-channel
  path: /v1/channels/{id}/extend
personas: []
provider_name: SingularityNET
provider_slug: singularity-net
search_terms:
- open an mpe payment channel to fund ai service calls.
- list organizations
- services by organization.
- payment channel management.
- single ai service metadata.
- get payment channel balance and expiration status.
- list org services
- list all ai services published by a specific organization.
- get service
- get details about a specific ai service provider organization.
- list all ai service publishing organizations on the network.
- check the balance and expiration of a payment channel.
- add asi token funds or extend the expiration of an existing payment channel.
- ai marketplace
- decentralized ai
- service discovery
- open payment channel
- list service groups
- get organization profile and contact information.
- blockchain
- artificial intelligence
- single payment channel.
- web3
- channel extension.
- get full service metadata including pricing and grpc endpoints.
- single organization details.
- list services
- get service endpoint groups, grpc daemon addresses, and pricing for an ai service.
- ai service provider organizations.
- search and browse ai services on the singularitynet marketplace by keyword or tag.
- get channel
- search and browse all ai services on the marketplace.
- service endpoint groups.
- get service endpoint groups and pricing.
- get organization
- open a multi-party escrow payment channel with asi tokens to fund ai service calls.
- add funds or extend channel expiration.
- ai service marketplace.
- extend channel
- get full metadata for a specific ai service including pricing, endpoints, and api specification.
- list all ai service publishing organizations on the singularitynet network.
slug: ai-service-discovery
source_filename: ai-service-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SingularityNET AI Service Discovery\"\n  description: \"Workflow capability for discovering, evaluating, and accessing AI services on the SingularityNET decentralized marketplace. Covers organization browsing, service discovery and metadata, endpoint retrieval, and payment channel management for service access.\"\n  tags:\n  - Artificial Intelligence\n  - AI Marketplace\n  - Blockchain\n  - Decentralized AI\n  - Service Discovery\n  - Web3\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SNET_WALLET_ADDRESS: SNET_WALLET_ADDRESS\n\ncapability:\n  consumes:\n    - import: singularitynet\n      location: ./shared/singularitynet-marketplace.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: ai-discovery-api\n      description: \"Unified REST API for AI service discovery and access management on SingularityNET.\"\n      resources:\n        - path: /v1/organizations\n\
  \          name: organizations\n          description: \"AI service provider organizations.\"\n          operations:\n            - method: GET\n              name: list-organizations\n              description: \"List all AI service publishing organizations on the network.\"\n              call: \"singularitynet.list-organizations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/organizations/{id}\n          name: organization\n          description: \"Single organization details.\"\n          operations:\n            - method: GET\n              name: get-organization\n              description: \"Get organization profile and contact information.\"\n              call: \"singularitynet.get-organization\"\n              with:\n                org_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/organizations/{id}/services\n \
  \         name: org-services\n          description: \"Services by organization.\"\n          operations:\n            - method: GET\n              name: list-org-services\n              description: \"List all AI services published by a specific organization.\"\n              call: \"singularitynet.list-org-services\"\n              with:\n                org_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/services\n          name: services\n          description: \"AI service marketplace.\"\n          operations:\n            - method: GET\n              name: list-services\n              description: \"Search and browse all AI services on the marketplace.\"\n              call: \"singularitynet.list-services\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/organizations/{org_id}/services/{id}\n          name: service\n   \
  \       description: \"Single AI service metadata.\"\n          operations:\n            - method: GET\n              name: get-service\n              description: \"Get full service metadata including pricing and gRPC endpoints.\"\n              call: \"singularitynet.get-service\"\n              with:\n                org_id: \"rest.org_id\"\n                service_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/organizations/{org_id}/services/{id}/groups\n          name: service-groups\n          description: \"Service endpoint groups.\"\n          operations:\n            - method: GET\n              name: list-service-groups\n              description: \"Get service endpoint groups and pricing.\"\n              call: \"singularitynet.list-service-groups\"\n              with:\n                org_id: \"rest.org_id\"\n                service_id: \"rest.id\"\n              outputParameters:\n \
  \               - type: object\n                  mapping: \"$.\"\n        - path: /v1/channels\n          name: open-channel\n          description: \"Payment channel management.\"\n          operations:\n            - method: POST\n              name: open-payment-channel\n              description: \"Open an MPE payment channel to fund AI service calls.\"\n              call: \"singularitynet.open-payment-channel\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/channels/{id}\n          name: channel\n          description: \"Single payment channel.\"\n          operations:\n            - method: GET\n              name: get-channel\n              description: \"Get payment channel balance and expiration status.\"\n              call: \"singularitynet.get-channel\"\n              with:\n                channel_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n        - path: /v1/channels/{id}/extend\n          name: extend-channel\n          description: \"Channel extension.\"\n          operations:\n            - method: POST\n              name: extend-channel\n              description: \"Add funds or extend channel expiration.\"\n              call: \"singularitynet.extend-channel\"\n              with:\n                channel_id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: ai-discovery-mcp\n      transport: http\n      description: \"MCP server for AI-assisted discovery and management of decentralized AI services on SingularityNET.\"\n      tools:\n        - name: list-organizations\n          description: \"List all AI service publishing organizations on the SingularityNET network.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"singularitynet.list-organizations\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-organization\n          description: \"Get details about a specific AI service provider organization.\"\n          hints:\n            readOnly: true\n          call: \"singularitynet.get-organization\"\n          with:\n            org_id: \"tools.org_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-org-services\n          description: \"List all AI services published by a specific organization.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"singularitynet.list-org-services\"\n          with:\n            org_id: \"tools.org_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-services\n          description: \"Search and browse AI services on the SingularityNET marketplace by keyword or tag.\"\n      \
  \    hints:\n            readOnly: true\n            openWorld: true\n          call: \"singularitynet.list-services\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-service\n          description: \"Get full metadata for a specific AI service including pricing, endpoints, and API specification.\"\n          hints:\n            readOnly: true\n          call: \"singularitynet.get-service\"\n          with:\n            org_id: \"tools.org_id\"\n            service_id: \"tools.service_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-service-groups\n          description: \"Get service endpoint groups, gRPC daemon addresses, and pricing for an AI service.\"\n          hints:\n            readOnly: true\n          call: \"singularitynet.list-service-groups\"\n          with:\n            org_id: \"tools.org_id\"\n            service_id: \"tools.service_id\"\n   \
  \       outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: open-payment-channel\n          description: \"Open a Multi-Party Escrow payment channel with ASI tokens to fund AI service calls.\"\n          hints:\n            readOnly: false\n          call: \"singularitynet.open-payment-channel\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-channel\n          description: \"Check the balance and expiration of a payment channel.\"\n          hints:\n            readOnly: true\n          call: \"singularitynet.get-channel\"\n          with:\n            channel_id: \"tools.channel_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: extend-channel\n          description: \"Add ASI token funds or extend the expiration of an existing payment channel.\"\n          hints:\n            readOnly: false\n            idempotent: true\n\
  \          call: \"singularitynet.extend-channel\"\n          with:\n            channel_id: \"tools.channel_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/singularity-net/refs/heads/main/capabilities/ai-service-discovery.yaml
tags:
- Artificial Intelligence
- AI Marketplace
- Blockchain
- Decentralized AI
- Service Discovery
- Web3
tools:
- description: List all AI service publishing organizations on the SingularityNET network.
  hints:
    openWorld: true
    readOnly: true
  name: list-organizations
- description: Get details about a specific AI service provider organization.
  hints:
    readOnly: true
  name: get-organization
- description: List all AI services published by a specific organization.
  hints:
    openWorld: true
    readOnly: true
  name: list-org-services
- description: Search and browse AI services on the SingularityNET marketplace by keyword or tag.
  hints:
    openWorld: true
    readOnly: true
  name: list-services
- description: Get full metadata for a specific AI service including pricing, endpoints, and API specification.
  hints:
    readOnly: true
  name: get-service
- description: Get service endpoint groups, gRPC daemon addresses, and pricing for an AI service.
  hints:
    readOnly: true
  name: list-service-groups
- description: Open a Multi-Party Escrow payment channel with ASI tokens to fund AI service calls.
  hints:
    readOnly: false
  name: open-payment-channel
- description: Check the balance and expiration of a payment channel.
  hints:
    readOnly: true
  name: get-channel
- description: Add ASI token funds or extend the expiration of an existing payment channel.
  hints:
    idempotent: true
    readOnly: false
  name: extend-channel
---
