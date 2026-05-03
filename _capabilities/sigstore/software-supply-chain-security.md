---
api_specs:
- filename: rekor-openapi.yaml
  format: yaml
  label: rekor
  slug: rekor
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/sigstore/refs/heads/main/openapi/rekor-openapi.yaml
- filename: fulcio-openapi.json
  format: json
  label: fulcio
  slug: fulcio
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/sigstore/refs/heads/main/openapi/fulcio-openapi.json
categories: []
consumed_apis:
- rekor
- fulcio
description: Unified software supply chain security workflow combining Sigstore's Rekor transparency log and Fulcio certificate authority. Enables artifact signing, verification, certificate issuance, and transparency log auditing for DevOps engineers, security teams, and platform administrators building secure software delivery pipelines.
layout: capability
name: Sigstore Software Supply Chain Security
operations:
- description: Add a signed artifact to the Rekor transparency log
  method: POST
  name: create-log-entry
  path: /v1/log-entries
- description: Search transparency log entries by UUID or log index
  method: POST
  name: search-log-entries
  path: /v1/log-entries
- description: Retrieve a specific log entry including inclusion proof
  method: GET
  name: get-log-entry
  path: /v1/log-entries/{entryUUID}
- description: Find log entries by artifact hash or signer identity
  method: POST
  name: search-artifact
  path: /v1/index
- description: Get current log tree information and size
  method: GET
  name: get-log-info
  path: /v1/log
- description: Issue a short-lived X.509 signing certificate via Fulcio
  method: POST
  name: create-signing-certificate
  path: /v1/signing-certificates
- description: Retrieve the Fulcio CA trust bundle
  method: GET
  name: get-trust-bundle
  path: /v1/trust-bundle
- description: Get the supported OIDC identity providers for keyless signing
  method: GET
  name: get-ca-configuration
  path: /v1/configuration
personas: []
provider_name: Sigstore
provider_slug: sigstore
search_terms:
- transparency log
- certificate authority
- get log entry
- rekor get log entry
- security
- fulcio get trust bundle
- create signing certificate
- software supply chain
- transparency log entries for signed artifacts
- transparency log status and tree information
- open source
- devsecops
- submit a signed artifact to the rekor transparency log to create an immutable audit record
- request a short-lived x.509 signing certificate from fulcio using oidc identity token
- search transparency log by artifact metadata
- retrieve a specific rekor transparency log entry by uuid, including the inclusion proof
- get the fulcio ca configuration including all supported oidc identity providers
- cryptography
- search log entries
- search transparency log entries by uuid or log index
- issue a short-lived x.509 signing certificate via fulcio
- get the supported oidc identity providers for keyless signing
- code signing
- get ca configuration
- fulcio get configuration
- rekor get log info
- retrieve the fulcio ca trust bundle
- create log entry
- retrieve a specific log entry including inclusion proof
- get trust bundle
- retrieve multiple rekor log entries by uuids or log indexes
- containers
- get log info
- ca trust bundle for certificate verification
- fulcio ca oidc issuer configuration
- rekor search entries
- get current rekor transparency log tree size and signed tree head information
- get current log tree information and size
- add a signed artifact to the rekor transparency log
- search the rekor index to find log entries for a specific artifact hash or signer email
- fulcio create signing certificate
- retrieve the fulcio ca root and intermediate certificates for offline verification
- search artifact
- rekor search artifact
- find log entries by artifact hash or signer identity
- pki
- rekor create log entry
- individual transparency log entry
- short-lived signing certificate issuance
slug: software-supply-chain-security
source_filename: software-supply-chain-security.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sigstore Software Supply Chain Security\"\n  description: >-\n    Unified software supply chain security workflow combining Sigstore's Rekor\n    transparency log and Fulcio certificate authority. Enables artifact signing,\n    verification, certificate issuance, and transparency log auditing for DevOps\n    engineers, security teams, and platform administrators building secure software\n    delivery pipelines.\n  tags:\n    - Certificate Authority\n    - Code Signing\n    - Cryptography\n    - DevSecOps\n    - Open Source\n    - PKI\n    - Security\n    - Software Supply Chain\n    - Transparency Log\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      REKOR_BASE_URL: REKOR_BASE_URL\n      FULCIO_BASE_URL: FULCIO_BASE_URL\n\ncapability:\n  consumes:\n    - import: rekor\n      location: ./shared/rekor.yaml\n    - import: fulcio\n      location: ./shared/fulcio.yaml\n\n  exposes:\n\
  \    - type: rest\n      port: 8080\n      namespace: sigstore-supply-chain-api\n      description: \"Unified REST API for Sigstore software supply chain security workflows.\"\n      resources:\n        - path: /v1/log-entries\n          name: log-entries\n          description: Transparency log entries for signed artifacts\n          operations:\n            - method: POST\n              name: create-log-entry\n              description: Add a signed artifact to the Rekor transparency log\n              call: \"rekor.create-log-entry\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n            - method: POST\n              name: search-log-entries\n              description: Search transparency log entries by UUID or log index\n              call: \"rekor.search-log-entries\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/log-entries/{entryUUID}\n       \
  \   name: log-entry\n          description: Individual transparency log entry\n          operations:\n            - method: GET\n              name: get-log-entry\n              description: Retrieve a specific log entry including inclusion proof\n              call: \"rekor.get-log-entry\"\n              with:\n                entryUUID: \"rest.entryUUID\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/index\n          name: artifact-index\n          description: Search transparency log by artifact metadata\n          operations:\n            - method: POST\n              name: search-artifact\n              description: Find log entries by artifact hash or signer identity\n              call: \"rekor.search-index\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/log\n          name: log-info\n          description: Transparency log status\
  \ and tree information\n          operations:\n            - method: GET\n              name: get-log-info\n              description: Get current log tree information and size\n              call: \"rekor.get-log-info\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/signing-certificates\n          name: signing-certificates\n          description: Short-lived signing certificate issuance\n          operations:\n            - method: POST\n              name: create-signing-certificate\n              description: Issue a short-lived X.509 signing certificate via Fulcio\n              call: \"fulcio.create-signing-cert\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/trust-bundle\n          name: trust-bundle\n          description: CA trust bundle for certificate verification\n          operations:\n            - method: GET\n         \
  \     name: get-trust-bundle\n              description: Retrieve the Fulcio CA trust bundle\n              call: \"fulcio.get-trust-bundle\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/configuration\n          name: ca-configuration\n          description: Fulcio CA OIDC issuer configuration\n          operations:\n            - method: GET\n              name: get-ca-configuration\n              description: Get the supported OIDC identity providers for keyless signing\n              call: \"fulcio.get-configuration\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: sigstore-supply-chain-mcp\n      transport: http\n      description: \"MCP server for AI-assisted software supply chain security, artifact signing, and transparency log auditing.\"\n      tools:\n        - name: rekor-create-log-entry\n   \
  \       description: Submit a signed artifact to the Rekor transparency log to create an immutable audit record\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"rekor.create-log-entry\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: rekor-get-log-entry\n          description: Retrieve a specific Rekor transparency log entry by UUID, including the inclusion proof\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"rekor.get-log-entry\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: rekor-search-artifact\n          description: Search the Rekor index to find log entries for a specific artifact hash or signer email\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"rekor.search-index\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: rekor-search-entries\n          description: Retrieve multiple Rekor log entries by UUIDs or log indexes\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"rekor.search-log-entries\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: rekor-get-log-info\n          description: Get current Rekor transparency log tree size and signed tree head information\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"rekor.get-log-info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: fulcio-create-signing-certificate\n          description: Request a short-lived X.509 signing certificate from Fulcio using OIDC identity token\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"fulcio.create-signing-cert\"\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: fulcio-get-trust-bundle\n          description: Retrieve the Fulcio CA root and intermediate certificates for offline verification\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"fulcio.get-trust-bundle\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: fulcio-get-configuration\n          description: Get the Fulcio CA configuration including all supported OIDC identity providers\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"fulcio.get-configuration\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sigstore/refs/heads/main/capabilities/software-supply-chain-security.yaml
tags:
- Certificate Authority
- Code Signing
- Cryptography
- DevSecOps
- Open Source
- PKI
- Security
- Software Supply Chain
- Transparency Log
tools:
- description: Submit a signed artifact to the Rekor transparency log to create an immutable audit record
  hints:
    idempotent: false
    readOnly: false
  name: rekor-create-log-entry
- description: Retrieve a specific Rekor transparency log entry by UUID, including the inclusion proof
  hints:
    idempotent: true
    readOnly: true
  name: rekor-get-log-entry
- description: Search the Rekor index to find log entries for a specific artifact hash or signer email
  hints:
    idempotent: true
    readOnly: true
  name: rekor-search-artifact
- description: Retrieve multiple Rekor log entries by UUIDs or log indexes
  hints:
    idempotent: true
    readOnly: true
  name: rekor-search-entries
- description: Get current Rekor transparency log tree size and signed tree head information
  hints:
    idempotent: true
    readOnly: true
  name: rekor-get-log-info
- description: Request a short-lived X.509 signing certificate from Fulcio using OIDC identity token
  hints:
    idempotent: false
    readOnly: false
  name: fulcio-create-signing-certificate
- description: Retrieve the Fulcio CA root and intermediate certificates for offline verification
  hints:
    idempotent: true
    readOnly: true
  name: fulcio-get-trust-bundle
- description: Get the Fulcio CA configuration including all supported OIDC identity providers
  hints:
    idempotent: true
    readOnly: true
  name: fulcio-get-configuration
---
