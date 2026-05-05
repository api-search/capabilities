---
api_specs:
- filename: spire-health-openapi.yml
  format: yaml
  label: spire-health
  slug: spire-health
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/spire/refs/heads/main/openapi/spire-health-openapi.yml
- filename: spire-oidc-discovery-openapi.yml
  format: yaml
  label: spire-oidc
  slug: spire-oidc
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/spire/refs/heads/main/openapi/spire-oidc-discovery-openapi.yml
categories: []
consumed_apis:
- spire-health
- spire-oidc
description: Unified SPIRE capability for workload identity verification and health monitoring. Combines the SPIRE health check and OIDC discovery APIs to support operators managing SPIRE deployments — verifying component readiness, retrieving OIDC configuration, and inspecting JWT signing keys for federation and token validation.
layout: capability
name: SPIRE Workload Identity
operations:
- description: Check if the SPIRE component process is alive.
  method: GET
  name: get-liveness
  path: /v1/health/live
- description: Check if the SPIRE component is ready to serve requests.
  method: GET
  name: get-readiness
  path: /v1/health/ready
- description: Retrieve the OIDC provider configuration document.
  method: GET
  name: get-openid-configuration
  path: /v1/oidc/discovery
- description: Retrieve public keys used to verify JWT-SVIDs.
  method: GET
  name: get-jwks
  path: /v1/oidc/keys
personas: []
provider_name: SPIRE
provider_slug: spire
search_terms:
- retrieve the json web key set containing public keys for verifying jwt-svids issued by spire.
- security
- get jwks
- graduated
- check if the spire component process is alive and running.
- spire component liveness probe.
- json web key set for jwt-svid verification.
- get readiness
- get oidc configuration
- get openid configuration
- check spire readiness
- openid connect discovery document from spire.
- get jwt signing keys
- check if the spire component is ready to serve identity requests.
- retrieve the oidc discovery document describing spire's identity provider configuration for jwt-svid validation.
- check if the spire component process is alive.
- cloud native
- oidc
- retrieve public keys used to verify jwt-svids.
- check spire liveness
- get liveness
- retrieve the oidc provider configuration document.
- zero trust
- authentication
- health
- check if the spire component is ready to serve requests.
- spire component readiness probe.
- identity
slug: workload-identity
source_filename: workload-identity.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SPIRE Workload Identity\"\n  description: >-\n    Unified SPIRE capability for workload identity verification and health monitoring.\n    Combines the SPIRE health check and OIDC discovery APIs to support operators\n    managing SPIRE deployments — verifying component readiness, retrieving OIDC\n    configuration, and inspecting JWT signing keys for federation and token validation.\n  tags:\n    - Security\n    - Identity\n    - Zero Trust\n    - Cloud Native\n    - OIDC\n    - Health\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SPIRE_HOST: SPIRE_HOST\n      SPIRE_PORT: SPIRE_PORT\n      SPIRE_OIDC_DOMAIN: SPIRE_OIDC_DOMAIN\n\ncapability:\n  consumes:\n    - import: spire-health\n      location: ./shared/spire-health.yaml\n    - import: spire-oidc\n      location: ./shared/spire-oidc-discovery.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: spire-workload-identity-api\n\
  \      description: \"Unified REST API for SPIRE workload identity operations.\"\n      resources:\n        - path: /v1/health/live\n          name: liveness\n          description: \"SPIRE component liveness probe.\"\n          operations:\n            - method: GET\n              name: get-liveness\n              description: \"Check if the SPIRE component process is alive.\"\n              call: \"spire-health.get-liveness\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/health/ready\n          name: readiness\n          description: \"SPIRE component readiness probe.\"\n          operations:\n            - method: GET\n              name: get-readiness\n              description: \"Check if the SPIRE component is ready to serve requests.\"\n              call: \"spire-health.get-readiness\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path:\
  \ /v1/oidc/discovery\n          name: oidc-discovery\n          description: \"OpenID Connect discovery document from SPIRE.\"\n          operations:\n            - method: GET\n              name: get-openid-configuration\n              description: \"Retrieve the OIDC provider configuration document.\"\n              call: \"spire-oidc.get-openid-configuration\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/oidc/keys\n          name: oidc-keys\n          description: \"JSON Web Key Set for JWT-SVID verification.\"\n          operations:\n            - method: GET\n              name: get-jwks\n              description: \"Retrieve public keys used to verify JWT-SVIDs.\"\n              call: \"spire-oidc.get-jwks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: spire-workload-identity-mcp\n      transport:\
  \ http\n      description: \"MCP server for AI-assisted SPIRE workload identity management.\"\n      tools:\n        - name: check-spire-liveness\n          description: \"Check if the SPIRE component process is alive and running.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"spire-health.get-liveness\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: check-spire-readiness\n          description: \"Check if the SPIRE component is ready to serve identity requests.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"spire-health.get-readiness\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-oidc-configuration\n          description: \"Retrieve the OIDC discovery document describing SPIRE's identity provider configuration for JWT-SVID validation.\"\n          hints:\n      \
  \      readOnly: true\n            idempotent: true\n          call: \"spire-oidc.get-openid-configuration\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-jwt-signing-keys\n          description: \"Retrieve the JSON Web Key Set containing public keys for verifying JWT-SVIDs issued by SPIRE.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"spire-oidc.get-jwks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spire/refs/heads/main/capabilities/workload-identity.yaml
tags:
- Security
- Identity
- Zero Trust
- Cloud Native
- OIDC
- Health
tools:
- description: Check if the SPIRE component process is alive and running.
  hints:
    idempotent: true
    readOnly: true
  name: check-spire-liveness
- description: Check if the SPIRE component is ready to serve identity requests.
  hints:
    idempotent: true
    readOnly: true
  name: check-spire-readiness
- description: Retrieve the OIDC discovery document describing SPIRE's identity provider configuration for JWT-SVID validation.
  hints:
    idempotent: true
    readOnly: true
  name: get-oidc-configuration
- description: Retrieve the JSON Web Key Set containing public keys for verifying JWT-SVIDs issued by SPIRE.
  hints:
    idempotent: true
    readOnly: true
  name: get-jwt-signing-keys
---
