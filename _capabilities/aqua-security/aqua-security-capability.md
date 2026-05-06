---
categories: []
consumed_apis: []
description: The Aqua Security REST API provides programmatic access to manage images, containers, policies, users, registries, and runtime security configurations for the Aqua Cloud Native Security Platform.
layout: capability
name: Aqua Security REST API
operations:
- description: Aqua Security Authenticate User
  method: POST
  name: login
  path: /v1/login
- description: Aqua Security List Images
  method: GET
  name: listimages
  path: /v1/images
- description: Aqua Security Register Image
  method: POST
  name: registerimage
  path: /v1/images
- description: Aqua Security Get Image Details
  method: GET
  name: getimage
  path: /v1/images/{registry}/{image_name}/{image_tag}
- description: Aqua Security Delete Image
  method: DELETE
  name: deleteimage
  path: /v1/images/{registry}/{image_name}/{image_tag}
- description: Aqua Security List Containers
  method: GET
  name: listcontainers
  path: /v1/containers
- description: Aqua Security List Security Policies
  method: GET
  name: listpolicies
  path: /v1/securitypolicies
- description: Aqua Security Create Security Policy
  method: POST
  name: createpolicy
  path: /v1/securitypolicies
- description: Aqua Security List Registries
  method: GET
  name: listregistries
  path: /v1/registries
- description: Aqua Security List Users
  method: GET
  name: listusers
  path: /v1/users
personas: []
provider_name: Aqua Security
provider_slug: aqua-security
search_terms:
- aqua security list containers
- vulnerability scanning
- aqua security delete image
- createpolicy
- aqua security create security policy
- aqua security list registries
- registerimage
- aqua security authenticate user
- cve identification, prioritization, and remediation
- runtime protection
- aqua security get image details
- aqua security list images
- listpolicies
- security
- containers
- cloud native
- aqua security register image
- kubernetes
- integrates security scanning into ci/cd pipelines
- regulatory compliance enforcement and auditing
- aqua security list users
- login
- listregistries
- api
- aqua security list security policies
- getimage
- real-time monitoring and enforcement for running containers
- monitors runtime security events and responds to container threats
- manages aqua platform configuration, users, and policies
- listimages
- securing container images throughout build-to-runtime lifecycle
- listusers
- listcontainers
- aqua
- deleteimage
slug: aqua-security-capability
source_filename: aqua-security-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Aqua Security REST API\n  description: The Aqua Security REST API provides programmatic access to manage images, containers, policies, users, registries,\n    and runtime security configurations for the Aqua Cloud Native Security Platform.\n  tags:\n  - Aqua\n  - Security\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: aqua-security\n    baseUri: https://your-tenant.cloud.aquasec.com/api\n    description: Aqua Security REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{AQUA_SECURITY_TOKEN}}'\n    resources:\n    - name: v1-login\n      path: /v1/login\n      operations:\n      - name: login\n        method: POST\n        description: Aqua Security Authenticate User\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-images\n      path: /v1/images\n   \
  \   operations:\n      - name: listimages\n        method: GET\n        description: Aqua Security List Images\n        inputParameters:\n        - name: registry\n          in: query\n          type: string\n          description: Filter images by registry name\n        - name: repository\n          in: query\n          type: string\n          description: Filter images by repository name\n        - name: tag\n          in: query\n          type: string\n          description: Filter images by tag\n        - name: page\n          in: query\n          type: integer\n          description: Page number for pagination\n        - name: pagesize\n          in: query\n          type: integer\n          description: Number of results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: registerimage\n        method: POST\n        description: Aqua Security Register Image\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-images-registry-image-name-image-tag\n      path: /v1/images/{registry}/{image_name}/{image_tag}\n      operations:\n      - name: getimage\n        method: GET\n        description: Aqua Security Get Image Details\n        inputParameters:\n        - name: registry\n          in: path\n          type: string\n          required: true\n          description: Registry name\n        - name: image_name\n          in: path\n          type: string\n          required: true\n          description: Image repository name\n        - name: image_tag\n          in: path\n          type: string\n          required: true\n          description: Image tag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteimage\n        method: DELETE\n        description: Aqua Security Delete Image\n  \
  \      inputParameters:\n        - name: registry\n          in: path\n          type: string\n          required: true\n          description: Registry name\n        - name: image_name\n          in: path\n          type: string\n          required: true\n          description: Image repository name\n        - name: image_tag\n          in: path\n          type: string\n          required: true\n          description: Image tag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-containers\n      path: /v1/containers\n      operations:\n      - name: listcontainers\n        method: GET\n        description: Aqua Security List Containers\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter by container status\n        - name: page\n          in: query\n          type: integer\n          description: Page number for pagination\n\
  \        - name: pagesize\n          in: query\n          type: integer\n          description: Number of results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-securitypolicies\n      path: /v1/securitypolicies\n      operations:\n      - name: listpolicies\n        method: GET\n        description: Aqua Security List Security Policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpolicy\n        method: POST\n        description: Aqua Security Create Security Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-registries\n      path: /v1/registries\n      operations:\n      - name: listregistries\n        method: GET\n        description: Aqua Security List Registries\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-users\n      path: /v1/users\n      operations:\n      - name: listusers\n        method: GET\n        description: Aqua Security List Users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: aqua-security-rest\n    description: REST adapter for Aqua Security REST API.\n    resources:\n    - path: /v1/login\n      name: login\n      operations:\n      - method: POST\n        name: login\n        description: Aqua Security Authenticate User\n        call: aqua-security.login\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/images\n      name: listimages\n      operations:\n      - method: GET\n        name: listimages\n        description: Aqua Security List Images\n        call: aqua-security.listimages\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/images\n      name: registerimage\n      operations:\n      - method: POST\n        name: registerimage\n        description: Aqua Security Register Image\n        call: aqua-security.registerimage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/images/{registry}/{image_name}/{image_tag}\n      name: getimage\n      operations:\n      - method: GET\n        name: getimage\n        description: Aqua Security Get Image Details\n        call: aqua-security.getimage\n        with:\n          registry: rest.registry\n          image_name: rest.image_name\n          image_tag: rest.image_tag\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/images/{registry}/{image_name}/{image_tag}\n      name: deleteimage\n      operations:\n      - method: DELETE\n        name: deleteimage\n        description: Aqua Security Delete Image\n\
  \        call: aqua-security.deleteimage\n        with:\n          registry: rest.registry\n          image_name: rest.image_name\n          image_tag: rest.image_tag\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/containers\n      name: listcontainers\n      operations:\n      - method: GET\n        name: listcontainers\n        description: Aqua Security List Containers\n        call: aqua-security.listcontainers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/securitypolicies\n      name: listpolicies\n      operations:\n      - method: GET\n        name: listpolicies\n        description: Aqua Security List Security Policies\n        call: aqua-security.listpolicies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/securitypolicies\n      name: createpolicy\n      operations:\n      - method: POST\n        name: createpolicy\n        description: Aqua Security\
  \ Create Security Policy\n        call: aqua-security.createpolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/registries\n      name: listregistries\n      operations:\n      - method: GET\n        name: listregistries\n        description: Aqua Security List Registries\n        call: aqua-security.listregistries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: listusers\n      operations:\n      - method: GET\n        name: listusers\n        description: Aqua Security List Users\n        call: aqua-security.listusers\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: aqua-security-mcp\n    transport: http\n    description: MCP adapter for Aqua Security REST API for AI agent use.\n    tools:\n    - name: login\n      description: Aqua Security Authenticate User\n      hints:\n        readOnly: false\n       \
  \ destructive: false\n        idempotent: false\n      call: aqua-security.login\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listimages\n      description: Aqua Security List Images\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: aqua-security.listimages\n      with:\n        registry: tools.registry\n        repository: tools.repository\n        tag: tools.tag\n        page: tools.page\n        pagesize: tools.pagesize\n      inputParameters:\n      - name: registry\n        type: string\n        description: Filter images by registry name\n      - name: repository\n        type: string\n        description: Filter images by repository name\n      - name: tag\n        type: string\n        description: Filter images by tag\n      - name: page\n        type: integer\n        description: Page number for pagination\n      - name: pagesize\n        type: integer\n        description: Number of results\
  \ per page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: registerimage\n      description: Aqua Security Register Image\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aqua-security.registerimage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getimage\n      description: Aqua Security Get Image Details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: aqua-security.getimage\n      with:\n        registry: tools.registry\n        image_name: tools.image_name\n        image_tag: tools.image_tag\n      inputParameters:\n      - name: registry\n        type: string\n        description: Registry name\n        required: true\n      - name: image_name\n        type: string\n        description: Image repository name\n        required: true\n      - name: image_tag\n        type: string\n        description: Image\
  \ tag\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteimage\n      description: Aqua Security Delete Image\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: aqua-security.deleteimage\n      with:\n        registry: tools.registry\n        image_name: tools.image_name\n        image_tag: tools.image_tag\n      inputParameters:\n      - name: registry\n        type: string\n        description: Registry name\n        required: true\n      - name: image_name\n        type: string\n        description: Image repository name\n        required: true\n      - name: image_tag\n        type: string\n        description: Image tag\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcontainers\n      description: Aqua Security List Containers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: aqua-security.listcontainers\n      with:\n        status: tools.status\n        page: tools.page\n        pagesize: tools.pagesize\n      inputParameters:\n      - name: status\n        type: string\n        description: Filter by container status\n      - name: page\n        type: integer\n        description: Page number for pagination\n      - name: pagesize\n        type: integer\n        description: Number of results per page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpolicies\n      description: Aqua Security List Security Policies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: aqua-security.listpolicies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpolicy\n      description: Aqua Security Create Security Policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aqua-security.createpolicy\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listregistries\n      description: Aqua Security List Registries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: aqua-security.listregistries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listusers\n      description: Aqua Security List Users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: aqua-security.listusers\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    AQUA_SECURITY_TOKEN: AQUA_SECURITY_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/aqua-security/refs/heads/main/capabilities/aqua-security-capability.yaml
tags:
- Aqua
- Security
- API
tools:
- description: Aqua Security Authenticate User
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: login
- description: Aqua Security List Images
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listimages
- description: Aqua Security Register Image
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: registerimage
- description: Aqua Security Get Image Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getimage
- description: Aqua Security Delete Image
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteimage
- description: Aqua Security List Containers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcontainers
- description: Aqua Security List Security Policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpolicies
- description: Aqua Security Create Security Policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpolicy
- description: Aqua Security List Registries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listregistries
- description: Aqua Security List Users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
---
