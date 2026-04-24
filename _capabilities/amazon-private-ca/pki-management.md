---
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
- list cas
- issue certificate
- issue a new certificate
- retrieve a certificate
- private pki infrastructure management workflow
- Platform Engineer
- manages pki infrastructure, ca hierarchies, and certificate policies
- certificate lifecycle management
- certificate management
- x.509
- certificates
- issues certificates for internal services and manages certificate lifecycle
- iot
- create a new private certificate authority
- tls
- list all certificate authorities
- get certificate
- individual certificate authority operations
- list all private certificate authorities
- get details about a specific certificate authority
- create ca
- certificate authority hierarchy management
- retrieve an issued certificate by arn
- get certificate authority details
- describe ca
- list certificate authorities
- revoke an issued certificate
- Security Engineer
- issue a new x.509 certificate from a certificate authority
- pki
- revoke certificate
- aws
- create a new private certificate authority in the ca hierarchy
- create certificate authority
- certificate authority
- amazon
- security
- individual certificate operations
- describe certificate authority
- revoke a certificate
slug: pki-management
tags:
- Amazon
- AWS
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
