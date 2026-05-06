---
categories: []
consumed_apis: []
description: Workflow for enriching content with NYT semantic metadata and tags. Combines the Semantic API and TimesTags API to support knowledge graph construction, entity resolution, and metadata classification workflows. Used by data teams, NLP engineers, and editorial teams standardizing entity metadata.
layout: capability
name: NYT Metadata Enrichment
operations:
- description: Get full concept metadata including links, taxonomy, and article associations.
  method: GET
  name: get-concept-by-name
  path: /v1/concepts/{concept-type}/{specific-concept}
- description: Search concepts by substring across all concept types.
  method: GET
  name: search-concepts
  path: /v1/concepts/search
personas: []
provider_name: The New York Times
provider_slug: the-new-york-times
search_terms:
- get full concept metadata including links, taxonomy, and article associations.
- books
- movies
- search nyt controlled vocabulary concepts.
- publishing
- new york times
- get concept by name
- look up a specific nyt concept by type and name.
- news
- look up a specific nyt concept (person, place, organization, or descriptor) by type and exact name to get full metadata including taxonomy, geocodes, and related articles.
- journalism
- search the nyt controlled vocabulary by substring to find people (nytd_per), places (nytd_geo), organizations (nytd_org), or descriptors (nytd_des).
- entities
- media
- search concepts
- search concepts by substring across all concept types.
- semantic
- metadata
- articles
- knowledge graph
slug: metadata-enrichment
source_filename: metadata-enrichment.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: NYT Metadata Enrichment\n  description: Workflow for enriching content with NYT semantic metadata and tags. Combines the Semantic API and TimesTags\n    API to support knowledge graph construction, entity resolution, and metadata classification workflows. Used by data teams,\n    NLP engineers, and editorial teams standardizing entity metadata.\n  tags:\n  - New York Times\n  - Metadata\n  - Semantic\n  - Entities\n  - Knowledge Graph\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    NYT_API_KEY: NYT_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: nyt-semantic\n    baseUri: https://api.nytimes.com/svc/semantic/v2/concept\n    description: NYT Semantic API providing access to the NYT controlled vocabulary of concepts.\n    authentication:\n      type: apikey\n      key: api-key\n      value: '{{NYT_API_KEY}}'\n      placement: query\n    resources:\n    - name: concept-by-name\n\
  \      path: /name/{concept-type}/{specific-concept}.json\n      description: Get a specific concept by its type and name.\n      operations:\n      - name: get-concept-by-name\n        method: GET\n        description: Look up a specific NYT concept by its type and name.\n        inputParameters:\n        - name: concept-type\n          in: path\n          type: string\n          required: true\n          description: 'Concept type: nytd_geo, nytd_per, nytd_org, nytd_des.'\n        - name: specific-concept\n          in: path\n          type: string\n          required: true\n          description: The specific concept name (e.g., Baseball, Obama Barack).\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated optional fields to include in the response.\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Search term string.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: concept-search\n      path: /search.json\n      description: Search across all NYT concepts by substring.\n      operations:\n      - name: search-concepts\n        method: GET\n        description: Search the NYT concept vocabulary by query substring.\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Search term to match against concept names.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Starting index for pagination (up to 10 results per page).\n        - name: fields\n          in: query\n          type: string\n          required: false\n          description: Comma-separated optional fields to include in the response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: nyt-metadata-enrichment-api\n    description: Unified REST API for NYT metadata enrichment using the controlled vocabulary.\n    resources:\n    - path: /v1/concepts/{concept-type}/{specific-concept}\n      name: concept-by-name\n      description: Look up a specific NYT concept by type and name.\n      operations:\n      - method: GET\n        name: get-concept-by-name\n        description: Get full concept metadata including links, taxonomy, and article associations.\n        call: nyt-semantic.get-concept-by-name\n        with:\n          concept-type: rest.concept-type\n          specific-concept: rest.specific-concept\n          fields: rest.fields\n          query: rest.query\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/concepts/search\n      name: concept-search\n      description: Search NYT controlled vocabulary concepts.\n    \
  \  operations:\n      - method: GET\n        name: search-concepts\n        description: Search concepts by substring across all concept types.\n        call: nyt-semantic.search-concepts\n        with:\n          query: rest.query\n          offset: rest.offset\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9092\n    namespace: nyt-metadata-enrichment-mcp\n    transport: http\n    description: MCP server for AI-assisted semantic metadata enrichment using the NYT controlled vocabulary.\n    tools:\n    - name: get-concept-by-name\n      description: Look up a specific NYT concept (person, place, organization, or descriptor) by type and exact name to get\n        full metadata including taxonomy, geocodes, and related articles.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nyt-semantic.get-concept-by-name\n      with:\n        concept-type: tools.concept-type\n        specific-concept: tools.specific-concept\n\
  \        fields: tools.fields\n        query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-concepts\n      description: Search the NYT controlled vocabulary by substring to find people (nytd_per), places (nytd_geo), organizations\n        (nytd_org), or descriptors (nytd_des).\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nyt-semantic.search-concepts\n      with:\n        query: tools.query\n        offset: tools.offset\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/the-new-york-times/refs/heads/main/capabilities/metadata-enrichment.yaml
tags:
- New York Times
- Metadata
- Semantic
- Entities
- Knowledge Graph
tools:
- description: Look up a specific NYT concept (person, place, organization, or descriptor) by type and exact name to get full metadata including taxonomy, geocodes, and related articles.
  hints:
    idempotent: true
    readOnly: true
  name: get-concept-by-name
- description: Search the NYT controlled vocabulary by substring to find people (nytd_per), places (nytd_geo), organizations (nytd_org), or descriptors (nytd_des).
  hints:
    idempotent: true
    readOnly: true
  name: search-concepts
---
