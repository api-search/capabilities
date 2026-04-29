---
categories:
- security
consumed_apis:
- acm
description: Unified workflow for managing SSL/TLS certificate lifecycles on AWS, enabling DevOps engineers and security teams to provision, inspect, and retire certificates for websites and internal services.
layout: capability
name: Amazon Certificate Manager Certificate Lifecycle Management
operations:
- description: List all ACM certificates with optional status filtering
  method: GET
  name: list-certificates
  path: /v1/certificates
- description: Request a new SSL/TLS certificate with DNS or email validation
  method: POST
  name: request-certificate
  path: /v1/certificates
- description: Get full details of a specific ACM certificate
  method: GET
  name: describe-certificate
  path: /v1/certificates/{certificateArn}
- description: Delete an ACM certificate
  method: DELETE
  name: delete-certificate
  path: /v1/certificates/{certificateArn}
personas: []
provider_name: Amazon Certificate Manager
provider_slug: amazon-certificate-manager
search_terms:
- DevOps Engineer
- security professionals overseeing certificate compliance and expiry monitoring
- ssl/tls certificate provisioning, validation, and lifecycle operations
- request certificate
- manage the full lifecycle of acm ssl/tls certificates
- list certificates
- request a new acm ssl/tls certificate for a domain using dns or email validation
- end-to-end ssl/tls certificate provisioning, inspection, and retirement workflow
- aws
- amazon web services
- delete an acm certificate
- get detailed metadata for a specific acm certificate by arn, including domain, status, expiry, and issuer
- list all acm ssl/tls certificates, optionally filtered by status
- inspect or delete a specific certificate
- tls
- list all acm certificates with optional status filtering
- request a new ssl/tls certificate with dns or email validation
- get full details of a specific acm certificate
- devops
- Security Engineer
- certificates
- encryption
- delete certificate
- engineers managing infrastructure and certificate rotation for web services
- describe certificate
- security
- delete an acm certificate by arn. cannot delete certificates in use by aws services.
- ssl
slug: certificate-lifecycle-management
source_filename: certificate-lifecycle-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amazon Certificate Manager Certificate Lifecycle Management\"\n  description: \"Unified workflow for managing SSL/TLS certificate lifecycles on AWS, enabling DevOps engineers and security teams to provision, inspect, and retire certificates for websites and internal services.\"\n  tags:\n    - Amazon Web Services\n    - Certificates\n    - SSL\n    - TLS\n    - Security\n    - DevOps\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: acm\n      location: ./shared/certificate-manager.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: certificate-lifecycle-api\n      description: \"Unified REST API for SSL/TLS certificate lifecycle management on AWS.\"\n      resources:\n        - path: /v1/certificates\n\
  \          name: certificates\n          description: \"Manage the full lifecycle of ACM SSL/TLS certificates\"\n          operations:\n            - method: GET\n              name: list-certificates\n              description: \"List all ACM certificates with optional status filtering\"\n              call: \"acm.list-certificates\"\n              with:\n                maxItems: \"rest.max_items\"\n                nextToken: \"rest.next_token\"\n                certificateStatuses: \"rest.statuses\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: request-certificate\n              description: \"Request a new SSL/TLS certificate with DNS or email validation\"\n              call: \"acm.request-certificate\"\n              with:\n                DomainName: \"rest.domain_name\"\n                ValidationMethod: \"rest.validation_method\"\n              outputParameters:\n           \
  \     - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/certificates/{certificateArn}\n          name: certificate\n          description: \"Inspect or delete a specific certificate\"\n          operations:\n            - method: GET\n              name: describe-certificate\n              description: \"Get full details of a specific ACM certificate\"\n              call: \"acm.describe-certificate\"\n              with:\n                certificateArn: \"rest.certificateArn\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-certificate\n              description: \"Delete an ACM certificate\"\n              call: \"acm.delete-certificate\"\n              with:\n                certificateArn: \"rest.certificateArn\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n \
  \     namespace: certificate-lifecycle-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SSL/TLS certificate lifecycle management on AWS.\"\n      tools:\n        - name: list-certificates\n          description: \"List all ACM SSL/TLS certificates, optionally filtered by status\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"acm.list-certificates\"\n          with:\n            maxItems: \"tools.max_items\"\n            nextToken: \"tools.next_token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-certificate\n          description: \"Get detailed metadata for a specific ACM certificate by ARN, including domain, status, expiry, and issuer\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"acm.describe-certificate\"\n          with:\n            certificateArn: \"tools.certificate_arn\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: request-certificate\n          description: \"Request a new ACM SSL/TLS certificate for a domain using DNS or email validation\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"acm.request-certificate\"\n          with:\n            DomainName: \"tools.domain_name\"\n            ValidationMethod: \"tools.validation_method\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-certificate\n          description: \"Delete an ACM certificate by ARN. Cannot delete certificates in use by AWS services.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"acm.delete-certificate\"\n          with:\n            certificateArn: \"tools.certificate_arn\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-certificate-manager/refs/heads/main/capabilities/certificate-lifecycle-management.yaml
tags:
- Amazon Web Services
- Certificates
- SSL
- TLS
- Security
- DevOps
tools:
- description: List all ACM SSL/TLS certificates, optionally filtered by status
  hints:
    idempotent: true
    readOnly: true
  name: list-certificates
- description: Get detailed metadata for a specific ACM certificate by ARN, including domain, status, expiry, and issuer
  hints:
    idempotent: true
    readOnly: true
  name: describe-certificate
- description: Request a new ACM SSL/TLS certificate for a domain using DNS or email validation
  hints:
    idempotent: false
    readOnly: false
  name: request-certificate
- description: Delete an ACM certificate by ARN. Cannot delete certificates in use by AWS services.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-certificate
---
