---
categories: []
consumed_apis: []
description: Unified capability for B2B identity and access management workflows. Combines Stytch's B2B API for organization creation, member management, SSO configuration, and session management. Used by SaaS platform developers building multi-tenant authentication.
layout: capability
name: Stytch B2B Identity Management
operations:
- description: Create a B2B organization
  method: POST
  name: create-organization
  path: /v1/organizations
- description: Get an organization
  method: GET
  name: get-organization
  path: /v1/organizations/{organization_id}
- description: List members
  method: GET
  name: list-members
  path: /v1/organizations/{organization_id}/members
- description: Invite a member
  method: POST
  name: create-member
  path: /v1/organizations/{organization_id}/members
- description: Send a magic link to a member
  method: POST
  name: send-b2b-magic-link
  path: /v1/magic-links/send
- description: List SSO connections for an organization
  method: GET
  name: list-sso-connections
  path: /v1/sso/connections
personas: []
provider_name: Stytch
provider_slug: stytch
search_terms:
- create organization
- b2b magic link authentication
- create a b2b organization
- delete member
- remove a member from a stytch b2b organization
- list sso connections
- identity management
- b2b
- get an organization
- authentication
- sso
- saas
- list members
- list sso (saml/oidc) connections for a stytch b2b organization
- organization member management
- organization (tenant) management
- passwordless
- invite a new member to a stytch b2b organization
- send a magic link to a member
- sso connection management
- identity
- multi-tenant
- developer tools
- stytch
- discover organizations
- retrieve a stytch b2b organization by id
- list sso connections for an organization
- invite a member
- send a stytch magic link to authenticate a b2b organization member
- individual organization
- create member
- create a new stytch b2b organization (tenant) for a saas customer
- validate a stytch b2b member session token
- authenticate b2b session
- send b2b magic link
- list members of a stytch b2b organization
- discover stytch b2b organizations a user can access
- security
- get organization
slug: b2b-identity-management
source_filename: b2b-identity-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Stytch B2B Identity Management\n  description: Unified capability for B2B identity and access management workflows. Combines Stytch's B2B API for organization\n    creation, member management, SSO configuration, and session management. Used by SaaS platform developers building multi-tenant\n    authentication.\n  tags:\n  - Stytch\n  - Authentication\n  - B2B\n  - Identity Management\n  - SSO\n  - Multi-Tenant\n  - SaaS\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STYTCH_PROJECT_ID: STYTCH_PROJECT_ID\n    STYTCH_SECRET: STYTCH_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: stytch-b2b\n    baseUri: https://api.stytch.com/v1/b2b\n    description: Stytch B2B Authentication API for multi-tenant applications.\n    authentication:\n      type: basic\n      username: '{{STYTCH_PROJECT_ID}}'\n      password: '{{STYTCH_SECRET}}'\n    resources:\n    - name: organizations\n      path:\
  \ /organizations\n      description: Organization management\n      operations:\n      - name: create-organization\n        method: POST\n        description: Create a new B2B organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            organization_name: '{{tools.organization_name}}'\n    - name: organization\n      path: /organizations/{organization_id}\n      description: Individual organization\n      operations:\n      - name: get-organization\n        method: GET\n        description: Get an organization by ID\n        inputParameters:\n        - name: organization_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-organization\n        method: DELETE\n        description:\
  \ Delete an organization\n        inputParameters:\n        - name: organization_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organization-members\n      path: /organizations/{organization_id}/members\n      description: Organization member management\n      operations:\n      - name: list-members\n        method: GET\n        description: List organization members\n        inputParameters:\n        - name: organization_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-member\n        method: POST\n        description: Create a new organization member\n        inputParameters:\n        - name: organization_id\n          in: path\n          type: string\n\
  \          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email_address: '{{tools.email_address}}'\n    - name: member\n      path: /organizations/{organization_id}/members/{member_id}\n      description: Individual member\n      operations:\n      - name: get-member\n        method: GET\n        description: Get a member by ID\n        inputParameters:\n        - name: organization_id\n          in: path\n          type: string\n          required: true\n        - name: member_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-member\n        method: DELETE\n        description: Delete a member\n        inputParameters:\n        - name: organization_id\n   \
  \       in: path\n          type: string\n          required: true\n        - name: member_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: b2b-magic-link-send\n      path: /magic_links/email/send\n      description: Send B2B magic links\n      operations:\n      - name: send-b2b-magic-link\n        method: POST\n        description: Send a magic link to a member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            email_address: '{{tools.email_address}}'\n            organization_id: '{{tools.organization_id}}'\n    - name: b2b-magic-link-authenticate\n      path: /magic_links/authenticate\n      description: Authenticate B2B magic links\n      operations:\n      - name: authenticate-b2b-magic-link\n\
  \        method: POST\n        description: Authenticate a member with a magic link token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            magic_links_token: '{{tools.token}}'\n            session_duration_minutes: '{{tools.session_duration_minutes}}'\n    - name: b2b-session-authenticate\n      path: /sessions/authenticate\n      description: Authenticate B2B sessions\n      operations:\n      - name: authenticate-b2b-session\n        method: POST\n        description: Validate and authenticate a B2B session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sso-connections\n      path: /sso/connections\n      description: SSO connection management\n      operations:\n      - name: list-sso-connections\n        method: GET\n        description: List SSO connections\
  \ for an organization\n        inputParameters:\n        - name: organization_id\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: discovery\n      path: /discovery/organizations\n      description: Organization discovery\n      operations:\n      - name: discover-organizations\n        method: POST\n        description: Discover organizations a user can access\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: stytch-b2b-identity-api\n    description: Unified REST API for Stytch B2B identity and access management.\n    resources:\n    - path: /v1/organizations\n      name: organizations\n      description: Organization (tenant) management\n      operations:\n      - method: POST\n        name:\
  \ create-organization\n        description: Create a B2B organization\n        call: stytch-b2b.create-organization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{organization_id}\n      name: organization\n      description: Individual organization\n      operations:\n      - method: GET\n        name: get-organization\n        description: Get an organization\n        call: stytch-b2b.get-organization\n        with:\n          organization_id: rest.organization_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{organization_id}/members\n      name: members\n      description: Organization member management\n      operations:\n      - method: GET\n        name: list-members\n        description: List members\n        call: stytch-b2b.list-members\n        with:\n          organization_id: rest.organization_id\n        outputParameters:\n        - type: object\n        \
  \  mapping: $.\n      - method: POST\n        name: create-member\n        description: Invite a member\n        call: stytch-b2b.create-member\n        with:\n          organization_id: rest.organization_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/magic-links/send\n      name: b2b-magic-links\n      description: B2B magic link authentication\n      operations:\n      - method: POST\n        name: send-b2b-magic-link\n        description: Send a magic link to a member\n        call: stytch-b2b.send-b2b-magic-link\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sso/connections\n      name: sso-connections\n      description: SSO connection management\n      operations:\n      - method: GET\n        name: list-sso-connections\n        description: List SSO connections for an organization\n        call: stytch-b2b.list-sso-connections\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n  - type: mcp\n    port: 9081\n    namespace: stytch-b2b-identity-mcp\n    transport: http\n    description: MCP server for AI-assisted Stytch B2B identity management.\n    tools:\n    - name: create-organization\n      description: Create a new Stytch B2B organization (tenant) for a SaaS customer\n      hints:\n        readOnly: false\n        destructive: false\n      call: stytch-b2b.create-organization\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-organization\n      description: Retrieve a Stytch B2B organization by ID\n      hints:\n        readOnly: true\n      call: stytch-b2b.get-organization\n      with:\n        organization_id: tools.organization_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-members\n      description: List members of a Stytch B2B organization\n      hints:\n        readOnly: true\n      call: stytch-b2b.list-members\n      with:\n        organization_id: tools.organization_id\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-member\n      description: Invite a new member to a Stytch B2B organization\n      hints:\n        readOnly: false\n        destructive: false\n      call: stytch-b2b.create-member\n      with:\n        organization_id: tools.organization_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-member\n      description: Remove a member from a Stytch B2B organization\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: stytch-b2b.delete-member\n      with:\n        organization_id: tools.organization_id\n        member_id: tools.member_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-b2b-magic-link\n      description: Send a Stytch magic link to authenticate a B2B organization member\n      hints:\n        readOnly: false\n        destructive: false\n      call: stytch-b2b.send-b2b-magic-link\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authenticate-b2b-session\n      description: Validate a Stytch B2B member session token\n      hints:\n        readOnly: true\n        idempotent: true\n      call: stytch-b2b.authenticate-b2b-session\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-sso-connections\n      description: List SSO (SAML/OIDC) connections for a Stytch B2B organization\n      hints:\n        readOnly: true\n      call: stytch-b2b.list-sso-connections\n      with:\n        organization_id: tools.organization_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: discover-organizations\n      description: Discover Stytch B2B organizations a user can access\n      hints:\n        readOnly: true\n        openWorld: true\n      call: stytch-b2b.discover-organizations\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/stytch/refs/heads/main/capabilities/b2b-identity-management.yaml
tags:
- Stytch
- Authentication
- B2B
- Identity Management
- SSO
- Multi-Tenant
- SaaS
tools:
- description: Create a new Stytch B2B organization (tenant) for a SaaS customer
  hints:
    destructive: false
    readOnly: false
  name: create-organization
- description: Retrieve a Stytch B2B organization by ID
  hints:
    readOnly: true
  name: get-organization
- description: List members of a Stytch B2B organization
  hints:
    readOnly: true
  name: list-members
- description: Invite a new member to a Stytch B2B organization
  hints:
    destructive: false
    readOnly: false
  name: create-member
- description: Remove a member from a Stytch B2B organization
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-member
- description: Send a Stytch magic link to authenticate a B2B organization member
  hints:
    destructive: false
    readOnly: false
  name: send-b2b-magic-link
- description: Validate a Stytch B2B member session token
  hints:
    idempotent: true
    readOnly: true
  name: authenticate-b2b-session
- description: List SSO (SAML/OIDC) connections for a Stytch B2B organization
  hints:
    readOnly: true
  name: list-sso-connections
- description: Discover Stytch B2B organizations a user can access
  hints:
    openWorld: true
    readOnly: true
  name: discover-organizations
---
