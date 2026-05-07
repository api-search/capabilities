---
categories: []
consumed_apis: []
description: The Cloud IAM API enables management of identity and access control policies, service accounts, roles, and permissions for Google Cloud resources.
layout: capability
name: Google Cloud IAM API
operations:
- description: Google Cloud IAM List service accounts
  method: GET
  name: listserviceaccounts
  path: /projects/{projectId}/serviceAccounts
- description: Google Cloud IAM Create a service account
  method: POST
  name: createserviceaccount
  path: /projects/{projectId}/serviceAccounts
- description: Google Cloud IAM Get a service account
  method: GET
  name: getserviceaccount
  path: /projects/{projectId}/serviceAccounts/{serviceAccountEmail}
- description: Google Cloud IAM Update a service account
  method: PATCH
  name: patchserviceaccount
  path: /projects/{projectId}/serviceAccounts/{serviceAccountEmail}
- description: Google Cloud IAM Delete a service account
  method: DELETE
  name: deleteserviceaccount
  path: /projects/{projectId}/serviceAccounts/{serviceAccountEmail}
- description: Google Cloud IAM List service account keys
  method: GET
  name: listserviceaccountkeys
  path: /projects/{projectId}/serviceAccounts/{serviceAccountEmail}/keys
- description: Google Cloud IAM Create a service account key
  method: POST
  name: createserviceaccountkey
  path: /projects/{projectId}/serviceAccounts/{serviceAccountEmail}/keys
- description: Google Cloud IAM List roles
  method: GET
  name: listroles
  path: /roles
- description: Google Cloud IAM List project roles
  method: GET
  name: listprojectroles
  path: /projects/{projectId}/roles
- description: Google Cloud IAM Create a custom role
  method: POST
  name: createprojectrole
  path: /projects/{projectId}/roles
- description: Google Cloud IAM Query testable permissions
  method: POST
  name: querytestablepermissions
  path: /permissions:queryTestablePermissions
personas: []
provider_name: Google Cloud IAM
provider_slug: google-cloud-iam
search_terms:
- querytestablepermissions
- google cloud iam list service account keys
- listserviceaccountkeys
- permissions
- listprojectroles
- google cloud iam list service accounts
- google cloud iam update a service account
- google cloud iam list project roles
- deleteserviceaccount
- api
- google cloud iam list roles
- google cloud iam delete a service account
- google cloud iam get a service account
- createserviceaccount
- google cloud iam create a custom role
- createprojectrole
- google
- identity
- iam
- getserviceaccount
- listserviceaccounts
- cloud
- access management
- createserviceaccountkey
- google cloud iam query testable permissions
- listroles
- patchserviceaccount
- google cloud iam create a service account
- google cloud
- security
- google cloud iam create a service account key
slug: google-cloud-iam-capability
source_filename: google-cloud-iam-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud IAM API\n  description: The Cloud IAM API enables management of identity and access control policies, service accounts, roles, and\n    permissions for Google Cloud resources.\n  tags:\n  - Google\n  - Cloud\n  - Iam\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-iam\n    baseUri: https://iam.googleapis.com/v1\n    description: Google Cloud IAM API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_IAM_TOKEN}}'\n    resources:\n    - name: projects-projectid-serviceaccounts\n      path: /projects/{projectId}/serviceAccounts\n      operations:\n      - name: listserviceaccounts\n        method: GET\n        description: Google Cloud IAM List service accounts\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n     \
  \     in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createserviceaccount\n        method: POST\n        description: Google Cloud IAM Create a service account\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-serviceaccounts-serviceaccoun\n      path: /projects/{projectId}/serviceAccounts/{serviceAccountEmail}\n      operations:\n      - name: getserviceaccount\n        method: GET\n        description: Google Cloud IAM Get a service account\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n\
  \        - name: serviceAccountEmail\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchserviceaccount\n        method: PATCH\n        description: Google Cloud IAM Update a service account\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: serviceAccountEmail\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteserviceaccount\n        method: DELETE\n        description: Google Cloud IAM Delete a service account\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: serviceAccountEmail\n \
  \         in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-serviceaccounts-serviceaccoun\n      path: /projects/{projectId}/serviceAccounts/{serviceAccountEmail}/keys\n      operations:\n      - name: listserviceaccountkeys\n        method: GET\n        description: Google Cloud IAM List service account keys\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: serviceAccountEmail\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createserviceaccountkey\n        method: POST\n        description: Google Cloud IAM Create a service account key\n        inputParameters:\n       \
  \ - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: serviceAccountEmail\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: roles\n      path: /roles\n      operations:\n      - name: listroles\n        method: GET\n        description: Google Cloud IAM List roles\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-roles\n      path: /projects/{projectId}/roles\n      operations:\n      - name: listprojectroles\n        method: GET\n        description: Google Cloud IAM List project roles\n        inputParameters:\n\
  \        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createprojectrole\n        method: POST\n        description: Google Cloud IAM Create a custom role\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: permissions-querytestablepermissions\n      path: /permissions:queryTestablePermissions\n      operations:\n      - name: querytestablepermissions\n        method: POST\n        description: Google Cloud IAM Query testable permissions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port:\
  \ 8080\n    namespace: google-cloud-iam-rest\n    description: REST adapter for Google Cloud IAM API.\n    resources:\n    - path: /projects/{projectId}/serviceAccounts\n      name: listserviceaccounts\n      operations:\n      - method: GET\n        name: listserviceaccounts\n        description: Google Cloud IAM List service accounts\n        call: google-cloud-iam.listserviceaccounts\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/serviceAccounts\n      name: createserviceaccount\n      operations:\n      - method: POST\n        name: createserviceaccount\n        description: Google Cloud IAM Create a service account\n        call: google-cloud-iam.createserviceaccount\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/serviceAccounts/{serviceAccountEmail}\n    \
  \  name: getserviceaccount\n      operations:\n      - method: GET\n        name: getserviceaccount\n        description: Google Cloud IAM Get a service account\n        call: google-cloud-iam.getserviceaccount\n        with:\n          projectId: rest.projectId\n          serviceAccountEmail: rest.serviceAccountEmail\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/serviceAccounts/{serviceAccountEmail}\n      name: patchserviceaccount\n      operations:\n      - method: PATCH\n        name: patchserviceaccount\n        description: Google Cloud IAM Update a service account\n        call: google-cloud-iam.patchserviceaccount\n        with:\n          projectId: rest.projectId\n          serviceAccountEmail: rest.serviceAccountEmail\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/serviceAccounts/{serviceAccountEmail}\n      name: deleteserviceaccount\n      operations:\n\
  \      - method: DELETE\n        name: deleteserviceaccount\n        description: Google Cloud IAM Delete a service account\n        call: google-cloud-iam.deleteserviceaccount\n        with:\n          projectId: rest.projectId\n          serviceAccountEmail: rest.serviceAccountEmail\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/serviceAccounts/{serviceAccountEmail}/keys\n      name: listserviceaccountkeys\n      operations:\n      - method: GET\n        name: listserviceaccountkeys\n        description: Google Cloud IAM List service account keys\n        call: google-cloud-iam.listserviceaccountkeys\n        with:\n          projectId: rest.projectId\n          serviceAccountEmail: rest.serviceAccountEmail\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/serviceAccounts/{serviceAccountEmail}/keys\n      name: createserviceaccountkey\n      operations:\n      - method:\
  \ POST\n        name: createserviceaccountkey\n        description: Google Cloud IAM Create a service account key\n        call: google-cloud-iam.createserviceaccountkey\n        with:\n          projectId: rest.projectId\n          serviceAccountEmail: rest.serviceAccountEmail\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /roles\n      name: listroles\n      operations:\n      - method: GET\n        name: listroles\n        description: Google Cloud IAM List roles\n        call: google-cloud-iam.listroles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/roles\n      name: listprojectroles\n      operations:\n      - method: GET\n        name: listprojectroles\n        description: Google Cloud IAM List project roles\n        call: google-cloud-iam.listprojectroles\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /projects/{projectId}/roles\n      name: createprojectrole\n      operations:\n      - method: POST\n        name: createprojectrole\n        description: Google Cloud IAM Create a custom role\n        call: google-cloud-iam.createprojectrole\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /permissions:queryTestablePermissions\n      name: querytestablepermissions\n      operations:\n      - method: POST\n        name: querytestablepermissions\n        description: Google Cloud IAM Query testable permissions\n        call: google-cloud-iam.querytestablepermissions\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-iam-mcp\n    transport: http\n    description: MCP adapter for Google Cloud IAM API for AI agent use.\n    tools:\n    - name: listserviceaccounts\n      description: Google Cloud IAM List\
  \ service accounts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-iam.listserviceaccounts\n      with:\n        projectId: tools.projectId\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createserviceaccount\n      description: Google Cloud IAM Create a service account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-iam.createserviceaccount\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n     \
  \   description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getserviceaccount\n      description: Google Cloud IAM Get a service account\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-iam.getserviceaccount\n      with:\n        projectId: tools.projectId\n        serviceAccountEmail: tools.serviceAccountEmail\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: serviceAccountEmail\n        type: string\n        description: serviceAccountEmail\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchserviceaccount\n      description: Google Cloud IAM Update a service account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-iam.patchserviceaccount\n\
  \      with:\n        projectId: tools.projectId\n        serviceAccountEmail: tools.serviceAccountEmail\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: serviceAccountEmail\n        type: string\n        description: serviceAccountEmail\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteserviceaccount\n      description: Google Cloud IAM Delete a service account\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-iam.deleteserviceaccount\n      with:\n        projectId: tools.projectId\n        serviceAccountEmail: tools.serviceAccountEmail\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: serviceAccountEmail\n        type: string\n        description: serviceAccountEmail\n     \
  \   required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listserviceaccountkeys\n      description: Google Cloud IAM List service account keys\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-iam.listserviceaccountkeys\n      with:\n        projectId: tools.projectId\n        serviceAccountEmail: tools.serviceAccountEmail\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: serviceAccountEmail\n        type: string\n        description: serviceAccountEmail\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createserviceaccountkey\n      description: Google Cloud IAM Create a service account key\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-iam.createserviceaccountkey\n\
  \      with:\n        projectId: tools.projectId\n        serviceAccountEmail: tools.serviceAccountEmail\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: serviceAccountEmail\n        type: string\n        description: serviceAccountEmail\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listroles\n      description: Google Cloud IAM List roles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-iam.listroles\n      with:\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listprojectroles\n      description:\
  \ Google Cloud IAM List project roles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-iam.listprojectroles\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createprojectrole\n      description: Google Cloud IAM Create a custom role\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-iam.createprojectrole\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: querytestablepermissions\n      description: Google Cloud IAM Query testable permissions\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-iam.querytestablepermissions\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_IAM_TOKEN: GOOGLE_CLOUD_IAM_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-iam/refs/heads/main/capabilities/google-cloud-iam-capability.yaml
tags:
- Google
- Cloud
- Iam
- API
tools:
- description: Google Cloud IAM List service accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listserviceaccounts
- description: Google Cloud IAM Create a service account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createserviceaccount
- description: Google Cloud IAM Get a service account
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getserviceaccount
- description: Google Cloud IAM Update a service account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchserviceaccount
- description: Google Cloud IAM Delete a service account
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteserviceaccount
- description: Google Cloud IAM List service account keys
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listserviceaccountkeys
- description: Google Cloud IAM Create a service account key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createserviceaccountkey
- description: Google Cloud IAM List roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listroles
- description: Google Cloud IAM List project roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojectroles
- description: Google Cloud IAM Create a custom role
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createprojectrole
- description: Google Cloud IAM Query testable permissions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: querytestablepermissions
---
