---
categories: []
consumed_apis: []
description: The Boltic Gateway API provides a developer-friendly API gateway designed to simplify and secure how services interact across your platform. It enables seamless request routing, payload transformation, and enforcement of security policies across diverse integration types including serverless functions, workflows, tables, and proxy endpoints. The Gateway supports dynamic URL rewriting, path parameter injection, fine-grained authentication, and real-time observability.
layout: capability
name: Boltic Gateway API
operations:
- description: Boltic List all routes
  method: GET
  name: listroutes
  path: /routes
- description: Boltic Create a new route
  method: POST
  name: createroute
  path: /routes
- description: Boltic Get a route by ID
  method: GET
  name: getroute
  path: /routes/{routeId}
- description: Boltic Update a route
  method: PUT
  name: updateroute
  path: /routes/{routeId}
- description: Boltic Delete a route
  method: DELETE
  name: deleteroute
  path: /routes/{routeId}
- description: Boltic List all services
  method: GET
  name: listservices
  path: /services
- description: Boltic Create a new service
  method: POST
  name: createservice
  path: /services
- description: Boltic Get a service by ID
  method: GET
  name: getservice
  path: /services/{serviceId}
- description: Boltic Update a service
  method: PUT
  name: updateservice
  path: /services/{serviceId}
- description: Boltic Delete a service
  method: DELETE
  name: deleteservice
  path: /services/{serviceId}
- description: Boltic List all plugins
  method: GET
  name: listplugins
  path: /plugins
- description: Boltic Create a new plugin
  method: POST
  name: createplugin
  path: /plugins
- description: Boltic Get a plugin by ID
  method: GET
  name: getplugin
  path: /plugins/{pluginId}
- description: Boltic Update a plugin
  method: PUT
  name: updateplugin
  path: /plugins/{pluginId}
- description: Boltic Delete a plugin
  method: DELETE
  name: deleteplugin
  path: /plugins/{pluginId}
- description: Boltic List all consumers
  method: GET
  name: listconsumers
  path: /consumers
- description: Boltic Create a new consumer
  method: POST
  name: createconsumer
  path: /consumers
- description: Boltic Get a consumer by ID
  method: GET
  name: getconsumer
  path: /consumers/{consumerId}
- description: Boltic Delete a consumer
  method: DELETE
  name: deleteconsumer
  path: /consumers/{consumerId}
- description: Boltic List all certificates
  method: GET
  name: listcertificates
  path: /certificates
- description: Boltic Upload a new certificate
  method: POST
  name: createcertificate
  path: /certificates
personas: []
provider_name: Boltic
provider_slug: boltic
search_terms:
- boltic get a consumer by id
- listplugins
- boltic create a new plugin
- gateways
- boltic update a plugin
- listroutes
- createcertificate
- updateroute
- boltic list all services
- datasync
- nocode
- boltic get a plugin by id
- getroute
- boltic delete a route
- boltic list all plugins
- boltic create a new route
- boltic get a service by id
- boltic list all certificates
- createroute
- createplugin
- getservice
- boltic create a new consumer
- getplugin
- deleteservice
- deleteplugin
- listcertificates
- boltic upload a new certificate
- updateplugin
- boltic update a route
- boltic delete a plugin
- boltic delete a consumer
- api
- deleteconsumer
- boltic list all routes
- updateservice
- boltic update a service
- boltic list all consumers
- boltic
- workflows
- getconsumer
- boltic get a route by id
- deleteroute
- streaming
- boltic create a new service
- createconsumer
- listconsumers
- listservices
- boltic delete a service
- createservice
- automation
slug: boltic-capability
source_filename: boltic-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Boltic Gateway API\n  description: The Boltic Gateway API provides a developer-friendly API gateway designed to simplify and secure how services\n    interact across your platform. It enables seamless request routing, payload transformation, and enforcement of security\n    policies across diverse integration types including serverless functions, workflows, tables, and proxy endpoints. The\n    Gateway supports dynamic URL rewriting, path parameter injection, fine-grained authentication, and real-time observability.\n  tags:\n  - Boltic\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: boltic\n    baseUri: https://gateway.boltic.io/v1\n    description: Boltic Gateway API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{BOLTIC_TOKEN}}'\n    resources:\n    - name: routes\n      path: /routes\n      operations:\n      - name: listroutes\n        method:\
  \ GET\n        description: Boltic List all routes\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createroute\n        method: POST\n        description: Boltic Create a new route\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: routes-routeid\n      path: /routes/{routeId}\n      operations:\n      - name: getroute\n        method: GET\n        description: Boltic Get a route by ID\n        inputParameters:\n        - name: routeId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateroute\n\
  \        method: PUT\n        description: Boltic Update a route\n        inputParameters:\n        - name: routeId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteroute\n        method: DELETE\n        description: Boltic Delete a route\n        inputParameters:\n        - name: routeId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services\n      path: /services\n      operations:\n      - name: listservices\n        method: GET\n        description: Boltic List all services\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createservice\n        method: POST\n        description: Boltic Create a new service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-serviceid\n      path: /services/{serviceId}\n      operations:\n      - name: getservice\n        method: GET\n        description: Boltic Get a service by ID\n        inputParameters:\n        - name: serviceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateservice\n        method: PUT\n        description: Boltic Update a service\n        inputParameters:\n        - name: serviceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteservice\n        method: DELETE\n        description: Boltic Delete a service\n        inputParameters:\n        - name: serviceId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plugins\n      path: /plugins\n      operations:\n      - name: listplugins\n        method: GET\n        description: Boltic List all plugins\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createplugin\n        method: POST\n        description: Boltic Create a new plugin\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: plugins-pluginid\n      path:\
  \ /plugins/{pluginId}\n      operations:\n      - name: getplugin\n        method: GET\n        description: Boltic Get a plugin by ID\n        inputParameters:\n        - name: pluginId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateplugin\n        method: PUT\n        description: Boltic Update a plugin\n        inputParameters:\n        - name: pluginId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteplugin\n        method: DELETE\n        description: Boltic Delete a plugin\n        inputParameters:\n        - name: pluginId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: consumers\n      path: /consumers\n      operations:\n      - name: listconsumers\n        method: GET\n        description: Boltic List all consumers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createconsumer\n        method: POST\n        description: Boltic Create a new consumer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: consumers-consumerid\n      path: /consumers/{consumerId}\n      operations:\n      - name: getconsumer\n        method: GET\n        description: Boltic Get a consumer by ID\n        inputParameters:\n        - name: consumerId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: deleteconsumer\n        method: DELETE\n        description: Boltic Delete a consumer\n        inputParameters:\n        - name: consumerId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: certificates\n      path: /certificates\n      operations:\n      - name: listcertificates\n        method: GET\n        description: Boltic List all certificates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcertificate\n        method: POST\n        description: Boltic Upload a new certificate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: boltic-rest\n    description:\
  \ REST adapter for Boltic Gateway API.\n    resources:\n    - path: /routes\n      name: listroutes\n      operations:\n      - method: GET\n        name: listroutes\n        description: Boltic List all routes\n        call: boltic.listroutes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /routes\n      name: createroute\n      operations:\n      - method: POST\n        name: createroute\n        description: Boltic Create a new route\n        call: boltic.createroute\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /routes/{routeId}\n      name: getroute\n      operations:\n      - method: GET\n        name: getroute\n        description: Boltic Get a route by ID\n        call: boltic.getroute\n        with:\n          routeId: rest.routeId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /routes/{routeId}\n      name: updateroute\n      operations:\n      - method: PUT\n\
  \        name: updateroute\n        description: Boltic Update a route\n        call: boltic.updateroute\n        with:\n          routeId: rest.routeId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /routes/{routeId}\n      name: deleteroute\n      operations:\n      - method: DELETE\n        name: deleteroute\n        description: Boltic Delete a route\n        call: boltic.deleteroute\n        with:\n          routeId: rest.routeId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /services\n      name: listservices\n      operations:\n      - method: GET\n        name: listservices\n        description: Boltic List all services\n        call: boltic.listservices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /services\n      name: createservice\n      operations:\n      - method: POST\n        name: createservice\n        description: Boltic Create a new service\n  \
  \      call: boltic.createservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /services/{serviceId}\n      name: getservice\n      operations:\n      - method: GET\n        name: getservice\n        description: Boltic Get a service by ID\n        call: boltic.getservice\n        with:\n          serviceId: rest.serviceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /services/{serviceId}\n      name: updateservice\n      operations:\n      - method: PUT\n        name: updateservice\n        description: Boltic Update a service\n        call: boltic.updateservice\n        with:\n          serviceId: rest.serviceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /services/{serviceId}\n      name: deleteservice\n      operations:\n      - method: DELETE\n        name: deleteservice\n        description: Boltic Delete a service\n        call: boltic.deleteservice\n  \
  \      with:\n          serviceId: rest.serviceId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /plugins\n      name: listplugins\n      operations:\n      - method: GET\n        name: listplugins\n        description: Boltic List all plugins\n        call: boltic.listplugins\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /plugins\n      name: createplugin\n      operations:\n      - method: POST\n        name: createplugin\n        description: Boltic Create a new plugin\n        call: boltic.createplugin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /plugins/{pluginId}\n      name: getplugin\n      operations:\n      - method: GET\n        name: getplugin\n        description: Boltic Get a plugin by ID\n        call: boltic.getplugin\n        with:\n          pluginId: rest.pluginId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /plugins/{pluginId}\n      name: updateplugin\n      operations:\n      - method: PUT\n        name: updateplugin\n        description: Boltic Update a plugin\n        call: boltic.updateplugin\n        with:\n          pluginId: rest.pluginId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /plugins/{pluginId}\n      name: deleteplugin\n      operations:\n      - method: DELETE\n        name: deleteplugin\n        description: Boltic Delete a plugin\n        call: boltic.deleteplugin\n        with:\n          pluginId: rest.pluginId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /consumers\n      name: listconsumers\n      operations:\n      - method: GET\n        name: listconsumers\n        description: Boltic List all consumers\n        call: boltic.listconsumers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /consumers\n      name: createconsumer\n      operations:\n\
  \      - method: POST\n        name: createconsumer\n        description: Boltic Create a new consumer\n        call: boltic.createconsumer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /consumers/{consumerId}\n      name: getconsumer\n      operations:\n      - method: GET\n        name: getconsumer\n        description: Boltic Get a consumer by ID\n        call: boltic.getconsumer\n        with:\n          consumerId: rest.consumerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /consumers/{consumerId}\n      name: deleteconsumer\n      operations:\n      - method: DELETE\n        name: deleteconsumer\n        description: Boltic Delete a consumer\n        call: boltic.deleteconsumer\n        with:\n          consumerId: rest.consumerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /certificates\n      name: listcertificates\n      operations:\n      - method: GET\n\
  \        name: listcertificates\n        description: Boltic List all certificates\n        call: boltic.listcertificates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /certificates\n      name: createcertificate\n      operations:\n      - method: POST\n        name: createcertificate\n        description: Boltic Upload a new certificate\n        call: boltic.createcertificate\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: boltic-mcp\n    transport: http\n    description: MCP adapter for Boltic Gateway API for AI agent use.\n    tools:\n    - name: listroutes\n      description: Boltic List all routes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: boltic.listroutes\n      with:\n        page: tools.page\n        limit: tools.limit\n      inputParameters:\n      - name: page\n        type: integer\n        description:\
  \ page\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createroute\n      description: Boltic Create a new route\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: boltic.createroute\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getroute\n      description: Boltic Get a route by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: boltic.getroute\n      with:\n        routeId: tools.routeId\n      inputParameters:\n      - name: routeId\n        type: string\n        description: routeId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateroute\n      description: Boltic Update a route\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n  \
  \    call: boltic.updateroute\n      with:\n        routeId: tools.routeId\n      inputParameters:\n      - name: routeId\n        type: string\n        description: routeId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteroute\n      description: Boltic Delete a route\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: boltic.deleteroute\n      with:\n        routeId: tools.routeId\n      inputParameters:\n      - name: routeId\n        type: string\n        description: routeId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listservices\n      description: Boltic List all services\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: boltic.listservices\n      with:\n        page: tools.page\n        limit: tools.limit\n      inputParameters:\n      - name: page\n\
  \        type: integer\n        description: page\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createservice\n      description: Boltic Create a new service\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: boltic.createservice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getservice\n      description: Boltic Get a service by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: boltic.getservice\n      with:\n        serviceId: tools.serviceId\n      inputParameters:\n      - name: serviceId\n        type: string\n        description: serviceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateservice\n      description: Boltic Update a service\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: true\n      call: boltic.updateservice\n      with:\n        serviceId: tools.serviceId\n      inputParameters:\n      - name: serviceId\n        type: string\n        description: serviceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteservice\n      description: Boltic Delete a service\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: boltic.deleteservice\n      with:\n        serviceId: tools.serviceId\n      inputParameters:\n      - name: serviceId\n        type: string\n        description: serviceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listplugins\n      description: Boltic List all plugins\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: boltic.listplugins\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: createplugin\n      description: Boltic Create a new plugin\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: boltic.createplugin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getplugin\n      description: Boltic Get a plugin by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: boltic.getplugin\n      with:\n        pluginId: tools.pluginId\n      inputParameters:\n      - name: pluginId\n        type: string\n        description: pluginId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateplugin\n      description: Boltic Update a plugin\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: boltic.updateplugin\n      with:\n        pluginId: tools.pluginId\n      inputParameters:\n\
  \      - name: pluginId\n        type: string\n        description: pluginId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteplugin\n      description: Boltic Delete a plugin\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: boltic.deleteplugin\n      with:\n        pluginId: tools.pluginId\n      inputParameters:\n      - name: pluginId\n        type: string\n        description: pluginId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listconsumers\n      description: Boltic List all consumers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: boltic.listconsumers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createconsumer\n      description: Boltic Create a new consumer\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: boltic.createconsumer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getconsumer\n      description: Boltic Get a consumer by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: boltic.getconsumer\n      with:\n        consumerId: tools.consumerId\n      inputParameters:\n      - name: consumerId\n        type: string\n        description: consumerId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteconsumer\n      description: Boltic Delete a consumer\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: boltic.deleteconsumer\n      with:\n        consumerId: tools.consumerId\n      inputParameters:\n      - name: consumerId\n        type: string\n        description: consumerId\n        required: true\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: listcertificates\n      description: Boltic List all certificates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: boltic.listcertificates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcertificate\n      description: Boltic Upload a new certificate\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: boltic.createcertificate\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    BOLTIC_TOKEN: BOLTIC_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/boltic/refs/heads/main/capabilities/boltic-capability.yaml
tags:
- Boltic
- API
tools:
- description: Boltic List all routes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listroutes
- description: Boltic Create a new route
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createroute
- description: Boltic Get a route by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getroute
- description: Boltic Update a route
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateroute
- description: Boltic Delete a route
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteroute
- description: Boltic List all services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listservices
- description: Boltic Create a new service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createservice
- description: Boltic Get a service by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getservice
- description: Boltic Update a service
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateservice
- description: Boltic Delete a service
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteservice
- description: Boltic List all plugins
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listplugins
- description: Boltic Create a new plugin
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createplugin
- description: Boltic Get a plugin by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getplugin
- description: Boltic Update a plugin
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateplugin
- description: Boltic Delete a plugin
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteplugin
- description: Boltic List all consumers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listconsumers
- description: Boltic Create a new consumer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createconsumer
- description: Boltic Get a consumer by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconsumer
- description: Boltic Delete a consumer
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteconsumer
- description: Boltic List all certificates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcertificates
- description: Boltic Upload a new certificate
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcertificate
---
