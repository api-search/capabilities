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
- certificate authority hierarchy management
- issues certificates for internal services and manages certificate lifecycle
- x.509
- retrieve a certificate
- issue a new certificate
- iot
- certificate authority
- tls
- describe certificate authority
- create certificate authority
- revoke a certificate
- retrieve an issued certificate by arn
- describe ca
- list all certificate authorities
- get certificate
- security
- certificate management
- issue a new x.509 certificate from a certificate authority
- issue certificate
- individual certificate operations
- private pki infrastructure management workflow
- certificate lifecycle management
- list all private certificate authorities
- Security Engineer
- create a new private certificate authority in the ca hierarchy
- list certificate authorities
- certificates
- get certificate authority details
- pki
- get details about a specific certificate authority
- revoke certificate
- list cas
- individual certificate authority operations
- create a new private certificate authority
- aws
- revoke an issued certificate
- manages pki infrastructure, ca hierarchies, and certificate policies
- create ca
- amazon
- Platform Engineer
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
