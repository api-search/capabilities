---
categories:
- identity
- security
consumed_apis:
- auth0-management
description: Workflow capability for security teams enforcing user-scoped agent access where the agent acts as the human user via OBO token exchange — no machine-to-machine privilege escalation. Combines RFC 8693 token exchange, access token introspection, user grant inventory, refresh token revocation, and resource server discovery into a unified surface for delegated agent authorization.
layout: capability
name: Auth0 Agent On-Behalf-Of Token Exchange
operations:
- description: Exchange a user token for an agent access token via RFC 8693 token-exchange
  method: POST
  name: exchange-token
  path: /oauth/token
- description: Introspect an access token to verify scopes and validity
  method: POST
  name: introspect-token
  path: /oauth/introspect
- description: List the grants a user has issued to clients and agents
  method: GET
  name: list-user-grants
  path: /api/v2/users/{id}/grants
- description: Revoke a refresh token to terminate delegated agent access
  method: POST
  name: revoke-refresh-token
  path: /oauth/revoke
- description: List resource servers (APIs) that agents can be authorized against
  method: GET
  name: list-resource-servers
  path: /api/v2/resource-servers
- description: Get a specific resource server (API) definition
  method: GET
  name: get-resource-server
  path: /api/v2/resource-servers/{id}
personas:
- Security Team
provider_name: Auth0
provider_slug: auth0
search_terms:
- on-behalf-of token exchange
- rfc 8693 token exchange
- agent acts as user
- delegated agent authorization
- introspect access token
- list user grants
- revoke refresh token
- list resource servers
- auth0 obo
- agent identity
- no machine-to-machine privilege escalation
- user-scoped agent access
- delegated authorization
- auth0 token exchange
- agent on behalf of
- token introspection
- refresh token revoke
- resource server discovery
- security team identity
- enforce user scopes for agents
- auth0 management api
- prevent agent privilege escalation
- audit agent grants
slug: agent-on-behalf-of
tags:
- Identity
- OAuth
- Token Exchange
- Agent Authorization
- Auth0
tools:
- description: Exchange a user-issued token for an agent access token via RFC 8693 OAuth token exchange
  hints:
    destructive: false
    idempotent: false
    openWorld: false
    readOnly: false
  name: exchange-token
- description: Introspect an access token to verify its scopes, audience, and validity
  hints:
    openWorld: false
    readOnly: true
  name: introspect-token
- description: List the grants a user has issued to clients and agents to audit delegated access
  hints:
    openWorld: false
    readOnly: true
  name: list-user-grants
- description: Revoke a refresh token to immediately terminate delegated agent access for a user
  hints:
    destructive: true
    idempotent: true
    openWorld: false
    readOnly: false
  name: revoke-refresh-token
- description: List resource servers (APIs) registered in Auth0 that agents can be authorized against
  hints:
    openWorld: false
    readOnly: true
  name: list-resource-servers
- description: Get a specific Auth0 resource server (API) definition including its scopes
  hints:
    openWorld: false
    readOnly: true
  name: get-resource-server
---
