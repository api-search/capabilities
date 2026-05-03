---
categories: []
consumed_apis:
- ssl-tls-cert-mgmt
description: Unified workflow capability for SSL/TLS certificate lifecycle management. Enables security and infrastructure teams to request, monitor, renew, and revoke TLS certificates across domains. Combines certificate issuance, automated renewal workflows, expiry monitoring, and domain verification into a single operational interface.
layout: capability
name: SSL/TLS Certificate Lifecycle
operations:
- description: List certificates with optional status and domain filtering
  method: GET
  name: list-certificates
  path: /v1/certificates
- description: Request a new SSL/TLS certificate for domain validation
  method: POST
  name: request-certificate
  path: /v1/certificates
- description: Get certificate details and PEM data
  method: GET
  name: get-certificate
  path: /v1/certificates/{certificateId}
- description: Download certificate in PEM or PKCS12 format
  method: GET
  name: download-certificate
  path: /v1/certificates/{certificateId}/download
- description: Initiate certificate renewal
  method: POST
  name: renew-certificate
  path: /v1/certificates/{certificateId}/renew
- description: Revoke a certificate with reason code
  method: POST
  name: revoke-certificate
  path: /v1/certificates/{certificateId}/revoke
- description: List certificate orders
  method: GET
  name: list-orders
  path: /v1/orders
- description: Get order details with challenge status
  method: GET
  name: get-order
  path: /v1/orders/{orderId}
- description: List domains and validation status
  method: GET
  name: list-domains
  path: /v1/domains
- description: Get certificates expiring within N days
  method: GET
  name: get-expiring-certificates
  path: /v1/monitoring/expiring
personas: []
provider_name: SSL/TLS
provider_slug: ssl-tls
search_terms:
- certificate authority
- request certificate
- security
- get ssl/tls certificate details including pem, chain, and metadata
- renew certificate
- tls
- get certificate order status including domain validation challenges
- list ssl/tls certificates with optional status, domain, and expiry filtering
- certificate management
- ssl/tls
- domain validation status
- list domains and validation status
- cryptography
- initiate renewal for an existing ssl/tls certificate
- https
- get certificates expiring within n days
- get expiring certificates
- request a new ssl/tls certificate for domain validation
- certificate orders
- order details and challenges
- download certificate
- list domains
- download certificate in pem or pkcs12 format
- get order
- revoke a certificate with reason code
- get order details with challenge status
- request a new ssl/tls certificate for one or more domains
- revoke certificate
- list domains and their certificate validation status
- list certificates
- certificate renewal
- get ssl/tls certificates expiring within the next n days for proactive renewal
- list certificates with optional status and domain filtering
- certificate revocation
- initiate certificate renewal
- pki
- list certificate orders
- certificates
- revoke an ssl/tls certificate with a reason code
- list orders
- get certificate details and pem data
- certificate details
- download ssl/tls certificate in pem or pkcs12 format
- get certificate
- expiry monitoring
slug: certificate-lifecycle
source_filename: certificate-lifecycle.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SSL/TLS Certificate Lifecycle\"\n  description: >-\n    Unified workflow capability for SSL/TLS certificate lifecycle management.\n    Enables security and infrastructure teams to request, monitor, renew, and\n    revoke TLS certificates across domains. Combines certificate issuance,\n    automated renewal workflows, expiry monitoring, and domain verification\n    into a single operational interface.\n  tags:\n    - SSL/TLS\n    - Certificate Management\n    - PKI\n    - HTTPS\n    - Security\n    - Certificate Authority\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      CERT_MANAGER_API_KEY: CERT_MANAGER_API_KEY\n\ncapability:\n  consumes:\n    - import: ssl-tls-cert-mgmt\n      location: ./shared/certificate-management.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: ssl-tls-cert-lifecycle-api\n      description: \"Unified REST API for SSL/TLS certificate\
  \ lifecycle management.\"\n      resources:\n        - path: /v1/certificates\n          name: certificates\n          description: \"Certificate management\"\n          operations:\n            - method: GET\n              name: list-certificates\n              description: \"List certificates with optional status and domain filtering\"\n              call: \"ssl-tls-cert-mgmt.list-certificates\"\n              with:\n                status: \"rest.status\"\n                domain: \"rest.domain\"\n                expiringBefore: \"rest.expiringBefore\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: request-certificate\n              description: \"Request a new SSL/TLS certificate for domain validation\"\n              call: \"ssl-tls-cert-mgmt.request-certificate\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/certificates/{certificateId}\n\
  \          name: certificate-detail\n          description: \"Certificate details\"\n          operations:\n            - method: GET\n              name: get-certificate\n              description: \"Get certificate details and PEM data\"\n              call: \"ssl-tls-cert-mgmt.get-certificate\"\n              with:\n                certificateId: \"rest.certificateId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/certificates/{certificateId}/download\n          name: certificate-download\n          description: \"Download certificate\"\n          operations:\n            - method: GET\n              name: download-certificate\n              description: \"Download certificate in PEM or PKCS12 format\"\n              call: \"ssl-tls-cert-mgmt.download-certificate\"\n              with:\n                certificateId: \"rest.certificateId\"\n                format: \"rest.format\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/certificates/{certificateId}/renew\n          name: certificate-renew\n          description: \"Certificate renewal\"\n          operations:\n            - method: POST\n              name: renew-certificate\n              description: \"Initiate certificate renewal\"\n              call: \"ssl-tls-cert-mgmt.renew-certificate\"\n              with:\n                certificateId: \"rest.certificateId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/certificates/{certificateId}/revoke\n          name: certificate-revoke\n          description: \"Certificate revocation\"\n          operations:\n            - method: POST\n              name: revoke-certificate\n              description: \"Revoke a certificate with reason code\"\n              call: \"ssl-tls-cert-mgmt.revoke-certificate\"\n              with:\n                certificateId:\
  \ \"rest.certificateId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orders\n          name: orders\n          description: \"Certificate orders\"\n          operations:\n            - method: GET\n              name: list-orders\n              description: \"List certificate orders\"\n              call: \"ssl-tls-cert-mgmt.list-orders\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/orders/{orderId}\n          name: order-detail\n          description: \"Order details and challenges\"\n          operations:\n            - method: GET\n              name: get-order\n              description: \"Get order details with challenge status\"\n              call: \"ssl-tls-cert-mgmt.get-order\"\n              with:\n                orderId: \"rest.orderId\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n        - path: /v1/domains\n          name: domains\n          description: \"Domain validation status\"\n          operations:\n            - method: GET\n              name: list-domains\n              description: \"List domains and validation status\"\n              call: \"ssl-tls-cert-mgmt.list-domains\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/monitoring/expiring\n          name: expiring-certificates\n          description: \"Expiry monitoring\"\n          operations:\n            - method: GET\n              name: get-expiring-certificates\n              description: \"Get certificates expiring within N days\"\n              call: \"ssl-tls-cert-mgmt.get-expiring-certificates\"\n              with:\n                days: \"rest.days\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace:\
  \ ssl-tls-cert-lifecycle-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SSL/TLS certificate lifecycle management.\"\n      tools:\n        - name: list-certificates\n          description: \"List SSL/TLS certificates with optional status, domain, and expiry filtering\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ssl-tls-cert-mgmt.list-certificates\"\n          with:\n            status: \"tools.status\"\n            domain: \"tools.domain\"\n            expiringBefore: \"tools.expiringBefore\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-certificate\n          description: \"Get SSL/TLS certificate details including PEM, chain, and metadata\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ssl-tls-cert-mgmt.get-certificate\"\n          with:\n            certificateId: \"tools.certificateId\"\n   \
  \       outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: request-certificate\n          description: \"Request a new SSL/TLS certificate for one or more domains\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"ssl-tls-cert-mgmt.request-certificate\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: download-certificate\n          description: \"Download SSL/TLS certificate in PEM or PKCS12 format\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ssl-tls-cert-mgmt.download-certificate\"\n          with:\n            certificateId: \"tools.certificateId\"\n            format: \"tools.format\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: renew-certificate\n          description: \"Initiate renewal for an existing SSL/TLS certificate\"\n\
  \          hints:\n            readOnly: false\n            idempotent: false\n          call: \"ssl-tls-cert-mgmt.renew-certificate\"\n          with:\n            certificateId: \"tools.certificateId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: revoke-certificate\n          description: \"Revoke an SSL/TLS certificate with a reason code\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"ssl-tls-cert-mgmt.revoke-certificate\"\n          with:\n            certificateId: \"tools.certificateId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-order\n          description: \"Get certificate order status including domain validation challenges\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ssl-tls-cert-mgmt.get-order\"\n          with:\n     \
  \       orderId: \"tools.orderId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-domains\n          description: \"List domains and their certificate validation status\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ssl-tls-cert-mgmt.list-domains\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-expiring-certificates\n          description: \"Get SSL/TLS certificates expiring within the next N days for proactive renewal\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"ssl-tls-cert-mgmt.get-expiring-certificates\"\n          with:\n            days: \"tools.days\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ssl-tls/refs/heads/main/capabilities/certificate-lifecycle.yaml
tags:
- SSL/TLS
- Certificate Management
- PKI
- HTTPS
- Security
- Certificate Authority
tools:
- description: List SSL/TLS certificates with optional status, domain, and expiry filtering
  hints:
    idempotent: true
    readOnly: true
  name: list-certificates
- description: Get SSL/TLS certificate details including PEM, chain, and metadata
  hints:
    idempotent: true
    readOnly: true
  name: get-certificate
- description: Request a new SSL/TLS certificate for one or more domains
  hints:
    idempotent: false
    readOnly: false
  name: request-certificate
- description: Download SSL/TLS certificate in PEM or PKCS12 format
  hints:
    idempotent: true
    readOnly: true
  name: download-certificate
- description: Initiate renewal for an existing SSL/TLS certificate
  hints:
    idempotent: false
    readOnly: false
  name: renew-certificate
- description: Revoke an SSL/TLS certificate with a reason code
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: revoke-certificate
- description: Get certificate order status including domain validation challenges
  hints:
    idempotent: true
    readOnly: true
  name: get-order
- description: List domains and their certificate validation status
  hints:
    idempotent: true
    readOnly: true
  name: list-domains
- description: Get SSL/TLS certificates expiring within the next N days for proactive renewal
  hints:
    idempotent: true
    readOnly: true
  name: get-expiring-certificates
---
