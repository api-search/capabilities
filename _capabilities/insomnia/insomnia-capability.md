---
categories: []
consumed_apis: []
description: The Insomnia Mock Server API allows developers to create, manage, and interact with mock servers powered by Insomnia (Kong). Mock servers simulate API endpoints by returning predefined responses based on OpenAPI specifications or custom route configurations. This enables frontend and backend teams to develop and test against realistic API behavior before the actual implementation is complete. Insomnia supports both cloud-hosted and self-hosted mock server deployments.
layout: capability
name: Insomnia Mock Server API
operations:
- description: Insomnia List Mock Servers
  method: GET
  name: listmockservers
  path: /mock-servers
- description: Insomnia Create Mock Server
  method: POST
  name: createmockserver
  path: /mock-servers
- description: Insomnia Get Mock Server
  method: GET
  name: getmockserver
  path: /mock-servers/{mockServerId}
- description: Insomnia Update Mock Server
  method: PUT
  name: updatemockserver
  path: /mock-servers/{mockServerId}
- description: Insomnia Delete Mock Server
  method: DELETE
  name: deletemockserver
  path: /mock-servers/{mockServerId}
- description: Insomnia List Mock Routes
  method: GET
  name: listmockroutes
  path: /mock-servers/{mockServerId}/routes
- description: Insomnia Create Mock Route
  method: POST
  name: createmockroute
  path: /mock-servers/{mockServerId}/routes
- description: Insomnia Update Mock Route
  method: PUT
  name: updatemockroute
  path: /mock-servers/{mockServerId}/routes/{routeId}
- description: Insomnia Delete Mock Route
  method: DELETE
  name: deletemockroute
  path: /mock-servers/{mockServerId}/routes/{routeId}
- description: Insomnia List Mock Server Logs
  method: GET
  name: listmockserverlogs
  path: /mock-servers/{mockServerId}/logs
personas: []
provider_name: Insomnia
provider_slug: insomnia
search_terms:
- deletemockroute
- insomnia delete mock route
- testing
- mocking
- api
- platform
- insomnia create mock server
- insomnia delete mock server
- listmockserverlogs
- updatemockserver
- clients
- getmockserver
- insomnia list mock server logs
- api design
- insomnia
- createmockserver
- cli
- updatemockroute
- insomnia update mock route
- deletemockserver
- createmockroute
- listmockroutes
- insomnia create mock route
- listmockservers
- insomnia update mock server
- insomnia list mock routes
- insomnia list mock servers
- insomnia get mock server
slug: insomnia-capability
source_filename: insomnia-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Insomnia Mock Server API\n  description: The Insomnia Mock Server API allows developers to create, manage, and interact with mock servers powered by\n    Insomnia (Kong). Mock servers simulate API endpoints by returning predefined responses based on OpenAPI specifications\n    or custom route configurations. This enables frontend and backend teams to develop and test against realistic API behavior\n    before the actual implementation is complete. Insomnia supports both cloud-hosted and self-hosted mock server deployments.\n  tags:\n  - Insomnia\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: insomnia\n    baseUri: https://mock.insomnia.rest\n    description: Insomnia Mock Server API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{INSOMNIA_TOKEN}}'\n    resources:\n    - name: mock-servers\n      path: /mock-servers\n      operations:\n      - name:\
  \ listmockservers\n        method: GET\n        description: Insomnia List Mock Servers\n        inputParameters:\n        - name: workspaceId\n          in: query\n          type: string\n          description: Filter mock servers by workspace identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createmockserver\n        method: POST\n        description: Insomnia Create Mock Server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mock-servers-mockserverid\n      path: /mock-servers/{mockServerId}\n      operations:\n      - name: getmockserver\n        method: GET\n        description: Insomnia Get Mock Server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatemockserver\n        method: PUT\n      \
  \  description: Insomnia Update Mock Server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemockserver\n        method: DELETE\n        description: Insomnia Delete Mock Server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mock-servers-mockserverid-routes\n      path: /mock-servers/{mockServerId}/routes\n      operations:\n      - name: listmockroutes\n        method: GET\n        description: Insomnia List Mock Routes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createmockroute\n        method: POST\n        description: Insomnia Create Mock Route\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mock-servers-mockserverid-routes-routeid\n\
  \      path: /mock-servers/{mockServerId}/routes/{routeId}\n      operations:\n      - name: updatemockroute\n        method: PUT\n        description: Insomnia Update Mock Route\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemockroute\n        method: DELETE\n        description: Insomnia Delete Mock Route\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mock-servers-mockserverid-logs\n      path: /mock-servers/{mockServerId}/logs\n      operations:\n      - name: listmockserverlogs\n        method: GET\n        description: Insomnia List Mock Server Logs\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of log entries to return.\n        - name: offset\n          in: query\n          type: integer\n          description:\
  \ Number of log entries to skip for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: insomnia-rest\n    description: REST adapter for Insomnia Mock Server API.\n    resources:\n    - path: /mock-servers\n      name: listmockservers\n      operations:\n      - method: GET\n        name: listmockservers\n        description: Insomnia List Mock Servers\n        call: insomnia.listmockservers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mock-servers\n      name: createmockserver\n      operations:\n      - method: POST\n        name: createmockserver\n        description: Insomnia Create Mock Server\n        call: insomnia.createmockserver\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mock-servers/{mockServerId}\n      name: getmockserver\n      operations:\n\
  \      - method: GET\n        name: getmockserver\n        description: Insomnia Get Mock Server\n        call: insomnia.getmockserver\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mock-servers/{mockServerId}\n      name: updatemockserver\n      operations:\n      - method: PUT\n        name: updatemockserver\n        description: Insomnia Update Mock Server\n        call: insomnia.updatemockserver\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mock-servers/{mockServerId}\n      name: deletemockserver\n      operations:\n      - method: DELETE\n        name: deletemockserver\n        description: Insomnia Delete Mock Server\n        call: insomnia.deletemockserver\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mock-servers/{mockServerId}/routes\n      name: listmockroutes\n      operations:\n      - method: GET\n        name: listmockroutes\n        description: Insomnia\
  \ List Mock Routes\n        call: insomnia.listmockroutes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mock-servers/{mockServerId}/routes\n      name: createmockroute\n      operations:\n      - method: POST\n        name: createmockroute\n        description: Insomnia Create Mock Route\n        call: insomnia.createmockroute\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mock-servers/{mockServerId}/routes/{routeId}\n      name: updatemockroute\n      operations:\n      - method: PUT\n        name: updatemockroute\n        description: Insomnia Update Mock Route\n        call: insomnia.updatemockroute\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mock-servers/{mockServerId}/routes/{routeId}\n      name: deletemockroute\n      operations:\n      - method: DELETE\n        name: deletemockroute\n        description: Insomnia Delete Mock Route\n        call: insomnia.deletemockroute\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mock-servers/{mockServerId}/logs\n      name: listmockserverlogs\n      operations:\n      - method: GET\n        name: listmockserverlogs\n        description: Insomnia List Mock Server Logs\n        call: insomnia.listmockserverlogs\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: insomnia-mcp\n    transport: http\n    description: MCP adapter for Insomnia Mock Server API for AI agent use.\n    tools:\n    - name: listmockservers\n      description: Insomnia List Mock Servers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: insomnia.listmockservers\n      with:\n        workspaceId: tools.workspaceId\n      inputParameters:\n      - name: workspaceId\n        type: string\n        description: Filter mock servers by workspace identifier.\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: createmockserver\n      description: Insomnia Create Mock Server\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: insomnia.createmockserver\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmockserver\n      description: Insomnia Get Mock Server\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: insomnia.getmockserver\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatemockserver\n      description: Insomnia Update Mock Server\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: insomnia.updatemockserver\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletemockserver\n      description: Insomnia Delete Mock Server\n      hints:\n        readOnly: false\n        destructive:\
  \ true\n        idempotent: true\n      call: insomnia.deletemockserver\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmockroutes\n      description: Insomnia List Mock Routes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: insomnia.listmockroutes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createmockroute\n      description: Insomnia Create Mock Route\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: insomnia.createmockroute\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatemockroute\n      description: Insomnia Update Mock Route\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: insomnia.updatemockroute\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletemockroute\n      description:\
  \ Insomnia Delete Mock Route\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: insomnia.deletemockroute\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmockserverlogs\n      description: Insomnia List Mock Server Logs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: insomnia.listmockserverlogs\n      with:\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: limit\n        type: integer\n        description: Maximum number of log entries to return.\n      - name: offset\n        type: integer\n        description: Number of log entries to skip for pagination.\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    INSOMNIA_TOKEN: INSOMNIA_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/insomnia/refs/heads/main/capabilities/insomnia-capability.yaml
tags:
- Insomnia
- API
tools:
- description: Insomnia List Mock Servers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmockservers
- description: Insomnia Create Mock Server
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmockserver
- description: Insomnia Get Mock Server
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmockserver
- description: Insomnia Update Mock Server
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatemockserver
- description: Insomnia Delete Mock Server
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemockserver
- description: Insomnia List Mock Routes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmockroutes
- description: Insomnia Create Mock Route
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmockroute
- description: Insomnia Update Mock Route
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatemockroute
- description: Insomnia Delete Mock Route
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemockroute
- description: Insomnia List Mock Server Logs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmockserverlogs
---
