---
categories: []
consumed_apis: []
description: The Google Knowledge Graph Search API allows developers to search for entities (people, places, things) in the Google Knowledge Graph and retrieve structured data about them in JSON-LD format conforming to schema.org standards.
layout: capability
name: Google Knowledge Graph Search API
operations:
- description: Google Knowledge Graph Search Search Entities
  method: GET
  name: searchentities
  path: /entities:search
personas: []
provider_name: Google Knowledge Graph Search
provider_slug: google-knowledge-graph
search_terms:
- knowledge graph
- schema.org
- google
- knowledge
- entities
- google knowledge graph search search entities
- graph
- searchentities
- api
- semantic search
- linked data
slug: google-knowledge-graph-capability
source_filename: google-knowledge-graph-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Knowledge Graph Search API\n  description: The Google Knowledge Graph Search API allows developers to search for entities (people, places, things) in\n    the Google Knowledge Graph and retrieve structured data about them in JSON-LD format conforming to schema.org standards.\n  tags:\n  - Google\n  - Knowledge\n  - Graph\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-knowledge-graph\n    baseUri: https://kgsearch.googleapis.com/v1\n    description: Google Knowledge Graph Search API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: key\n      value: '{{GOOGLE_KNOWLEDGE_GRAPH_TOKEN}}'\n    resources:\n    - name: entities-search\n      path: /entities:search\n      operations:\n      - name: searchentities\n        method: GET\n        description: Google Knowledge Graph Search Search Entities\n        inputParameters:\n  \
  \      - name: key\n          in: query\n          type: string\n          required: true\n          description: API key.\n        - name: query\n          in: query\n          type: string\n          description: A literal string to search for in the Knowledge Graph.\n        - name: ids\n          in: query\n          type: array\n          description: A list of entity IDs to search for.\n        - name: languages\n          in: query\n          type: array\n          description: The list of language codes (ISO 639) to run the query with.\n        - name: types\n          in: query\n          type: array\n          description: Restricts returned entities to those of the specified types.\n        - name: limit\n          in: query\n          type: integer\n          description: Limits the number of entities returned (max 500, default 20).\n        - name: prefix\n          in: query\n          type: boolean\n          description: Enables prefix (substring) matching against entity\
  \ names and aliases.\n        - name: indent\n          in: query\n          type: boolean\n          description: Enables indenting of JSON results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-knowledge-graph-rest\n    description: REST adapter for Google Knowledge Graph Search API.\n    resources:\n    - path: /entities:search\n      name: searchentities\n      operations:\n      - method: GET\n        name: searchentities\n        description: Google Knowledge Graph Search Search Entities\n        call: google-knowledge-graph.searchentities\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-knowledge-graph-mcp\n    transport: http\n    description: MCP adapter for Google Knowledge Graph Search API for AI agent use.\n    tools:\n    - name: searchentities\n   \
  \   description: Google Knowledge Graph Search Search Entities\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-knowledge-graph.searchentities\n      with:\n        key: tools.key\n        query: tools.query\n        ids: tools.ids\n        languages: tools.languages\n        types: tools.types\n        limit: tools.limit\n        prefix: tools.prefix\n        indent: tools.indent\n      inputParameters:\n      - name: key\n        type: string\n        description: API key.\n        required: true\n      - name: query\n        type: string\n        description: A literal string to search for in the Knowledge Graph.\n      - name: ids\n        type: array\n        description: A list of entity IDs to search for.\n      - name: languages\n        type: array\n        description: The list of language codes (ISO 639) to run the query with.\n      - name: types\n        type: array\n        description: Restricts returned entities\
  \ to those of the specified types.\n      - name: limit\n        type: integer\n        description: Limits the number of entities returned (max 500, default 20).\n      - name: prefix\n        type: boolean\n        description: Enables prefix (substring) matching against entity names and aliases.\n      - name: indent\n        type: boolean\n        description: Enables indenting of JSON results.\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_KNOWLEDGE_GRAPH_TOKEN: GOOGLE_KNOWLEDGE_GRAPH_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-knowledge-graph/refs/heads/main/capabilities/google-knowledge-graph-capability.yaml
tags:
- Google
- Knowledge
- Graph
- API
tools:
- description: Google Knowledge Graph Search Search Entities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchentities
---
