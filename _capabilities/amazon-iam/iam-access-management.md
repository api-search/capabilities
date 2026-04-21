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
- policy management
- delete an iam user from the account
- create policy
- aws
- attach a managed policy to an iam role
- manage iam users
- list all iam users in the account
- create a new iam policy with specified permissions
- reviews and audits iam configurations for security compliance
- create a new iam user
- list all iam roles
- create a new iam role with a trust policy
- manages iam users, roles, and policies for aws account governance
- access management
- Cloud Administrator
- creating and managing aws user identities
- Security Engineer
- attach role policy
- create a new iam role
- iam
- attach a managed policy to an iam user
- manage iam policies
- list all iam users
- list all iam roles in the account
- attach user policy
- access control
- authorization
- authentication
- manage iam roles
- list access keys for an iam user
- security
- defining and enforcing what users and services can do
- create a new iam user with the specified username
- create role
- list policies
- list all iam policies
- create a new iam policy
- list access keys
- creating and attaching permission policies
- identity
- list iam policies available for attachment
- delete user
- list roles
- list users
- create user
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
