---
categories: []
consumed_apis: []
description: The Binary Authorization API provides deploy-time security controls for container images on Google Cloud. It enables management of policies, attestors, and attestations to ensure only trusted container images are deployed to GKE, Cloud Run, and Anthos environments.
layout: capability
name: Google Cloud Binary Authorization API
operations:
- description: Google Cloud Binary Authorization Get project policy
  method: GET
  name: getpolicy
  path: /projects/{projectId}/policy
- description: Google Cloud Binary Authorization Update project policy
  method: PUT
  name: updatepolicy
  path: /projects/{projectId}/policy
- description: Google Cloud Binary Authorization List attestors
  method: GET
  name: listattestors
  path: /projects/{projectId}/attestors
- description: Google Cloud Binary Authorization Create an attestor
  method: POST
  name: createattestor
  path: /projects/{projectId}/attestors
- description: Google Cloud Binary Authorization Get an attestor
  method: GET
  name: getattestor
  path: /projects/{projectId}/attestors/{attestorId}
- description: Google Cloud Binary Authorization Update an attestor
  method: PUT
  name: updateattestor
  path: /projects/{projectId}/attestors/{attestorId}
- description: Google Cloud Binary Authorization Delete an attestor
  method: DELETE
  name: deleteattestor
  path: /projects/{projectId}/attestors/{attestorId}
- description: Google Cloud Binary Authorization Validate attestation occurrence
  method: POST
  name: validateattestationoccurrence
  path: /projects/{projectId}/attestors/{attestorId}:validateAttestationOccurrence
personas: []
provider_name: Google Cloud Binary Authorization
provider_slug: google-cloud-binary-authorization
search_terms:
- google cloud binary authorization create an attestor
- binary
- google cloud binary authorization update an attestor
- google cloud binary authorization validate attestation occurrence
- attestation
- container security
- validateattestationoccurrence
- google cloud binary authorization get project policy
- cloud
- google
- updatepolicy
- google cloud binary authorization get an attestor
- kubernetes
- getpolicy
- google cloud binary authorization update project policy
- listattestors
- getattestor
- api
- updateattestor
- authorization
- google cloud binary authorization list attestors
- createattestor
- google cloud binary authorization delete an attestor
- devsecops
- supply chain security
- deleteattestor
- policy enforcement
slug: google-cloud-binary-authorization-capability
source_filename: google-cloud-binary-authorization-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Binary Authorization API\n  description: The Binary Authorization API provides deploy-time security controls for container images on Google Cloud. It\n    enables management of policies, attestors, and attestations to ensure only trusted container images are deployed to GKE,\n    Cloud Run, and Anthos environments.\n  tags:\n  - Google\n  - Cloud\n  - Binary\n  - Authorization\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-binary-authorization\n    baseUri: https://binaryauthorization.googleapis.com/v1\n    description: Google Cloud Binary Authorization API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_BINARY_AUTHORIZATION_TOKEN}}'\n    resources:\n    - name: projects-projectid-policy\n      path: /projects/{projectId}/policy\n      operations:\n      - name: getpolicy\n        method: GET\n        description:\
  \ Google Cloud Binary Authorization Get project policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepolicy\n        method: PUT\n        description: Google Cloud Binary Authorization Update project policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-attestors\n      path: /projects/{projectId}/attestors\n      operations:\n      - name: listattestors\n        method: GET\n        description: Google Cloud Binary Authorization List attestors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createattestor\n        method: POST\n        description: Google Cloud Binary Authorization Create an attestor\n        inputParameters:\n        - name: attestorId\n          in: query\n      \
  \    type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-attestors-attestorid\n      path: /projects/{projectId}/attestors/{attestorId}\n      operations:\n      - name: getattestor\n        method: GET\n        description: Google Cloud Binary Authorization Get an attestor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateattestor\n        method: PUT\n        description: Google Cloud Binary Authorization Update an attestor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteattestor\n        method: DELETE\n        description: Google Cloud Binary Authorization Delete an attestor\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: projects-projectid-attestors-attestorid-validate\n      path: /projects/{projectId}/attestors/{attestorId}:validateAttestationOccurrence\n      operations:\n      - name: validateattestationoccurrence\n        method: POST\n        description: Google Cloud Binary Authorization Validate attestation occurrence\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-binary-authorization-rest\n    description: REST adapter for Google Cloud Binary Authorization API.\n    resources:\n    - path: /projects/{projectId}/policy\n      name: getpolicy\n      operations:\n      - method: GET\n        name: getpolicy\n        description: Google Cloud Binary Authorization Get project policy\n        call: google-cloud-binary-authorization.getpolicy\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /projects/{projectId}/policy\n      name: updatepolicy\n      operations:\n      - method: PUT\n        name: updatepolicy\n        description: Google Cloud Binary Authorization Update project policy\n        call: google-cloud-binary-authorization.updatepolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/attestors\n      name: listattestors\n      operations:\n      - method: GET\n        name: listattestors\n        description: Google Cloud Binary Authorization List attestors\n        call: google-cloud-binary-authorization.listattestors\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/attestors\n      name: createattestor\n      operations:\n      - method: POST\n        name: createattestor\n        description: Google Cloud Binary Authorization Create an attestor\n        call: google-cloud-binary-authorization.createattestor\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/attestors/{attestorId}\n      name: getattestor\n      operations:\n      - method: GET\n        name: getattestor\n        description: Google Cloud Binary Authorization Get an attestor\n        call: google-cloud-binary-authorization.getattestor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/attestors/{attestorId}\n      name: updateattestor\n      operations:\n      - method: PUT\n        name: updateattestor\n        description: Google Cloud Binary Authorization Update an attestor\n        call: google-cloud-binary-authorization.updateattestor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/attestors/{attestorId}\n      name: deleteattestor\n      operations:\n      - method: DELETE\n        name: deleteattestor\n        description: Google Cloud Binary\
  \ Authorization Delete an attestor\n        call: google-cloud-binary-authorization.deleteattestor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/attestors/{attestorId}:validateAttestationOccurrence\n      name: validateattestationoccurrence\n      operations:\n      - method: POST\n        name: validateattestationoccurrence\n        description: Google Cloud Binary Authorization Validate attestation occurrence\n        call: google-cloud-binary-authorization.validateattestationoccurrence\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-binary-authorization-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Binary Authorization API for AI agent use.\n    tools:\n    - name: getpolicy\n      description: Google Cloud Binary Authorization Get project policy\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: google-cloud-binary-authorization.getpolicy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatepolicy\n      description: Google Cloud Binary Authorization Update project policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-cloud-binary-authorization.updatepolicy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listattestors\n      description: Google Cloud Binary Authorization List attestors\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-binary-authorization.listattestors\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createattestor\n      description: Google Cloud Binary Authorization Create an attestor\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-binary-authorization.createattestor\n\
  \      with:\n        attestorId: tools.attestorId\n      inputParameters:\n      - name: attestorId\n        type: string\n        description: attestorId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getattestor\n      description: Google Cloud Binary Authorization Get an attestor\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-binary-authorization.getattestor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateattestor\n      description: Google Cloud Binary Authorization Update an attestor\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: google-cloud-binary-authorization.updateattestor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteattestor\n      description: Google Cloud Binary Authorization Delete an attestor\n      hints:\n\
  \        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-binary-authorization.deleteattestor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: validateattestationoccurrence\n      description: Google Cloud Binary Authorization Validate attestation occurrence\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-binary-authorization.validateattestationoccurrence\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_BINARY_AUTHORIZATION_TOKEN: GOOGLE_CLOUD_BINARY_AUTHORIZATION_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-binary-authorization/refs/heads/main/capabilities/google-cloud-binary-authorization-capability.yaml
tags:
- Google
- Cloud
- Binary
- Authorization
- API
tools:
- description: Google Cloud Binary Authorization Get project policy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpolicy
- description: Google Cloud Binary Authorization Update project policy
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepolicy
- description: Google Cloud Binary Authorization List attestors
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listattestors
- description: Google Cloud Binary Authorization Create an attestor
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createattestor
- description: Google Cloud Binary Authorization Get an attestor
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getattestor
- description: Google Cloud Binary Authorization Update an attestor
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateattestor
- description: Google Cloud Binary Authorization Delete an attestor
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteattestor
- description: Google Cloud Binary Authorization Validate attestation occurrence
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: validateattestationoccurrence
---
