---
consumed_apis:
- beyondtrust
description: Unified privileged access management workflow combining Password Safe credential management, access request workflows, and secrets management. Used by security engineers and DevOps teams to manage just-in-time privileged access and secrets retrieval for automated pipelines.
layout: capability
name: BeyondTrust Privileged Access Management
operations:
- description: List managed accounts
  method: GET
  name: list-managed-accounts
  path: /v1/managed-accounts
- description: List managed systems
  method: GET
  name: list-managed-systems
  path: /v1/managed-systems
- description: List access requests
  method: GET
  name: list-requests
  path: /v1/requests
- description: Create an access request
  method: POST
  name: create-request
  path: /v1/requests
- description: Get credentials for approved request
  method: GET
  name: get-request-credentials
  path: /v1/requests/{requestId}/credentials
- description: List secrets
  method: GET
  name: list-secrets
  path: /v1/secrets
- description: Create a new secret
  method: POST
  name: create-secret
  path: /v1/secrets
- description: Get a secret value
  method: GET
  name: get-secret
  path: /v1/secrets/{id}
- description: Delete a secret
  method: DELETE
  name: delete-secret
  path: /v1/secrets/{id}
personas:
- description: Security team member managing privileged access policies and requests
  id: security-engineer
  name: Security Engineer
- description: DevOps engineer retrieving secrets and credentials for CI/CD pipelines
  id: devops-engineer
  name: DevOps Engineer
provider_name: BeyondTrust
provider_slug: beyondtrust
search_terms:
- just in time access
- list secrets
- create a just-in-time access request for a privileged account
- delete secret
- secrets management
- beyondtrust
- individual secret operations
- zero trust
- compliance
- secure storage and retrieval of secrets and credentials
- delete a secret
- list access requests
- create an access request
- access management
- list requests
- privileged access
- security
- managed system discovery
- privileged access management
- security engineer
- list all active privileged access requests
- access request management
- cancel and delete an access request
- create secret
- list privileged accounts available for just-in-time access
- credential retrieval for approved requests
- get secret
- credentials
- security team member managing privileged access policies and requests
- list secrets stored in beyondtrust secrets safe
- list systems registered in password safe
- get a secret value
- list managed systems
- access
- create request
- just-in-time access to privileged accounts on managed systems
- create a new secret
- retrieve a specific secret value from secrets safe
- devops engineer retrieving secrets and credentials for ci/cd pipelines
- delete request
- secrets
- store a new secret in secrets safe
- privileged account discovery
- get credentials for approved request
- get request credentials
- devops engineer
- list managed accounts
- retrieve credentials for an approved privileged access request
slug: privileged-access-management
tags:
- BeyondTrust
- Privileged Access Management
- Zero Trust
- Secrets Management
- Just In Time Access
tools:
- description: List privileged accounts available for just-in-time access
  hints:
    openWorld: true
    readOnly: true
  name: list-managed-accounts
- description: List systems registered in Password Safe
  hints:
    readOnly: true
  name: list-managed-systems
- description: List all active privileged access requests
  hints:
    readOnly: true
  name: list-requests
- description: Create a just-in-time access request for a privileged account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-request
- description: Retrieve credentials for an approved privileged access request
  hints:
    readOnly: true
  name: get-request-credentials
- description: List secrets stored in BeyondTrust Secrets Safe
  hints:
    readOnly: true
  name: list-secrets
- description: Retrieve a specific secret value from Secrets Safe
  hints:
    readOnly: true
  name: get-secret
- description: Store a new secret in Secrets Safe
  hints:
    destructive: false
    readOnly: false
  name: create-secret
- description: Cancel and delete an access request
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-request
---
