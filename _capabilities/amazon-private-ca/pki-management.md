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
- retrieve a certificate
- certificates
- manages pki infrastructure, ca hierarchies, and certificate policies
- certificate management
- list all private certificate authorities
- get certificate authority details
- private pki infrastructure management workflow
- list certificate authorities
- amazon
- revoke a certificate
- issue a new certificate
- get certificate
- aws
- issue a new x.509 certificate from a certificate authority
- list cas
- security
- create certificate authority
- retrieve an issued certificate by arn
- certificate lifecycle management
- get details about a specific certificate authority
- revoke an issued certificate
- list all certificate authorities
- certificate authority hierarchy management
- Security Engineer
- create a new private certificate authority in the ca hierarchy
- tls
- Platform Engineer
- describe ca
- create a new private certificate authority
- revoke certificate
- iot
- certificate authority
- x.509
- individual certificate authority operations
- issues certificates for internal services and manages certificate lifecycle
- create ca
- individual certificate operations
- describe certificate authority
- pki
- issue certificate
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
