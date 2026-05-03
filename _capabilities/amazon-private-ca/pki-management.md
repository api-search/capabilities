---
categories:
- security
consumed_apis:
- amazon-private-ca
description: Workflow capability for managing private PKI infrastructure using Amazon Private CA. Combines certificate authority management, certificate issuance, revocation, and audit reporting for security engineers and platform teams.
layout: capability
name: Amazon Private CA PKI Management
operations:
- description: Create a new private certificate authority
  method: POST
  name: create-ca
  path: /v1/certificate-authorities
- description: List all certificate authorities
  method: GET
  name: list-cas
  path: /v1/certificate-authorities
- description: Get certificate authority details
  method: GET
  name: describe-ca
  path: /v1/certificate-authorities/{ca-id}
- description: Issue a new certificate
  method: POST
  name: issue-certificate
  path: /v1/certificates
- description: Retrieve a certificate
  method: GET
  name: get-certificate
  path: /v1/certificates/{cert-id}
- description: Revoke a certificate
  method: DELETE
  name: revoke-certificate
  path: /v1/certificates/{cert-id}
personas: []
provider_name: Amazon Private CA
provider_slug: amazon-private-ca
search_terms:
- certificate authority
- Platform Engineer
- revoke a certificate
- security
- issues certificates for internal services and manages certificate lifecycle
- tls
- certificate management
- list all certificate authorities
- revoke an issued certificate
- individual certificate authority operations
- issue certificate
- Security Engineer
- manages pki infrastructure, ca hierarchies, and certificate policies
- list all private certificate authorities
- x.509
- create a new private certificate authority
- aws
- describe ca
- certificate lifecycle management
- retrieve an issued certificate by arn
- issue a new certificate
- retrieve a certificate
- amazon
- create ca
- individual certificate operations
- revoke certificate
- certificate authority hierarchy management
- create certificate authority
- private pki infrastructure management workflow
- pki
- list cas
- certificates
- describe certificate authority
- get details about a specific certificate authority
- issue a new x.509 certificate from a certificate authority
- iot
- get certificate
- create a new private certificate authority in the ca hierarchy
- list certificate authorities
- get certificate authority details
slug: pki-management
source_filename: pki-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Amazon Private CA PKI Management\n  description: Workflow capability for managing private PKI infrastructure using Amazon Private CA. Combines certificate authority management, certificate issuance, revocation, and audit reporting for security engineers and platform teams.\n  tags:\n    - Amazon\n    - AWS\n    - PKI\n    - Certificate Authority\n    - Security\n    - X.509\n    - Certificates\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: amazon-private-ca\n      location: ./shared/amazon-private-ca.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: pki-management-api\n      description: Unified REST API for Amazon Private CA PKI management workflows.\n      resources:\n        - path: /v1/certificate-authorities\n\
  \          name: certificate-authorities\n          description: Certificate authority hierarchy management\n          operations:\n            - method: POST\n              name: create-ca\n              description: Create a new private certificate authority\n              call: \"amazon-private-ca.create-certificate-authority\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-cas\n              description: List all certificate authorities\n              call: \"amazon-private-ca.list-certificate-authorities\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/certificate-authorities/{ca-id}\n          name: certificate-authority\n          description: Individual certificate authority operations\n          operations:\n            - method: GET\n              name: describe-ca\n              description: Get\
  \ certificate authority details\n              call: \"amazon-private-ca.describe-certificate-authority\"\n              with:\n                ca_arn: \"rest.ca_arn\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/certificates\n          name: certificates\n          description: Certificate lifecycle management\n          operations:\n            - method: POST\n              name: issue-certificate\n              description: Issue a new certificate\n              call: \"amazon-private-ca.issue-certificate\"\n              with:\n                ca_arn: \"rest.ca_arn\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/certificates/{cert-id}\n          name: certificate\n          description: Individual certificate operations\n          operations:\n            - method: GET\n              name: get-certificate\n              description:\
  \ Retrieve a certificate\n              call: \"amazon-private-ca.get-certificate\"\n              with:\n                ca_arn: \"rest.ca_arn\"\n                cert_arn: \"rest.cert_arn\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: revoke-certificate\n              description: Revoke a certificate\n              call: \"amazon-private-ca.revoke-certificate\"\n              with:\n                ca_arn: \"rest.ca_arn\"\n                serial: \"rest.serial\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: pki-management-mcp\n      transport: http\n      description: MCP server for AI-assisted PKI management workflows with Amazon Private CA.\n      tools:\n        - name: create-certificate-authority\n          description: Create a new private certificate authority in the\
  \ CA hierarchy\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"amazon-private-ca.create-certificate-authority\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-certificate-authorities\n          description: List all private certificate authorities\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"amazon-private-ca.list-certificate-authorities\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-certificate-authority\n          description: Get details about a specific certificate authority\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"amazon-private-ca.describe-certificate-authority\"\n          with:\n            ca_arn: \"tools.ca_arn\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n\n        - name: issue-certificate\n          description: Issue a new X.509 certificate from a certificate authority\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"amazon-private-ca.issue-certificate\"\n          with:\n            ca_arn: \"tools.ca_arn\"\n            csr: \"tools.csr\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-certificate\n          description: Retrieve an issued certificate by ARN\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"amazon-private-ca.get-certificate\"\n          with:\n            ca_arn: \"tools.ca_arn\"\n            cert_arn: \"tools.cert_arn\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: revoke-certificate\n          description: Revoke an issued certificate\n          hints:\n            readOnly: false\n       \
  \     destructive: true\n          call: \"amazon-private-ca.revoke-certificate\"\n          with:\n            ca_arn: \"tools.ca_arn\"\n            serial: \"tools.serial\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-private-ca/refs/heads/main/capabilities/pki-management.yaml
tags:
- Amazon
- PKI
- Certificate Authority
- Security
- X.509
- Certificates
tools:
- description: Create a new private certificate authority in the CA hierarchy
  hints:
    destructive: false
    readOnly: false
  name: create-certificate-authority
- description: List all private certificate authorities
  hints:
    openWorld: true
    readOnly: true
  name: list-certificate-authorities
- description: Get details about a specific certificate authority
  hints:
    openWorld: false
    readOnly: true
  name: describe-certificate-authority
- description: Issue a new X.509 certificate from a certificate authority
  hints:
    destructive: false
    readOnly: false
  name: issue-certificate
- description: Retrieve an issued certificate by ARN
  hints:
    openWorld: false
    readOnly: true
  name: get-certificate
- description: Revoke an issued certificate
  hints:
    destructive: true
    readOnly: false
  name: revoke-certificate
---
