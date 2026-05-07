---
categories: []
consumed_apis: []
description: The Lumen Internet On-Demand API enables programmatic provisioning and management of internet bandwidth services. It provides access to Lumen's global fiber network, allowing customers to dynamically adjust bandwidth, manage connections, and automate network provisioning through a secure REST API using OAuth 2.0 client credentials authentication.
layout: capability
name: Lumen Internet On-Demand API
operations:
- description: List connections
  method: GET
  name: listconnections
  path: /internet-on-demand/connections
- description: Create a connection
  method: POST
  name: createconnection
  path: /internet-on-demand/connections
- description: Get connection details
  method: GET
  name: getconnection
  path: /internet-on-demand/connections/{connectionId}
- description: Update bandwidth
  method: PUT
  name: updatebandwidth
  path: /internet-on-demand/connections/{connectionId}/bandwidth
personas: []
provider_name: Lumen Technologies
provider_slug: lumen-technologies
search_terms:
- networking
- list connections
- telecom
- technologies
- api
- updatebandwidth
- get connection details
- bandwidth
- fiber
- create a connection
- infrastructure
- update bandwidth
- internet
- edge cloud
- lumen
- network
- getconnection
- listconnections
- security
- createconnection
slug: lumen-technologies-capability
source_filename: lumen-technologies-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Lumen Internet On-Demand API\n  description: The Lumen Internet On-Demand API enables programmatic provisioning and management of internet bandwidth services.\n    It provides access to Lumen's global fiber network, allowing customers to dynamically adjust bandwidth, manage connections,\n    and automate network provisioning through a secure REST API using OAuth 2.0 client credentials authentication.\n  tags:\n  - Lumen\n  - Technologies\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: lumen-technologies\n    baseUri: https://api.lumen.com\n    description: Lumen Internet On-Demand API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{LUMEN_TECHNOLOGIES_TOKEN}}'\n    resources:\n    - name: internet-on-demand-connections\n      path: /internet-on-demand/connections\n      operations:\n      - name: listconnections\n        method: GET\n        description:\
  \ List connections\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createconnection\n        method: POST\n        description: Create a connection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: internet-on-demand-connections-connectionid\n      path: /internet-on-demand/connections/{connectionId}\n      operations:\n      - name: getconnection\n        method: GET\n        description: Get connection details\n        inputParameters:\n        - name: connectionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: internet-on-demand-connections-connectionid-band\n      path: /internet-on-demand/connections/{connectionId}/bandwidth\n      operations:\n\
  \      - name: updatebandwidth\n        method: PUT\n        description: Update bandwidth\n        inputParameters:\n        - name: connectionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: lumen-technologies-rest\n    description: REST adapter for Lumen Internet On-Demand API.\n    resources:\n    - path: /internet-on-demand/connections\n      name: listconnections\n      operations:\n      - method: GET\n        name: listconnections\n        description: List connections\n        call: lumen-technologies.listconnections\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /internet-on-demand/connections\n      name: createconnection\n      operations:\n      - method: POST\n        name: createconnection\n        description: Create a connection\n\
  \        call: lumen-technologies.createconnection\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /internet-on-demand/connections/{connectionId}\n      name: getconnection\n      operations:\n      - method: GET\n        name: getconnection\n        description: Get connection details\n        call: lumen-technologies.getconnection\n        with:\n          connectionId: rest.connectionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /internet-on-demand/connections/{connectionId}/bandwidth\n      name: updatebandwidth\n      operations:\n      - method: PUT\n        name: updatebandwidth\n        description: Update bandwidth\n        call: lumen-technologies.updatebandwidth\n        with:\n          connectionId: rest.connectionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: lumen-technologies-mcp\n    transport: http\n    description:\
  \ MCP adapter for Lumen Internet On-Demand API for AI agent use.\n    tools:\n    - name: listconnections\n      description: List connections\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: lumen-technologies.listconnections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createconnection\n      description: Create a connection\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: lumen-technologies.createconnection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getconnection\n      description: Get connection details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: lumen-technologies.getconnection\n      with:\n        connectionId: tools.connectionId\n      inputParameters:\n      - name: connectionId\n        type: string\n        description: connectionId\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatebandwidth\n      description: Update bandwidth\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: lumen-technologies.updatebandwidth\n      with:\n        connectionId: tools.connectionId\n      inputParameters:\n      - name: connectionId\n        type: string\n        description: connectionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    LUMEN_TECHNOLOGIES_TOKEN: LUMEN_TECHNOLOGIES_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/lumen-technologies/refs/heads/main/capabilities/lumen-technologies-capability.yaml
tags:
- Lumen
- Technologies
- API
tools:
- description: List connections
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listconnections
- description: Create a connection
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createconnection
- description: Get connection details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconnection
- description: Update bandwidth
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatebandwidth
---
