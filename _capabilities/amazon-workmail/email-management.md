---
categories:
- messaging
consumed_apis:
- workmail
description: Unified workflow for IT administrators and email operations teams to manage Amazon WorkMail organizations, users, groups, and mobile device access. Enables programmatic provisioning, deprovisioning, and governance of enterprise email infrastructure.
layout: capability
name: Amazon WorkMail Email Management
operations:
- description: List all WorkMail organizations.
  method: GET
  name: list-organizations
  path: /v1/organizations
- description: List users in an organization.
  method: GET
  name: list-users
  path: /v1/users
- description: Create a new email user.
  method: POST
  name: create-user
  path: /v1/users
- description: List email groups.
  method: GET
  name: list-groups
  path: /v1/groups
- description: List mobile device access rules.
  method: GET
  name: list-mobile-device-access-rules
  path: /v1/mobile-device-access
personas: []
provider_name: Amazon WorkMail
provider_slug: amazon-workmail
search_terms:
- mobile device access control and compliance
- list all amazon workmail organizations in the account.
- list mobile device access control rules.
- create a new workmail user with mailbox.
- create user
- it administration of email infrastructure
- Email Operations
- email
- exchange
- aws
- list email distribution groups in an organization.
- administration
- workmail organization management.
- create a new email user.
- calendar
- list users in an organization.
- list email groups.
- mobile device access control.
- manages workmail infrastructure, user provisioning, and security policies.
- enterprise email provisioning and management
- list users
- group management.
- list groups
- list users in a workmail organization.
- list organizations
- workflow for it administrators to manage workmail organizations, users, groups, and mobile device access policies.
- list mobile device access rules
- enterprise
- handles day-to-day email user and group management.
- list mobile device access rules.
- business communication
- user provisioning and management.
- IT Administrator
- list all workmail organizations.
slug: email-management
tags:
- AWS
- Email
- Calendar
- Business Communication
- Administration
tools:
- description: List all Amazon WorkMail organizations in the account.
  hints:
    openWorld: true
    readOnly: true
  name: list-organizations
- description: List users in a WorkMail organization.
  hints:
    openWorld: false
    readOnly: true
  name: list-users
- description: Create a new WorkMail user with mailbox.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-user
- description: List email distribution groups in an organization.
  hints:
    openWorld: false
    readOnly: true
  name: list-groups
- description: List mobile device access control rules.
  hints:
    openWorld: false
    readOnly: true
  name: list-mobile-device-access-rules
---
