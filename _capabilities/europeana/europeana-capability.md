---
categories: []
consumed_apis: []
description: The Europeana REST API gives programmatic access to over 50 million cultural heritage items, including books, paintings, films, museum objects, and archival records aggregated from more than 3,500 institutions across Europe. The Search API discovers records, and the Record API returns the full metadata for a specific item.
layout: capability
name: Europeana Search and Record API
operations:
- description: Search records
  method: GET
  name: searchrecords
  path: /search.json
- description: Get record
  method: GET
  name: getrecord
  path: /{datasetId}/{localId}.json
personas: []
provider_name: Europeana
provider_slug: europeana
search_terms:
- archives
- search records
- api
- europe
- libraries
- search
- getrecord
- europeana
- searchrecords
- get record
- museums
- cultural heritage
slug: europeana-capability
source_filename: europeana-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Europeana Search and Record API\n  description: The Europeana REST API gives programmatic access to over 50 million cultural heritage items, including books,\n    paintings, films, museum objects, and archival records aggregated from more than 3,500 institutions across Europe. The\n    Search API discovers records, and the Record API returns the full metadata for a specific item.\n  tags:\n  - Europeana\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: europeana\n    baseUri: https://api.europeana.eu/record/v2\n    description: Europeana Search and Record API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: wskey\n      value: '{{EUROPEANA_TOKEN}}'\n    resources:\n    - name: search-json\n      path: /search.json\n      operations:\n      - name: searchrecords\n        method: GET\n        description: Search records\n        inputParameters:\n\
  \        - name: query\n          in: query\n          type: string\n          required: true\n          description: Search query string.\n        - name: qf\n          in: query\n          type: array\n          description: Query refinement filter (repeatable).\n        - name: rows\n          in: query\n          type: integer\n          description: Number of records to return (max 100).\n        - name: start\n          in: query\n          type: integer\n        - name: profile\n          in: query\n          type: string\n          description: Response profile (minimal, standard, rich, facets).\n        - name: media\n          in: query\n          type: boolean\n        - name: thumbnail\n          in: query\n          type: boolean\n        - name: reusability\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datasetid-localid-json\n      path:\
  \ /{datasetId}/{localId}.json\n      operations:\n      - name: getrecord\n        method: GET\n        description: Get record\n        inputParameters:\n        - name: datasetId\n          in: path\n          type: string\n          required: true\n          description: Dataset identifier (collection prefix).\n        - name: localId\n          in: path\n          type: string\n          required: true\n          description: Local identifier within the dataset.\n        - name: profile\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: europeana-rest\n    description: REST adapter for Europeana Search and Record API.\n    resources:\n    - path: /search.json\n      name: searchrecords\n      operations:\n      - method: GET\n        name: searchrecords\n        description: Search records\n        call:\
  \ europeana.searchrecords\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /{datasetId}/{localId}.json\n      name: getrecord\n      operations:\n      - method: GET\n        name: getrecord\n        description: Get record\n        call: europeana.getrecord\n        with:\n          datasetId: rest.datasetId\n          localId: rest.localId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: europeana-mcp\n    transport: http\n    description: MCP adapter for Europeana Search and Record API for AI agent use.\n    tools:\n    - name: searchrecords\n      description: Search records\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: europeana.searchrecords\n      with:\n        query: tools.query\n        qf: tools.qf\n        rows: tools.rows\n        start: tools.start\n        profile: tools.profile\n        media: tools.media\n\
  \        thumbnail: tools.thumbnail\n        reusability: tools.reusability\n      inputParameters:\n      - name: query\n        type: string\n        description: Search query string.\n        required: true\n      - name: qf\n        type: array\n        description: Query refinement filter (repeatable).\n      - name: rows\n        type: integer\n        description: Number of records to return (max 100).\n      - name: start\n        type: integer\n        description: start\n      - name: profile\n        type: string\n        description: Response profile (minimal, standard, rich, facets).\n      - name: media\n        type: boolean\n        description: media\n      - name: thumbnail\n        type: boolean\n        description: thumbnail\n      - name: reusability\n        type: string\n        description: reusability\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrecord\n      description: Get record\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: europeana.getrecord\n      with:\n        datasetId: tools.datasetId\n        localId: tools.localId\n        profile: tools.profile\n      inputParameters:\n      - name: datasetId\n        type: string\n        description: Dataset identifier (collection prefix).\n        required: true\n      - name: localId\n        type: string\n        description: Local identifier within the dataset.\n        required: true\n      - name: profile\n        type: string\n        description: profile\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    EUROPEANA_TOKEN: EUROPEANA_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/europeana/refs/heads/main/capabilities/europeana-capability.yaml
tags:
- Europeana
- API
tools:
- description: Search records
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchrecords
- description: Get record
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrecord
---
