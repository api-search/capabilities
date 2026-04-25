---
consumed_apis:
- iam
description: Unified capability for cloud administrators to manage IAM users, roles, groups, and policies for AWS account access control and security governance.
layout: capability
name: Amazon IAM - Access Management
operations:
- description: List all IAM users
  method: GET
  name: list-users
  path: /v1/users
- description: Create a new IAM user
  method: POST
  name: create-user
  path: /v1/users
- description: List all IAM roles
  method: GET
  name: list-roles
  path: /v1/roles
- description: Create a new IAM role
  method: POST
  name: create-role
  path: /v1/roles
- description: List all IAM policies
  method: GET
  name: list-policies
  path: /v1/policies
- description: Create a new IAM policy
  method: POST
  name: create-policy
  path: /v1/policies
personas: []
provider_name: Amazon IAM
provider_slug: amazon-iam
search_terms:
- create role
- create a new iam policy
- list all iam users
- create user
- iam
- attach user policy
- policy management
- attach a managed policy to an iam user
- create policy
- reviews and audits iam configurations for security compliance
- list all iam policies
- list all iam roles in the account
- authentication
- manages iam users, roles, and policies for aws account governance
- list all iam users in the account
- creating and attaching permission policies
- create a new iam role
- manage iam users
- authorization
- security
- list all iam roles
- list roles
- manage iam policies
- manage iam roles
- attach a managed policy to an iam role
- identity
- delete user
- create a new iam user
- delete an iam user from the account
- list access keys
- access control
- create a new iam user with the specified username
- Security Engineer
- defining and enforcing what users and services can do
- list policies
- create a new iam role with a trust policy
- creating and managing aws user identities
- access management
- Cloud Administrator
- list access keys for an iam user
- aws
- list users
- attach role policy
- list iam policies available for attachment
- create a new iam policy with specified permissions
slug: iam-access-management
tags:
- AWS
- IAM
- Security
- Access Control
- Identity
- Policy Management
tools:
- description: List all IAM users in the account
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: Create a new IAM user with the specified username
  hints:
    readOnly: false
  name: create-user
- description: Delete an IAM user from the account
  hints:
    destructive: true
    readOnly: false
  name: delete-user
- description: List all IAM roles in the account
  hints:
    openWorld: true
    readOnly: true
  name: list-roles
- description: Create a new IAM role with a trust policy
  hints:
    readOnly: false
  name: create-role
- description: List IAM policies available for attachment
  hints:
    openWorld: true
    readOnly: true
  name: list-policies
- description: Create a new IAM policy with specified permissions
  hints:
    readOnly: false
  name: create-policy
- description: Attach a managed policy to an IAM user
  hints:
    readOnly: false
  name: attach-user-policy
- description: Attach a managed policy to an IAM role
  hints:
    readOnly: false
  name: attach-role-policy
- description: List access keys for an IAM user
  hints:
    openWorld: true
    readOnly: true
  name: list-access-keys
---
