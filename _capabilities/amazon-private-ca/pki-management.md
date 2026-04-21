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
- revoke certificate
- create certificate authority
- certificate lifecycle management
- certificate authority
- issue certificate
- aws
- x.509
- Platform Engineer
- list cas
- retrieve an issued certificate by arn
- revoke a certificate
- certificates
- create a new private certificate authority in the ca hierarchy
- describe certificate authority
- iot
- pki
- get certificate authority details
- Security Engineer
- list all certificate authorities
- retrieve a certificate
- issue a new x.509 certificate from a certificate authority
- create a new private certificate authority
- revoke an issued certificate
- certificate authority hierarchy management
- private pki infrastructure management workflow
- certificate management
- create ca
- describe ca
- security
- get certificate
- list certificate authorities
- manages pki infrastructure, ca hierarchies, and certificate policies
- issues certificates for internal services and manages certificate lifecycle
- amazon
- tls
- issue a new certificate
- get details about a specific certificate authority
- individual certificate operations
- individual certificate authority operations
- list all private certificate authorities
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
