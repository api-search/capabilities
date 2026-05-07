---
categories: []
consumed_apis: []
description: The Orbital Query API allows developers to submit TaxiQL queries to the Orbital data gateway for integrating, transforming, and discovering data across APIs, databases, event streams, and other data sources. Queries are written in TaxiQL, a technology-agnostic query language, and submitted to the /api/taxiql endpoint. Results can be returned as a single JSON batch or streamed via Server-Sent Events. Orbital automatically orchestrates the required data fetching across connected services based on semantic type metadata in your API specs.
layout: capability
name: Orbital Query API
operations:
- description: Orbital Submit a TaxiQL query
  method: POST
  name: submittaxiqlquery
  path: /api/taxiql
- description: Orbital List schemas
  method: GET
  name: listschemas
  path: /api/schemas
- description: Orbital List connected services
  method: GET
  name: listservices
  path: /api/services
- description: Orbital List data source connections
  method: GET
  name: listconnections
  path: /api/connections
- description: Orbital Create a data source connection
  method: POST
  name: createconnection
  path: /api/connections
- description: Orbital Get a data source connection
  method: GET
  name: getconnection
  path: /api/connections/{connectionId}
- description: Orbital Delete a data source connection
  method: DELETE
  name: deleteconnection
  path: /api/connections/{connectionId}
- description: Orbital List registered types
  method: GET
  name: listtypes
  path: /api/types
- description: Orbital List cache configurations
  method: GET
  name: listcaches
  path: /api/caches
personas: []
provider_name: Orbital
provider_slug: orbital
search_terms:
- listtypes
- orbital get a data source connection
- submittaxiqlquery
- api
- listcaches
- gateways
- orbital delete a data source connection
- orbital list schemas
- orbital list data source connections
- orbital create a data source connection
- orbital submit a taxiql query
- orbital list connected services
- listservices
- listschemas
- orbital
- getconnection
- orbital list cache configurations
- data
- listconnections
- orbital list registered types
- createconnection
- deleteconnection
slug: orbital-capability
source_filename: orbital-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Orbital Query API\n  description: The Orbital Query API allows developers to submit TaxiQL queries to the Orbital data gateway for integrating,\n    transforming, and discovering data across APIs, databases, event streams, and other data sources. Queries are written\n    in TaxiQL, a technology-agnostic query language, and submitted to the /api/taxiql endpoint. Results can be returned as\n    a single JSON batch or streamed via Server-Sent Events. Orbital automatically orchestrates the required data fetching\n    across connected services based on semantic type metadata in your API specs.\n  tags:\n  - Orbital\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: orbital\n    baseUri: https://localhost:9022\n    description: Orbital Query API HTTP API.\n    resources:\n    - name: api-taxiql\n      path: /api/taxiql\n      operations:\n      - name: submittaxiqlquery\n   \
  \     method: POST\n        description: Orbital Submit a TaxiQL query\n        inputParameters:\n        - name: resultMode\n          in: query\n          type: string\n          description: Controls how type metadata is included in the response. Set to TYPED to include type metadata with\n            results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-schemas\n      path: /api/schemas\n      operations:\n      - name: listschemas\n        method: GET\n        description: Orbital List schemas\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-services\n      path: /api/services\n      operations:\n      - name: listservices\n        method: GET\n        description: Orbital List connected services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: api-connections\n      path: /api/connections\n      operations:\n      - name: listconnections\n        method: GET\n        description: Orbital List data source connections\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createconnection\n        method: POST\n        description: Orbital Create a data source connection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-connections-connectionid\n      path: /api/connections/{connectionId}\n      operations:\n      - name: getconnection\n        method: GET\n        description: Orbital Get a data source connection\n        inputParameters:\n        - name: connectionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: deleteconnection\n        method: DELETE\n        description: Orbital Delete a data source connection\n        inputParameters:\n        - name: connectionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-types\n      path: /api/types\n      operations:\n      - name: listtypes\n        method: GET\n        description: Orbital List registered types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-caches\n      path: /api/caches\n      operations:\n      - name: listcaches\n        method: GET\n        description: Orbital List cache configurations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: orbital-rest\n    description: REST adapter for Orbital Query API.\n    resources:\n    - path: /api/taxiql\n      name: submittaxiqlquery\n      operations:\n      - method: POST\n        name: submittaxiqlquery\n        description: Orbital Submit a TaxiQL query\n        call: orbital.submittaxiqlquery\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/schemas\n      name: listschemas\n      operations:\n      - method: GET\n        name: listschemas\n        description: Orbital List schemas\n        call: orbital.listschemas\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/services\n      name: listservices\n      operations:\n      - method: GET\n        name: listservices\n        description: Orbital List connected services\n        call: orbital.listservices\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /api/connections\n      name: listconnections\n      operations:\n      - method: GET\n        name: listconnections\n        description: Orbital List data source connections\n        call: orbital.listconnections\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/connections\n      name: createconnection\n      operations:\n      - method: POST\n        name: createconnection\n        description: Orbital Create a data source connection\n        call: orbital.createconnection\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/connections/{connectionId}\n      name: getconnection\n      operations:\n      - method: GET\n        name: getconnection\n        description: Orbital Get a data source connection\n        call: orbital.getconnection\n        with:\n          connectionId: rest.connectionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/connections/{connectionId}\n\
  \      name: deleteconnection\n      operations:\n      - method: DELETE\n        name: deleteconnection\n        description: Orbital Delete a data source connection\n        call: orbital.deleteconnection\n        with:\n          connectionId: rest.connectionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/types\n      name: listtypes\n      operations:\n      - method: GET\n        name: listtypes\n        description: Orbital List registered types\n        call: orbital.listtypes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/caches\n      name: listcaches\n      operations:\n      - method: GET\n        name: listcaches\n        description: Orbital List cache configurations\n        call: orbital.listcaches\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: orbital-mcp\n    transport: http\n    description: MCP adapter for\
  \ Orbital Query API for AI agent use.\n    tools:\n    - name: submittaxiqlquery\n      description: Orbital Submit a TaxiQL query\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: orbital.submittaxiqlquery\n      with:\n        resultMode: tools.resultMode\n      inputParameters:\n      - name: resultMode\n        type: string\n        description: Controls how type metadata is included in the response. Set to TYPED to include type metadata with results.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listschemas\n      description: Orbital List schemas\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orbital.listschemas\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listservices\n      description: Orbital List connected services\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: orbital.listservices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listconnections\n      description: Orbital List data source connections\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orbital.listconnections\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createconnection\n      description: Orbital Create a data source connection\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: orbital.createconnection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getconnection\n      description: Orbital Get a data source connection\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orbital.getconnection\n      with:\n        connectionId: tools.connectionId\n      inputParameters:\n      - name: connectionId\n\
  \        type: string\n        description: connectionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteconnection\n      description: Orbital Delete a data source connection\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: orbital.deleteconnection\n      with:\n        connectionId: tools.connectionId\n      inputParameters:\n      - name: connectionId\n        type: string\n        description: connectionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtypes\n      description: Orbital List registered types\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: orbital.listtypes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcaches\n      description: Orbital List cache configurations\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: orbital.listcaches\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/orbital/refs/heads/main/capabilities/orbital-capability.yaml
tags:
- Orbital
- API
tools:
- description: Orbital Submit a TaxiQL query
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submittaxiqlquery
- description: Orbital List schemas
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listschemas
- description: Orbital List connected services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listservices
- description: Orbital List data source connections
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listconnections
- description: Orbital Create a data source connection
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createconnection
- description: Orbital Get a data source connection
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconnection
- description: Orbital Delete a data source connection
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteconnection
- description: Orbital List registered types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtypes
- description: Orbital List cache configurations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcaches
---
