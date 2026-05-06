---
categories: []
consumed_apis: []
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
- revoke an ssl/tls certificate with a reason code
- list certificate orders
- get ssl/tls certificate details including pem, chain, and metadata
- cryptography
- request a new ssl/tls certificate for one or more domains
- request certificate
- certificate revocation
- get order
- list ssl/tls certificates with optional status, domain, and expiry filtering
- pki
- request a new ssl/tls certificate for domain validation
- revoke certificate
- download certificate
- security
- tls
- certificate authority
- list certificates
- download certificate in pem or pkcs12 format
- revoke a certificate with reason code
- download ssl/tls certificate in pem or pkcs12 format
- certificate details
- list domains and their certificate validation status
- list domains and validation status
- get ssl/tls certificates expiring within the next n days for proactive renewal
- list certificates with optional status and domain filtering
- expiry monitoring
- get certificate
- get certificate details and pem data
- initiate renewal for an existing ssl/tls certificate
- order details and challenges
- certificate renewal
- list orders
- list domains
- initiate certificate renewal
- get certificates expiring within n days
- certificate orders
- domain validation status
- get order details with challenge status
- certificate management
- certificates
- get certificate order status including domain validation challenges
- renew certificate
- https
- get expiring certificates
- ssl/tls
slug: certificate-lifecycle
source_filename: certificate-lifecycle.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SSL/TLS Certificate Lifecycle\n  description: Unified workflow capability for SSL/TLS certificate lifecycle management. Enables security and infrastructure\n    teams to request, monitor, renew, and revoke TLS certificates across domains. Combines certificate issuance, automated\n    renewal workflows, expiry monitoring, and domain verification into a single operational interface.\n  tags:\n  - SSL/TLS\n  - Certificate Management\n  - PKI\n  - HTTPS\n  - Security\n  - Certificate Authority\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    CERT_MANAGER_API_KEY: CERT_MANAGER_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: ssl-tls-cert-mgmt\n    baseUri: https://api.certmanager.example.com/v1\n    description: SSL/TLS Certificate Management API\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{CERT_MANAGER_API_KEY}}'\n      placement: header\n    resources:\n\
  \    - name: certificates\n      path: /certificates\n      description: Certificate issuance and management\n      operations:\n      - name: list-certificates\n        method: GET\n        description: List SSL/TLS certificates\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n        - name: domain\n          in: query\n          type: string\n          required: false\n        - name: expiringBefore\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: request-certificate\n        method: POST\n        description: Request a new certificate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            domains: '{{tools.domains}}'\n\
  \            certType: '{{tools.certType}}'\n    - name: certificate-by-id\n      path: /certificates/{certificateId}\n      description: Individual certificate management\n      operations:\n      - name: get-certificate\n        method: GET\n        description: Get certificate details\n        inputParameters:\n        - name: certificateId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: certificate-download\n      path: /certificates/{certificateId}/download\n      description: Certificate download\n      operations:\n      - name: download-certificate\n        method: GET\n        description: Download certificate in PEM format\n        inputParameters:\n        - name: certificateId\n          in: path\n          type: string\n          required: true\n        - name: format\n          in: query\n          type: string\n\
  \          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: certificate-renew\n      path: /certificates/{certificateId}/renew\n      description: Certificate renewal\n      operations:\n      - name: renew-certificate\n        method: POST\n        description: Renew an existing certificate\n        inputParameters:\n        - name: certificateId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: certificate-revoke\n      path: /certificates/{certificateId}/revoke\n      description: Certificate revocation\n      operations:\n      - name: revoke-certificate\n        method: POST\n        description: Revoke a certificate\n        inputParameters:\n        - name: certificateId\n          in: path\n          type: string\n\
  \          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orders\n      path: /orders\n      description: Certificate order management\n      operations:\n      - name: list-orders\n        method: GET\n        description: List certificate orders\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: order-by-id\n      path: /orders/{orderId}\n      description: Order details\n      operations:\n      - name: get-order\n        method: GET\n        description: Get certificate order details\n        inputParameters:\n        - name: orderId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: domains\n      path: /domains\n      description:\
  \ Domain management\n      operations:\n      - name: list-domains\n        method: GET\n        description: List registered domains\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: monitoring-expiring\n      path: /monitoring/expiring\n      description: Certificate expiry monitoring\n      operations:\n      - name: get-expiring-certificates\n        method: GET\n        description: Get certificates expiring within N days\n        inputParameters:\n        - name: days\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ssl-tls-cert-lifecycle-api\n    description: Unified REST API for SSL/TLS certificate lifecycle management.\n    resources:\n    - path: /v1/certificates\n      name: certificates\n\
  \      description: Certificate management\n      operations:\n      - method: GET\n        name: list-certificates\n        description: List certificates with optional status and domain filtering\n        call: ssl-tls-cert-mgmt.list-certificates\n        with:\n          status: rest.status\n          domain: rest.domain\n          expiringBefore: rest.expiringBefore\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: request-certificate\n        description: Request a new SSL/TLS certificate for domain validation\n        call: ssl-tls-cert-mgmt.request-certificate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/certificates/{certificateId}\n      name: certificate-detail\n      description: Certificate details\n      operations:\n      - method: GET\n        name: get-certificate\n        description: Get certificate details and PEM data\n        call: ssl-tls-cert-mgmt.get-certificate\n\
  \        with:\n          certificateId: rest.certificateId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/certificates/{certificateId}/download\n      name: certificate-download\n      description: Download certificate\n      operations:\n      - method: GET\n        name: download-certificate\n        description: Download certificate in PEM or PKCS12 format\n        call: ssl-tls-cert-mgmt.download-certificate\n        with:\n          certificateId: rest.certificateId\n          format: rest.format\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/certificates/{certificateId}/renew\n      name: certificate-renew\n      description: Certificate renewal\n      operations:\n      - method: POST\n        name: renew-certificate\n        description: Initiate certificate renewal\n        call: ssl-tls-cert-mgmt.renew-certificate\n        with:\n          certificateId: rest.certificateId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/certificates/{certificateId}/revoke\n      name: certificate-revoke\n      description: Certificate revocation\n      operations:\n      - method: POST\n        name: revoke-certificate\n        description: Revoke a certificate with reason code\n        call: ssl-tls-cert-mgmt.revoke-certificate\n        with:\n          certificateId: rest.certificateId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders\n      name: orders\n      description: Certificate orders\n      operations:\n      - method: GET\n        name: list-orders\n        description: List certificate orders\n        call: ssl-tls-cert-mgmt.list-orders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders/{orderId}\n      name: order-detail\n      description: Order details and challenges\n      operations:\n      - method: GET\n        name: get-order\n        description:\
  \ Get order details with challenge status\n        call: ssl-tls-cert-mgmt.get-order\n        with:\n          orderId: rest.orderId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/domains\n      name: domains\n      description: Domain validation status\n      operations:\n      - method: GET\n        name: list-domains\n        description: List domains and validation status\n        call: ssl-tls-cert-mgmt.list-domains\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/monitoring/expiring\n      name: expiring-certificates\n      description: Expiry monitoring\n      operations:\n      - method: GET\n        name: get-expiring-certificates\n        description: Get certificates expiring within N days\n        call: ssl-tls-cert-mgmt.get-expiring-certificates\n        with:\n          days: rest.days\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n\
  \    namespace: ssl-tls-cert-lifecycle-mcp\n    transport: http\n    description: MCP server for AI-assisted SSL/TLS certificate lifecycle management.\n    tools:\n    - name: list-certificates\n      description: List SSL/TLS certificates with optional status, domain, and expiry filtering\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ssl-tls-cert-mgmt.list-certificates\n      with:\n        status: tools.status\n        domain: tools.domain\n        expiringBefore: tools.expiringBefore\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-certificate\n      description: Get SSL/TLS certificate details including PEM, chain, and metadata\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ssl-tls-cert-mgmt.get-certificate\n      with:\n        certificateId: tools.certificateId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: request-certificate\n      description: Request\
  \ a new SSL/TLS certificate for one or more domains\n      hints:\n        readOnly: false\n        idempotent: false\n      call: ssl-tls-cert-mgmt.request-certificate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: download-certificate\n      description: Download SSL/TLS certificate in PEM or PKCS12 format\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ssl-tls-cert-mgmt.download-certificate\n      with:\n        certificateId: tools.certificateId\n        format: tools.format\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: renew-certificate\n      description: Initiate renewal for an existing SSL/TLS certificate\n      hints:\n        readOnly: false\n        idempotent: false\n      call: ssl-tls-cert-mgmt.renew-certificate\n      with:\n        certificateId: tools.certificateId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: revoke-certificate\n      description:\
  \ Revoke an SSL/TLS certificate with a reason code\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: ssl-tls-cert-mgmt.revoke-certificate\n      with:\n        certificateId: tools.certificateId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-order\n      description: Get certificate order status including domain validation challenges\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ssl-tls-cert-mgmt.get-order\n      with:\n        orderId: tools.orderId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-domains\n      description: List domains and their certificate validation status\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ssl-tls-cert-mgmt.list-domains\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-expiring-certificates\n      description: Get SSL/TLS certificates\
  \ expiring within the next N days for proactive renewal\n      hints:\n        readOnly: true\n        idempotent: true\n      call: ssl-tls-cert-mgmt.get-expiring-certificates\n      with:\n        days: tools.days\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
