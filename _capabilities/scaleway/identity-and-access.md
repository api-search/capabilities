---
categories: []
consumed_apis: []
description: Unified workflow capability for managing Scaleway identity and access management, combining IAM policies, API keys, users, groups, applications, and secret storage. Used by platform administrators and security teams to control access to Scaleway resources and manage credentials securely.
layout: capability
name: Scaleway Identity and Access
operations:
- description: List IAM API keys
  method: GET
  name: list-api-keys
  path: /v1/api-keys
- description: Create an IAM API key
  method: POST
  name: create-api-key
  path: /v1/api-keys
- description: Get API key details
  method: GET
  name: get-api-key
  path: /v1/api-keys/{access_key}
- description: Delete an API key
  method: DELETE
  name: delete-api-key
  path: /v1/api-keys/{access_key}
- description: List IAM users
  method: GET
  name: list-users
  path: /v1/users
- description: List IAM groups
  method: GET
  name: list-groups
  path: /v1/groups
- description: Create an IAM group
  method: POST
  name: create-group
  path: /v1/groups
- description: List IAM policies
  method: GET
  name: list-policies
  path: /v1/policies
- description: Create an IAM policy
  method: POST
  name: create-policy
  path: /v1/policies
- description: List secrets
  method: GET
  name: list-secrets
  path: /v1/secrets
- description: Create a secret
  method: POST
  name: create-secret
  path: /v1/secrets
- description: Get secret details
  method: GET
  name: get-secret
  path: /v1/secrets/{id}
- description: Delete a secret
  method: DELETE
  name: delete-secret
  path: /v1/secrets/{id}
personas: []
provider_name: Scaleway
provider_slug: scaleway
search_terms:
- create group
- create an iam group
- containers
- delete api key
- list iam api keys
- list iam policies
- permissions
- api keys
- create an iam api key
- create a new secret in secret manager
- delete secret
- list groups
- api key management
- ai
- get secret
- scaleway
- create secret
- list secrets
- get a secret from secret manager
- access control
- access policy management
- create an iam policy
- policies
- get api key
- cloud computing
- infrastructure
- identity
- serverless
- secret management
- manage a specific api key
- delete an api key
- list users
- list iam users in the organization
- create a new iam api key
- kubernetes
- list iam groups
- iam
- european cloud
- list iam users
- list api keys
- list scaleway iam api keys
- list policies
- database
- user management
- storage
- create policy
- get secret details
- delete a secret
- manage a specific secret
- delete a secret from secret manager
- create a secret
- list secrets in secret manager
- security
- delete an iam api key
- group management
- create api key
- get api key details
slug: identity-and-access
source_filename: identity-and-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Scaleway Identity and Access\n  description: Unified workflow capability for managing Scaleway identity and access management, combining IAM policies, API\n    keys, users, groups, applications, and secret storage. Used by platform administrators and security teams to control access\n    to Scaleway resources and manage credentials securely.\n  tags:\n  - Access Control\n  - API Keys\n  - IAM\n  - Identity\n  - Permissions\n  - Policies\n  - Scaleway\n  - Security\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SCALEWAY_API_KEY: SCALEWAY_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: scaleway-iam\n    baseUri: https://api.scaleway.com\n    description: Scaleway IAM API for identity and access management\n    authentication:\n      type: apikey\n      key: X-Auth-Token\n      value: '{{SCALEWAY_API_KEY}}'\n      placement: header\n    resources:\n    - name: api-keys\n      path:\
  \ /iam/v1alpha1/api-keys\n      description: API key management\n      operations:\n      - name: list-api-keys\n        method: GET\n        description: List API Keys\n        inputParameters:\n        - name: order_by\n          in: query\n          type: string\n          required: false\n          description: Sort order\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-api-key\n        method: POST\n        description: Create an API Key\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            description: '{{tools.description}}'\n            expires_at: '{{tools.expires_at}}'\n    - name: api-key\n\
  \      path: /iam/v1alpha1/api-keys/{access_key}\n      description: Manage a specific API key\n      operations:\n      - name: get-api-key\n        method: GET\n        description: Get an API Key\n        inputParameters:\n        - name: access_key\n          in: path\n          type: string\n          required: true\n          description: API key access key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-api-key\n        method: DELETE\n        description: Delete an API Key\n        inputParameters:\n        - name: access_key\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /iam/v1alpha1/users\n      description: User management\n      operations:\n      - name: list-users\n        method: GET\n      \
  \  description: List Users\n        inputParameters:\n        - name: organization_id\n          in: query\n          type: string\n          required: false\n          description: Organization ID filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: groups\n      path: /iam/v1alpha1/groups\n      description: Group management\n      operations:\n      - name: list-groups\n        method: GET\n        description: List Groups\n        inputParameters:\n        - name: organization_id\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-group\n        method: POST\n        description: Create a Group\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n    - name: policies\n      path: /iam/v1alpha1/policies\n      description: Policy management\n      operations:\n      - name: list-policies\n        method: GET\n        description: List Policies\n        inputParameters:\n        - name: organization_id\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-policy\n        method: POST\n        description: Create a Policy\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            rules: '{{tools.rules}}'\n    -\
  \ name: applications\n      path: /iam/v1alpha1/applications\n      description: Application management\n      operations:\n      - name: list-applications\n        method: GET\n        description: List Applications\n        inputParameters:\n        - name: organization_id\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: scaleway-secrets\n    baseUri: https://api.scaleway.com\n    description: Scaleway Secret Manager API\n    authentication:\n      type: apikey\n      key: X-Auth-Token\n      value: '{{SCALEWAY_API_KEY}}'\n      placement: header\n    resources:\n    - name: secrets\n      path: /secret-manager/v1beta1/regions/{region}/secrets\n      description: Secret management\n      operations:\n      - name: list-secrets\n        method: GET\n        description: List all secrets in a project\n    \
  \    inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: project_id\n          in: query\n          type: string\n          required: false\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-secret\n        method: POST\n        description: Create a new secret\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            project_id: '{{tools.project_id}}'\n            description: '{{tools.description}}'\n            type: '{{tools.type}}'\n\
  \      - name: get-secret\n        method: GET\n        description: Get a secret by ID\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: secret_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-secret\n        method: DELETE\n        description: Delete a secret\n        inputParameters:\n        - name: region\n          in: path\n          type: string\n          required: true\n        - name: secret_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8083\n    namespace: scaleway-identity-api\n    description: Unified REST API for Scaleway identity,\
  \ access management, and secret storage.\n    resources:\n    - path: /v1/api-keys\n      name: api-keys\n      description: API key management\n      operations:\n      - method: GET\n        name: list-api-keys\n        description: List IAM API keys\n        call: scaleway-iam.list-api-keys\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-api-key\n        description: Create an IAM API key\n        call: scaleway-iam.create-api-key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/api-keys/{access_key}\n      name: api-key\n      description: Manage a specific API key\n      operations:\n      - method: GET\n        name: get-api-key\n        description: Get API key details\n        call: scaleway-iam.get-api-key\n        with:\n          access_key: rest.access_key\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name:\
  \ delete-api-key\n        description: Delete an API key\n        call: scaleway-iam.delete-api-key\n        with:\n          access_key: rest.access_key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: users\n      description: User management\n      operations:\n      - method: GET\n        name: list-users\n        description: List IAM users\n        call: scaleway-iam.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/groups\n      name: groups\n      description: Group management\n      operations:\n      - method: GET\n        name: list-groups\n        description: List IAM groups\n        call: scaleway-iam.list-groups\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-group\n        description: Create an IAM group\n        call: scaleway-iam.create-group\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/policies\n      name: policies\n      description: Access policy management\n      operations:\n      - method: GET\n        name: list-policies\n        description: List IAM policies\n        call: scaleway-iam.list-policies\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-policy\n        description: Create an IAM policy\n        call: scaleway-iam.create-policy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/secrets\n      name: secrets\n      description: Secret management\n      operations:\n      - method: GET\n        name: list-secrets\n        description: List secrets\n        call: scaleway-secrets.list-secrets\n        with:\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-secret\n        description: Create a secret\n      \
  \  call: scaleway-secrets.create-secret\n        with:\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/secrets/{id}\n      name: secret\n      description: Manage a specific secret\n      operations:\n      - method: GET\n        name: get-secret\n        description: Get secret details\n        call: scaleway-secrets.get-secret\n        with:\n          region: rest.region\n          secret_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-secret\n        description: Delete a secret\n        call: scaleway-secrets.delete-secret\n        with:\n          region: rest.region\n          secret_id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9093\n    namespace: scaleway-identity-mcp\n    transport: http\n    description: MCP server for AI-assisted Scaleway identity, access,\
  \ and secrets management.\n    tools:\n    - name: list-api-keys\n      description: List Scaleway IAM API keys\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scaleway-iam.list-api-keys\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-api-key\n      description: Create a new IAM API key\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: scaleway-iam.create-api-key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-api-key\n      description: Delete an IAM API key\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: scaleway-iam.delete-api-key\n      with:\n        access_key: tools.access_key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List IAM users in the organization\n      hints:\n        readOnly: true\n\
  \        openWorld: true\n      call: scaleway-iam.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-groups\n      description: List IAM groups\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scaleway-iam.list-groups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-policies\n      description: List IAM policies\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scaleway-iam.list-policies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-secrets\n      description: List secrets in Secret Manager\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scaleway-secrets.list-secrets\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-secret\n      description: Create a new secret in Secret Manager\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: scaleway-secrets.create-secret\n      with:\n        region: tools.region\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-secret\n      description: Get a secret from Secret Manager\n      hints:\n        readOnly: true\n        openWorld: false\n      call: scaleway-secrets.get-secret\n      with:\n        region: tools.region\n        secret_id: tools.secret_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-secret\n      description: Delete a secret from Secret Manager\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: scaleway-secrets.delete-secret\n      with:\n        region: tools.region\n        secret_id: tools.secret_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/scaleway/refs/heads/main/capabilities/identity-and-access.yaml
tags:
- Access Control
- API Keys
- IAM
- Identity
- Permissions
- Policies
- Scaleway
- Security
tools:
- description: List Scaleway IAM API keys
  hints:
    openWorld: true
    readOnly: true
  name: list-api-keys
- description: Create a new IAM API key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-api-key
- description: Delete an IAM API key
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-api-key
- description: List IAM users in the organization
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: List IAM groups
  hints:
    openWorld: true
    readOnly: true
  name: list-groups
- description: List IAM policies
  hints:
    openWorld: true
    readOnly: true
  name: list-policies
- description: List secrets in Secret Manager
  hints:
    openWorld: true
    readOnly: true
  name: list-secrets
- description: Create a new secret in Secret Manager
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-secret
- description: Get a secret from Secret Manager
  hints:
    openWorld: false
    readOnly: true
  name: get-secret
- description: Delete a secret from Secret Manager
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-secret
---
