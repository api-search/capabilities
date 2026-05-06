---
categories: []
consumed_apis: []
description: The frp client (frpc) exposes a built-in HTTP admin API on its local web server. The API lets operators inspect or hot-reload the client configuration, stop the client, query proxy and visitor status, and (when a configuration store is enabled) manage stored proxy and visitor definitions. All routes (except /healthz) require HTTP Basic authentication using the user and password configured in webServer.user and webServer.password.
layout: capability
name: frp Client Admin API
operations:
- description: Health check
  method: GET
  name: gethealthz
  path: /healthz
- description: Reload configuration
  method: GET
  name: reloadconfig
  path: /api/reload
- description: Stop client
  method: POST
  name: stopclient
  path: /api/stop
- description: Get proxy status
  method: GET
  name: getstatus
  path: /api/status
- description: Get current configuration
  method: GET
  name: getconfig
  path: /api/config
- description: Replace configuration
  method: PUT
  name: putconfig
  path: /api/config
- description: Get proxy configuration
  method: GET
  name: getproxyconfig
  path: /api/proxy/{name}/config
- description: Get visitor configuration
  method: GET
  name: getvisitorconfig
  path: /api/visitor/{name}/config
- description: List stored proxies
  method: GET
  name: liststoreproxies
  path: /api/store/proxies
- description: Create stored proxy
  method: POST
  name: createstoreproxy
  path: /api/store/proxies
- description: Get stored proxy
  method: GET
  name: getstoreproxy
  path: /api/store/proxies/{name}
- description: Update stored proxy
  method: PUT
  name: updatestoreproxy
  path: /api/store/proxies/{name}
- description: Delete stored proxy
  method: DELETE
  name: deletestoreproxy
  path: /api/store/proxies/{name}
- description: List stored visitors
  method: GET
  name: liststorevisitors
  path: /api/store/visitors
- description: Create stored visitor
  method: POST
  name: createstorevisitor
  path: /api/store/visitors
- description: Get stored visitor
  method: GET
  name: getstorevisitor
  path: /api/store/visitors/{name}
- description: Update stored visitor
  method: PUT
  name: updatestorevisitor
  path: /api/store/visitors/{name}
- description: Delete stored visitor
  method: DELETE
  name: deletestorevisitor
  path: /api/store/visitors/{name}
personas: []
provider_name: frp
provider_slug: frp
search_terms:
- reverse proxy
- putconfig
- getvisitorconfig
- get stored visitor
- updatestorevisitor
- getstoreproxy
- deletestorevisitor
- get current configuration
- create stored proxy
- updatestoreproxy
- create stored visitor
- reload configuration
- get stored proxy
- stop client
- replace configuration
- update stored visitor
- open source
- reloadconfig
- get proxy status
- getstatus
- getproxyconfig
- liststoreproxies
- deletestoreproxy
- api
- get visitor configuration
- list stored proxies
- delete stored proxy
- frp
- liststorevisitors
- tunneling
- createstoreproxy
- stopclient
- health check
- getstorevisitor
- update stored proxy
- delete stored visitor
- createstorevisitor
- nat traversal
- list stored visitors
- getconfig
- gethealthz
- get proxy configuration
slug: frp-capability
source_filename: frp-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: frp Client Admin API\n  description: The frp client (frpc) exposes a built-in HTTP admin API on its local web server. The API lets operators inspect\n    or hot-reload the client configuration, stop the client, query proxy and visitor status, and (when a configuration store\n    is enabled) manage stored proxy and visitor definitions. All routes (except /healthz) require HTTP Basic authentication\n    using the user and password configured in webServer.user and webServer.password.\n  tags:\n  - Frp\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: frp\n    baseUri: http://127.0.0.1:7400\n    description: frp Client Admin API HTTP API.\n    authentication:\n      type: basic\n      username: '{{FRP_USERNAME}}'\n      password: '{{FRP_PASSWORD}}'\n    resources:\n    - name: healthz\n      path: /healthz\n      operations:\n      - name: gethealthz\n        method: GET\n\
  \        description: Health check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-reload\n      path: /api/reload\n      operations:\n      - name: reloadconfig\n        method: GET\n        description: Reload configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-stop\n      path: /api/stop\n      operations:\n      - name: stopclient\n        method: POST\n        description: Stop client\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-status\n      path: /api/status\n      operations:\n      - name: getstatus\n        method: GET\n        description: Get proxy status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: api-config\n      path: /api/config\n      operations:\n      - name: getconfig\n        method: GET\n        description: Get current configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: putconfig\n        method: PUT\n        description: Replace configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-proxy-name-config\n      path: /api/proxy/{name}/config\n      operations:\n      - name: getproxyconfig\n        method: GET\n        description: Get proxy configuration\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Proxy name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-visitor-name-config\n\
  \      path: /api/visitor/{name}/config\n      operations:\n      - name: getvisitorconfig\n        method: GET\n        description: Get visitor configuration\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Visitor name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-store-proxies\n      path: /api/store/proxies\n      operations:\n      - name: liststoreproxies\n        method: GET\n        description: List stored proxies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createstoreproxy\n        method: POST\n        description: Create stored proxy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-store-proxies-name\n\
  \      path: /api/store/proxies/{name}\n      operations:\n      - name: getstoreproxy\n        method: GET\n        description: Get stored proxy\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Stored proxy name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatestoreproxy\n        method: PUT\n        description: Update stored proxy\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Stored proxy name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletestoreproxy\n        method: DELETE\n        description: Delete stored proxy\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n\
  \          required: true\n          description: Stored proxy name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-store-visitors\n      path: /api/store/visitors\n      operations:\n      - name: liststorevisitors\n        method: GET\n        description: List stored visitors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createstorevisitor\n        method: POST\n        description: Create stored visitor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-store-visitors-name\n      path: /api/store/visitors/{name}\n      operations:\n      - name: getstorevisitor\n        method: GET\n        description: Get stored visitor\n        inputParameters:\n        - name: name\n          in: path\n          type:\
  \ string\n          required: true\n          description: Stored visitor name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatestorevisitor\n        method: PUT\n        description: Update stored visitor\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Stored visitor name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletestorevisitor\n        method: DELETE\n        description: Delete stored visitor\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Stored visitor name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n \
  \ - type: rest\n    port: 8080\n    namespace: frp-rest\n    description: REST adapter for frp Client Admin API.\n    resources:\n    - path: /healthz\n      name: gethealthz\n      operations:\n      - method: GET\n        name: gethealthz\n        description: Health check\n        call: frp.gethealthz\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/reload\n      name: reloadconfig\n      operations:\n      - method: GET\n        name: reloadconfig\n        description: Reload configuration\n        call: frp.reloadconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/stop\n      name: stopclient\n      operations:\n      - method: POST\n        name: stopclient\n        description: Stop client\n        call: frp.stopclient\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/status\n      name: getstatus\n      operations:\n      - method: GET\n        name:\
  \ getstatus\n        description: Get proxy status\n        call: frp.getstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/config\n      name: getconfig\n      operations:\n      - method: GET\n        name: getconfig\n        description: Get current configuration\n        call: frp.getconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/config\n      name: putconfig\n      operations:\n      - method: PUT\n        name: putconfig\n        description: Replace configuration\n        call: frp.putconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/proxy/{name}/config\n      name: getproxyconfig\n      operations:\n      - method: GET\n        name: getproxyconfig\n        description: Get proxy configuration\n        call: frp.getproxyconfig\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /api/visitor/{name}/config\n      name: getvisitorconfig\n      operations:\n      - method: GET\n        name: getvisitorconfig\n        description: Get visitor configuration\n        call: frp.getvisitorconfig\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/store/proxies\n      name: liststoreproxies\n      operations:\n      - method: GET\n        name: liststoreproxies\n        description: List stored proxies\n        call: frp.liststoreproxies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/store/proxies\n      name: createstoreproxy\n      operations:\n      - method: POST\n        name: createstoreproxy\n        description: Create stored proxy\n        call: frp.createstoreproxy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/store/proxies/{name}\n      name: getstoreproxy\n      operations:\n\
  \      - method: GET\n        name: getstoreproxy\n        description: Get stored proxy\n        call: frp.getstoreproxy\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/store/proxies/{name}\n      name: updatestoreproxy\n      operations:\n      - method: PUT\n        name: updatestoreproxy\n        description: Update stored proxy\n        call: frp.updatestoreproxy\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/store/proxies/{name}\n      name: deletestoreproxy\n      operations:\n      - method: DELETE\n        name: deletestoreproxy\n        description: Delete stored proxy\n        call: frp.deletestoreproxy\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/store/visitors\n      name: liststorevisitors\n      operations:\n    \
  \  - method: GET\n        name: liststorevisitors\n        description: List stored visitors\n        call: frp.liststorevisitors\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/store/visitors\n      name: createstorevisitor\n      operations:\n      - method: POST\n        name: createstorevisitor\n        description: Create stored visitor\n        call: frp.createstorevisitor\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/store/visitors/{name}\n      name: getstorevisitor\n      operations:\n      - method: GET\n        name: getstorevisitor\n        description: Get stored visitor\n        call: frp.getstorevisitor\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/store/visitors/{name}\n      name: updatestorevisitor\n      operations:\n      - method: PUT\n        name: updatestorevisitor\n        description:\
  \ Update stored visitor\n        call: frp.updatestorevisitor\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/store/visitors/{name}\n      name: deletestorevisitor\n      operations:\n      - method: DELETE\n        name: deletestorevisitor\n        description: Delete stored visitor\n        call: frp.deletestorevisitor\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: frp-mcp\n    transport: http\n    description: MCP adapter for frp Client Admin API for AI agent use.\n    tools:\n    - name: gethealthz\n      description: Health check\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: frp.gethealthz\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reloadconfig\n      description: Reload configuration\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: frp.reloadconfig\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stopclient\n      description: Stop client\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: frp.stopclient\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstatus\n      description: Get proxy status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: frp.getstatus\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getconfig\n      description: Get current configuration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: frp.getconfig\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: putconfig\n      description: Replace configuration\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: frp.putconfig\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproxyconfig\n      description: Get proxy configuration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: frp.getproxyconfig\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: Proxy name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvisitorconfig\n      description: Get visitor configuration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: frp.getvisitorconfig\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: Visitor name\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: liststoreproxies\n      description: List stored proxies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: frp.liststoreproxies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createstoreproxy\n      description: Create stored proxy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: frp.createstoreproxy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstoreproxy\n      description: Get stored proxy\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: frp.getstoreproxy\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: Stored proxy name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n \
  \   - name: updatestoreproxy\n      description: Update stored proxy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: frp.updatestoreproxy\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: Stored proxy name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletestoreproxy\n      description: Delete stored proxy\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: frp.deletestoreproxy\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: Stored proxy name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: liststorevisitors\n      description: List stored visitors\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: frp.liststorevisitors\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createstorevisitor\n      description: Create stored visitor\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: frp.createstorevisitor\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstorevisitor\n      description: Get stored visitor\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: frp.getstorevisitor\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: Stored visitor name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatestorevisitor\n      description: Update stored visitor\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n\
  \      call: frp.updatestorevisitor\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: Stored visitor name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletestorevisitor\n      description: Delete stored visitor\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: frp.deletestorevisitor\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: Stored visitor name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    FRP_USERNAME: FRP_USERNAME\n    FRP_PASSWORD: FRP_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/frp/refs/heads/main/capabilities/frp-capability.yaml
tags:
- Frp
- API
tools:
- description: Health check
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethealthz
- description: Reload configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: reloadconfig
- description: Stop client
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stopclient
- description: Get proxy status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstatus
- description: Get current configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconfig
- description: Replace configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putconfig
- description: Get proxy configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproxyconfig
- description: Get visitor configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvisitorconfig
- description: List stored proxies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: liststoreproxies
- description: Create stored proxy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createstoreproxy
- description: Get stored proxy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstoreproxy
- description: Update stored proxy
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatestoreproxy
- description: Delete stored proxy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletestoreproxy
- description: List stored visitors
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: liststorevisitors
- description: Create stored visitor
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createstorevisitor
- description: Get stored visitor
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstorevisitor
- description: Update stored visitor
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatestorevisitor
- description: Delete stored visitor
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletestorevisitor
---
