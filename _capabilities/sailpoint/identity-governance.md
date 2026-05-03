---
api_specs:
- filename: identity-security-cloud-v3.yml
  format: yaml
  label: isc-v3
  slug: isc-v3
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/sailpoint/refs/heads/main/openapi/identity-security-cloud-v3.yml
categories: []
consumed_apis:
- isc-v3
description: Unified workflow capability for identity governance and access management using SailPoint Identity Security Cloud. Combines identity lifecycle, access profile management, role administration, and certification review into a single governance workflow for IAM administrators and compliance teams.
layout: capability
name: SailPoint Identity Governance
operations:
- description: List public identities with filtering and pagination.
  method: GET
  name: list-identities
  path: /v1/identities
- description: Get a public identity by ID.
  method: GET
  name: get-identity
  path: /v1/identities/{id}
- description: List identity profiles.
  method: GET
  name: list-identity-profiles
  path: /v1/identity-profiles
- description: Create a new identity profile.
  method: POST
  name: create-identity-profile
  path: /v1/identity-profiles
- description: Get an identity profile by ID.
  method: GET
  name: get-identity-profile
  path: /v1/identity-profiles/{id}
- description: Update an identity profile.
  method: PUT
  name: update-identity-profile
  path: /v1/identity-profiles/{id}
- description: Delete an identity profile.
  method: DELETE
  name: delete-identity-profile
  path: /v1/identity-profiles/{id}
- description: List access profiles.
  method: GET
  name: list-access-profiles
  path: /v1/access-profiles
- description: Create a new access profile.
  method: POST
  name: create-access-profile
  path: /v1/access-profiles
- description: Get an access profile by ID.
  method: GET
  name: get-access-profile
  path: /v1/access-profiles/{id}
- description: Delete an access profile.
  method: DELETE
  name: delete-access-profile
  path: /v1/access-profiles/{id}
- description: List roles.
  method: GET
  name: list-roles
  path: /v1/roles
- description: Create a new role.
  method: POST
  name: create-role
  path: /v1/roles
- description: Get a role by ID.
  method: GET
  name: get-role
  path: /v1/roles/{id}
- description: Delete a role.
  method: DELETE
  name: delete-role
  path: /v1/roles/{id}
- description: List identities assigned to a role.
  method: GET
  name: list-role-identities
  path: /v1/roles/{id}/identities
- description: List identity campaign certifications.
  method: GET
  name: list-certifications
  path: /v1/certifications
- description: Get a certification by ID.
  method: GET
  name: get-certification
  path: /v1/certifications/{id}
- description: List access review items for a certification.
  method: GET
  name: list-access-review-items
  path: /v1/certifications/{id}/access-review-items
- description: Approve or revoke access certification items.
  method: POST
  name: decide-certification
  path: /v1/certifications/{id}/decide
- description: Sign off and finalize a certification.
  method: POST
  name: sign-off-certification
  path: /v1/certifications/{id}/sign-off
personas: []
provider_name: SailPoint
provider_slug: sailpoint
search_terms:
- roles for organizational access management.
- security
- get a certification by id.
- decide certification
- identity profiles for users in the organization.
- delete identity profile
- list access review items
- approve or revoke access certification items.
- delete access profile
- certifications
- list access review items for a certification campaign.
- identity security
- delete an identity profile.
- list access profiles grouping entitlements.
- delete an access profile.
- create a new access profile.
- access governance
- get a public identity by id.
- finalize certification decisions.
- list role identities
- access review items within a certification.
- sign off and finalize a certification.
- make approve or revoke decisions on certification access items.
- list access profiles
- sailpoint
- manage a specific certification.
- update identity profile
- manage a specific identity profile.
- get a role by id.
- list organizational roles for access management.
- create access profile
- roles
- list identities assigned to a role.
- list identity profiles.
- identities assigned to a role.
- manage a specific access profile.
- list certifications
- list public identities with filtering and pagination.
- create a new identity profile.
- list public identities in sailpoint identity security cloud with filtering.
- list identities
- access certifications for compliance reviews.
- manage a specific role.
- compliance
- get certification
- list identity campaign certifications for compliance review.
- finalize and sign off a completed certification review.
- get an identity profile by id.
- list access profiles.
- list identity profiles defining source attribute mappings.
- create a new role.
- get role
- iam
- get a specific identity by id.
- update an identity profile.
- list roles
- sign off certification
- identity management
- list access review items for a certification.
- create identity profile
- delete a role.
- get access profile
- retrieve a specific identity.
- delete role
- decide certification items
- list identity profiles
- get an access profile by id.
- create role
- make decisions on certification items.
- identity profiles defining source-to-identity attribute mappings.
- get identity
- get identity profile
- list roles.
- get a specific certification by id.
- list identities assigned to a specific role.
- create a new role in identity security cloud.
- access profiles grouping entitlements for provisioning.
- list identity campaign certifications.
slug: identity-governance
source_filename: identity-governance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SailPoint Identity Governance\"\n  description: >-\n    Unified workflow capability for identity governance and access management\n    using SailPoint Identity Security Cloud. Combines identity lifecycle,\n    access profile management, role administration, and certification review\n    into a single governance workflow for IAM administrators and compliance teams.\n  tags:\n    - Access Governance\n    - Certifications\n    - Compliance\n    - IAM\n    - Identity Management\n    - Identity Security\n    - Roles\n    - SailPoint\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SAILPOINT_OAUTH2_TOKEN: SAILPOINT_OAUTH2_TOKEN\n      SAILPOINT_TENANT: SAILPOINT_TENANT\n\ncapability:\n  consumes:\n    - import: isc-v3\n      location: ./shared/identity-security-cloud-v3.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sailpoint-identity-governance-api\n   \
  \   description: \"Unified REST API for SailPoint identity governance workflows.\"\n      resources:\n        - path: /v1/identities\n          name: identities\n          description: \"Identity profiles for users in the organization.\"\n          operations:\n            - method: GET\n              name: list-identities\n              description: \"List public identities with filtering and pagination.\"\n              call: \"isc-v3.list-public-identities\"\n              with:\n                filters: \"rest.filters\"\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n        - path: /v1/identities/{id}\n          name: identity-by-id\n          description: \"Retrieve a specific identity.\"\n          operations:\n            - method: GET\n              name: get-identity\n              description: \"Get a public identity by ID.\"\n              call:\
  \ \"isc-v3.get-public-identity\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/identity-profiles\n          name: identity-profiles\n          description: \"Identity profiles defining source-to-identity attribute mappings.\"\n          operations:\n            - method: GET\n              name: list-identity-profiles\n              description: \"List identity profiles.\"\n              call: \"isc-v3.list-identity-profiles\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-identity-profile\n              description: \"Create a new identity profile.\"\n              call: \"isc-v3.create-identity-profile\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/identity-profiles/{id}\n   \
  \       name: identity-profile-by-id\n          description: \"Manage a specific identity profile.\"\n          operations:\n            - method: GET\n              name: get-identity-profile\n              description: \"Get an identity profile by ID.\"\n              call: \"isc-v3.get-identity-profile\"\n              with:\n                identity-profile-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-identity-profile\n              description: \"Update an identity profile.\"\n              call: \"isc-v3.update-identity-profile\"\n              with:\n                identity-profile-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-identity-profile\n              description: \"Delete an identity profile.\"\n              call: \"isc-v3.delete-identity-profile\"\
  \n              with:\n                identity-profile-id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/access-profiles\n          name: access-profiles\n          description: \"Access profiles grouping entitlements for provisioning.\"\n          operations:\n            - method: GET\n              name: list-access-profiles\n              description: \"List access profiles.\"\n              call: \"isc-v3.list-access-profiles\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-access-profile\n              description: \"Create a new access profile.\"\n              call: \"isc-v3.create-access-profile\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/access-profiles/{id}\n          name: access-profile-by-id\n        \
  \  description: \"Manage a specific access profile.\"\n          operations:\n            - method: GET\n              name: get-access-profile\n              description: \"Get an access profile by ID.\"\n              call: \"isc-v3.get-access-profile\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-access-profile\n              description: \"Delete an access profile.\"\n              call: \"isc-v3.delete-access-profile\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/roles\n          name: roles\n          description: \"Roles for organizational access management.\"\n          operations:\n            - method: GET\n              name: list-roles\n              description: \"List roles.\"\n \
  \             call: \"isc-v3.list-roles\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-role\n              description: \"Create a new role.\"\n              call: \"isc-v3.create-role\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/roles/{id}\n          name: role-by-id\n          description: \"Manage a specific role.\"\n          operations:\n            - method: GET\n              name: get-role\n              description: \"Get a role by ID.\"\n              call: \"isc-v3.get-role\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-role\n              description: \"Delete a role.\"\n              call: \"isc-v3.delete-role\"\n          \
  \    with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/roles/{id}/identities\n          name: role-identities\n          description: \"Identities assigned to a role.\"\n          operations:\n            - method: GET\n              name: list-role-identities\n              description: \"List identities assigned to a role.\"\n              call: \"isc-v3.list-role-identities\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n        - path: /v1/certifications\n          name: certifications\n          description: \"Access certifications for compliance reviews.\"\n          operations:\n            - method: GET\n              name: list-certifications\n              description: \"List identity campaign certifications.\"\n              call: \"isc-v3.list-certifications\"\
  \n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n        - path: /v1/certifications/{id}\n          name: certification-by-id\n          description: \"Manage a specific certification.\"\n          operations:\n            - method: GET\n              name: get-certification\n              description: \"Get a certification by ID.\"\n              call: \"isc-v3.get-certification\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/certifications/{id}/access-review-items\n          name: certification-review-items\n          description: \"Access review items within a certification.\"\n          operations:\n            - method: GET\n              name: list-access-review-items\n              description: \"List access review items for a certification.\"\n              call: \"isc-v3.list-access-review-items\"\n\
  \              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n        - path: /v1/certifications/{id}/decide\n          name: certification-decisions\n          description: \"Make decisions on certification items.\"\n          operations:\n            - method: POST\n              name: decide-certification\n              description: \"Approve or revoke access certification items.\"\n              call: \"isc-v3.decide-certification\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/certifications/{id}/sign-off\n          name: certification-sign-off\n          description: \"Finalize certification decisions.\"\n          operations:\n            - method: POST\n              name: sign-off-certification\n              description: \"Sign off and finalize a certification.\"\
  \n              call: \"isc-v3.sign-off-certification\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: sailpoint-identity-governance-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SailPoint identity governance workflows.\"\n      tools:\n        - name: list-identities\n          description: \"List public identities in SailPoint Identity Security Cloud with filtering.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"isc-v3.list-public-identities\"\n          with:\n            filters: \"tools.filters\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: get-identity\n          description: \"Get a specific identity by ID.\"\n          hints:\n            readOnly:\
  \ true\n            idempotent: true\n          call: \"isc-v3.get-public-identity\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-identity-profiles\n          description: \"List identity profiles defining source attribute mappings.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"isc-v3.list-identity-profiles\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: create-identity-profile\n          description: \"Create a new identity profile.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"isc-v3.create-identity-profile\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-access-profiles\n          description: \"List access profiles grouping entitlements.\"\n        \
  \  hints:\n            readOnly: true\n            idempotent: true\n          call: \"isc-v3.list-access-profiles\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: create-access-profile\n          description: \"Create a new access profile.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"isc-v3.create-access-profile\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-roles\n          description: \"List organizational roles for access management.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"isc-v3.list-roles\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: create-role\n          description: \"Create a new role in Identity Security Cloud.\"\n          hints:\n            readOnly: false\n            destructive:\
  \ false\n          call: \"isc-v3.create-role\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-role-identities\n          description: \"List identities assigned to a specific role.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"isc-v3.list-role-identities\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: list-certifications\n          description: \"List identity campaign certifications for compliance review.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"isc-v3.list-certifications\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: get-certification\n          description: \"Get a specific certification by ID.\"\n          hints:\n            readOnly: true\n          \
  \  idempotent: true\n          call: \"isc-v3.get-certification\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-access-review-items\n          description: \"List access review items for a certification campaign.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"isc-v3.list-access-review-items\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: decide-certification-items\n          description: \"Make approve or revoke decisions on certification access items.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"isc-v3.decide-certification\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name:\
  \ sign-off-certification\n          description: \"Finalize and sign off a completed certification review.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"isc-v3.sign-off-certification\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sailpoint/refs/heads/main/capabilities/identity-governance.yaml
tags:
- Access Governance
- Certifications
- Compliance
- IAM
- Identity Management
- Identity Security
- Roles
- SailPoint
tools:
- description: List public identities in SailPoint Identity Security Cloud with filtering.
  hints:
    idempotent: true
    readOnly: true
  name: list-identities
- description: Get a specific identity by ID.
  hints:
    idempotent: true
    readOnly: true
  name: get-identity
- description: List identity profiles defining source attribute mappings.
  hints:
    idempotent: true
    readOnly: true
  name: list-identity-profiles
- description: Create a new identity profile.
  hints:
    destructive: false
    readOnly: false
  name: create-identity-profile
- description: List access profiles grouping entitlements.
  hints:
    idempotent: true
    readOnly: true
  name: list-access-profiles
- description: Create a new access profile.
  hints:
    destructive: false
    readOnly: false
  name: create-access-profile
- description: List organizational roles for access management.
  hints:
    idempotent: true
    readOnly: true
  name: list-roles
- description: Create a new role in Identity Security Cloud.
  hints:
    destructive: false
    readOnly: false
  name: create-role
- description: List identities assigned to a specific role.
  hints:
    idempotent: true
    readOnly: true
  name: list-role-identities
- description: List identity campaign certifications for compliance review.
  hints:
    idempotent: true
    readOnly: true
  name: list-certifications
- description: Get a specific certification by ID.
  hints:
    idempotent: true
    readOnly: true
  name: get-certification
- description: List access review items for a certification campaign.
  hints:
    idempotent: true
    readOnly: true
  name: list-access-review-items
- description: Make approve or revoke decisions on certification access items.
  hints:
    destructive: false
    readOnly: false
  name: decide-certification-items
- description: Finalize and sign off a completed certification review.
  hints:
    destructive: false
    readOnly: false
  name: sign-off-certification
---
