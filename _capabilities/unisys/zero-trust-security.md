---
categories: []
consumed_apis: []
description: Zero trust security operations workflow for dynamic endpoint and user isolation, security incident response, and Stealth network management. Used by security operations teams, SIEM/SOAR platforms, and incident response workflows integrating Unisys Stealth zero trust network segmentation.
layout: capability
name: Unisys Zero Trust Security Operations
operations:
- description: Retrieve Stealth network role configurations
  method: GET
  name: get-stealth-roles
  path: /v1/roles
- description: Isolate an endpoint from the Stealth network
  method: POST
  name: isolate-endpoint
  path: /v1/endpoints/isolate
- description: Remove isolation from an endpoint
  method: POST
  name: unisolate-endpoint
  path: /v1/endpoints/unisolate
- description: Isolate a user from the Stealth network
  method: POST
  name: isolate-user
  path: /v1/users/isolate
- description: Remove isolation from a user
  method: POST
  name: unisolate-user
  path: /v1/users/unisolate
- description: Isolate both an endpoint and user simultaneously
  method: POST
  name: isolate-machine-and-user
  path: /v1/isolate
- description: Remove isolation from both endpoint and user
  method: POST
  name: unisolate-machine-and-user
  path: /v1/unisolate
personas: []
provider_name: Unisys
provider_slug: unisys
search_terms:
- remove isolation from an endpoint
- end-to-end security incident response using stealth dynamic isolation — from detecting threats to containing and restoring endpoints and users
- unisolate machine and user
- it services
- isolate an endpoint from the stealth network
- isolate a user from the stealth network
- unisolate user
- retrieve stealth network role configurations for use in isolation requests
- unisys
- restore a previously isolated user to normal stealth network access
- simultaneously isolate both an endpoint and user in response to a security incident
- remove isolation from a user
- user isolation operations
- get stealth roles
- isolate endpoint
- combined endpoint and user un-isolation
- endpoint isolation operations
- security
- isolate both an endpoint and user simultaneously
- network security
- responds to security incidents by isolating compromised endpoints and users in real time
- user un-isolation operations
- isolate a compromised or suspected user from the stealth zero trust network
- isolate a compromised or suspected endpoint from the stealth zero trust network
- restore a previously isolated endpoint to normal stealth network access
- isolate machine and user
- zero trust
- security operations
- performs coordinated containment of security incidents requiring simultaneous isolation
- retrieve stealth network role configurations
- endpoint un-isolation operations
- stealth
- simultaneously restore both an endpoint and user to normal stealth network access
- combined endpoint and user isolation
- cybersecurity
- incident response
- remove isolation from both endpoint and user
- isolate user
- stealth network role management
- endpoint isolation
- automated security orchestration platform triggering stealth isolation in response to siem alerts
- unisolate endpoint
- enterprise technology
slug: zero-trust-security
source_filename: zero-trust-security.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Unisys Zero Trust Security Operations\n  description: Zero trust security operations workflow for dynamic endpoint and user isolation, security incident response,\n    and Stealth network management. Used by security operations teams, SIEM/SOAR platforms, and incident response workflows\n    integrating Unisys Stealth zero trust network segmentation.\n  tags:\n  - Unisys\n  - Stealth\n  - Zero Trust\n  - Security Operations\n  - Incident Response\n  - Endpoint Isolation\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    STEALTH_HOST: STEALTH_HOST\n    STEALTH_PORT: STEALTH_PORT\n    STEALTH_USERNAME: STEALTH_USERNAME\n    STEALTH_PASSWORD: STEALTH_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: stealth\n    baseUri: https://{{STEALTH_HOST}}:{{STEALTH_PORT}}\n    description: Unisys Stealth EcoAPI server.\n    authentication:\n      type: basic\n      username: '{{STEALTH_USERNAME}}'\n\
  \      password: '{{STEALTH_PASSWORD}}'\n    resources:\n    - name: roles\n      path: /api/roles\n      description: Stealth role management\n      operations:\n      - name: get-stealth-roles\n        method: GET\n        description: Retrieve Stealth network roles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoint-isolation\n      path: /api/endpoint/isolate\n      description: Endpoint isolation operations\n      operations:\n      - name: isolate-endpoint\n        method: POST\n        description: Isolate an endpoint from the Stealth network\n        inputParameters:\n        - name: endpoint\n          in: body\n          type: string\n          required: true\n          description: FQDN of the endpoint to isolate\n        - name: roleId\n          in: body\n          type: string\n          required: false\n          description: Optional isolation role ID\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoint-unisolation\n      path: /api/endpoint/unisolate\n      description: Endpoint un-isolation operations\n      operations:\n      - name: unisolate-endpoint\n        method: POST\n        description: Remove isolation from an endpoint in the Stealth network\n        inputParameters:\n        - name: endpoint\n          in: body\n          type: string\n          required: true\n          description: FQDN of the endpoint to un-isolate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-isolation\n      path: /api/user/isolate\n      description: User isolation operations\n      operations:\n      - name: isolate-user\n        method: POST\n        description: Isolate a user from the Stealth network\n        inputParameters:\n        - name: user\n          in: body\n     \
  \     type: string\n          required: true\n          description: Username to isolate\n        - name: roleId\n          in: body\n          type: string\n          required: false\n          description: Optional isolation role ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-unisolation\n      path: /api/user/unisolate\n      description: User un-isolation operations\n      operations:\n      - name: unisolate-user\n        method: POST\n        description: Remove isolation from a user in the Stealth network\n        inputParameters:\n        - name: user\n          in: body\n          type: string\n          required: true\n          description: Username to un-isolate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: combined-isolation\n      path: /api/isolate\n      description: Combined endpoint\
  \ and user isolation\n      operations:\n      - name: isolate-machine-and-user\n        method: POST\n        description: Isolate both an endpoint and user simultaneously\n        inputParameters:\n        - name: endpoint\n          in: body\n          type: string\n          required: false\n          description: FQDN of the endpoint to isolate\n        - name: user\n          in: body\n          type: string\n          required: false\n          description: Username to isolate\n        - name: roleId\n          in: body\n          type: string\n          required: false\n          description: Optional isolation role ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: combined-unisolation\n      path: /api/unisolate\n      description: Combined endpoint and user un-isolation\n      operations:\n      - name: unisolate-machine-and-user\n        method: POST\n        description: Remove isolation\
  \ from both an endpoint and user simultaneously\n        inputParameters:\n        - name: endpoint\n          in: body\n          type: string\n          required: false\n          description: FQDN of the endpoint to un-isolate\n        - name: user\n          in: body\n          type: string\n          required: false\n          description: Username to un-isolate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: unisys-zero-trust-api\n    description: Unified REST API for Unisys zero trust security operations.\n    resources:\n    - path: /v1/roles\n      name: roles\n      description: Stealth network role management\n      operations:\n      - method: GET\n        name: get-stealth-roles\n        description: Retrieve Stealth network role configurations\n        call: stealth.get-stealth-roles\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/endpoints/isolate\n      name: endpoint-isolate\n      description: Endpoint isolation operations\n      operations:\n      - method: POST\n        name: isolate-endpoint\n        description: Isolate an endpoint from the Stealth network\n        call: stealth.isolate-endpoint\n        with:\n          endpoint: rest.endpoint\n          roleId: rest.roleId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/endpoints/unisolate\n      name: endpoint-unisolate\n      description: Endpoint un-isolation operations\n      operations:\n      - method: POST\n        name: unisolate-endpoint\n        description: Remove isolation from an endpoint\n        call: stealth.unisolate-endpoint\n        with:\n          endpoint: rest.endpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/isolate\n      name: user-isolate\n      description: User isolation operations\n   \
  \   operations:\n      - method: POST\n        name: isolate-user\n        description: Isolate a user from the Stealth network\n        call: stealth.isolate-user\n        with:\n          user: rest.user\n          roleId: rest.roleId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users/unisolate\n      name: user-unisolate\n      description: User un-isolation operations\n      operations:\n      - method: POST\n        name: unisolate-user\n        description: Remove isolation from a user\n        call: stealth.unisolate-user\n        with:\n          user: rest.user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/isolate\n      name: combined-isolate\n      description: Combined endpoint and user isolation\n      operations:\n      - method: POST\n        name: isolate-machine-and-user\n        description: Isolate both an endpoint and user simultaneously\n        call: stealth.isolate-machine-and-user\n\
  \        with:\n          endpoint: rest.endpoint\n          user: rest.user\n          roleId: rest.roleId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/unisolate\n      name: combined-unisolate\n      description: Combined endpoint and user un-isolation\n      operations:\n      - method: POST\n        name: unisolate-machine-and-user\n        description: Remove isolation from both endpoint and user\n        call: stealth.unisolate-machine-and-user\n        with:\n          endpoint: rest.endpoint\n          user: rest.user\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: unisys-zero-trust-mcp\n    transport: http\n    description: MCP server for AI-assisted zero trust security operations and incident response.\n    tools:\n    - name: get-stealth-roles\n      description: Retrieve Stealth network role configurations for use in isolation requests\n      hints:\n     \
  \   readOnly: true\n        openWorld: false\n      call: stealth.get-stealth-roles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: isolate-endpoint\n      description: Isolate a compromised or suspected endpoint from the Stealth zero trust network\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: stealth.isolate-endpoint\n      with:\n        endpoint: tools.endpoint\n        roleId: tools.roleId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: unisolate-endpoint\n      description: Restore a previously isolated endpoint to normal Stealth network access\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: stealth.unisolate-endpoint\n      with:\n        endpoint: tools.endpoint\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: isolate-user\n      description: Isolate a compromised or\
  \ suspected user from the Stealth zero trust network\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: stealth.isolate-user\n      with:\n        user: tools.user\n        roleId: tools.roleId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: unisolate-user\n      description: Restore a previously isolated user to normal Stealth network access\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: stealth.unisolate-user\n      with:\n        user: tools.user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: isolate-machine-and-user\n      description: Simultaneously isolate both an endpoint and user in response to a security incident\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: stealth.isolate-machine-and-user\n      with:\n        endpoint: tools.endpoint\n \
  \       user: tools.user\n        roleId: tools.roleId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: unisolate-machine-and-user\n      description: Simultaneously restore both an endpoint and user to normal Stealth network access\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: stealth.unisolate-machine-and-user\n      with:\n        endpoint: tools.endpoint\n        user: tools.user\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/unisys/refs/heads/main/capabilities/zero-trust-security.yaml
tags:
- Unisys
- Stealth
- Zero Trust
- Security Operations
- Incident Response
- Endpoint Isolation
tools:
- description: Retrieve Stealth network role configurations for use in isolation requests
  hints:
    openWorld: false
    readOnly: true
  name: get-stealth-roles
- description: Isolate a compromised or suspected endpoint from the Stealth zero trust network
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: isolate-endpoint
- description: Restore a previously isolated endpoint to normal Stealth network access
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: unisolate-endpoint
- description: Isolate a compromised or suspected user from the Stealth zero trust network
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: isolate-user
- description: Restore a previously isolated user to normal Stealth network access
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: unisolate-user
- description: Simultaneously isolate both an endpoint and user in response to a security incident
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: isolate-machine-and-user
- description: Simultaneously restore both an endpoint and user to normal Stealth network access
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: unisolate-machine-and-user
---
