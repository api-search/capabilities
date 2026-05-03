---
categories:
- identity-access
consumed_apis:
- dsar-api
- scim-api
- user-mapping-api
description: SCIM provisioning and privacy compliance. For IT admins and compliance teams.
layout: capability
name: Amplitude Identity and Privacy
operations:
- description: Amplitude Create a Data Subject Access Request
  method: POST
  name: createDsarRequest
  path: /v1/data-access
- description: Amplitude Get DSAR Request Status
  method: GET
  name: getDsarRequestStatus
  path: /v1/data-access
- description: Amplitude List Deletion Requests
  method: GET
  name: listDeletionRequests
  path: /v1/data-deletion
- description: Amplitude Request User Data Deletion
  method: POST
  name: createDeletionRequest
  path: /v1/data-deletion
- description: Amplitude List SCIM Users
  method: GET
  name: listScimUsers
  path: /v1/users
- description: Amplitude Create a SCIM User
  method: POST
  name: createScimUser
  path: /v1/users
- description: Amplitude Get a SCIM User
  method: GET
  name: getScimUser
  path: /v1/users
- description: Amplitude Replace a SCIM User
  method: PUT
  name: replaceScimUser
  path: /v1/users
- description: Amplitude Update a SCIM User
  method: PATCH
  name: updateScimUser
  path: /v1/users
- description: Amplitude Delete a SCIM User
  method: DELETE
  name: deleteScimUser
  path: /v1/users
- description: Amplitude List SCIM Groups
  method: GET
  name: listScimGroups
  path: /v1/groups
- description: Amplitude Create a SCIM Group
  method: POST
  name: createScimGroup
  path: /v1/groups
- description: Amplitude Get a SCIM Group
  method: GET
  name: getScimGroup
  path: /v1/groups
- description: Amplitude Update a SCIM Group
  method: PATCH
  name: updateScimGroup
  path: /v1/groups
- description: Amplitude Delete a SCIM Group
  method: DELETE
  name: deleteScimGroup
  path: /v1/groups
- description: Amplitude Map User Identities
  method: POST
  name: mapUser
  path: /v1/user-mapping
- description: Amplitude Unmap User Identities
  method: POST
  name: unmapUser
  path: /v1/user-mapping
personas: []
provider_name: Amplitude
provider_slug: amplitude
search_terms:
- feature flags
- createScimGroup
- createScimUser
- mapUser
- privacy compliance
- amplitude
- identity
- manage and evaluate a/b experiments and feature flags. for product managers.
- runs experiments and feature flags
- getScimGroup
- dsar api getDsarRequestStatus
- privacy
- scim api getScimGroup
- scim api getScimUser
- amplitude delete a scim group
- listDeletionRequests
- amplitude delete a scim user
- updateScimUser
- amplitude list scim groups
- scim api listScimUsers
- amplitude request user data deletion
- replaceScimUser
- amplitude update a scim user
- amplitude unmap user identities
- amplitude replace a scim user
- createDsarRequest
- scim api updateScimUser
- scim api updateScimGroup
- scim provisioning and privacy compliance. for it admins and compliance teams.
- deleteScimGroup
- user mapping api unmapUser
- scim api deleteScimGroup
- amplitude create a scim group
- amplitude create a data subject access request
- amplitude get dsar request status
- createDeletionRequest
- dsar api createDsarRequest
- scim api createScimGroup
- unified workflow for sending events and identifying users. for data engineers.
- manages privacy and compliance
- deleteScimUser
- product analytics
- a/b testing
- scim api createScimUser
- getDsarRequestStatus
- getScimUser
- user behavior
- identity management
- amplitude get a scim group
- updateScimGroup
- analyzes data and manages cohorts
- analytics
- experimentation
- data governance
- amplitude map user identities
- export raw event data and manage behavioral cohorts. for data analysts.
- amplitude list deletion requests
- dsar api listDeletionRequests
- amplitude update a scim group
- unmapUser
- ingests and exports event data
- dsar api createDeletionRequest
- scim api deleteScimUser
- scim api listScimGroups
- manage event schemas and chart annotations. for data governance teams.
- listScimGroups
- scim api replaceScimUser
- listScimUsers
- amplitude create a scim user
- user mapping api mapUser
- amplitude list scim users
- amplitude get a scim user
slug: amplitude-identity-and-privacy
source_filename: amplitude-identity-and-privacy.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amplitude Identity and Privacy\n  description: SCIM provisioning and privacy compliance. For IT admins and compliance teams.\n  tags:\n  - Amplitude\n  - Identity\n  - Privacy\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AMPLITUDE_API_KEY: AMPLITUDE_API_KEY\ncapability:\n  consumes:\n  - import: dsar-api\n    location: ./shared/dsar-api.yaml\n  - import: scim-api\n    location: ./shared/scim-api.yaml\n  - import: user-mapping-api\n    location: ./shared/user-mapping-api.yaml\n  exposes:\n  - type: rest\n    port: 8084\n    namespace: amplitude-identity-and-privacy-api\n    description: REST API for Amplitude Identity and Privacy\n    resources:\n    - path: /v1/data-access\n      name: data-access\n      operations:\n      - method: POST\n        name: createDsarRequest\n        description: Amplitude Create a Data Subject Access Request\n        call: dsar-api.createDsarRequest\n        with:\
  \ {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/data-access\n      name: data-access\n      operations:\n      - method: GET\n        name: getDsarRequestStatus\n        description: Amplitude Get DSAR Request Status\n        call: dsar-api.getDsarRequestStatus\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/data-deletion\n      name: data-deletion\n      operations:\n      - method: GET\n        name: listDeletionRequests\n        description: Amplitude List Deletion Requests\n        call: dsar-api.listDeletionRequests\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/data-deletion\n      name: data-deletion\n      operations:\n      - method: POST\n        name: createDeletionRequest\n        description: Amplitude Request User Data Deletion\n        call: dsar-api.createDeletionRequest\n        with: {}\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      operations:\n      - method: GET\n        name: listScimUsers\n        description: Amplitude List SCIM Users\n        call: scim-api.listScimUsers\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      operations:\n      - method: POST\n        name: createScimUser\n        description: Amplitude Create a SCIM User\n        call: scim-api.createScimUser\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      operations:\n      - method: GET\n        name: getScimUser\n        description: Amplitude Get a SCIM User\n        call: scim-api.getScimUser\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      operations:\n      - method: PUT\n\
  \        name: replaceScimUser\n        description: Amplitude Replace a SCIM User\n        call: scim-api.replaceScimUser\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      operations:\n      - method: PATCH\n        name: updateScimUser\n        description: Amplitude Update a SCIM User\n        call: scim-api.updateScimUser\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      operations:\n      - method: DELETE\n        name: deleteScimUser\n        description: Amplitude Delete a SCIM User\n        call: scim-api.deleteScimUser\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups\n      name: groups\n      operations:\n      - method: GET\n        name: listScimGroups\n        description: Amplitude List SCIM Groups\n        call: scim-api.listScimGroups\n\
  \        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups\n      name: groups\n      operations:\n      - method: POST\n        name: createScimGroup\n        description: Amplitude Create a SCIM Group\n        call: scim-api.createScimGroup\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups\n      name: groups\n      operations:\n      - method: GET\n        name: getScimGroup\n        description: Amplitude Get a SCIM Group\n        call: scim-api.getScimGroup\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups\n      name: groups\n      operations:\n      - method: PATCH\n        name: updateScimGroup\n        description: Amplitude Update a SCIM Group\n        call: scim-api.updateScimGroup\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups\n\
  \      name: groups\n      operations:\n      - method: DELETE\n        name: deleteScimGroup\n        description: Amplitude Delete a SCIM Group\n        call: scim-api.deleteScimGroup\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/user-mapping\n      name: user-mapping\n      operations:\n      - method: POST\n        name: mapUser\n        description: Amplitude Map User Identities\n        call: user-mapping-api.mapUser\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/user-mapping\n      name: user-mapping\n      operations:\n      - method: POST\n        name: unmapUser\n        description: Amplitude Unmap User Identities\n        call: user-mapping-api.unmapUser\n        with: {}\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9094\n    namespace: amplitude-identity-and-privacy-mcp\n    transport: http\n   \
  \ description: MCP for Amplitude Identity and Privacy\n    tools:\n    - name: dsar-api-createDsarRequest\n      description: Amplitude Create a Data Subject Access Request\n      hints:\n        readOnly: false\n      call: dsar-api.createDsarRequest\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dsar-api-getDsarRequestStatus\n      description: Amplitude Get DSAR Request Status\n      hints:\n        readOnly: true\n      call: dsar-api.getDsarRequestStatus\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dsar-api-listDeletionRequests\n      description: Amplitude List Deletion Requests\n      hints:\n        readOnly: true\n      call: dsar-api.listDeletionRequests\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dsar-api-createDeletionRequest\n      description: Amplitude Request User Data Deletion\n      hints:\n        readOnly: false\n\
  \      call: dsar-api.createDeletionRequest\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: scim-api-listScimUsers\n      description: Amplitude List SCIM Users\n      hints:\n        readOnly: true\n      call: scim-api.listScimUsers\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: scim-api-createScimUser\n      description: Amplitude Create a SCIM User\n      hints:\n        readOnly: false\n      call: scim-api.createScimUser\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: scim-api-getScimUser\n      description: Amplitude Get a SCIM User\n      hints:\n        readOnly: true\n      call: scim-api.getScimUser\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: scim-api-replaceScimUser\n      description: Amplitude Replace a SCIM User\n      hints:\n        readOnly: false\n      call: scim-api.replaceScimUser\n\
  \      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: scim-api-updateScimUser\n      description: Amplitude Update a SCIM User\n      hints:\n        readOnly: false\n      call: scim-api.updateScimUser\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: scim-api-deleteScimUser\n      description: Amplitude Delete a SCIM User\n      hints:\n        readOnly: false\n      call: scim-api.deleteScimUser\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: scim-api-listScimGroups\n      description: Amplitude List SCIM Groups\n      hints:\n        readOnly: true\n      call: scim-api.listScimGroups\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: scim-api-createScimGroup\n      description: Amplitude Create a SCIM Group\n      hints:\n        readOnly: false\n      call: scim-api.createScimGroup\n      with: {}\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: scim-api-getScimGroup\n      description: Amplitude Get a SCIM Group\n      hints:\n        readOnly: true\n      call: scim-api.getScimGroup\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: scim-api-updateScimGroup\n      description: Amplitude Update a SCIM Group\n      hints:\n        readOnly: false\n      call: scim-api.updateScimGroup\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: scim-api-deleteScimGroup\n      description: Amplitude Delete a SCIM Group\n      hints:\n        readOnly: false\n      call: scim-api.deleteScimGroup\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: user-mapping-api-mapUser\n      description: Amplitude Map User Identities\n      hints:\n        readOnly: false\n      call: user-mapping-api.mapUser\n      with: {}\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: user-mapping-api-unmapUser\n      description: Amplitude Unmap User Identities\n      hints:\n        readOnly: false\n      call: user-mapping-api.unmapUser\n      with: {}\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amplitude/refs/heads/main/capabilities/amplitude-identity-and-privacy.yaml
tags:
- Amplitude
- Identity
- Privacy
tools:
- description: Amplitude Create a Data Subject Access Request
  hints:
    readOnly: false
  name: dsar-api-createDsarRequest
- description: Amplitude Get DSAR Request Status
  hints:
    readOnly: true
  name: dsar-api-getDsarRequestStatus
- description: Amplitude List Deletion Requests
  hints:
    readOnly: true
  name: dsar-api-listDeletionRequests
- description: Amplitude Request User Data Deletion
  hints:
    readOnly: false
  name: dsar-api-createDeletionRequest
- description: Amplitude List SCIM Users
  hints:
    readOnly: true
  name: scim-api-listScimUsers
- description: Amplitude Create a SCIM User
  hints:
    readOnly: false
  name: scim-api-createScimUser
- description: Amplitude Get a SCIM User
  hints:
    readOnly: true
  name: scim-api-getScimUser
- description: Amplitude Replace a SCIM User
  hints:
    readOnly: false
  name: scim-api-replaceScimUser
- description: Amplitude Update a SCIM User
  hints:
    readOnly: false
  name: scim-api-updateScimUser
- description: Amplitude Delete a SCIM User
  hints:
    readOnly: false
  name: scim-api-deleteScimUser
- description: Amplitude List SCIM Groups
  hints:
    readOnly: true
  name: scim-api-listScimGroups
- description: Amplitude Create a SCIM Group
  hints:
    readOnly: false
  name: scim-api-createScimGroup
- description: Amplitude Get a SCIM Group
  hints:
    readOnly: true
  name: scim-api-getScimGroup
- description: Amplitude Update a SCIM Group
  hints:
    readOnly: false
  name: scim-api-updateScimGroup
- description: Amplitude Delete a SCIM Group
  hints:
    readOnly: false
  name: scim-api-deleteScimGroup
- description: Amplitude Map User Identities
  hints:
    readOnly: false
  name: user-mapping-api-mapUser
- description: Amplitude Unmap User Identities
  hints:
    readOnly: false
  name: user-mapping-api-unmapUser
---
