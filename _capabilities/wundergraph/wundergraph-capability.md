---
categories: []
consumed_apis: []
description: The WunderGraph Cosmo Platform API provides programmatic access to manage federated GraphQL architectures at scale. It powers the Cosmo CLI (wgc) and Cosmo Studio, enabling management of federated graphs, subgraphs, namespaces, schema contracts, feature flags, router configurations, and API keys. The API uses Connect-RPC protocol with HTTP/JSON support. Cosmo is the open-source alternative to Apollo GraphOS for full lifecycle GraphQL federation management including schema registry, composition checks, analytics, metrics, tracing, and routing.
layout: capability
name: WunderGraph Cosmo Platform API
operations:
- description: WunderGraph List namespaces
  method: GET
  name: listnamespaces
  path: /v1/namespaces
- description: WunderGraph Create a namespace
  method: POST
  name: createnamespace
  path: /v1/namespaces
- description: WunderGraph Delete a namespace
  method: DELETE
  name: deletenamespace
  path: /v1/namespaces/{name}
- description: WunderGraph Rename a namespace
  method: POST
  name: renamenamespace
  path: /v1/namespaces/{name}/rename
- description: WunderGraph List federated graphs
  method: GET
  name: listfederatedgraphs
  path: /v1/federated-graphs
- description: WunderGraph Create a federated graph
  method: POST
  name: createfederatedgraph
  path: /v1/federated-graphs
- description: WunderGraph Get a federated graph
  method: GET
  name: getfederatedgraph
  path: /v1/federated-graphs/{name}
- description: WunderGraph Update a federated graph
  method: PUT
  name: updatefederatedgraph
  path: /v1/federated-graphs/{name}
- description: WunderGraph Delete a federated graph
  method: DELETE
  name: deletefederatedgraph
  path: /v1/federated-graphs/{name}
- description: WunderGraph Fetch federated graph SDL
  method: GET
  name: fetchfederatedgraphsdl
  path: /v1/federated-graphs/{name}/fetch
- description: WunderGraph Get federated graph changelog
  method: GET
  name: getfederatedgraphchangelog
  path: /v1/federated-graphs/{name}/changelog
- description: WunderGraph Move a federated graph to another namespace
  method: POST
  name: movefederatedgraph
  path: /v1/federated-graphs/{name}/move
- description: WunderGraph List subgraphs
  method: GET
  name: listsubgraphs
  path: /v1/subgraphs
- description: WunderGraph Create a subgraph
  method: POST
  name: createsubgraph
  path: /v1/subgraphs
- description: WunderGraph Get a subgraph
  method: GET
  name: getsubgraph
  path: /v1/subgraphs/{name}
- description: WunderGraph Update a subgraph
  method: PUT
  name: updatesubgraph
  path: /v1/subgraphs/{name}
- description: WunderGraph Delete a subgraph
  method: DELETE
  name: deletesubgraph
  path: /v1/subgraphs/{name}
- description: WunderGraph Publish a subgraph schema
  method: POST
  name: publishsubgraph
  path: /v1/subgraphs/{name}/publish
- description: WunderGraph Check a subgraph schema
  method: POST
  name: checksubgraph
  path: /v1/subgraphs/{name}/check
- description: WunderGraph Fetch subgraph SDL
  method: GET
  name: fetchsubgraphsdl
  path: /v1/subgraphs/{name}/fetch
- description: WunderGraph Move a subgraph to another namespace
  method: POST
  name: movesubgraph
  path: /v1/subgraphs/{name}/move
- description: WunderGraph List monographs
  method: GET
  name: listmonographs
  path: /v1/monographs
- description: WunderGraph Create a monograph
  method: POST
  name: createmonograph
  path: /v1/monographs
- description: WunderGraph Update a monograph
  method: PUT
  name: updatemonograph
  path: /v1/monographs/{name}
- description: WunderGraph Delete a monograph
  method: DELETE
  name: deletemonograph
  path: /v1/monographs/{name}
- description: WunderGraph Publish a monograph schema
  method: POST
  name: publishmonograph
  path: /v1/monographs/{name}/publish
- description: WunderGraph List schema contracts
  method: GET
  name: listschemacontracts
  path: /v1/schema-contracts
- description: WunderGraph Create a schema contract
  method: POST
  name: createschemacontract
  path: /v1/schema-contracts
- description: WunderGraph Create a feature subgraph
  method: POST
  name: createfeaturesubgraph
  path: /v1/feature-subgraphs
- description: WunderGraph List feature flags
  method: GET
  name: listfeatureflags
  path: /v1/feature-flags
- description: WunderGraph Create a feature flag
  method: POST
  name: createfeatureflag
  path: /v1/feature-flags
- description: WunderGraph Compose router configuration
  method: POST
  name: composerouterconfig
  path: /v1/router/compose
- description: WunderGraph List router tokens
  method: GET
  name: listroutertokens
  path: /v1/router/tokens
- description: WunderGraph Create a router token
  method: POST
  name: createroutertoken
  path: /v1/router/tokens
- description: WunderGraph List API keys
  method: GET
  name: listapikeys
  path: /v1/api-keys
- description: WunderGraph Create an API key
  method: POST
  name: createapikey
  path: /v1/api-keys
- description: WunderGraph Delete an API key
  method: DELETE
  name: deleteapikey
  path: /v1/api-keys/{name}
- description: WunderGraph Get graph analytics
  method: GET
  name: getanalytics
  path: /v1/analytics
personas: []
provider_name: WunderGraph
provider_slug: wundergraph
search_terms:
- publishsubgraph
- wundergraph fetch subgraph sdl
- createroutertoken
- wundergraph get graph analytics
- listmonographs
- wundergraph list federated graphs
- wundergraph create a subgraph
- wundergraph delete a federated graph
- getfederatedgraphchangelog
- getfederatedgraph
- createnamespace
- listnamespaces
- wundergraph list feature flags
- wundergraph list namespaces
- api
- wundergraph list schema contracts
- wundergraph create a feature flag
- deleteapikey
- movesubgraph
- federation
- wundergraph create a namespace
- movefederatedgraph
- wundergraph update a monograph
- getanalytics
- renamenamespace
- listschemacontracts
- wundergraph create a monograph
- deletefederatedgraph
- fetchsubgraphsdl
- checksubgraph
- wundergraph create an api key
- createsubgraph
- createfederatedgraph
- publishmonograph
- wundergraph create a feature subgraph
- updatefederatedgraph
- wundergraph delete a subgraph
- wundergraph create a router token
- wundergraph list monographs
- wundergraph list router tokens
- listapikeys
- wundergraph rename a namespace
- wundergraph list api keys
- wundergraph move a federated graph to another namespace
- wundergraph get federated graph changelog
- createfeatureflag
- getsubgraph
- createmonograph
- wundergraph
- createschemacontract
- wundergraph update a federated graph
- fetchfederatedgraphsdl
- wundergraph get a subgraph
- createfeaturesubgraph
- wundergraph publish a monograph schema
- updatesubgraph
- wundergraph publish a subgraph schema
- wundergraph list subgraphs
- listfederatedgraphs
- wundergraph update a subgraph
- composerouterconfig
- wundergraph create a schema contract
- listroutertokens
- deletesubgraph
- wundergraph compose router configuration
- wundergraph delete a namespace
- listfeatureflags
- wundergraph move a subgraph to another namespace
- wundergraph check a subgraph schema
- graphql
- wundergraph delete a monograph
- wundergraph create a federated graph
- listsubgraphs
- updatemonograph
- deletenamespace
- schema registry
- management
- createapikey
- wundergraph fetch federated graph sdl
- wundergraph get a federated graph
- deletemonograph
- wundergraph delete an api key
slug: wundergraph-capability
source_filename: wundergraph-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: WunderGraph Cosmo Platform API\n  description: The WunderGraph Cosmo Platform API provides programmatic access to manage federated GraphQL architectures at\n    scale. It powers the Cosmo CLI (wgc) and Cosmo Studio, enabling management of federated graphs, subgraphs, namespaces,\n    schema contracts, feature flags, router configurations, and API keys. The API uses Connect-RPC protocol with HTTP/JSON\n    support. Cosmo is the open-source alternative to Apollo GraphOS for full lifecycle GraphQL federation management including\n    schema registry, composition checks, analytics, metrics, tracing, and routing.\n  tags:\n  - Wundergraph\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: wundergraph\n    baseUri: https://cosmo-cp.wundergraph.com\n    description: WunderGraph Cosmo Platform API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name:\
  \ Authorization\n      value: '{{WUNDERGRAPH_TOKEN}}'\n    resources:\n    - name: v1-namespaces\n      path: /v1/namespaces\n      operations:\n      - name: listnamespaces\n        method: GET\n        description: WunderGraph List namespaces\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnamespace\n        method: POST\n        description: WunderGraph Create a namespace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-namespaces-name\n      path: /v1/namespaces/{name}\n      operations:\n      - name: deletenamespace\n        method: DELETE\n        description: WunderGraph Delete a namespace\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the namespace to delete.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-namespaces-name-rename\n      path: /v1/namespaces/{name}/rename\n      operations:\n      - name: renamenamespace\n        method: POST\n        description: WunderGraph Rename a namespace\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The current name of the namespace.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-federated-graphs\n      path: /v1/federated-graphs\n      operations:\n      - name: listfederatedgraphs\n        method: GET\n        description: WunderGraph List federated graphs\n        inputParameters:\n        - name: namespace\n          in: query\n          type: string\n          description: Filter by namespace name.\n        - name: limit\n          in: query\n\
  \          type: integer\n          description: Maximum number of results to return.\n        - name: offset\n          in: query\n          type: integer\n          description: Number of results to skip.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createfederatedgraph\n        method: POST\n        description: WunderGraph Create a federated graph\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-federated-graphs-name\n      path: /v1/federated-graphs/{name}\n      operations:\n      - name: getfederatedgraph\n        method: GET\n        description: WunderGraph Get a federated graph\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the federated graph.\n        - name: namespace\n          in:\
  \ query\n          type: string\n          description: The namespace of the graph.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatefederatedgraph\n        method: PUT\n        description: WunderGraph Update a federated graph\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the federated graph to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletefederatedgraph\n        method: DELETE\n        description: WunderGraph Delete a federated graph\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the federated graph to delete.\n        - name: namespace\n          in: query\n       \
  \   type: string\n          description: The namespace of the graph.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-federated-graphs-name-fetch\n      path: /v1/federated-graphs/{name}/fetch\n      operations:\n      - name: fetchfederatedgraphsdl\n        method: GET\n        description: WunderGraph Fetch federated graph SDL\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the federated graph.\n        - name: namespace\n          in: query\n          type: string\n          description: The namespace of the graph.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-federated-graphs-name-changelog\n      path: /v1/federated-graphs/{name}/changelog\n      operations:\n      - name: getfederatedgraphchangelog\n\
  \        method: GET\n        description: WunderGraph Get federated graph changelog\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the federated graph.\n        - name: namespace\n          in: query\n          type: string\n          description: The namespace of the graph.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-federated-graphs-name-move\n      path: /v1/federated-graphs/{name}/move\n      operations:\n      - name: movefederatedgraph\n        method: POST\n        description: WunderGraph Move a federated graph to another namespace\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the federated graph to move.\n        outputRawFormat: json\n        outputParameters:\n    \
  \    - name: result\n          type: object\n          value: $.\n    - name: v1-subgraphs\n      path: /v1/subgraphs\n      operations:\n      - name: listsubgraphs\n        method: GET\n        description: WunderGraph List subgraphs\n        inputParameters:\n        - name: namespace\n          in: query\n          type: string\n          description: Filter by namespace name.\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of results to return.\n        - name: offset\n          in: query\n          type: integer\n          description: Number of results to skip.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsubgraph\n        method: POST\n        description: WunderGraph Create a subgraph\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: v1-subgraphs-name\n      path: /v1/subgraphs/{name}\n      operations:\n      - name: getsubgraph\n        method: GET\n        description: WunderGraph Get a subgraph\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the subgraph.\n        - name: namespace\n          in: query\n          type: string\n          description: The namespace of the subgraph.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatesubgraph\n        method: PUT\n        description: WunderGraph Update a subgraph\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the subgraph to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: deletesubgraph\n        method: DELETE\n        description: WunderGraph Delete a subgraph\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the subgraph to delete.\n        - name: namespace\n          in: query\n          type: string\n          description: The namespace of the subgraph.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-subgraphs-name-publish\n      path: /v1/subgraphs/{name}/publish\n      operations:\n      - name: publishsubgraph\n        method: POST\n        description: WunderGraph Publish a subgraph schema\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the subgraph to publish.\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n    - name: v1-subgraphs-name-check\n      path: /v1/subgraphs/{name}/check\n      operations:\n      - name: checksubgraph\n        method: POST\n        description: WunderGraph Check a subgraph schema\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the subgraph to check.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-subgraphs-name-fetch\n      path: /v1/subgraphs/{name}/fetch\n      operations:\n      - name: fetchsubgraphsdl\n        method: GET\n        description: WunderGraph Fetch subgraph SDL\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the subgraph.\n        - name: namespace\n          in: query\n       \
  \   type: string\n          description: The namespace of the subgraph.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-subgraphs-name-move\n      path: /v1/subgraphs/{name}/move\n      operations:\n      - name: movesubgraph\n        method: POST\n        description: WunderGraph Move a subgraph to another namespace\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the subgraph to move.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-monographs\n      path: /v1/monographs\n      operations:\n      - name: listmonographs\n        method: GET\n        description: WunderGraph List monographs\n        inputParameters:\n        - name: namespace\n          in: query\n          type: string\n        \
  \  description: Filter by namespace name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createmonograph\n        method: POST\n        description: WunderGraph Create a monograph\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-monographs-name\n      path: /v1/monographs/{name}\n      operations:\n      - name: updatemonograph\n        method: PUT\n        description: WunderGraph Update a monograph\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the monograph to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemonograph\n        method: DELETE\n        description: WunderGraph Delete a monograph\n\
  \        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the monograph to delete.\n        - name: namespace\n          in: query\n          type: string\n          description: The namespace of the monograph.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-monographs-name-publish\n      path: /v1/monographs/{name}/publish\n      operations:\n      - name: publishmonograph\n        method: POST\n        description: WunderGraph Publish a monograph schema\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the monograph to publish.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-schema-contracts\n      path:\
  \ /v1/schema-contracts\n      operations:\n      - name: listschemacontracts\n        method: GET\n        description: WunderGraph List schema contracts\n        inputParameters:\n        - name: namespace\n          in: query\n          type: string\n          description: Filter by namespace name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createschemacontract\n        method: POST\n        description: WunderGraph Create a schema contract\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-feature-subgraphs\n      path: /v1/feature-subgraphs\n      operations:\n      - name: createfeaturesubgraph\n        method: POST\n        description: WunderGraph Create a feature subgraph\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: v1-feature-flags\n      path: /v1/feature-flags\n      operations:\n      - name: listfeatureflags\n        method: GET\n        description: WunderGraph List feature flags\n        inputParameters:\n        - name: namespace\n          in: query\n          type: string\n          description: Filter by namespace name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createfeatureflag\n        method: POST\n        description: WunderGraph Create a feature flag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-router-compose\n      path: /v1/router/compose\n      operations:\n      - name: composerouterconfig\n        method: POST\n        description: WunderGraph Compose router configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: v1-router-tokens\n      path: /v1/router/tokens\n      operations:\n      - name: listroutertokens\n        method: GET\n        description: WunderGraph List router tokens\n        inputParameters:\n        - name: federatedGraphName\n          in: query\n          type: string\n          required: true\n          description: The name of the federated graph.\n        - name: namespace\n          in: query\n          type: string\n          description: The namespace of the graph.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createroutertoken\n        method: POST\n        description: WunderGraph Create a router token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-api-keys\n      path: /v1/api-keys\n      operations:\n      - name: listapikeys\n      \
  \  method: GET\n        description: WunderGraph List API keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapikey\n        method: POST\n        description: WunderGraph Create an API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-api-keys-name\n      path: /v1/api-keys/{name}\n      operations:\n      - name: deleteapikey\n        method: DELETE\n        description: WunderGraph Delete an API key\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: The name of the API key to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-analytics\n      path: /v1/analytics\n      operations:\n      - name: getanalytics\n\
  \        method: GET\n        description: WunderGraph Get graph analytics\n        inputParameters:\n        - name: federatedGraphName\n          in: query\n          type: string\n          required: true\n          description: The name of the federated graph.\n        - name: namespace\n          in: query\n          type: string\n          description: The namespace of the graph.\n        - name: startDate\n          in: query\n          type: string\n          description: Start of the analytics time range.\n        - name: endDate\n          in: query\n          type: string\n          description: End of the analytics time range.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: wundergraph-rest\n    description: REST adapter for WunderGraph Cosmo Platform API.\n    resources:\n    - path: /v1/namespaces\n      name: listnamespaces\n      operations:\n\
  \      - method: GET\n        name: listnamespaces\n        description: WunderGraph List namespaces\n        call: wundergraph.listnamespaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/namespaces\n      name: createnamespace\n      operations:\n      - method: POST\n        name: createnamespace\n        description: WunderGraph Create a namespace\n        call: wundergraph.createnamespace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/namespaces/{name}\n      name: deletenamespace\n      operations:\n      - method: DELETE\n        name: deletenamespace\n        description: WunderGraph Delete a namespace\n        call: wundergraph.deletenamespace\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/namespaces/{name}/rename\n      name: renamenamespace\n      operations:\n      - method: POST\n        name: renamenamespace\n\
  \        description: WunderGraph Rename a namespace\n        call: wundergraph.renamenamespace\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/federated-graphs\n      name: listfederatedgraphs\n      operations:\n      - method: GET\n        name: listfederatedgraphs\n        description: WunderGraph List federated graphs\n        call: wundergraph.listfederatedgraphs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/federated-graphs\n      name: createfederatedgraph\n      operations:\n      - method: POST\n        name: createfederatedgraph\n        description: WunderGraph Create a federated graph\n        call: wundergraph.createfederatedgraph\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/federated-graphs/{name}\n      name: getfederatedgraph\n      operations:\n      - method: GET\n        name: getfederatedgraph\n\
  \        description: WunderGraph Get a federated graph\n        call: wundergraph.getfederatedgraph\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/federated-graphs/{name}\n      name: updatefederatedgraph\n      operations:\n      - method: PUT\n        name: updatefederatedgraph\n        description: WunderGraph Update a federated graph\n        call: wundergraph.updatefederatedgraph\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/federated-graphs/{name}\n      name: deletefederatedgraph\n      operations:\n      - method: DELETE\n        name: deletefederatedgraph\n        description: WunderGraph Delete a federated graph\n        call: wundergraph.deletefederatedgraph\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/federated-graphs/{name}/fetch\n\
  \      name: fetchfederatedgraphsdl\n      operations:\n      - method: GET\n        name: fetchfederatedgraphsdl\n        description: WunderGraph Fetch federated graph SDL\n        call: wundergraph.fetchfederatedgraphsdl\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/federated-graphs/{name}/changelog\n      name: getfederatedgraphchangelog\n      operations:\n      - method: GET\n        name: getfederatedgraphchangelog\n        description: WunderGraph Get federated graph changelog\n        call: wundergraph.getfederatedgraphchangelog\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/federated-graphs/{name}/move\n      name: movefederatedgraph\n      operations:\n      - method: POST\n        name: movefederatedgraph\n        description: WunderGraph Move a federated graph to another namespace\n        call: wundergraph.movefederatedgraph\n\
  \        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subgraphs\n      name: listsubgraphs\n      operations:\n      - method: GET\n        name: listsubgraphs\n        description: WunderGraph List subgraphs\n        call: wundergraph.listsubgraphs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subgraphs\n      name: createsubgraph\n      operations:\n      - method: POST\n        name: createsubgraph\n        description: WunderGraph Create a subgraph\n        call: wundergraph.createsubgraph\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subgraphs/{name}\n      name: getsubgraph\n      operations:\n      - method: GET\n        name: getsubgraph\n        description: WunderGraph Get a subgraph\n        call: wundergraph.getsubgraph\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/subgraphs/{name}\n      name: updatesubgraph\n      operations:\n      - method: PUT\n        name: updatesubgraph\n        description: WunderGraph Update a subgraph\n        call: wundergraph.updatesubgraph\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subgraphs/{name}\n      name: deletesubgraph\n      operations:\n      - method: DELETE\n        name: deletesubgraph\n        description: WunderGraph Delete a subgraph\n        call: wundergraph.deletesubgraph\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subgraphs/{name}/publish\n      name: publishsubgraph\n      operations:\n      - method: POST\n        name: publishsubgraph\n        description: WunderGraph Publish a subgraph schema\n        call: wundergraph.publishsubgraph\n        with:\n          name: rest.name\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subgraphs/{name}/check\n      name: checksubgraph\n      operations:\n      - method: POST\n        name: checksubgraph\n        description: WunderGraph Check a subgraph schema\n        call: wundergraph.checksubgraph\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subgraphs/{name}/fetch\n      name: fetchsubgraphsdl\n      operations:\n      - method: GET\n        name: fetchsubgraphsdl\n        description: WunderGraph Fetch subgraph SDL\n        call: wundergraph.fetchsubgraphsdl\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subgraphs/{name}/move\n      name: movesubgraph\n      operations:\n      - method: POST\n        name: movesubgraph\n        description: WunderGraph Move a subgraph to another namespace\n        call:\
  \ wundergraph.movesubgraph\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/monographs\n      name: listmonographs\n      operations:\n      - method: GET\n        name: listmonographs\n        description: WunderGraph List monographs\n        call: wundergraph.listmonographs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/monographs\n      name: createmonograph\n      operations:\n      - method: POST\n        name: createmonograph\n        description: WunderGraph Create a monograph\n        call: wundergraph.createmonograph\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/monographs/{name}\n      name: updatemonograph\n      operations:\n      - method: PUT\n        name: updatemonograph\n        description: WunderGraph Update a monograph\n        call: wundergraph.updatemonograph\n        with:\n          name: rest.name\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/monographs/{name}\n      name: deletemonograph\n      operations:\n      - method: DELETE\n        name: deletemonograph\n        description: WunderGraph Delete a monograph\n        call: wundergraph.deletemonograph\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/monographs/{name}/publish\n      name: publishmonograph\n      operations:\n      - method: POST\n        name: publishmonograph\n        description: WunderGraph Publish a monograph schema\n        call: wundergraph.publishmonograph\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/schema-contracts\n      name: listschemacontracts\n      operations:\n      - method: GET\n        name: listschemacontracts\n        description: WunderGraph List schema contracts\n        call:\
  \ wundergraph.listschemacontracts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/schema-contracts\n      name: createschemacontract\n      operations:\n      - method: POST\n        name: createschemacontract\n        description: WunderGraph Create a schema contract\n        call: wundergraph.createschemacontract\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/feature-subgraphs\n      name: createfeaturesubgraph\n      operations:\n      - method: POST\n        name: createfeaturesubgraph\n        description: WunderGraph Create a feature subgraph\n        call: wundergraph.createfeaturesubgraph\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/feature-flags\n      name: listfeatureflags\n      operations:\n      - method: GET\n        name: listfeatureflags\n        description: WunderGraph List feature flags\n        call: wundergraph.listfeatureflags\n   \
  \     outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/feature-flags\n      name: createfeatureflag\n      operations:\n      - method: POST\n        name: createfeatureflag\n        description: WunderGraph Create a feature flag\n        call: wundergraph.createfeatureflag\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/router/compose\n      name: composerouterconfig\n      operations:\n      - method: POST\n        name: composerouterconfig\n        description: WunderGraph Compose router configuration\n        call: wundergraph.composerouterconfig\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/router/tokens\n      name: listroutertokens\n      operations:\n      - method: GET\n        name: listroutertokens\n        description: WunderGraph List router tokens\n        call: wundergraph.listroutertokens\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/router/tokens\n      name: createroutertoken\n      operations:\n      - method: POST\n        name: createroutertoken\n        description: WunderGraph Create a router token\n        call: wundergraph.createroutertoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/api-keys\n      name: listapikeys\n      operations:\n      - method: GET\n        name: listapikeys\n        description: WunderGraph List API keys\n        call: wundergraph.listapikeys\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/api-keys\n      name: createapikey\n      operations:\n      - method: POST\n        name: createapikey\n        description: WunderGraph Create an API key\n        call: wundergraph.createapikey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/api-keys/{name}\n      name: deleteapikey\n      operations:\n      - method: DELETE\n        name: deleteapikey\n\
  \        description: WunderGraph Delete an API key\n        call: wundergraph.deleteapikey\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analytics\n      name: getanalytics\n      operations:\n      - method: GET\n        name: getanalytics\n        description: WunderGraph Get graph analytics\n        call: wundergraph.getanalytics\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: wundergraph-mcp\n    transport: http\n    description: MCP adapter for WunderGraph Cosmo Platform API for AI agent use.\n    tools:\n    - name: listnamespaces\n      description: WunderGraph List namespaces\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: wundergraph.listnamespaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnamespace\n      description:\
  \ WunderGraph Create a namespace\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: wundergraph.createnamespace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletenamespace\n      description: WunderGraph Delete a namespace\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: wundergraph.deletenamespace\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n        type: string\n        description: The name of the namespace to delete.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: renamenamespace\n      description: WunderGraph Rename a namespace\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: wundergraph.renamenamespace\n      with:\n        name: tools.name\n      inputParameters:\n      - name: name\n\
  \        type: string\n        description: The current name of the namespace.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfederatedgraphs\n      description: WunderGraph List federated graphs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: wundergraph.listfederatedgraphs\n      with:\n        namespace: tools.namespace\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: namespace\n        type: string\n        description: Filter by namespace name.\n      - name: limit\n        type: integer\n        description: Maximum number of results to return.\n      - name: offset\n        type: integer\n        description:\n\n# --- truncated at 32 KB (46 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/wundergraph/refs/heads/main/capabilities/wundergraph-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/wundergraph/refs/heads/main/capabilities/wundergraph-capability.yaml
tags:
- Wundergraph
- API
tools:
- description: WunderGraph List namespaces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnamespaces
- description: WunderGraph Create a namespace
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnamespace
- description: WunderGraph Delete a namespace
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletenamespace
- description: WunderGraph Rename a namespace
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: renamenamespace
- description: WunderGraph List federated graphs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfederatedgraphs
- description: WunderGraph Create a federated graph
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfederatedgraph
- description: WunderGraph Get a federated graph
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfederatedgraph
- description: WunderGraph Update a federated graph
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatefederatedgraph
- description: WunderGraph Delete a federated graph
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletefederatedgraph
- description: WunderGraph Fetch federated graph SDL
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetchfederatedgraphsdl
- description: WunderGraph Get federated graph changelog
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfederatedgraphchangelog
- description: WunderGraph Move a federated graph to another namespace
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: movefederatedgraph
- description: WunderGraph List subgraphs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsubgraphs
- description: WunderGraph Create a subgraph
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsubgraph
- description: WunderGraph Get a subgraph
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsubgraph
- description: WunderGraph Update a subgraph
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatesubgraph
- description: WunderGraph Delete a subgraph
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesubgraph
- description: WunderGraph Publish a subgraph schema
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: publishsubgraph
- description: WunderGraph Check a subgraph schema
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: checksubgraph
- description: WunderGraph Fetch subgraph SDL
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: fetchsubgraphsdl
- description: WunderGraph Move a subgraph to another namespace
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: movesubgraph
- description: WunderGraph List monographs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmonographs
- description: WunderGraph Create a monograph
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmonograph
- description: WunderGraph Update a monograph
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatemonograph
- description: WunderGraph Delete a monograph
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemonograph
- description: WunderGraph Publish a monograph schema
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: publishmonograph
- description: WunderGraph List schema contracts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listschemacontracts
- description: WunderGraph Create a schema contract
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createschemacontract
- description: WunderGraph Create a feature subgraph
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfeaturesubgraph
- description: WunderGraph List feature flags
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfeatureflags
- description: WunderGraph Create a feature flag
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfeatureflag
- description: WunderGraph Compose router configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: composerouterconfig
- description: WunderGraph List router tokens
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listroutertokens
- description: WunderGraph Create a router token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createroutertoken
- description: WunderGraph List API keys
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapikeys
- description: WunderGraph Create an API key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapikey
- description: WunderGraph Delete an API key
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapikey
- description: WunderGraph Get graph analytics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getanalytics
---
