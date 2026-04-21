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
- identity management
- restore from snapshot
- create trust
- directories shared with other aws accounts
- create a trust relationship between aws managed microsoft ad and an on-premises directory
- create a trust relationship
- list trust relationships
- list all managed directories
- provisioning and managing microsoft ad and simple ad directories
- list directory snapshots
- directory services
- share directory
- list certificates registered for ldaps or client certificate authentication
- list certificates
- identity engineer provisioning and managing active directory in aws
- list domain controllers provisioned for an aws managed microsoft ad directory
- certificate management, ldaps, and audit logging
- describe shared directories
- describe trusts
- list registered certificates
- amazon directory service
- trust relationships and shared directory access across accounts
- directory snapshots for backup and restore
- create a simple ad directory powered by samba 4
- hybrid cloud
- describe domain controllers
- list shared directories
- list directories shared from your account or shared with your account
- end-to-end active directory lifecycle management using amazon directory service
- create a manual snapshot of a directory for backup
- managed active directory instances
- create an aws managed microsoft ad directory
- authentication
- Identity Engineer
- trust relationships between directories
- create a manual directory snapshot
- create directory
- restore a directory to a previous state using a snapshot
- create snapshot
- cloud architect designing hybrid identity solutions with aws directory service
- delete directory
- get directory limits
- describe snapshots
- list trust relationships established for aws managed microsoft ad directories
- list manual snapshots of a directory for backup and restore purposes
- get the directory service limits for the current aws account and region
- share a directory with another aws account for multi-account access
- delete an aws directory service directory
- create an aws managed microsoft active directory in the aws cloud
- aws
- list all aws managed microsoft ad and simple ad directories in the account
- Cloud Architect
- active directory
- create microsoft ad
- describe directories
- certificates for directory authentication
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
