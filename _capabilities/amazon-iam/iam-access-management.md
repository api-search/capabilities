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
- create a new iam role with a trust policy
- manage iam users
- iam
- attach user policy
- security
- creating and attaching permission policies
- list roles
- delete user
- authorization
- list access keys
- reviews and audits iam configurations for security compliance
- identity
- list all iam users
- access control
- aws
- manage iam policies
- create policy
- attach a managed policy to an iam user
- creating and managing aws user identities
- list users
- Security Engineer
- list all iam policies
- list all iam roles in the account
- list iam policies available for attachment
- create a new iam role
- delete an iam user from the account
- list access keys for an iam user
- list all iam users in the account
- list policies
- create a new iam user with the specified username
- attach role policy
- manage iam roles
- policy management
- create a new iam user
- list all iam roles
- create role
- create a new iam policy
- defining and enforcing what users and services can do
- access management
- create a new iam policy with specified permissions
- authentication
- manages iam users, roles, and policies for aws account governance
- attach a managed policy to an iam role
- create user
- Cloud Administrator
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
