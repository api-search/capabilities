---
categories:
- identity
- security
consumed_apis:
- microsoft-graph
description: Workflow capability for issuing first-class agent identities in Microsoft Entra with on-behalf-of token propagation for agent-to-agent workflows. Combines service principal registration, client-credentials token issuance, OBO token exchange, app role assignment listing, and revocation into a single interface so Ford's AI agents get governed identities that flow through the same Apigee and 42Crunch gates as every other API consumer.
layout: capability
name: Microsoft Entra Agent Identity Issuance
operations:
- description: Register a new agent as an Entra application and service principal
  method: POST
  name: register-agent-as-service-principal
  path: /v1.0/applications
- description: Issue an agent access token using the client credentials grant
  method: POST
  name: issue-agent-token
  path: /oauth2/v2.0/token
- description: Exchange an upstream token on-behalf-of the user for downstream agent-to-agent calls
  method: POST
  name: exchange-token-on-behalf-of
  path: /oauth2/v2.0/token
- description: List app role assignments granted to the agent service principal
  method: GET
  name: list-app-role-assignments
  path: /v1.0/servicePrincipals/{id}/appRoleAssignments
- description: Revoke an agent identity by disabling its service principal
  method: PATCH
  name: revoke-agent-identity
  path: /v1.0/servicePrincipals/{id}
- description: List the service principals representing registered agents
  method: GET
  name: list-agent-service-principals
  path: /v1.0/servicePrincipals
personas:
- Security Team
- Head of AI
provider_name: Microsoft Entra
provider_slug: microsoft-entra
search_terms:
- issuing first-class agent identities
- obo token propagation for agent-to-agent workflows
- register agent as service principal
- issue agent token
- client credentials grant
- exchange token on-behalf-of
- obo token exchange
- list app role assignments
- revoke agent identity
- microsoft entra agent identity
- ford agent identity stack
- microsoft-based agent identity
- governed ai-era integration
- agent identity governance
- service principal registration
- microsoft graph api
- entra id
- azure ad agent identity
- agent-to-agent token flow
- non-human identity
- workload identity
- identity
- security
- head of ai
slug: agent-identity-issuance
tags:
- Agent Identity
- Microsoft Entra
- OAuth 2.0
- On-Behalf-Of
- Service Principal
tools:
- description: Register a new agent as an Entra application and service principal so it has a first-class identity
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: register-agent-as-service-principal
- description: Issue an agent access token using the client credentials grant for autonomous agent calls
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: issue-agent-token
- description: Exchange an upstream token on-behalf-of the user so downstream agents act with the user's scopes
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: exchange-token-on-behalf-of
- description: List app role assignments granted to the agent service principal to audit its entitlements
  hints:
    openWorld: false
    readOnly: true
  name: list-app-role-assignments
- description: Revoke an agent identity by disabling its service principal to immediately cut off access
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: revoke-agent-identity
- description: List the service principals representing registered agents in the tenant
  hints:
    openWorld: false
    readOnly: true
  name: list-agent-service-principals
---
