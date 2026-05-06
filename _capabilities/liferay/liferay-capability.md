---
categories: []
consumed_apis: []
description: Roles API Basics. You can create and manage roles from the Application menu, but you can also use Liferay's REST APIs. Call these services to manage roles, including associating and dissociating users to regular, site, and organization roles.
layout: capability
name: Liferay Roles API
operations:
- description: List roles
  method: GET
  name: getroles
  path: /roles
- description: Get a role
  method: GET
  name: getrole
  path: /roles/{roleId}
- description: Associate a regular role to a user
  method: POST
  name: associateroletouser
  path: /roles/{roleId}/association/user-account/{userId}
- description: Remove regular role association from a user
  method: DELETE
  name: dissociaterolefromuser
  path: /roles/{roleId}/association/user-account/{userId}
- description: Associate a site role to a user
  method: POST
  name: associatesiteroletouser
  path: /roles/{roleId}/association/user-account/{userId}/site/{siteId}
- description: Remove site role association from a user
  method: DELETE
  name: dissociatesiterolefromuser
  path: /roles/{roleId}/association/user-account/{userId}/site/{siteId}
- description: Associate an organization role to a user
  method: POST
  name: associateorgroletouser
  path: /roles/{roleId}/association/user-account/{userId}/organization/{orgId}
- description: Remove organization role association from a user
  method: DELETE
  name: dissociateorgrolefromuser
  path: /roles/{roleId}/association/user-account/{userId}/organization/{orgId}
personas: []
provider_name: Liferay
provider_slug: liferay
search_terms:
- associate a regular role to a user
- dissociaterolefromuser
- remove site role association from a user
- liferay
- permissions
- dissociatesiterolefromuser
- digital experience
- associatesiteroletouser
- users
- associate an organization role to a user
- getrole
- roles
- getroles
- remove organization role association from a user
- dxp
- dissociateorgrolefromuser
- remove regular role association from a user
- associate a site role to a user
- open source
- api
- headless
- get a role
- associateorgroletouser
- associateroletouser
- list roles
slug: liferay-capability
source_filename: liferay-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Liferay Roles API\n  description: Roles API Basics. You can create and manage roles from the Application menu, but you can also use Liferay's\n    REST APIs. Call these services to manage roles, including associating and dissociating users to regular, site, and organization\n    roles.\n  tags:\n  - Liferay\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: liferay\n    baseUri: http://localhost:8080/o/headless-admin-user/v1.0\n    description: Liferay Roles API HTTP API.\n    authentication:\n      type: basic\n      username: '{{LIFERAY_USERNAME}}'\n      password: '{{LIFERAY_PASSWORD}}'\n    resources:\n    - name: roles\n      path: /roles\n      operations:\n      - name: getroles\n        method: GET\n        description: List roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: roles-roleid\n      path: /roles/{roleId}\n      operations:\n      - name: getrole\n        method: GET\n        description: Get a role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: roles-roleid-association-user-account-userid\n      path: /roles/{roleId}/association/user-account/{userId}\n      operations:\n      - name: associateroletouser\n        method: POST\n        description: Associate a regular role to a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: dissociaterolefromuser\n        method: DELETE\n        description: Remove regular role association from a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: roles-roleid-association-user-account-userid-sit\n      path: /roles/{roleId}/association/user-account/{userId}/site/{siteId}\n\
  \      operations:\n      - name: associatesiteroletouser\n        method: POST\n        description: Associate a site role to a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: dissociatesiterolefromuser\n        method: DELETE\n        description: Remove site role association from a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: roles-roleid-association-user-account-userid-org\n      path: /roles/{roleId}/association/user-account/{userId}/organization/{orgId}\n      operations:\n      - name: associateorgroletouser\n        method: POST\n        description: Associate an organization role to a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: dissociateorgrolefromuser\n        method: DELETE\n \
  \       description: Remove organization role association from a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: liferay-rest\n    description: REST adapter for Liferay Roles API.\n    resources:\n    - path: /roles\n      name: getroles\n      operations:\n      - method: GET\n        name: getroles\n        description: List roles\n        call: liferay.getroles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /roles/{roleId}\n      name: getrole\n      operations:\n      - method: GET\n        name: getrole\n        description: Get a role\n        call: liferay.getrole\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /roles/{roleId}/association/user-account/{userId}\n      name: associateroletouser\n      operations:\n      - method: POST\n        name: associateroletouser\n\
  \        description: Associate a regular role to a user\n        call: liferay.associateroletouser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /roles/{roleId}/association/user-account/{userId}\n      name: dissociaterolefromuser\n      operations:\n      - method: DELETE\n        name: dissociaterolefromuser\n        description: Remove regular role association from a user\n        call: liferay.dissociaterolefromuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /roles/{roleId}/association/user-account/{userId}/site/{siteId}\n      name: associatesiteroletouser\n      operations:\n      - method: POST\n        name: associatesiteroletouser\n        description: Associate a site role to a user\n        call: liferay.associatesiteroletouser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /roles/{roleId}/association/user-account/{userId}/site/{siteId}\n      name: dissociatesiterolefromuser\n\
  \      operations:\n      - method: DELETE\n        name: dissociatesiterolefromuser\n        description: Remove site role association from a user\n        call: liferay.dissociatesiterolefromuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /roles/{roleId}/association/user-account/{userId}/organization/{orgId}\n      name: associateorgroletouser\n      operations:\n      - method: POST\n        name: associateorgroletouser\n        description: Associate an organization role to a user\n        call: liferay.associateorgroletouser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /roles/{roleId}/association/user-account/{userId}/organization/{orgId}\n      name: dissociateorgrolefromuser\n      operations:\n      - method: DELETE\n        name: dissociateorgrolefromuser\n        description: Remove organization role association from a user\n        call: liferay.dissociateorgrolefromuser\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: liferay-mcp\n    transport: http\n    description: MCP adapter for Liferay Roles API for AI agent use.\n    tools:\n    - name: getroles\n      description: List roles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: liferay.getroles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrole\n      description: Get a role\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: liferay.getrole\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: associateroletouser\n      description: Associate a regular role to a user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: liferay.associateroletouser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dissociaterolefromuser\n\
  \      description: Remove regular role association from a user\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: liferay.dissociaterolefromuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: associatesiteroletouser\n      description: Associate a site role to a user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: liferay.associatesiteroletouser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dissociatesiterolefromuser\n      description: Remove site role association from a user\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: liferay.dissociatesiterolefromuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: associateorgroletouser\n      description: Associate an organization role to a user\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: liferay.associateorgroletouser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: dissociateorgrolefromuser\n      description: Remove organization role association from a user\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: liferay.dissociateorgrolefromuser\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    LIFERAY_USERNAME: LIFERAY_USERNAME\n    LIFERAY_PASSWORD: LIFERAY_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/liferay/refs/heads/main/capabilities/liferay-capability.yaml
tags:
- Liferay
- API
tools:
- description: List roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getroles
- description: Get a role
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrole
- description: Associate a regular role to a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: associateroletouser
- description: Remove regular role association from a user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: dissociaterolefromuser
- description: Associate a site role to a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: associatesiteroletouser
- description: Remove site role association from a user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: dissociatesiterolefromuser
- description: Associate an organization role to a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: associateorgroletouser
- description: Remove organization role association from a user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: dissociateorgrolefromuser
---
