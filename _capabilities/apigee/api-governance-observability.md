---
categories: []
consumed_apis:
- api-hub
- apim
- registry
description: Unified workflow for API governance, discovery, and observability using Apigee API Hub for cataloguing, API Observation (APIM) for shadow API discovery, and Registry for tracking specifications.
layout: capability
name: Apigee API Governance and Observability
operations:
- description: List all catalogued APIs.
  method: GET
  name: list-apis
  path: /v1/apis
- description: List observed shadow APIs.
  method: GET
  name: list-observed-apis
  path: /v1/observed-apis
personas: []
provider_name: Apigee
provider_slug: apigee
search_terms:
- developer portal
- manager packaging api products and managing developer relationships.
- list observed apis
- list catalogued apis
- engineer managing api proxies, deployments, and policies in apigee.
- shadow apis discovered via apim.
- enterprise
- apigee
- analytics
- discover shadow apis
- google cloud
- api discovery
- API Governance Lead
- leader establishing api standards, cataloguing apis, and discovering shadow apis.
- list all apis in the apigee api hub catalog.
- Platform Architect
- API Platform Engineer
- api catalog
- hybrid
- microservices
- architect overseeing api platform strategy and governance across the organization.
- integrations
- api governance
- list apis
- api management
- discover undocumented shadow apis in google cloud infrastructure using apim.
- monetization
- api catalog from api hub.
- list observed shadow apis.
- list api specifications tracked in the apigee registry.
- api gateway
- API Product Manager
- list all catalogued apis.
- list api specs
- api hub
slug: api-governance-observability
source_filename: api-governance-observability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Apigee API Governance and Observability\"\n  description: \"Unified workflow for API governance, discovery, and observability using Apigee API Hub for cataloguing, API Observation (APIM) for shadow API discovery, and Registry for tracking specifications.\"\n  tags:\n    - Apigee\n    - API Governance\n    - API Catalog\n    - API Discovery\n    - Google Cloud\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      GOOGLE_ACCESS_TOKEN: GOOGLE_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: api-hub\n      location: ./shared/api-hub.yaml\n    - import: apim\n      location: ./shared/apim.yaml\n    - import: registry\n      location: ./shared/registry.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: apigee-governance-api\n      description: \"Unified REST API for Apigee API governance and observability.\"\n      resources:\n        - path: /v1/apis\n   \
  \       name: api-catalog\n          description: \"API catalog from API Hub.\"\n          operations:\n            - method: GET\n              name: list-apis\n              description: \"List all catalogued APIs.\"\n              call: \"api-hub.listApis\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/observed-apis\n          name: observed-apis\n          description: \"Shadow APIs discovered via APIM.\"\n          operations:\n            - method: GET\n              name: list-observed-apis\n              description: \"List observed shadow APIs.\"\n              call: \"apim.listObservedApis\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: apigee-governance-mcp\n      transport: http\n      description: \"MCP server for AI-assisted API governance and catalog management.\"\n      tools:\n        - name:\
  \ list-catalogued-apis\n          description: \"List all APIs in the Apigee API Hub catalog.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"api-hub.listApis\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: discover-shadow-apis\n          description: \"Discover undocumented shadow APIs in Google Cloud infrastructure using APIM.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"apim.listObservedApis\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-api-specs\n          description: \"List API specifications tracked in the Apigee Registry.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n          call: \"registry.listApiSpecs\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apigee/refs/heads/main/capabilities/api-governance-observability.yaml
tags:
- Apigee
- API Governance
- API Catalog
- API Discovery
- Google Cloud
tools:
- description: List all APIs in the Apigee API Hub catalog.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-catalogued-apis
- description: Discover undocumented shadow APIs in Google Cloud infrastructure using APIM.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: discover-shadow-apis
- description: List API specifications tracked in the Apigee Registry.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-api-specs
---
