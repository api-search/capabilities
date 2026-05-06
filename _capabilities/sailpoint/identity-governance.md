---
categories: []
consumed_apis: []
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
- retrieve a specific identity.
- make decisions on certification items.
- identity management
- security
- get certification
- list public identities in sailpoint identity security cloud with filtering.
- sign off and finalize a certification.
- list access review items for a certification.
- access governance
- delete an access profile.
- delete identity profile
- manage a specific certification.
- list access profiles grouping entitlements.
- sailpoint
- create role
- manage a specific role.
- get access profile
- make approve or revoke decisions on certification access items.
- delete an identity profile.
- manage a specific access profile.
- identity security
- list public identities with filtering and pagination.
- create identity profile
- decide certification
- roles
- finalize and sign off a completed certification review.
- list identity campaign certifications for compliance review.
- create a new role in identity security cloud.
- get identity profile
- decide certification items
- get identity
- approve or revoke access certification items.
- delete access profile
- sign off certification
- identity profiles defining source-to-identity attribute mappings.
- list certifications
- iam
- list access review items
- certifications
- list access review items for a certification campaign.
- get an access profile by id.
- access review items within a certification.
- list identity profiles.
- compliance
- get a specific identity by id.
- list access profiles.
- access profiles grouping entitlements for provisioning.
- create a new access profile.
- list identities assigned to a role.
- get a specific certification by id.
- get a certification by id.
- update an identity profile.
- list roles
- create access profile
- list access profiles
- update identity profile
- get role
- access certifications for compliance reviews.
- list role identities
- list identity profiles
- get an identity profile by id.
- identity profiles for users in the organization.
- delete a role.
- list identity campaign certifications.
- identities assigned to a role.
- list identities assigned to a specific role.
- create a new role.
- create a new identity profile.
- list roles.
- get a public identity by id.
- list organizational roles for access management.
- roles for organizational access management.
- manage a specific identity profile.
- list identity profiles defining source attribute mappings.
- delete role
- list identities
- get a role by id.
- finalize certification decisions.
slug: identity-governance
source_filename: identity-governance.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SailPoint Identity Governance\n  description: Unified workflow capability for identity governance and access management using SailPoint Identity Security\n    Cloud. Combines identity lifecycle, access profile management, role administration, and certification review into a single\n    governance workflow for IAM administrators and compliance teams.\n  tags:\n  - Access Governance\n  - Certifications\n  - Compliance\n  - IAM\n  - Identity Management\n  - Identity Security\n  - Roles\n  - SailPoint\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SAILPOINT_OAUTH2_TOKEN: SAILPOINT_OAUTH2_TOKEN\n    SAILPOINT_TENANT: SAILPOINT_TENANT\ncapability:\n  consumes:\n  - type: http\n    namespace: isc-v3\n    baseUri: https://{{env.SAILPOINT_TENANT}}.api.identitynow.com/v3\n    description: SailPoint Identity Security Cloud V3 REST API.\n    authentication:\n      type: bearer\n      token: '{{env.SAILPOINT_OAUTH2_TOKEN}}'\n\
  \    resources:\n    - name: public-identities\n      path: /public-identities\n      description: Public identity profiles for users in Identity Security Cloud.\n      operations:\n      - name: list-public-identities\n        method: GET\n        description: List public identities with optional filtering and sorting.\n        inputParameters:\n        - name: add-core-filters\n          in: query\n          type: boolean\n          required: false\n          description: Exclude incomplete identities and uncorrelated accounts.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results (max 250).\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Offset into the full result set.\n        - name: filters\n          in: query\n          type: string\n          required: false\n          description: Filter expression (e.g. name eq\
  \ \"John Smith\").\n        - name: sorters\n          in: query\n          type: string\n          required: false\n          description: Sort expression (e.g. name,-email).\n        outputRawFormat: json\n        outputParameters:\n        - name: identities\n          type: array\n          value: $.\n      - name: get-public-identity\n        method: GET\n        description: Get a single public identity by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The identity ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: identity\n          type: object\n          value: $.\n    - name: identity-profiles\n      path: /identity-profiles\n      description: Identity profile mappings between source accounts and identity attributes.\n      operations:\n      - name: list-identity-profiles\n        method: GET\n        description: List identity profiles.\n        inputParameters:\n\
  \        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Offset into the full result set.\n        - name: filters\n          in: query\n          type: string\n          required: false\n          description: Filter expression.\n        outputRawFormat: json\n        outputParameters:\n        - name: profiles\n          type: array\n          value: $.\n      - name: create-identity-profile\n        method: POST\n        description: Create a new identity profile.\n        outputRawFormat: json\n        outputParameters:\n        - name: profile\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            authoritativeSource: '{{tools.authoritativeSource}}'\n      - name: get-identity-profile\n\
  \        method: GET\n        description: Get an identity profile by ID.\n        inputParameters:\n        - name: identity-profile-id\n          in: path\n          type: string\n          required: true\n          description: The identity profile ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: profile\n          type: object\n          value: $.\n      - name: update-identity-profile\n        method: PUT\n        description: Update an identity profile.\n        inputParameters:\n        - name: identity-profile-id\n          in: path\n          type: string\n          required: true\n          description: The identity profile ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: profile\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: delete-identity-profile\n        method: DELETE\n        description: Delete an identity profile.\n\
  \        inputParameters:\n        - name: identity-profile-id\n          in: path\n          type: string\n          required: true\n          description: The identity profile ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: access-profiles\n      path: /access-profiles\n      description: Access profiles grouping entitlements for provisioning and certifications.\n      operations:\n      - name: list-access-profiles\n        method: GET\n        description: List access profiles with optional filtering and sorting.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Offset into the result set.\n        - name: filters\n          in: query\n          type:\
  \ string\n          required: false\n          description: Filter expression.\n        - name: sorters\n          in: query\n          type: string\n          required: false\n          description: Sort expression.\n        outputRawFormat: json\n        outputParameters:\n        - name: accessProfiles\n          type: array\n          value: $.\n      - name: create-access-profile\n        method: POST\n        description: Create a new access profile.\n        outputRawFormat: json\n        outputParameters:\n        - name: accessProfile\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            owner: '{{tools.owner}}'\n            source: '{{tools.source}}'\n            entitlements: '{{tools.entitlements}}'\n      - name: get-access-profile\n        method: GET\n        description: Get an access profile by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type:\
  \ string\n          required: true\n          description: The access profile ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: accessProfile\n          type: object\n          value: $.\n      - name: delete-access-profile\n        method: DELETE\n        description: Delete an access profile.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The access profile ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: bulk-delete-access-profiles\n        method: POST\n        description: Bulk delete multiple access profiles.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            ids: '{{tools.ids}}'\n    - name: roles\n      path: /roles\n    \
  \  description: Roles grouping access profiles for broad organizational access assignment.\n      operations:\n      - name: list-roles\n        method: GET\n        description: List roles with optional filtering and sorting.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Offset into the result set.\n        - name: filters\n          in: query\n          type: string\n          required: false\n          description: Filter expression.\n        - name: sorters\n          in: query\n          type: string\n          required: false\n          description: Sort expression.\n        outputRawFormat: json\n        outputParameters:\n        - name: roles\n          type: array\n          value: $.\n      - name: create-role\n        method: POST\n\
  \        description: Create a new role.\n        outputRawFormat: json\n        outputParameters:\n        - name: role\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            owner: '{{tools.owner}}'\n            accessProfiles: '{{tools.accessProfiles}}'\n      - name: get-role\n        method: GET\n        description: Get a role by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The role ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: role\n          type: object\n          value: $.\n      - name: delete-role\n        method: DELETE\n        description: Delete a role.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The role ID.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: list-role-identities\n        method: GET\n        description: List identities assigned to a role.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The role ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: identities\n          type: array\n          value: $.\n    - name: certifications\n      path: /certifications\n      description: Access certifications for periodic access review and compliance.\n      operations:\n      - name: list-certifications\n        method: GET\n        description: List identity campaign certifications.\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results.\n        - name: offset\n          in: query\n          type: integer\n          required:\
  \ false\n          description: Offset into the result set.\n        - name: filters\n          in: query\n          type: string\n          required: false\n          description: Filter expression.\n        outputRawFormat: json\n        outputParameters:\n        - name: certifications\n          type: array\n          value: $.\n      - name: get-certification\n        method: GET\n        description: Get a single identity certification by ID.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The certification ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: certification\n          type: object\n          value: $.\n      - name: list-access-review-items\n        method: GET\n        description: List access review items for a certification.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n    \
  \      description: The certification ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: items\n          type: array\n          value: $.\n      - name: decide-certification\n        method: POST\n        description: Make approve/revoke decisions on certification items.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The certification ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            items: '{{tools.items}}'\n      - name: reassign-certification\n        method: POST\n        description: Reassign identities or items in a certification.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The certification ID.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            reassignTo: '{{tools.reassignTo}}'\n            items: '{{tools.items}}'\n      - name: sign-off-certification\n        method: POST\n        description: Finalize identity certification decisions.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The certification ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sailpoint-identity-governance-api\n    description: Unified REST API for SailPoint identity governance workflows.\n    resources:\n    - path: /v1/identities\n      name: identities\n      description: Identity profiles for users in the organization.\n      operations:\n      - method:\
  \ GET\n        name: list-identities\n        description: List public identities with filtering and pagination.\n        call: isc-v3.list-public-identities\n        with:\n          filters: rest.filters\n          limit: rest.limit\n          offset: rest.offset\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/identities/{id}\n      name: identity-by-id\n      description: Retrieve a specific identity.\n      operations:\n      - method: GET\n        name: get-identity\n        description: Get a public identity by ID.\n        call: isc-v3.get-public-identity\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/identity-profiles\n      name: identity-profiles\n      description: Identity profiles defining source-to-identity attribute mappings.\n      operations:\n      - method: GET\n        name: list-identity-profiles\n        description: List identity profiles.\n\
  \        call: isc-v3.list-identity-profiles\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-identity-profile\n        description: Create a new identity profile.\n        call: isc-v3.create-identity-profile\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/identity-profiles/{id}\n      name: identity-profile-by-id\n      description: Manage a specific identity profile.\n      operations:\n      - method: GET\n        name: get-identity-profile\n        description: Get an identity profile by ID.\n        call: isc-v3.get-identity-profile\n        with:\n          identity-profile-id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-identity-profile\n        description: Update an identity profile.\n        call: isc-v3.update-identity-profile\n        with:\n          identity-profile-id: rest.id\n  \
  \      outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-identity-profile\n        description: Delete an identity profile.\n        call: isc-v3.delete-identity-profile\n        with:\n          identity-profile-id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/access-profiles\n      name: access-profiles\n      description: Access profiles grouping entitlements for provisioning.\n      operations:\n      - method: GET\n        name: list-access-profiles\n        description: List access profiles.\n        call: isc-v3.list-access-profiles\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-access-profile\n        description: Create a new access profile.\n        call: isc-v3.create-access-profile\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/access-profiles/{id}\n\
  \      name: access-profile-by-id\n      description: Manage a specific access profile.\n      operations:\n      - method: GET\n        name: get-access-profile\n        description: Get an access profile by ID.\n        call: isc-v3.get-access-profile\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-access-profile\n        description: Delete an access profile.\n        call: isc-v3.delete-access-profile\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/roles\n      name: roles\n      description: Roles for organizational access management.\n      operations:\n      - method: GET\n        name: list-roles\n        description: List roles.\n        call: isc-v3.list-roles\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-role\n      \
  \  description: Create a new role.\n        call: isc-v3.create-role\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/roles/{id}\n      name: role-by-id\n      description: Manage a specific role.\n      operations:\n      - method: GET\n        name: get-role\n        description: Get a role by ID.\n        call: isc-v3.get-role\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-role\n        description: Delete a role.\n        call: isc-v3.delete-role\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/roles/{id}/identities\n      name: role-identities\n      description: Identities assigned to a role.\n      operations:\n      - method: GET\n        name: list-role-identities\n        description: List identities assigned to a role.\n        call: isc-v3.list-role-identities\n\
  \        with:\n          id: rest.id\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/certifications\n      name: certifications\n      description: Access certifications for compliance reviews.\n      operations:\n      - method: GET\n        name: list-certifications\n        description: List identity campaign certifications.\n        call: isc-v3.list-certifications\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/certifications/{id}\n      name: certification-by-id\n      description: Manage a specific certification.\n      operations:\n      - method: GET\n        name: get-certification\n        description: Get a certification by ID.\n        call: isc-v3.get-certification\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/certifications/{id}/access-review-items\n      name: certification-review-items\n      description:\
  \ Access review items within a certification.\n      operations:\n      - method: GET\n        name: list-access-review-items\n        description: List access review items for a certification.\n        call: isc-v3.list-access-review-items\n        with:\n          id: rest.id\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/certifications/{id}/decide\n      name: certification-decisions\n      description: Make decisions on certification items.\n      operations:\n      - method: POST\n        name: decide-certification\n        description: Approve or revoke access certification items.\n        call: isc-v3.decide-certification\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/certifications/{id}/sign-off\n      name: certification-sign-off\n      description: Finalize certification decisions.\n      operations:\n      - method: POST\n        name: sign-off-certification\n\
  \        description: Sign off and finalize a certification.\n        call: isc-v3.sign-off-certification\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: sailpoint-identity-governance-mcp\n    transport: http\n    description: MCP server for AI-assisted SailPoint identity governance workflows.\n    tools:\n    - name: list-identities\n      description: List public identities in SailPoint Identity Security Cloud with filtering.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: isc-v3.list-public-identities\n      with:\n        filters: tools.filters\n        limit: tools.limit\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-identity\n      description: Get a specific identity by ID.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: isc-v3.get-public-identity\n      with:\n        id: tools.id\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-identity-profiles\n      description: List identity profiles defining source attribute mappings.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: isc-v3.list-identity-profiles\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: create-identity-profile\n      description: Create a new identity profile.\n      hints:\n        readOnly: false\n        destructive: false\n      call: isc-v3.create-identity-profile\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-access-profiles\n      description: List access profiles grouping entitlements.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: isc-v3.list-access-profiles\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: create-access-profile\n      description: Create a new access profile.\n      hints:\n      \
  \  readOnly: false\n        destructive: false\n      call: isc-v3.create-access-profile\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-roles\n      description: List organizational roles for access management.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: isc-v3.list-roles\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: create-role\n      description: Create a new role in Identity Security Cloud.\n      hints:\n        readOnly: false\n        destructive: false\n      call: isc-v3.create-role\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-role-identities\n      description: List identities assigned to a specific role.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: isc-v3.list-role-identities\n      with:\n        id: tools.id\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: list-certifications\n\
  \      description: List identity campaign certifications for compliance review.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: isc-v3.list-certifications\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-certification\n      description: Get a specific certification by ID.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: isc-v3.get-certification\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-access-review-items\n      description: List access review items for a certification campaign.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: isc-v3.list-access-review-items\n      with:\n        id: tools.id\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: decide-certification-items\n      description: Make approve or revoke decisions on certification access items.\n      hints:\n\
  \        readOnly: false\n        destructive: false\n      call: isc-v3.decide-certification\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sign-off-certification\n      description: Finalize and sign off a completed certification review.\n      hints:\n        readOnly: false\n        destructive: false\n      call: isc-v3.sign-off-certification\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
