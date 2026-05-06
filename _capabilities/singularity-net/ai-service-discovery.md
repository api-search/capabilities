---
categories: []
consumed_apis: []
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
- list all ai service publishing organizations on the network.
- web3
- list all ai service publishing organizations on the singularitynet network.
- blockchain
- search and browse all ai services on the marketplace.
- extend channel
- single organization details.
- channel extension.
- list organizations
- get service endpoint groups and pricing.
- list org services
- list all ai services published by a specific organization.
- single payment channel.
- get service endpoint groups, grpc daemon addresses, and pricing for an ai service.
- get channel
- get organization profile and contact information.
- decentralized ai
- ai service provider organizations.
- list services
- get payment channel balance and expiration status.
- list service groups
- payment channel management.
- search and browse ai services on the singularitynet marketplace by keyword or tag.
- get organization
- service endpoint groups.
- artificial intelligence
- service discovery
- get full metadata for a specific ai service including pricing, endpoints, and api specification.
- get service
- open payment channel
- add funds or extend channel expiration.
- check the balance and expiration of a payment channel.
- get details about a specific ai service provider organization.
- ai service marketplace.
- single ai service metadata.
- ai marketplace
- get full service metadata including pricing and grpc endpoints.
- open a multi-party escrow payment channel with asi tokens to fund ai service calls.
- open an mpe payment channel to fund ai service calls.
- add asi token funds or extend the expiration of an existing payment channel.
- services by organization.
slug: ai-service-discovery
source_filename: ai-service-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SingularityNET AI Service Discovery\n  description: Workflow capability for discovering, evaluating, and accessing AI services on the SingularityNET decentralized\n    marketplace. Covers organization browsing, service discovery and metadata, endpoint retrieval, and payment channel management\n    for service access.\n  tags:\n  - Artificial Intelligence\n  - AI Marketplace\n  - Blockchain\n  - Decentralized AI\n  - Service Discovery\n  - Web3\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SNET_WALLET_ADDRESS: SNET_WALLET_ADDRESS\ncapability:\n  consumes:\n  - type: http\n    namespace: singularitynet\n    baseUri: https://marketplace-mt-v2.singularitynet.io\n    description: SingularityNET AI Marketplace REST API (no auth required for discovery).\n    resources:\n    - name: organizations\n      path: /org\n      description: AI service provider organization management.\n      operations:\n\
  \      - name: list-organizations\n        method: GET\n        description: List all organizations publishing AI services.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization\n      path: /org/{org_id}\n      description: Single organization operations.\n      operations:\n      - name: get-organization\n        method: GET\n        description: Get organization details.\n        inputParameters:\n        - name: org_id\n          in: path\n          type: string\n          required: true\n          description: Organization identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ org-services\n      path: /org/{org_id}/service\n      description: Services published by an organization.\n      operations:\n      - name: list-org-services\n        method: GET\n        description: List AI services by organization.\n        inputParameters:\n        - name: org_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services\n      path: /service\n      description: AI service marketplace discovery.\n      operations:\n      - name: list-services\n        method: GET\n        description: List all AI services on the marketplace.\n        inputParameters:\n        - name: search_string\n          in: query\n          type: string\n          required: false\n        - name: tags\n          in: query\n          type: array\n          required: false\n        - name: limit\n          in: query\n          type: integer\n\
  \          required: false\n        - name: offset\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: service\n      path: /org/{org_id}/service/{service_id}\n      description: Single service metadata.\n      operations:\n      - name: get-service\n        method: GET\n        description: Get full service metadata including pricing and endpoints.\n        inputParameters:\n        - name: org_id\n          in: path\n          type: string\n          required: true\n        - name: service_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: service-groups\n      path: /org/{org_id}/service/{service_id}/group\n      description: Service endpoint groups.\n      operations:\n\
  \      - name: list-service-groups\n        method: GET\n        description: Get service endpoint groups and pricing.\n        inputParameters:\n        - name: org_id\n          in: path\n          type: string\n          required: true\n        - name: service_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: open-channel\n      path: /channel/open\n      description: Payment channel operations.\n      operations:\n      - name: open-payment-channel\n        method: POST\n        description: Open an MPE payment channel to fund AI service calls.\n        body:\n          type: json\n          data:\n            org_id: '{{tools.org_id}}'\n            service_id: '{{tools.service_id}}'\n            group_id: '{{tools.group_id}}'\n            amount_in_cogs: '{{tools.amount_in_cogs}}'\n            expiration: '{{tools.expiration}}'\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: channel\n      path: /channel/{channel_id}\n      description: Payment channel management.\n      operations:\n      - name: get-channel\n        method: GET\n        description: Get payment channel balance and status.\n        inputParameters:\n        - name: channel_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: extend-channel\n      path: /channel/{channel_id}/extend\n      description: Extend payment channel.\n      operations:\n      - name: extend-channel\n        method: POST\n        description: Add funds or extend expiration of a payment channel.\n        inputParameters:\n        - name: channel_id\n          in: path\n          type: string\n          required: true\n   \
  \     body:\n          type: json\n          data:\n            amount: '{{tools.amount}}'\n            expiration: '{{tools.expiration}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ai-discovery-api\n    description: Unified REST API for AI service discovery and access management on SingularityNET.\n    resources:\n    - path: /v1/organizations\n      name: organizations\n      description: AI service provider organizations.\n      operations:\n      - method: GET\n        name: list-organizations\n        description: List all AI service publishing organizations on the network.\n        call: singularitynet.list-organizations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{id}\n      name: organization\n      description: Single organization details.\n      operations:\n      - method:\
  \ GET\n        name: get-organization\n        description: Get organization profile and contact information.\n        call: singularitynet.get-organization\n        with:\n          org_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{id}/services\n      name: org-services\n      description: Services by organization.\n      operations:\n      - method: GET\n        name: list-org-services\n        description: List all AI services published by a specific organization.\n        call: singularitynet.list-org-services\n        with:\n          org_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/services\n      name: services\n      description: AI service marketplace.\n      operations:\n      - method: GET\n        name: list-services\n        description: Search and browse all AI services on the marketplace.\n        call: singularitynet.list-services\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/organizations/{org_id}/services/{id}\n      name: service\n      description: Single AI service metadata.\n      operations:\n      - method: GET\n        name: get-service\n        description: Get full service metadata including pricing and gRPC endpoints.\n        call: singularitynet.get-service\n        with:\n          org_id: rest.org_id\n          service_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{org_id}/services/{id}/groups\n      name: service-groups\n      description: Service endpoint groups.\n      operations:\n      - method: GET\n        name: list-service-groups\n        description: Get service endpoint groups and pricing.\n        call: singularitynet.list-service-groups\n        with:\n          org_id: rest.org_id\n          service_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /v1/channels\n      name: open-channel\n      description: Payment channel management.\n      operations:\n      - method: POST\n        name: open-payment-channel\n        description: Open an MPE payment channel to fund AI service calls.\n        call: singularitynet.open-payment-channel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/channels/{id}\n      name: channel\n      description: Single payment channel.\n      operations:\n      - method: GET\n        name: get-channel\n        description: Get payment channel balance and expiration status.\n        call: singularitynet.get-channel\n        with:\n          channel_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/channels/{id}/extend\n      name: extend-channel\n      description: Channel extension.\n      operations:\n      - method: POST\n        name: extend-channel\n        description: Add funds or extend channel expiration.\n\
  \        call: singularitynet.extend-channel\n        with:\n          channel_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ai-discovery-mcp\n    transport: http\n    description: MCP server for AI-assisted discovery and management of decentralized AI services on SingularityNET.\n    tools:\n    - name: list-organizations\n      description: List all AI service publishing organizations on the SingularityNET network.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: singularitynet.list-organizations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-organization\n      description: Get details about a specific AI service provider organization.\n      hints:\n        readOnly: true\n      call: singularitynet.get-organization\n      with:\n        org_id: tools.org_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    -\
  \ name: list-org-services\n      description: List all AI services published by a specific organization.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: singularitynet.list-org-services\n      with:\n        org_id: tools.org_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-services\n      description: Search and browse AI services on the SingularityNET marketplace by keyword or tag.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: singularitynet.list-services\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-service\n      description: Get full metadata for a specific AI service including pricing, endpoints, and API specification.\n      hints:\n        readOnly: true\n      call: singularitynet.get-service\n      with:\n        org_id: tools.org_id\n        service_id: tools.service_id\n      outputParameters:\n      - type: object\n        mapping: $.\n \
  \   - name: list-service-groups\n      description: Get service endpoint groups, gRPC daemon addresses, and pricing for an AI service.\n      hints:\n        readOnly: true\n      call: singularitynet.list-service-groups\n      with:\n        org_id: tools.org_id\n        service_id: tools.service_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: open-payment-channel\n      description: Open a Multi-Party Escrow payment channel with ASI tokens to fund AI service calls.\n      hints:\n        readOnly: false\n      call: singularitynet.open-payment-channel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-channel\n      description: Check the balance and expiration of a payment channel.\n      hints:\n        readOnly: true\n      call: singularitynet.get-channel\n      with:\n        channel_id: tools.channel_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: extend-channel\n      description:\
  \ Add ASI token funds or extend the expiration of an existing payment channel.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: singularitynet.extend-channel\n      with:\n        channel_id: tools.channel_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
