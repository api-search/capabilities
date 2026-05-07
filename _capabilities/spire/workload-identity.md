---
categories: []
consumed_apis: []
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
- check spire liveness
- json web key set for jwt-svid verification.
- get liveness
- get openid configuration
- get oidc configuration
- retrieve public keys used to verify jwt-svids.
- cloud native
- oidc
- authentication
- health
- check if the spire component process is alive.
- graduated
- identity
- get jwt signing keys
- get readiness
- check if the spire component is ready to serve identity requests.
- check if the spire component process is alive and running.
- check if the spire component is ready to serve requests.
- spire component liveness probe.
- retrieve the oidc provider configuration document.
- check spire readiness
- zero trust
- retrieve the oidc discovery document describing spire's identity provider configuration for jwt-svid validation.
- get jwks
- openid connect discovery document from spire.
- security
- spire component readiness probe.
- retrieve the json web key set containing public keys for verifying jwt-svids issued by spire.
slug: workload-identity
source_filename: workload-identity.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SPIRE Workload Identity\n  description: Unified SPIRE capability for workload identity verification and health monitoring. Combines the SPIRE health\n    check and OIDC discovery APIs to support operators managing SPIRE deployments — verifying component readiness, retrieving\n    OIDC configuration, and inspecting JWT signing keys for federation and token validation.\n  tags:\n  - Security\n  - Identity\n  - Zero Trust\n  - Cloud Native\n  - OIDC\n  - Health\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SPIRE_HOST: SPIRE_HOST\n    SPIRE_PORT: SPIRE_PORT\n    SPIRE_OIDC_DOMAIN: SPIRE_OIDC_DOMAIN\ncapability:\n  consumes:\n  - type: http\n    namespace: spire-health\n    baseUri: http://{{SPIRE_HOST}}:{{SPIRE_PORT}}\n    description: SPIRE liveness and readiness health check endpoints.\n    resources:\n    - name: health\n      path: /\n      description: SPIRE health check probes.\n      operations:\n\
  \      - name: get-liveness\n        method: GET\n        description: Returns HTTP 200 if the SPIRE component process is alive.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-readiness\n        method: GET\n        description: Returns HTTP 200 if the SPIRE component is ready to serve requests.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: spire-oidc\n    baseUri: https://{{SPIRE_OIDC_DOMAIN}}\n    description: SPIRE OIDC Discovery Provider endpoints.\n    resources:\n    - name: discovery\n      path: /.well-known\n      description: OpenID Connect discovery document endpoint.\n      operations:\n      - name: get-openid-configuration\n        method: GET\n        description: Returns the OpenID Connect discovery document.\n\
  \        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: keys\n      path: /keys\n      description: JSON Web Key Set endpoint.\n      operations:\n      - name: get-jwks\n        method: GET\n        description: Returns the JSON Web Key Set for JWT-SVID verification.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: spire-workload-identity-api\n    description: Unified REST API for SPIRE workload identity operations.\n    resources:\n    - path: /v1/health/live\n      name: liveness\n      description: SPIRE component liveness probe.\n      operations:\n      - method: GET\n        name: get-liveness\n        description: Check if the SPIRE component process is alive.\n        call: spire-health.get-liveness\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/health/ready\n      name: readiness\n      description: SPIRE component readiness probe.\n      operations:\n      - method: GET\n        name: get-readiness\n        description: Check if the SPIRE component is ready to serve requests.\n        call: spire-health.get-readiness\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/oidc/discovery\n      name: oidc-discovery\n      description: OpenID Connect discovery document from SPIRE.\n      operations:\n      - method: GET\n        name: get-openid-configuration\n        description: Retrieve the OIDC provider configuration document.\n        call: spire-oidc.get-openid-configuration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/oidc/keys\n      name: oidc-keys\n      description: JSON Web Key Set for JWT-SVID verification.\n      operations:\n      - method: GET\n\
  \        name: get-jwks\n        description: Retrieve public keys used to verify JWT-SVIDs.\n        call: spire-oidc.get-jwks\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: spire-workload-identity-mcp\n    transport: http\n    description: MCP server for AI-assisted SPIRE workload identity management.\n    tools:\n    - name: check-spire-liveness\n      description: Check if the SPIRE component process is alive and running.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: spire-health.get-liveness\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-spire-readiness\n      description: Check if the SPIRE component is ready to serve identity requests.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: spire-health.get-readiness\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-oidc-configuration\n\
  \      description: Retrieve the OIDC discovery document describing SPIRE's identity provider configuration for JWT-SVID validation.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: spire-oidc.get-openid-configuration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-jwt-signing-keys\n      description: Retrieve the JSON Web Key Set containing public keys for verifying JWT-SVIDs issued by SPIRE.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: spire-oidc.get-jwks\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
