---
categories: []
consumed_apis: []
description: Dynamic Client Registration, Token, Introspection, Authorize API
layout: capability
name: Mastercard Developer Hub for FDX APIs FDX Authorization Server
operations:
- description: Mastercard Developer Hub for FDX APIs Client Registration Request
  method: POST
  name: registerclient
  path: /fdx/v6/register
- description: Mastercard Developer Hub for FDX APIs Get Token
  method: POST
  name: gettoken
  path: /oauth2/token
- description: Mastercard Developer Hub for FDX APIs Get Client
  method: GET
  name: getclient
  path: /fdx/v6/register/{clientId}
- description: Mastercard Developer Hub for FDX APIs Update Client
  method: PUT
  name: modifyclient
  path: /fdx/v6/register/{clientId}
- description: Mastercard Developer Hub for FDX APIs Delete Client
  method: DELETE
  name: deleteclient
  path: /fdx/v6/register/{clientId}
- description: Mastercard Developer Hub for FDX APIs Submit an Authorization Request
  method: POST
  name: authorizeviaparrar
  path: /oauth2/par
- description: Mastercard Developer Hub for FDX APIs User Authorization Endpoint
  method: GET
  name: parauthorizedonthitcopytheurlfromcurl
  path: /oauth2/authorize
- description: Mastercard Developer Hub for FDX APIs Token Introspection Endpoint
  method: POST
  name: introspectiontoken
  path: /oauth2/introspect
personas: []
provider_name: Mastercard Developer Hub for FDX APIs
provider_slug: mastercard-fdx
search_terms:
- developer
- mastercard developer hub for fdx apis user authorization endpoint
- for
- mastercard developer hub for fdx apis token introspection endpoint
- apis
- registerclient
- mastercard developer hub for fdx apis get client
- parauthorizedonthitcopytheurlfromcurl
- gettoken
- open banking
- fdx
- mastercard
- mastercard developer hub for fdx apis get token
- mastercard developer hub for fdx apis client registration request
- hub
- deleteclient
- mastercard developer hub for fdx apis delete client
- authorizeviaparrar
- getclient
- introspectiontoken
- modifyclient
- banking
- mastercard developer hub for fdx apis update client
- mastercard developer hub for fdx apis submit an authorization request
slug: mastercard-developer-hub-for-fdx-apis-capability
source_filename: mastercard-developer-hub-for-fdx-apis-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Mastercard Developer Hub for FDX APIs FDX Authorization Server\n  description: Dynamic Client Registration, Token, Introspection, Authorize API\n  tags:\n  - Mastercard\n  - Developer\n  - Hub\n  - For\n  - Fdx\n  - Apis\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: mastercard-developer-hub-for-fdx-apis\n    baseUri: http://localhost:8080\n    description: Mastercard Developer Hub for FDX APIs FDX Authorization Server HTTP API.\n    authentication:\n      type: bearer\n      token: '{{MASTERCARD_DEVELOPER_HUB_FOR_FDX_APIS_TOKEN}}'\n    resources:\n    - name: fdx-v6-register\n      path: /fdx/v6/register\n      operations:\n      - name: registerclient\n        method: POST\n        description: Mastercard Developer Hub for FDX APIs Client Registration Request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n    - name: oauth2-token\n      path: /oauth2/token\n      operations:\n      - name: gettoken\n        method: POST\n        description: Mastercard Developer Hub for FDX APIs Get Token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fdx-v6-register-clientid\n      path: /fdx/v6/register/{clientId}\n      operations:\n      - name: getclient\n        method: GET\n        description: Mastercard Developer Hub for FDX APIs Get Client\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: modifyclient\n        method: PUT\n        description: Mastercard Developer Hub for FDX APIs Update Client\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteclient\n        method: DELETE\n        description: Mastercard\
  \ Developer Hub for FDX APIs Delete Client\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth2-par\n      path: /oauth2/par\n      operations:\n      - name: authorizeviaparrar\n        method: POST\n        description: Mastercard Developer Hub for FDX APIs Submit an Authorization Request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth2-authorize\n      path: /oauth2/authorize\n      operations:\n      - name: parauthorizedonthitcopytheurlfromcurl\n        method: GET\n        description: Mastercard Developer Hub for FDX APIs User Authorization Endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth2-introspect\n      path: /oauth2/introspect\n      operations:\n      - name: introspectiontoken\n\
  \        method: POST\n        description: Mastercard Developer Hub for FDX APIs Token Introspection Endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mastercard-developer-hub-for-fdx-apis-rest\n    description: REST adapter for Mastercard Developer Hub for FDX APIs FDX Authorization Server.\n    resources:\n    - path: /fdx/v6/register\n      name: registerclient\n      operations:\n      - method: POST\n        name: registerclient\n        description: Mastercard Developer Hub for FDX APIs Client Registration Request\n        call: mastercard-developer-hub-for-fdx-apis.registerclient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth2/token\n      name: gettoken\n      operations:\n      - method: POST\n        name: gettoken\n        description: Mastercard Developer Hub for FDX APIs Get Token\n\
  \        call: mastercard-developer-hub-for-fdx-apis.gettoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fdx/v6/register/{clientId}\n      name: getclient\n      operations:\n      - method: GET\n        name: getclient\n        description: Mastercard Developer Hub for FDX APIs Get Client\n        call: mastercard-developer-hub-for-fdx-apis.getclient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fdx/v6/register/{clientId}\n      name: modifyclient\n      operations:\n      - method: PUT\n        name: modifyclient\n        description: Mastercard Developer Hub for FDX APIs Update Client\n        call: mastercard-developer-hub-for-fdx-apis.modifyclient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fdx/v6/register/{clientId}\n      name: deleteclient\n      operations:\n      - method: DELETE\n        name: deleteclient\n        description: Mastercard Developer\
  \ Hub for FDX APIs Delete Client\n        call: mastercard-developer-hub-for-fdx-apis.deleteclient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth2/par\n      name: authorizeviaparrar\n      operations:\n      - method: POST\n        name: authorizeviaparrar\n        description: Mastercard Developer Hub for FDX APIs Submit an Authorization Request\n        call: mastercard-developer-hub-for-fdx-apis.authorizeviaparrar\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth2/authorize\n      name: parauthorizedonthitcopytheurlfromcurl\n      operations:\n      - method: GET\n        name: parauthorizedonthitcopytheurlfromcurl\n        description: Mastercard Developer Hub for FDX APIs User Authorization Endpoint\n        call: mastercard-developer-hub-for-fdx-apis.parauthorizedonthitcopytheurlfromcurl\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth2/introspect\n\
  \      name: introspectiontoken\n      operations:\n      - method: POST\n        name: introspectiontoken\n        description: Mastercard Developer Hub for FDX APIs Token Introspection Endpoint\n        call: mastercard-developer-hub-for-fdx-apis.introspectiontoken\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: mastercard-developer-hub-for-fdx-apis-mcp\n    transport: http\n    description: MCP adapter for Mastercard Developer Hub for FDX APIs FDX Authorization Server for AI agent use.\n    tools:\n    - name: registerclient\n      description: Mastercard Developer Hub for FDX APIs Client Registration Request\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mastercard-developer-hub-for-fdx-apis.registerclient\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettoken\n      description: Mastercard Developer Hub for FDX APIs\
  \ Get Token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mastercard-developer-hub-for-fdx-apis.gettoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getclient\n      description: Mastercard Developer Hub for FDX APIs Get Client\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mastercard-developer-hub-for-fdx-apis.getclient\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: modifyclient\n      description: Mastercard Developer Hub for FDX APIs Update Client\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: mastercard-developer-hub-for-fdx-apis.modifyclient\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteclient\n      description: Mastercard Developer Hub for FDX APIs Delete Client\n      hints:\n        readOnly:\
  \ false\n        destructive: true\n        idempotent: true\n      call: mastercard-developer-hub-for-fdx-apis.deleteclient\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: authorizeviaparrar\n      description: Mastercard Developer Hub for FDX APIs Submit an Authorization Request\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mastercard-developer-hub-for-fdx-apis.authorizeviaparrar\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: parauthorizedonthitcopytheurlfromcurl\n      description: Mastercard Developer Hub for FDX APIs User Authorization Endpoint\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mastercard-developer-hub-for-fdx-apis.parauthorizedonthitcopytheurlfromcurl\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: introspectiontoken\n      description: Mastercard Developer\
  \ Hub for FDX APIs Token Introspection Endpoint\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mastercard-developer-hub-for-fdx-apis.introspectiontoken\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MASTERCARD_DEVELOPER_HUB_FOR_FDX_APIS_TOKEN: MASTERCARD_DEVELOPER_HUB_FOR_FDX_APIS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mastercard-fdx/refs/heads/main/capabilities/mastercard-developer-hub-for-fdx-apis-capability.yaml
tags:
- Mastercard
- Developer
- Hub
- For
- Fdx
- Apis
tools:
- description: Mastercard Developer Hub for FDX APIs Client Registration Request
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: registerclient
- description: Mastercard Developer Hub for FDX APIs Get Token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: gettoken
- description: Mastercard Developer Hub for FDX APIs Get Client
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclient
- description: Mastercard Developer Hub for FDX APIs Update Client
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: modifyclient
- description: Mastercard Developer Hub for FDX APIs Delete Client
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteclient
- description: Mastercard Developer Hub for FDX APIs Submit an Authorization Request
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authorizeviaparrar
- description: Mastercard Developer Hub for FDX APIs User Authorization Endpoint
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: parauthorizedonthitcopytheurlfromcurl
- description: Mastercard Developer Hub for FDX APIs Token Introspection Endpoint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: introspectiontoken
---
