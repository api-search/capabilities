---
categories: []
consumed_apis: []
description: MockServer enables easy mocking of any system you integrate with via HTTP or HTTPS with clients written in Java, JavaScript and Ruby and a simple REST API (as shown below). MockServer Proxy is a proxy that introspects all proxied traffic including encrypted SSL traffic and supports Port Forwarding, Web Proxying (i.e. HTTP proxy), HTTPS Tunneling Proxying (using HTTP CONNECT) and SOCKS Proxying (i.e. dynamic port forwarding). Both MockServer and the MockServer Proxy record all received requests so that it is possible to verify exactly what requests have been sent by the system under test.
layout: capability
name: MockServer API
operations:
- description: create expectation
  method: PUT
  name: put-mockserver-expectation
  path: /mockserver/expectation
- description: create expectations from OpenAPI or Swagger
  method: PUT
  name: put-mockserver-openapi
  path: /mockserver/openapi
- description: clears expectations and recorded requests that match the request matcher
  method: PUT
  name: put-mockserver-clear
  path: /mockserver/clear
- description: clears all expectations and recorded requests
  method: PUT
  name: put-mockserver-reset
  path: /mockserver/reset
- description: retrieve recorded requests, active expectations, recorded expectations or log messages
  method: PUT
  name: put-mockserver-retrieve
  path: /mockserver/retrieve
- description: verify a request has been received a specific number of times
  method: PUT
  name: put-mockserver-verify
  path: /mockserver/verify
- description: verify a sequence of request has been received in the specific order
  method: PUT
  name: put-mockserver-verifysequence
  path: /mockserver/verifySequence
- description: return listening ports
  method: PUT
  name: put-mockserver-status
  path: /mockserver/status
- description: bind additional listening ports
  method: PUT
  name: put-mockserver-bind
  path: /mockserver/bind
- description: stop running process
  method: PUT
  name: put-mockserver-stop
  path: /mockserver/stop
personas: []
provider_name: MockServer
provider_slug: mockserver
search_terms:
- verify a sequence of request has been received in the specific order
- testing
- put mockserver retrieve
- verify a request has been received a specific number of times
- mocking
- http
- api
- platform
- retrieve recorded requests, active expectations, recorded expectations or log messages
- bind additional listening ports
- clears all expectations and recorded requests
- put mockserver openapi
- put mockserver verify
- service virtualization
- return listening ports
- create expectations from openapi or swagger
- put mockserver expectation
- create expectation
- put mockserver reset
- put mockserver status
- put mockserver verifysequence
- mockserver
- put mockserver stop
- put mockserver bind
- rest api
- put mockserver clear
- mock server
- stop running process
- clears expectations and recorded requests that match the request matcher
slug: mockserver-capability
source_filename: mockserver-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: MockServer API\n  description: MockServer enables easy mocking of any system you integrate with via HTTP or HTTPS with clients written in\n    Java, JavaScript and Ruby and a simple REST API (as shown below). MockServer Proxy is a proxy that introspects all proxied\n    traffic including encrypted SSL traffic and supports Port Forwarding, Web Proxying (i.e. HTTP proxy), HTTPS Tunneling\n    Proxying (using HTTP CONNECT) and SOCKS Proxying (i.e. dynamic port forwarding). Both MockServer and the MockServer Proxy\n    record all received requests so that it is possible to verify exactly what requests have been sent by the system under\n    test.\n  tags:\n  - Mockserver\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: mockserver\n    baseUri: http://localhost:1080\n    description: MockServer API HTTP API.\n    resources:\n    - name: mockserver-expectation\n      path:\
  \ /mockserver/expectation\n      operations:\n      - name: put-mockserver-expectation\n        method: PUT\n        description: create expectation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mockserver-openapi\n      path: /mockserver/openapi\n      operations:\n      - name: put-mockserver-openapi\n        method: PUT\n        description: create expectations from OpenAPI or Swagger\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mockserver-clear\n      path: /mockserver/clear\n      operations:\n      - name: put-mockserver-clear\n        method: PUT\n        description: clears expectations and recorded requests that match the request matcher\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          description: specifies the type of information to clear,\
  \ default if not specified is \"all\", supported values are\n            \"all\", \"log\", \"expectations\"\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mockserver-reset\n      path: /mockserver/reset\n      operations:\n      - name: put-mockserver-reset\n        method: PUT\n        description: clears all expectations and recorded requests\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mockserver-retrieve\n      path: /mockserver/retrieve\n      operations:\n      - name: put-mockserver-retrieve\n        method: PUT\n        description: retrieve recorded requests, active expectations, recorded expectations or log messages\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          description: changes response format, default if not specified is \"json\"\
  , supported values are \"java\", \"json\", \"log_entries\"\n        - name: type\n          in: query\n          type: string\n          description: specifies the type of object that is retrieve, default if not specified is \"requests\", supported values\n            are \"logs\", \"requests\", \"recorded_expectations\", \"active\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mockserver-verify\n      path: /mockserver/verify\n      operations:\n      - name: put-mockserver-verify\n        method: PUT\n        description: verify a request has been received a specific number of times\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mockserver-verifysequence\n      path: /mockserver/verifySequence\n      operations:\n      - name: put-mockserver-verifysequence\n        method: PUT\n        description: verify\
  \ a sequence of request has been received in the specific order\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mockserver-status\n      path: /mockserver/status\n      operations:\n      - name: put-mockserver-status\n        method: PUT\n        description: return listening ports\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mockserver-bind\n      path: /mockserver/bind\n      operations:\n      - name: put-mockserver-bind\n        method: PUT\n        description: bind additional listening ports\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mockserver-stop\n      path: /mockserver/stop\n      operations:\n      - name: put-mockserver-stop\n        method: PUT\n        description: stop running process\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mockserver-rest\n    description: REST adapter for MockServer API.\n    resources:\n    - path: /mockserver/expectation\n      name: put-mockserver-expectation\n      operations:\n      - method: PUT\n        name: put-mockserver-expectation\n        description: create expectation\n        call: mockserver.put-mockserver-expectation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mockserver/openapi\n      name: put-mockserver-openapi\n      operations:\n      - method: PUT\n        name: put-mockserver-openapi\n        description: create expectations from OpenAPI or Swagger\n        call: mockserver.put-mockserver-openapi\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mockserver/clear\n      name: put-mockserver-clear\n   \
  \   operations:\n      - method: PUT\n        name: put-mockserver-clear\n        description: clears expectations and recorded requests that match the request matcher\n        call: mockserver.put-mockserver-clear\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mockserver/reset\n      name: put-mockserver-reset\n      operations:\n      - method: PUT\n        name: put-mockserver-reset\n        description: clears all expectations and recorded requests\n        call: mockserver.put-mockserver-reset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mockserver/retrieve\n      name: put-mockserver-retrieve\n      operations:\n      - method: PUT\n        name: put-mockserver-retrieve\n        description: retrieve recorded requests, active expectations, recorded expectations or log messages\n        call: mockserver.put-mockserver-retrieve\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /mockserver/verify\n      name: put-mockserver-verify\n      operations:\n      - method: PUT\n        name: put-mockserver-verify\n        description: verify a request has been received a specific number of times\n        call: mockserver.put-mockserver-verify\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mockserver/verifySequence\n      name: put-mockserver-verifysequence\n      operations:\n      - method: PUT\n        name: put-mockserver-verifysequence\n        description: verify a sequence of request has been received in the specific order\n        call: mockserver.put-mockserver-verifysequence\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mockserver/status\n      name: put-mockserver-status\n      operations:\n      - method: PUT\n        name: put-mockserver-status\n        description: return listening ports\n        call: mockserver.put-mockserver-status\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /mockserver/bind\n      name: put-mockserver-bind\n      operations:\n      - method: PUT\n        name: put-mockserver-bind\n        description: bind additional listening ports\n        call: mockserver.put-mockserver-bind\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mockserver/stop\n      name: put-mockserver-stop\n      operations:\n      - method: PUT\n        name: put-mockserver-stop\n        description: stop running process\n        call: mockserver.put-mockserver-stop\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: mockserver-mcp\n    transport: http\n    description: MCP adapter for MockServer API for AI agent use.\n    tools:\n    - name: put-mockserver-expectation\n      description: create expectation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n    \
  \  call: mockserver.put-mockserver-expectation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-mockserver-openapi\n      description: create expectations from OpenAPI or Swagger\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: mockserver.put-mockserver-openapi\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-mockserver-clear\n      description: clears expectations and recorded requests that match the request matcher\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: mockserver.put-mockserver-clear\n      with:\n        type: tools.type\n      inputParameters:\n      - name: type\n        type: string\n        description: specifies the type of information to clear, default if not specified is \"all\", supported values are \"all\",\n          \"log\", \"expectations\"\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: put-mockserver-reset\n      description: clears all expectations and recorded requests\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: mockserver.put-mockserver-reset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-mockserver-retrieve\n      description: retrieve recorded requests, active expectations, recorded expectations or log messages\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: mockserver.put-mockserver-retrieve\n      with:\n        format: tools.format\n        type: tools.type\n      inputParameters:\n      - name: format\n        type: string\n        description: changes response format, default if not specified is \"json\", supported values are \"java\", \"json\", \"log_entries\"\n      - name: type\n        type: string\n        description: specifies the type of object that is\
  \ retrieve, default if not specified is \"requests\", supported values\n          are \"logs\", \"requests\", \"recorded_expectations\", \"active\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-mockserver-verify\n      description: verify a request has been received a specific number of times\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: mockserver.put-mockserver-verify\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-mockserver-verifysequence\n      description: verify a sequence of request has been received in the specific order\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: mockserver.put-mockserver-verifysequence\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-mockserver-status\n      description: return listening ports\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: true\n      call: mockserver.put-mockserver-status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-mockserver-bind\n      description: bind additional listening ports\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: mockserver.put-mockserver-bind\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-mockserver-stop\n      description: stop running process\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: mockserver.put-mockserver-stop\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mockserver/refs/heads/main/capabilities/mockserver-capability.yaml
tags:
- Mockserver
- API
tools:
- description: create expectation
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-mockserver-expectation
- description: create expectations from OpenAPI or Swagger
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-mockserver-openapi
- description: clears expectations and recorded requests that match the request matcher
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-mockserver-clear
- description: clears all expectations and recorded requests
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-mockserver-reset
- description: retrieve recorded requests, active expectations, recorded expectations or log messages
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-mockserver-retrieve
- description: verify a request has been received a specific number of times
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-mockserver-verify
- description: verify a sequence of request has been received in the specific order
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-mockserver-verifysequence
- description: return listening ports
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-mockserver-status
- description: bind additional listening ports
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-mockserver-bind
- description: stop running process
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-mockserver-stop
---
