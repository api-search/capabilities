---
categories: []
consumed_apis:
- stytch-b2b
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
- multi-tenant
- saas
- identity management
- security
- organization member management
- b2b magic link authentication
- remove a member from a stytch b2b organization
- sso connection management
- list members
- create a new stytch b2b organization (tenant) for a saas customer
- stytch
- list sso connections
- discover stytch b2b organizations a user can access
- passwordless
- get an organization
- invite a member
- authenticate b2b session
- retrieve a stytch b2b organization by id
- validate a stytch b2b member session token
- developer tools
- create member
- send a stytch magic link to authenticate a b2b organization member
- delete member
- b2b
- create organization
- individual organization
- discover organizations
- list members of a stytch b2b organization
- sso
- list sso (saml/oidc) connections for a stytch b2b organization
- organization (tenant) management
- create a b2b organization
- send a magic link to a member
- authentication
- invite a new member to a stytch b2b organization
- get organization
- identity
- send b2b magic link
- list sso connections for an organization
slug: b2b-identity-management
source_filename: b2b-identity-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Stytch B2B Identity Management\"\n  description: >-\n    Unified capability for B2B identity and access management workflows. Combines Stytch's B2B API\n    for organization creation, member management, SSO configuration, and session management.\n    Used by SaaS platform developers building multi-tenant authentication.\n  tags:\n    - Stytch\n    - Authentication\n    - B2B\n    - Identity Management\n    - SSO\n    - Multi-Tenant\n    - SaaS\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STYTCH_PROJECT_ID: STYTCH_PROJECT_ID\n      STYTCH_SECRET: STYTCH_SECRET\n\ncapability:\n  consumes:\n    - import: stytch-b2b\n      location: ./shared/b2b-auth.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: stytch-b2b-identity-api\n      description: \"Unified REST API for Stytch B2B identity and access management.\"\n      resources:\n        - path: /v1/organizations\n\
  \          name: organizations\n          description: \"Organization (tenant) management\"\n          operations:\n            - method: POST\n              name: create-organization\n              description: \"Create a B2B organization\"\n              call: \"stytch-b2b.create-organization\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/organizations/{organization_id}\n          name: organization\n          description: \"Individual organization\"\n          operations:\n            - method: GET\n              name: get-organization\n              description: \"Get an organization\"\n              call: \"stytch-b2b.get-organization\"\n              with:\n                organization_id: \"rest.organization_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/organizations/{organization_id}/members\n          name: members\n      \
  \    description: \"Organization member management\"\n          operations:\n            - method: GET\n              name: list-members\n              description: \"List members\"\n              call: \"stytch-b2b.list-members\"\n              with:\n                organization_id: \"rest.organization_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-member\n              description: \"Invite a member\"\n              call: \"stytch-b2b.create-member\"\n              with:\n                organization_id: \"rest.organization_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/magic-links/send\n          name: b2b-magic-links\n          description: \"B2B magic link authentication\"\n          operations:\n            - method: POST\n              name: send-b2b-magic-link\n              description:\
  \ \"Send a magic link to a member\"\n              call: \"stytch-b2b.send-b2b-magic-link\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sso/connections\n          name: sso-connections\n          description: \"SSO connection management\"\n          operations:\n            - method: GET\n              name: list-sso-connections\n              description: \"List SSO connections for an organization\"\n              call: \"stytch-b2b.list-sso-connections\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: stytch-b2b-identity-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Stytch B2B identity management.\"\n      tools:\n        - name: create-organization\n          description: \"Create a new Stytch B2B organization (tenant) for a SaaS customer\"\n          hints:\n            readOnly:\
  \ false\n            destructive: false\n          call: \"stytch-b2b.create-organization\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-organization\n          description: \"Retrieve a Stytch B2B organization by ID\"\n          hints:\n            readOnly: true\n          call: \"stytch-b2b.get-organization\"\n          with:\n            organization_id: \"tools.organization_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-members\n          description: \"List members of a Stytch B2B organization\"\n          hints:\n            readOnly: true\n          call: \"stytch-b2b.list-members\"\n          with:\n            organization_id: \"tools.organization_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-member\n          description: \"Invite a new member to a Stytch B2B organization\"\n\
  \          hints:\n            readOnly: false\n            destructive: false\n          call: \"stytch-b2b.create-member\"\n          with:\n            organization_id: \"tools.organization_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-member\n          description: \"Remove a member from a Stytch B2B organization\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"stytch-b2b.delete-member\"\n          with:\n            organization_id: \"tools.organization_id\"\n            member_id: \"tools.member_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: send-b2b-magic-link\n          description: \"Send a Stytch magic link to authenticate a B2B organization member\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"stytch-b2b.send-b2b-magic-link\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: authenticate-b2b-session\n          description: \"Validate a Stytch B2B member session token\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"stytch-b2b.authenticate-b2b-session\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-sso-connections\n          description: \"List SSO (SAML/OIDC) connections for a Stytch B2B organization\"\n          hints:\n            readOnly: true\n          call: \"stytch-b2b.list-sso-connections\"\n          with:\n            organization_id: \"tools.organization_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: discover-organizations\n          description: \"Discover Stytch B2B organizations a user can access\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ true\n          call: \"stytch-b2b.discover-organizations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
