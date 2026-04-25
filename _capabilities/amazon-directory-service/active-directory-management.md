---
consumed_apis:
- directory-service
description: Workflow capability for identity engineers and cloud architects to manage AWS Managed Microsoft Active Directory, including directory provisioning, trust relationships, domain controllers, snapshots, IP routing, and certificate management for hybrid identity workloads.
layout: capability
name: Amazon Directory Service Active Directory Management
operations:
- description: List all managed directories
  method: GET
  name: describe-directories
  path: /v1/directories
- description: Create an AWS Managed Microsoft AD directory
  method: POST
  name: create-microsoft-ad
  path: /v1/directories
- description: List trust relationships
  method: GET
  name: describe-trusts
  path: /v1/trusts
- description: Create a trust relationship
  method: POST
  name: create-trust
  path: /v1/trusts
- description: List directory snapshots
  method: GET
  name: describe-snapshots
  path: /v1/snapshots
- description: Create a manual directory snapshot
  method: POST
  name: create-snapshot
  path: /v1/snapshots
- description: List registered certificates
  method: GET
  name: list-certificates
  path: /v1/certificates
- description: List shared directories
  method: GET
  name: describe-shared-directories
  path: /v1/shared-directories
personas: []
provider_name: Amazon Directory Service
provider_slug: amazon-directory-service
search_terms:
- directory snapshots for backup and restore
- list all aws managed microsoft ad and simple ad directories in the account
- list trust relationships
- describe snapshots
- certificate management, ldaps, and audit logging
- create a manual directory snapshot
- identity management
- create an aws managed microsoft ad directory
- list certificates
- list directories shared from your account or shared with your account
- get the directory service limits for the current aws account and region
- list registered certificates
- share directory
- provisioning and managing microsoft ad and simple ad directories
- create microsoft ad
- managed active directory instances
- create a trust relationship
- share a directory with another aws account for multi-account access
- aws
- Cloud Architect
- create a simple ad directory powered by samba 4
- get directory limits
- list shared directories
- list certificates registered for ldaps or client certificate authentication
- directory services
- create a manual snapshot of a directory for backup
- create a trust relationship between aws managed microsoft ad and an on-premises directory
- delete an aws directory service directory
- describe directories
- certificates for directory authentication
- create an aws managed microsoft active directory in the aws cloud
- create trust
- restore a directory to a previous state using a snapshot
- create snapshot
- list manual snapshots of a directory for backup and restore purposes
- hybrid cloud
- describe shared directories
- end-to-end active directory lifecycle management using amazon directory service
- list directory snapshots
- describe trusts
- create directory
- directories shared with other aws accounts
- Identity Engineer
- identity engineer provisioning and managing active directory in aws
- trust relationships and shared directory access across accounts
- trust relationships between directories
- delete directory
- authentication
- list domain controllers provisioned for an aws managed microsoft ad directory
- describe domain controllers
- active directory
- cloud architect designing hybrid identity solutions with aws directory service
- list all managed directories
- list trust relationships established for aws managed microsoft ad directories
- amazon directory service
- restore from snapshot
slug: active-directory-management
tags:
- Amazon Directory Service
- Active Directory
- Identity Management
- Hybrid Cloud
- AWS
tools:
- description: List all AWS Managed Microsoft AD and Simple AD directories in the account
  hints:
    openWorld: true
    readOnly: true
  name: describe-directories
- description: Create an AWS Managed Microsoft Active Directory in the AWS Cloud
  hints:
    destructive: false
    readOnly: false
  name: create-microsoft-ad
- description: Create a Simple AD directory powered by Samba 4
  hints:
    destructive: false
    readOnly: false
  name: create-directory
- description: Delete an AWS Directory Service directory
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-directory
- description: List trust relationships established for AWS Managed Microsoft AD directories
  hints:
    openWorld: true
    readOnly: true
  name: describe-trusts
- description: Create a trust relationship between AWS Managed Microsoft AD and an on-premises directory
  hints:
    destructive: false
    readOnly: false
  name: create-trust
- description: List manual snapshots of a directory for backup and restore purposes
  hints:
    openWorld: true
    readOnly: true
  name: describe-snapshots
- description: Create a manual snapshot of a directory for backup
  hints:
    destructive: false
    readOnly: false
  name: create-snapshot
- description: Restore a directory to a previous state using a snapshot
  hints:
    destructive: false
    readOnly: false
  name: restore-from-snapshot
- description: List domain controllers provisioned for an AWS Managed Microsoft AD directory
  hints:
    openWorld: true
    readOnly: true
  name: describe-domain-controllers
- description: List certificates registered for LDAPS or client certificate authentication
  hints:
    openWorld: true
    readOnly: true
  name: list-certificates
- description: Share a directory with another AWS account for multi-account access
  hints:
    destructive: false
    readOnly: false
  name: share-directory
- description: List directories shared from your account or shared with your account
  hints:
    openWorld: true
    readOnly: true
  name: describe-shared-directories
- description: Get the directory service limits for the current AWS account and region
  hints:
    openWorld: true
    readOnly: true
  name: get-directory-limits
---
