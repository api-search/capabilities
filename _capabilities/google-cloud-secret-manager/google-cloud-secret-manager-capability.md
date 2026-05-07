---
categories: []
consumed_apis: []
description: The Secret Manager API enables creating, managing, and accessing secrets and their versions, providing secure storage for sensitive configuration data and credentials.
layout: capability
name: Google Cloud Secret Manager API
operations:
- description: Google Cloud Secret Manager List secrets
  method: GET
  name: listsecrets
  path: /projects/{projectId}/secrets
- description: Google Cloud Secret Manager Create a secret
  method: POST
  name: createsecret
  path: /projects/{projectId}/secrets
- description: Google Cloud Secret Manager Get a secret
  method: GET
  name: getsecret
  path: /projects/{projectId}/secrets/{secretId}
- description: Google Cloud Secret Manager Update a secret
  method: PATCH
  name: updatesecret
  path: /projects/{projectId}/secrets/{secretId}
- description: Google Cloud Secret Manager Delete a secret
  method: DELETE
  name: deletesecret
  path: /projects/{projectId}/secrets/{secretId}
- description: Google Cloud Secret Manager Add a secret version
  method: POST
  name: addsecretversion
  path: /projects/{projectId}/secrets/{secretId}:addVersion
- description: Google Cloud Secret Manager List secret versions
  method: GET
  name: listsecretversions
  path: /projects/{projectId}/secrets/{secretId}/versions
- description: Google Cloud Secret Manager Access a secret version
  method: GET
  name: accesssecretversion
  path: /projects/{projectId}/secrets/{secretId}/versions/{versionId}:access
- description: Google Cloud Secret Manager Destroy a secret version
  method: POST
  name: destroysecretversion
  path: /projects/{projectId}/secrets/{secretId}/versions/{versionId}:destroy
personas: []
provider_name: Google Cloud Secret Manager
provider_slug: google-cloud-secret-manager
search_terms:
- google cloud secret manager get a secret
- google cloud secret manager update a secret
- google cloud secret manager delete a secret
- destroysecretversion
- secrets
- accesssecretversion
- api
- google cloud secret manager list secret versions
- listsecrets
- configuration
- key management
- google cloud secret manager list secrets
- google
- google cloud secret manager add a secret version
- getsecret
- google cloud secret manager create a secret
- listsecretversions
- secret
- manager
- google cloud secret manager destroy a secret version
- cloud
- credentials
- addsecretversion
- deletesecret
- google cloud secret manager access a secret version
- updatesecret
- google cloud
- security
- createsecret
slug: google-cloud-secret-manager-capability
source_filename: google-cloud-secret-manager-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Secret Manager API\n  description: The Secret Manager API enables creating, managing, and accessing secrets and their versions, providing secure\n    storage for sensitive configuration data and credentials.\n  tags:\n  - Google\n  - Cloud\n  - Secret\n  - Manager\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-secret-manager\n    baseUri: https://secretmanager.googleapis.com/v1\n    description: Google Cloud Secret Manager API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_SECRET_MANAGER_TOKEN}}'\n    resources:\n    - name: projects-projectid-secrets\n      path: /projects/{projectId}/secrets\n      operations:\n      - name: listsecrets\n        method: GET\n        description: Google Cloud Secret Manager List secrets\n        inputParameters:\n        - name: projectId\n          in: path\n          type:\
  \ string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        - name: filter\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsecret\n        method: POST\n        description: Google Cloud Secret Manager Create a secret\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: secretId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-secrets-secretid\n      path: /projects/{projectId}/secrets/{secretId}\n      operations:\n      - name: getsecret\n        method:\
  \ GET\n        description: Google Cloud Secret Manager Get a secret\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: secretId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatesecret\n        method: PATCH\n        description: Google Cloud Secret Manager Update a secret\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: secretId\n          in: path\n          type: string\n          required: true\n        - name: updateMask\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesecret\n        method: DELETE\n\
  \        description: Google Cloud Secret Manager Delete a secret\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: secretId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-secrets-secretid-addversion\n      path: /projects/{projectId}/secrets/{secretId}:addVersion\n      operations:\n      - name: addsecretversion\n        method: POST\n        description: Google Cloud Secret Manager Add a secret version\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: secretId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: projects-projectid-secrets-secretid-versions\n      path: /projects/{projectId}/secrets/{secretId}/versions\n      operations:\n      - name: listsecretversions\n        method: GET\n        description: Google Cloud Secret Manager List secret versions\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: secretId\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-secrets-secretid-versions-ver\n      path: /projects/{projectId}/secrets/{secretId}/versions/{versionId}:access\n      operations:\n      - name: accesssecretversion\n        method: GET\n  \
  \      description: Google Cloud Secret Manager Access a secret version\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: secretId\n          in: path\n          type: string\n          required: true\n        - name: versionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-secrets-secretid-versions-ver\n      path: /projects/{projectId}/secrets/{secretId}/versions/{versionId}:destroy\n      operations:\n      - name: destroysecretversion\n        method: POST\n        description: Google Cloud Secret Manager Destroy a secret version\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: secretId\n          in: path\n          type: string\n\
  \          required: true\n        - name: versionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-secret-manager-rest\n    description: REST adapter for Google Cloud Secret Manager API.\n    resources:\n    - path: /projects/{projectId}/secrets\n      name: listsecrets\n      operations:\n      - method: GET\n        name: listsecrets\n        description: Google Cloud Secret Manager List secrets\n        call: google-cloud-secret-manager.listsecrets\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/secrets\n      name: createsecret\n      operations:\n      - method: POST\n        name: createsecret\n        description: Google Cloud Secret Manager Create\
  \ a secret\n        call: google-cloud-secret-manager.createsecret\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/secrets/{secretId}\n      name: getsecret\n      operations:\n      - method: GET\n        name: getsecret\n        description: Google Cloud Secret Manager Get a secret\n        call: google-cloud-secret-manager.getsecret\n        with:\n          projectId: rest.projectId\n          secretId: rest.secretId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/secrets/{secretId}\n      name: updatesecret\n      operations:\n      - method: PATCH\n        name: updatesecret\n        description: Google Cloud Secret Manager Update a secret\n        call: google-cloud-secret-manager.updatesecret\n        with:\n          projectId: rest.projectId\n          secretId: rest.secretId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/secrets/{secretId}\n      name: deletesecret\n      operations:\n      - method: DELETE\n        name: deletesecret\n        description: Google Cloud Secret Manager Delete a secret\n        call: google-cloud-secret-manager.deletesecret\n        with:\n          projectId: rest.projectId\n          secretId: rest.secretId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/secrets/{secretId}:addVersion\n      name: addsecretversion\n      operations:\n      - method: POST\n        name: addsecretversion\n        description: Google Cloud Secret Manager Add a secret version\n        call: google-cloud-secret-manager.addsecretversion\n        with:\n          projectId: rest.projectId\n          secretId: rest.secretId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/secrets/{secretId}/versions\n\
  \      name: listsecretversions\n      operations:\n      - method: GET\n        name: listsecretversions\n        description: Google Cloud Secret Manager List secret versions\n        call: google-cloud-secret-manager.listsecretversions\n        with:\n          projectId: rest.projectId\n          secretId: rest.secretId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/secrets/{secretId}/versions/{versionId}:access\n      name: accesssecretversion\n      operations:\n      - method: GET\n        name: accesssecretversion\n        description: Google Cloud Secret Manager Access a secret version\n        call: google-cloud-secret-manager.accesssecretversion\n        with:\n          projectId: rest.projectId\n          secretId: rest.secretId\n          versionId: rest.versionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/secrets/{secretId}/versions/{versionId}:destroy\n\
  \      name: destroysecretversion\n      operations:\n      - method: POST\n        name: destroysecretversion\n        description: Google Cloud Secret Manager Destroy a secret version\n        call: google-cloud-secret-manager.destroysecretversion\n        with:\n          projectId: rest.projectId\n          secretId: rest.secretId\n          versionId: rest.versionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-secret-manager-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Secret Manager API for AI agent use.\n    tools:\n    - name: listsecrets\n      description: Google Cloud Secret Manager List secrets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-secret-manager.listsecrets\n      with:\n        projectId: tools.projectId\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n    \
  \    filter: tools.filter\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      - name: filter\n        type: string\n        description: filter\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsecret\n      description: Google Cloud Secret Manager Create a secret\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-secret-manager.createsecret\n      with:\n        projectId: tools.projectId\n        secretId: tools.secretId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: secretId\n        type: string\n        description: secretId\n        required: true\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsecret\n      description: Google Cloud Secret Manager Get a secret\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-secret-manager.getsecret\n      with:\n        projectId: tools.projectId\n        secretId: tools.secretId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: secretId\n        type: string\n        description: secretId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatesecret\n      description: Google Cloud Secret Manager Update a secret\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-secret-manager.updatesecret\n      with:\n        projectId: tools.projectId\n        secretId: tools.secretId\n   \
  \     updateMask: tools.updateMask\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: secretId\n        type: string\n        description: secretId\n        required: true\n      - name: updateMask\n        type: string\n        description: updateMask\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletesecret\n      description: Google Cloud Secret Manager Delete a secret\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-secret-manager.deletesecret\n      with:\n        projectId: tools.projectId\n        secretId: tools.secretId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: secretId\n        type: string\n        description: secretId\n        required: true\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: addsecretversion\n      description: Google Cloud Secret Manager Add a secret version\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-secret-manager.addsecretversion\n      with:\n        projectId: tools.projectId\n        secretId: tools.secretId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: secretId\n        type: string\n        description: secretId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsecretversions\n      description: Google Cloud Secret Manager List secret versions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-secret-manager.listsecretversions\n      with:\n        projectId: tools.projectId\n        secretId: tools.secretId\n        pageSize:\
  \ tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: secretId\n        type: string\n        description: secretId\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: accesssecretversion\n      description: Google Cloud Secret Manager Access a secret version\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-secret-manager.accesssecretversion\n      with:\n        projectId: tools.projectId\n        secretId: tools.secretId\n        versionId: tools.versionId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required:\
  \ true\n      - name: secretId\n        type: string\n        description: secretId\n        required: true\n      - name: versionId\n        type: string\n        description: versionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: destroysecretversion\n      description: Google Cloud Secret Manager Destroy a secret version\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-secret-manager.destroysecretversion\n      with:\n        projectId: tools.projectId\n        secretId: tools.secretId\n        versionId: tools.versionId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: secretId\n        type: string\n        description: secretId\n        required: true\n      - name: versionId\n        type: string\n        description: versionId\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_SECRET_MANAGER_TOKEN: GOOGLE_CLOUD_SECRET_MANAGER_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-secret-manager/refs/heads/main/capabilities/google-cloud-secret-manager-capability.yaml
tags:
- Google
- Cloud
- Secret
- Manager
- API
tools:
- description: Google Cloud Secret Manager List secrets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsecrets
- description: Google Cloud Secret Manager Create a secret
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsecret
- description: Google Cloud Secret Manager Get a secret
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsecret
- description: Google Cloud Secret Manager Update a secret
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatesecret
- description: Google Cloud Secret Manager Delete a secret
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesecret
- description: Google Cloud Secret Manager Add a secret version
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addsecretversion
- description: Google Cloud Secret Manager List secret versions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsecretversions
- description: Google Cloud Secret Manager Access a secret version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: accesssecretversion
- description: Google Cloud Secret Manager Destroy a secret version
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: destroysecretversion
---
