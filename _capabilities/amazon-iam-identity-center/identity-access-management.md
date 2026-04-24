---
consumed_apis:
- sso-admin
- identitystore
description: Unified capability for IT administrators to manage workforce identities, provision access to AWS accounts, and configure SSO for enterprise applications.
layout: capability
name: Amazon IAM Identity Center - Identity and Access Management
operations:
- description: List users in the identity store
  method: GET
  name: list-users
  path: /v1/users
- description: List groups in the identity store
  method: GET
  name: list-groups
  path: /v1/groups
- description: List all permission sets
  method: GET
  name: list-permission-sets
  path: /v1/permission-sets
- description: Assign access to a user or group for an AWS account
  method: POST
  name: create-account-assignment
  path: /v1/account-assignments
personas: []
provider_name: Amazon IAM Identity Center
provider_slug: amazon-iam-identity-center
search_terms:
- list permission sets for assigning aws account access
- assign a permission set to a user or group for an aws account
- create user
- manage user groups
- assign access to a user or group for an aws account
- create group
- list sso instances in the account
- remove account access
- list permission sets
- list groups in the identity store
- IT Administrator
- manages workforce identities and provisions access to aws accounts
- create a new group for organizing users
- remove a user or group's access to an aws account
- assigning aws account access to users and groups
- iam
- create account assignment
- manage workforce users
- create a permission set defining what access a user gets to an aws account
- manage permission sets for aws account access
- assign account access
- create a new workforce user in iam identity center
- IAM Administrator
- authentication
- list users in the identity store
- manage aws account access assignments
- list all permission sets
- list instances
- list workforce users in the identity store
- aws
- managing workforce user and group identities
- list user groups in the identity store
- single sign-on
- configures permission sets and account assignments
- access control
- workforce identity
- create permission set
- list groups
- identity management
- list users
slug: identity-access-management
tags:
- AWS
- IAM
- Identity Management
- Single Sign-On
- Access Control
- Workforce Identity
tools:
- description: List workforce users in the identity store
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: Create a new workforce user in IAM Identity Center
  hints:
    readOnly: false
  name: create-user
- description: List user groups in the identity store
  hints:
    openWorld: true
    readOnly: true
  name: list-groups
- description: Create a new group for organizing users
  hints:
    readOnly: false
  name: create-group
- description: List SSO instances in the account
  hints:
    openWorld: true
    readOnly: true
  name: list-instances
- description: List permission sets for assigning AWS account access
  hints:
    openWorld: true
    readOnly: true
  name: list-permission-sets
- description: Create a permission set defining what access a user gets to an AWS account
  hints:
    readOnly: false
  name: create-permission-set
- description: Assign a permission set to a user or group for an AWS account
  hints:
    readOnly: false
  name: assign-account-access
- description: Remove a user or group's access to an AWS account
  hints:
    destructive: true
    readOnly: false
  name: remove-account-access
---
