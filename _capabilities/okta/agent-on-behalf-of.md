---
categories:
- identity
- security
consumed_apis:
- okta-management
description: Workflow capability for OBO token exchange so agents can act as the human user without privilege escalation. Combines RFC 8693 token exchange, introspection, per-user scope listing, revocation, and active grant inspection into a single interface so Ford's agents inherit only the scopes the user already has — keeping AI-era integrations inside the existing identity boundary that Apigee and 42Crunch already enforce.
layout: capability
name: Okta Agent On-Behalf-Of Token Exchange
operations:
- description: Exchange an upstream token for a downstream agent token using the RFC 8693 token-exchange grant
  method: POST
  name: exchange-token
  path: /oauth2/v1/token
- description: Introspect a token to verify scopes, subject, and expiry before acting on the user's behalf
  method: POST
  name: introspect-token
  path: /oauth2/v1/introspect
- description: List the scopes a user has granted so the agent can request only what is already authorized
  method: GET
  name: list-scopes-for-user
  path: /api/v1/users/{userId}/grants
- description: Revoke a specific token to immediately cut off agent access on behalf of the user
  method: POST
  name: revoke-token
  path: /oauth2/v1/revoke
- description: List active grants for a user to audit which agents currently hold OBO tokens
  method: GET
  name: list-active-grants
  path: /api/v1/users/{userId}/grants
- description: Revoke a specific grant for a user to remove an agent's standing authorization
  method: DELETE
  name: revoke-user-grant
  path: /api/v1/users/{userId}/grants/{grantId}
personas:
- Security Team
- Head of AI
provider_name: Okta
provider_slug: okta
search_terms:
- obo token exchange so agents act as the human user
- without privilege escalation
- exchange token rfc 8693
- token-exchange grant
- introspect token
- list scopes for user
- revoke token
- list active grants
- okta agent on-behalf-of
- okta token exchange
- ford agent identity stack
- governed ai-era integration
- agent acts as user
- least-privilege agent token
- user-delegated agent access
- okta management api
- oauth 2.0 token exchange
- agent obo flow
- privilege escalation prevention
- per-user agent grants
- identity
- security
- head of ai
- agent identity boundary
slug: agent-on-behalf-of
tags:
- Agent Identity
- Okta
- OAuth 2.0
- Token Exchange
- On-Behalf-Of
tools:
- description: Exchange an upstream token for a downstream agent token using the RFC 8693 token-exchange grant
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: exchange-token
- description: Introspect a token to verify scopes, subject, and expiry before the agent acts on the user's behalf
  hints:
    openWorld: false
    readOnly: true
  name: introspect-token
- description: List the scopes a user has granted so the agent only requests what is already authorized
  hints:
    openWorld: false
    readOnly: true
  name: list-scopes-for-user
- description: Revoke a specific token to immediately cut off agent access on behalf of the user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: revoke-token
- description: List active grants for a user to audit which agents currently hold OBO tokens
  hints:
    openWorld: false
    readOnly: true
  name: list-active-grants
- description: Revoke a specific grant for a user to remove an agent's standing authorization
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: revoke-user-grant
---
