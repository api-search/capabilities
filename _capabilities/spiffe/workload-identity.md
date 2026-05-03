---
categories: []
consumed_apis:
- spiffe-federation
description: Workflow capability for SPIFFE-based workload identity and federation operations. Combines the SPIFFE Federation Bundle Endpoint for cross-domain trust bundle retrieval with identity verification workflows. Designed for platform engineers and security teams implementing zero-trust workload authentication using SPIFFE/SPIRE identity infrastructure.
layout: capability
name: SPIFFE Workload Identity
operations:
- description: Retrieve the SPIFFE trust bundle for a trust domain
  method: GET
  name: get-trust-bundle
  path: /v1/bundle
personas: []
provider_name: SPIFFE
provider_slug: spiffe
search_terms:
- federation
- workload identity
- spiffe trust bundle management
- retrieve the spiffe trust bundle for a trust domain
- cloud native
- zero trust
- security
- mtls
- graduated
- identity
- spiffe
- authentication
- get trust bundle
- retrieve the spiffe trust bundle (jwks) for a given trust domain. used to validate x.509-svids and jwt-svids issued by that trust domain.
slug: workload-identity
source_filename: workload-identity.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SPIFFE Workload Identity\"\n  description: >-\n    Workflow capability for SPIFFE-based workload identity and federation operations.\n    Combines the SPIFFE Federation Bundle Endpoint for cross-domain trust bundle\n    retrieval with identity verification workflows. Designed for platform engineers\n    and security teams implementing zero-trust workload authentication using\n    SPIFFE/SPIRE identity infrastructure.\n  tags:\n    - SPIFFE\n    - Identity\n    - Security\n    - Zero Trust\n    - Federation\n    - Workload Identity\n    - mTLS\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\ncapability:\n  consumes:\n    - import: spiffe-federation\n      location: ./shared/federation.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: spiffe-workload-identity-api\n      description: \"Unified REST API for SPIFFE workload identity and federation workflows.\"\n      resources:\n        - path: /v1/bundle\n\
  \          name: trust-bundle\n          description: \"SPIFFE trust bundle management\"\n          operations:\n            - method: GET\n              name: get-trust-bundle\n              description: \"Retrieve the SPIFFE trust bundle for a trust domain\"\n              call: \"spiffe-federation.get-trust-bundle\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: spiffe-workload-identity-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SPIFFE workload identity and federation management.\"\n      tools:\n        - name: get-trust-bundle\n          description: \"Retrieve the SPIFFE trust bundle (JWKS) for a given trust domain. Used to validate X.509-SVIDs and JWT-SVIDs issued by that trust domain.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"spiffe-federation.get-trust-bundle\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spiffe/refs/heads/main/capabilities/workload-identity.yaml
tags:
- SPIFFE
- Identity
- Security
- Zero Trust
- Federation
- Workload Identity
- mTLS
tools:
- description: Retrieve the SPIFFE trust bundle (JWKS) for a given trust domain. Used to validate X.509-SVIDs and JWT-SVIDs issued by that trust domain.
  hints:
    openWorld: false
    readOnly: true
  name: get-trust-bundle
---
