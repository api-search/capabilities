---
categories: []
consumed_apis: []
description: Nacos Open API for service discovery, configuration management, and namespace management. Nacos supports dynamic service discovery, service configuration, service metadata, and traffic management.
layout: capability
name: Nacos Open API
operations:
- description: User login
  method: POST
  name: login
  path: /v1/auth/login
- description: Get configuration
  method: GET
  name: getconfig
  path: /v1/cs/configs
- description: Publish configuration
  method: POST
  name: publishconfig
  path: /v1/cs/configs
- description: Delete configuration
  method: DELETE
  name: deleteconfig
  path: /v1/cs/configs
- description: Listen for configuration changes
  method: POST
  name: listenconfig
  path: /v1/cs/configs/listener
- description: Get configuration history
  method: GET
  name: getconfighistory
  path: /v1/cs/history
- description: Get previous configuration version
  method: GET
  name: getpreviousconfig
  path: /v1/cs/history/previous
- description: Register an instance
  method: POST
  name: registerinstance
  path: /v1/ns/instance
- description: Deregister an instance
  method: DELETE
  name: deregisterinstance
  path: /v1/ns/instance
- description: Update instance
  method: PUT
  name: updateinstance
  path: /v1/ns/instance
- description: List instances
  method: GET
  name: listinstances
  path: /v1/ns/instance/list
- description: Send instance heartbeat
  method: PUT
  name: sendbeat
  path: /v1/ns/instance/beat
- description: Create a service
  method: POST
  name: createservice
  path: /v1/ns/service
- description: Delete a service
  method: DELETE
  name: deleteservice
  path: /v1/ns/service
- description: Update a service
  method: PUT
  name: updateservice
  path: /v1/ns/service
- description: Get a service
  method: GET
  name: getservice
  path: /v1/ns/service
- description: List services
  method: GET
  name: listservices
  path: /v1/ns/service/list
- description: Get system switches
  method: GET
  name: getswitches
  path: /v1/ns/operator/switches
- description: Update system switches
  method: PUT
  name: updateswitches
  path: /v1/ns/operator/switches
- description: Get server metrics
  method: GET
  name: getmetrics
  path: /v1/ns/operator/metrics
- description: List cluster servers
  method: GET
  name: listservers
  path: /v1/ns/operator/servers
- description: List namespaces
  method: GET
  name: listnamespaces
  path: /v1/console/namespaces
- description: Create a namespace
  method: POST
  name: createnamespace
  path: /v1/console/namespaces
- description: Update a namespace
  method: PUT
  name: updatenamespace
  path: /v1/console/namespaces
- description: Delete a namespace
  method: DELETE
  name: deletenamespace
  path: /v1/console/namespaces
- description: Update instance health status
  method: PUT
  name: updateinstancehealth
  path: /v1/ns/health/instance
personas: []
provider_name: Nacos
provider_slug: nacos
search_terms:
- get previous configuration version
- get configuration history
- send instance heartbeat
- list services
- getswitches
- updateinstance
- list cluster servers
- getconfighistory
- deleteconfig
- service management
- getservice
- deletenamespace
- api
- getpreviousconfig
- deregisterinstance
- listservers
- updateswitches
- create a namespace
- getconfig
- cloud native
- java
- publishconfig
- registerinstance
- update system switches
- delete a namespace
- login
- updateservice
- list instances
- sendbeat
- deregister an instance
- update a namespace
- get configuration
- configuration management
- listen for configuration changes
- nacos
- service discovery
- update instance health status
- user login
- updateinstancehealth
- register an instance
- update instance
- updatenamespace
- createnamespace
- create a service
- get a service
- getmetrics
- list namespaces
- publish configuration
- get system switches
- dns
- delete a service
- update a service
- listnamespaces
- listinstances
- delete configuration
- createservice
- deleteservice
- get server metrics
- alibaba
- microservices
- listservices
- listenconfig
slug: nacos-capability
source_filename: nacos-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Nacos Open API\n  description: Nacos Open API for service discovery, configuration management, and namespace management. Nacos supports dynamic\n    service discovery, service configuration, service metadata, and traffic management.\n  tags:\n  - Nacos\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: nacos\n    baseUri: http://localhost:8848/nacos\n    description: Nacos Open API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: accessToken\n      value: '{{NACOS_TOKEN}}'\n    resources:\n    - name: v1-auth-login\n      path: /v1/auth/login\n      operations:\n      - name: login\n        method: POST\n        description: User login\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-cs-configs\n      path: /v1/cs/configs\n      operations:\n   \
  \   - name: getconfig\n        method: GET\n        description: Get configuration\n        inputParameters:\n        - name: dataId\n          in: query\n          type: string\n          required: true\n          description: Configuration ID\n        - name: group\n          in: query\n          type: string\n          required: true\n          description: Configuration group\n        - name: tenant\n          in: query\n          type: string\n          description: Tenant/namespace ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: publishconfig\n        method: POST\n        description: Publish configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteconfig\n        method: DELETE\n        description: Delete configuration\n        inputParameters:\n        - name: dataId\n        \
  \  in: query\n          type: string\n          required: true\n        - name: group\n          in: query\n          type: string\n          required: true\n        - name: tenant\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-cs-configs-listener\n      path: /v1/cs/configs/listener\n      operations:\n      - name: listenconfig\n        method: POST\n        description: Listen for configuration changes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-cs-history\n      path: /v1/cs/history\n      operations:\n      - name: getconfighistory\n        method: GET\n        description: Get configuration history\n        inputParameters:\n        - name: dataId\n          in: query\n          type: string\n          required: true\n        - name: group\n  \
  \        in: query\n          type: string\n          required: true\n        - name: tenant\n          in: query\n          type: string\n        - name: pageNo\n          in: query\n          type: integer\n        - name: pageSize\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-cs-history-previous\n      path: /v1/cs/history/previous\n      operations:\n      - name: getpreviousconfig\n        method: GET\n        description: Get previous configuration version\n        inputParameters:\n        - name: id\n          in: query\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ns-instance\n      path: /v1/ns/instance\n      operations:\n      - name: registerinstance\n        method: POST\n        description:\
  \ Register an instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deregisterinstance\n        method: DELETE\n        description: Deregister an instance\n        inputParameters:\n        - name: serviceName\n          in: query\n          type: string\n          required: true\n        - name: groupName\n          in: query\n          type: string\n        - name: namespaceId\n          in: query\n          type: string\n        - name: ip\n          in: query\n          type: string\n          required: true\n        - name: port\n          in: query\n          type: integer\n          required: true\n        - name: clusterName\n          in: query\n          type: string\n        - name: ephemeral\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateinstance\n\
  \        method: PUT\n        description: Update instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ns-instance-list\n      path: /v1/ns/instance/list\n      operations:\n      - name: listinstances\n        method: GET\n        description: List instances\n        inputParameters:\n        - name: serviceName\n          in: query\n          type: string\n          required: true\n        - name: groupName\n          in: query\n          type: string\n        - name: namespaceId\n          in: query\n          type: string\n        - name: clusters\n          in: query\n          type: string\n          description: Comma-separated cluster names\n        - name: healthyOnly\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ns-instance-beat\n      path:\
  \ /v1/ns/instance/beat\n      operations:\n      - name: sendbeat\n        method: PUT\n        description: Send instance heartbeat\n        inputParameters:\n        - name: serviceName\n          in: query\n          type: string\n          required: true\n        - name: groupName\n          in: query\n          type: string\n        - name: namespaceId\n          in: query\n          type: string\n        - name: beat\n          in: query\n          type: string\n          required: true\n          description: Beat info (JSON string)\n        - name: ephemeral\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ns-service\n      path: /v1/ns/service\n      operations:\n      - name: createservice\n        method: POST\n        description: Create a service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n      - name: deleteservice\n        method: DELETE\n        description: Delete a service\n        inputParameters:\n        - name: serviceName\n          in: query\n          type: string\n          required: true\n        - name: groupName\n          in: query\n          type: string\n        - name: namespaceId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateservice\n        method: PUT\n        description: Update a service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getservice\n        method: GET\n        description: Get a service\n        inputParameters:\n        - name: serviceName\n          in: query\n          type: string\n          required: true\n        - name: groupName\n          in: query\n\
  \          type: string\n        - name: namespaceId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ns-service-list\n      path: /v1/ns/service/list\n      operations:\n      - name: listservices\n        method: GET\n        description: List services\n        inputParameters:\n        - name: pageNo\n          in: query\n          type: integer\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n          required: true\n        - name: groupName\n          in: query\n          type: string\n        - name: namespaceId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ns-operator-switches\n      path: /v1/ns/operator/switches\n      operations:\n      - name: getswitches\n\
  \        method: GET\n        description: Get system switches\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateswitches\n        method: PUT\n        description: Update system switches\n        inputParameters:\n        - name: entry\n          in: query\n          type: string\n          required: true\n          description: Switch entry key\n        - name: value\n          in: query\n          type: string\n          required: true\n          description: Switch entry value\n        - name: debug\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ns-operator-metrics\n      path: /v1/ns/operator/metrics\n      operations:\n      - name: getmetrics\n        method: GET\n        description: Get server metrics\n        outputRawFormat: json\n       \
  \ outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ns-operator-servers\n      path: /v1/ns/operator/servers\n      operations:\n      - name: listservers\n        method: GET\n        description: List cluster servers\n        inputParameters:\n        - name: healthy\n          in: query\n          type: boolean\n          description: Filter by health status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-console-namespaces\n      path: /v1/console/namespaces\n      operations:\n      - name: listnamespaces\n        method: GET\n        description: List namespaces\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnamespace\n        method: POST\n        description: Create a namespace\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: updatenamespace\n        method: PUT\n        description: Update a namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletenamespace\n        method: DELETE\n        description: Delete a namespace\n        inputParameters:\n        - name: namespaceId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-ns-health-instance\n      path: /v1/ns/health/instance\n      operations:\n      - name: updateinstancehealth\n        method: PUT\n        description: Update instance health status\n        inputParameters:\n        - name: serviceName\n          in: query\n          type: string\n          required: true\n        - name: groupName\n        \
  \  in: query\n          type: string\n        - name: namespaceId\n          in: query\n          type: string\n        - name: ip\n          in: query\n          type: string\n          required: true\n        - name: port\n          in: query\n          type: integer\n          required: true\n        - name: healthy\n          in: query\n          type: boolean\n          required: true\n        - name: clusterName\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: nacos-rest\n    description: REST adapter for Nacos Open API.\n    resources:\n    - path: /v1/auth/login\n      name: login\n      operations:\n      - method: POST\n        name: login\n        description: User login\n        call: nacos.login\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cs/configs\n\
  \      name: getconfig\n      operations:\n      - method: GET\n        name: getconfig\n        description: Get configuration\n        call: nacos.getconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cs/configs\n      name: publishconfig\n      operations:\n      - method: POST\n        name: publishconfig\n        description: Publish configuration\n        call: nacos.publishconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cs/configs\n      name: deleteconfig\n      operations:\n      - method: DELETE\n        name: deleteconfig\n        description: Delete configuration\n        call: nacos.deleteconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cs/configs/listener\n      name: listenconfig\n      operations:\n      - method: POST\n        name: listenconfig\n        description: Listen for configuration changes\n        call: nacos.listenconfig\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cs/history\n      name: getconfighistory\n      operations:\n      - method: GET\n        name: getconfighistory\n        description: Get configuration history\n        call: nacos.getconfighistory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cs/history/previous\n      name: getpreviousconfig\n      operations:\n      - method: GET\n        name: getpreviousconfig\n        description: Get previous configuration version\n        call: nacos.getpreviousconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ns/instance\n      name: registerinstance\n      operations:\n      - method: POST\n        name: registerinstance\n        description: Register an instance\n        call: nacos.registerinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ns/instance\n      name:\
  \ deregisterinstance\n      operations:\n      - method: DELETE\n        name: deregisterinstance\n        description: Deregister an instance\n        call: nacos.deregisterinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ns/instance\n      name: updateinstance\n      operations:\n      - method: PUT\n        name: updateinstance\n        description: Update instance\n        call: nacos.updateinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ns/instance/list\n      name: listinstances\n      operations:\n      - method: GET\n        name: listinstances\n        description: List instances\n        call: nacos.listinstances\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ns/instance/beat\n      name: sendbeat\n      operations:\n      - method: PUT\n        name: sendbeat\n        description: Send instance heartbeat\n        call: nacos.sendbeat\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ns/service\n      name: createservice\n      operations:\n      - method: POST\n        name: createservice\n        description: Create a service\n        call: nacos.createservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ns/service\n      name: deleteservice\n      operations:\n      - method: DELETE\n        name: deleteservice\n        description: Delete a service\n        call: nacos.deleteservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ns/service\n      name: updateservice\n      operations:\n      - method: PUT\n        name: updateservice\n        description: Update a service\n        call: nacos.updateservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ns/service\n      name: getservice\n      operations:\n      - method: GET\n        name:\
  \ getservice\n        description: Get a service\n        call: nacos.getservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ns/service/list\n      name: listservices\n      operations:\n      - method: GET\n        name: listservices\n        description: List services\n        call: nacos.listservices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ns/operator/switches\n      name: getswitches\n      operations:\n      - method: GET\n        name: getswitches\n        description: Get system switches\n        call: nacos.getswitches\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ns/operator/switches\n      name: updateswitches\n      operations:\n      - method: PUT\n        name: updateswitches\n        description: Update system switches\n        call: nacos.updateswitches\n        outputParameters:\n        - type: object\n          mapping: $.\n  \
  \  - path: /v1/ns/operator/metrics\n      name: getmetrics\n      operations:\n      - method: GET\n        name: getmetrics\n        description: Get server metrics\n        call: nacos.getmetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ns/operator/servers\n      name: listservers\n      operations:\n      - method: GET\n        name: listservers\n        description: List cluster servers\n        call: nacos.listservers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/console/namespaces\n      name: listnamespaces\n      operations:\n      - method: GET\n        name: listnamespaces\n        description: List namespaces\n        call: nacos.listnamespaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/console/namespaces\n      name: createnamespace\n      operations:\n      - method: POST\n        name: createnamespace\n        description: Create a\
  \ namespace\n        call: nacos.createnamespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/console/namespaces\n      name: updatenamespace\n      operations:\n      - method: PUT\n        name: updatenamespace\n        description: Update a namespace\n        call: nacos.updatenamespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/console/namespaces\n      name: deletenamespace\n      operations:\n      - method: DELETE\n        name: deletenamespace\n        description: Delete a namespace\n        call: nacos.deletenamespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ns/health/instance\n      name: updateinstancehealth\n      operations:\n      - method: PUT\n        name: updateinstancehealth\n        description: Update instance health status\n        call: nacos.updateinstancehealth\n        outputParameters:\n        - type: object\n     \
  \     mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: nacos-mcp\n    transport: http\n    description: MCP adapter for Nacos Open API for AI agent use.\n    tools:\n    - name: login\n      description: User login\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nacos.login\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getconfig\n      description: Get configuration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nacos.getconfig\n      with:\n        dataId: tools.dataId\n        group: tools.group\n        tenant: tools.tenant\n      inputParameters:\n      - name: dataId\n        type: string\n        description: Configuration ID\n        required: true\n      - name: group\n        type: string\n        description: Configuration group\n        required: true\n      - name: tenant\n        type: string\n        description:\
  \ Tenant/namespace ID\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publishconfig\n      description: Publish configuration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nacos.publishconfig\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteconfig\n      description: Delete configuration\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: nacos.deleteconfig\n      with:\n        dataId: tools.dataId\n        group: tools.group\n        tenant: tools.tenant\n      inputParameters:\n      - name: dataId\n        type: string\n        description: dataId\n        required: true\n      - name: group\n        type: string\n        description: group\n        required: true\n      - name: tenant\n        type: string\n        description: tenant\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: listenconfig\n      description: Listen for configuration changes\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nacos.listenconfig\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getconfighistory\n      description: Get configuration history\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nacos.getconfighistory\n      with:\n        dataId: tools.dataId\n        group: tools.group\n        tenant: tools.tenant\n        pageNo: tools.pageNo\n        pageSize: tools.pageSize\n      inputParameters:\n      - name: dataId\n        type: string\n        description: dataId\n        required: true\n      - name: group\n        type: string\n        description: group\n        required: true\n      - name: tenant\n        type: string\n        description: tenant\n      - name: pageNo\n        type: integer\n        description:\
  \ pageNo\n      - name: pageSize\n        type: integer\n        description: pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpreviousconfig\n      description: Get previous configuration version\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nacos.getpreviousconfig\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: registerinstance\n      description: Register an instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nacos.registerinstance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deregisterinstance\n      description: Deregister an instance\n      hints:\n        readOnly: false\n        destructive: true\n \
  \       idempotent: true\n      call: nacos.deregisterinstance\n      with:\n        serviceName: tools.serviceName\n        groupName: tools.groupName\n        namespaceId: tools.namespaceId\n        ip: tools.ip\n        port: tools.port\n        clusterName: tools.clusterName\n        ephemeral: tools.ephemeral\n      inputParameters:\n      - name: serviceName\n        type: string\n        description: serviceName\n        required: true\n      - name: groupName\n        type: string\n        description: groupName\n      - name: namespaceId\n        type: string\n        description: namespaceId\n      - name: ip\n        type: string\n        description: ip\n        required: true\n      - name: port\n        type: integer\n        description: port\n        required: true\n      - name: clusterName\n        type: string\n        description: clusterName\n      - name: ephemeral\n        type: boolean\n        description: ephemeral\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: updateinstance\n      description: Update instance\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: nacos.updateinstance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listinstances\n      description: List instances\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nacos.listinstances\n      with:\n        serviceName: tools.serviceName\n        groupName: tools.groupName\n        namespaceId: tools.namespaceId\n        clusters: tools.clusters\n        healthyOnly: tools.healthyOnly\n      inputParameters:\n      - name: serviceName\n        type: string\n        description: serviceName\n        required: true\n      - name: groupName\n        type: string\n        description: groupName\n      - name: namespaceId\n        type: string\n        description: namespaceId\n      - name: clusters\n        type:\
  \ string\n        description: Comma-separated cluster names\n      - name: healthyOnly\n        type: boolean\n        description: healthyOnly\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sendbeat\n      description: Send instance heartbeat\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: nacos.sendbeat\n      with:\n        serviceName: tools.serviceName\n        groupName: tools.groupName\n        namespaceId: tools.namespaceId\n        beat: tools.beat\n        ephemeral: tools.ephemeral\n      inputParameters:\n      - name: serviceName\n        type: string\n        description: serviceName\n        required: true\n      - name: groupName\n        type: string\n        description: groupName\n      - name: namespaceId\n        type: string\n        description: namespaceId\n      - name: beat\n        type: string\n        description: Beat info (JSON string)\n        required: true\n  \
  \    - name: ephemeral\n        type: boolean\n        description: ephemeral\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createservice\n      description: Create a service\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nacos.createservice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteservice\n      description: Delete a service\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: nacos.deleteservice\n      with:\n        serviceName: tools.serviceName\n        groupName: tools.groupName\n        namespaceId: tools.namespaceId\n      inputParameters:\n      - name: serviceName\n        type: string\n        description: serviceName\n        required: true\n      - name: groupName\n        type: string\n        description: groupName\n      - name: namespaceId\n        type: string\n        description:\
  \ namespaceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateservice\n      description: Update a service\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: nacos.updateservice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getservice\n      description: Get a service\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nacos.getservice\n      with:\n        serviceName: tools.serviceName\n        groupName: tools.groupName\n        namespaceId: tools.namespaceId\n      inputParameters:\n      - name: serviceName\n        type: string\n        description: serviceName\n        required: true\n      - name: groupName\n        type: string\n        description: groupName\n      - name: namespaceId\n        type: string\n        description: namespaceId\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: listservices\n      description: List services\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nacos.listservices\n      with:\n        pageNo: tools.pageNo\n        pageSize: tools.pageSize\n        groupName: tools.groupName\n        namespaceId: tools.namespaceId\n      inputParameters:\n      - name: pageNo\n        type: integer\n        description: pageNo\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n        required: true\n      - name: groupName\n        type: string\n        description: groupName\n      - name: namespaceId\n        type: string\n        description: namespaceId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getswitches\n      description: Get system switches\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nacos.getswitches\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: updateswitches\n      description: Update system switches\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: nacos.updateswitches\n      with:\n        entry: tools.entry\n        value: tools.value\n        debug: tools.debug\n      inputParameters:\n      - name: entry\n        type: string\n        description: Switch entry key\n        required: true\n      - name: value\n        type: string\n        description: Switch entry value\n        required: true\n      - name: debug\n        type: boolean\n        description: debug\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmetrics\n      description: Get server metrics\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nacos.getmetrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listservers\n    \
  \  description: List cluster servers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nacos.listservers\n      with:\n        healthy: tools.healthy\n      inputParameters:\n      - name: healthy\n        type: boolean\n        description: Filter by health status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnamespaces\n      description: List namespaces\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nacos.listnamespaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnamespace\n      description: Create a namespace\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: nacos.createnamespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatenamespace\n      description: Update a namespace\n      hints:\n    \
  \    readOnly: false\n        destructive: false\n        idempotent: true\n      call: nacos.updatenamespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletenamespace\n      description: Delete a namespace\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: nacos.deletenamespace\n      with:\n        namespaceId: tools.namespaceId\n      inputParameters:\n      - name: namespaceId\n        type: string\n        description: namespaceId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateinstancehealth\n      description: Update instance health status\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: nacos.updateinstancehealth\n      with:\n        serviceName: tools.serviceName\n        groupName: tools.groupName\n        namespaceId: tools.namespaceId\n        ip: tools.ip\n     \
  \   port: tools.port\n        healthy: tools.healthy\n        clusterName: tools.clusterName\n      inputParameters:\n      - name: serviceName\n        type: string\n        description: serviceName\n        required: true\n      - name: groupName\n        type: string\n        description: groupName\n      - name: namespaceId\n        type: string\n        description: namespaceId\n      - name: ip\n        type: string\n        description: ip\n        required: true\n      - name: port\n        type: integer\n        description: port\n        required: true\n      - name: healthy\n        type: boolean\n        description: healthy\n        required: true\n      - name: clusterName\n        type: string\n        description: clusterName\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    NACOS_TOKEN: NACOS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/nacos/refs/heads/main/capabilities/nacos-capability.yaml
tags:
- Nacos
- API
tools:
- description: User login
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: login
- description: Get configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconfig
- description: Publish configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: publishconfig
- description: Delete configuration
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteconfig
- description: Listen for configuration changes
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listenconfig
- description: Get configuration history
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconfighistory
- description: Get previous configuration version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpreviousconfig
- description: Register an instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: registerinstance
- description: Deregister an instance
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deregisterinstance
- description: Update instance
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateinstance
- description: List instances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinstances
- description: Send instance heartbeat
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: sendbeat
- description: Create a service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createservice
- description: Delete a service
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteservice
- description: Update a service
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateservice
- description: Get a service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getservice
- description: List services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listservices
- description: Get system switches
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getswitches
- description: Update system switches
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateswitches
- description: Get server metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmetrics
- description: List cluster servers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listservers
- description: List namespaces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnamespaces
- description: Create a namespace
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnamespace
- description: Update a namespace
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatenamespace
- description: Delete a namespace
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletenamespace
- description: Update instance health status
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateinstancehealth
---
