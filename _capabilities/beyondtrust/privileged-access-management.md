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
- list requests
- privileged account discovery
- create a just-in-time access request for a privileged account
- access request management
- get secret
- list all active privileged access requests
- list access requests
- security team member managing privileged access policies and requests
- store a new secret in secrets safe
- get credentials for approved request
- cancel and delete an access request
- list managed accounts
- devops engineer
- create request
- retrieve credentials for an approved privileged access request
- privileged access management
- security engineer
- individual secret operations
- credentials
- create a new secret
- compliance
- secure storage and retrieval of secrets and credentials
- credential retrieval for approved requests
- managed system discovery
- zero trust
- security
- secrets management
- just in time access
- create secret
- get a secret value
- beyondtrust
- delete a secret
- list systems registered in password safe
- list secrets
- access management
- get request credentials
- delete request
- privileged access
- devops engineer retrieving secrets and credentials for ci/cd pipelines
- secrets
- retrieve a specific secret value from secrets safe
- just-in-time access to privileged accounts on managed systems
- delete secret
- create an access request
- list secrets stored in beyondtrust secrets safe
- list privileged accounts available for just-in-time access
- list managed systems
- access
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
