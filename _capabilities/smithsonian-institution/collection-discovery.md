---
categories: []
consumed_apis: []
description: Workflow capability for discovering and exploring Smithsonian Institution collections. Used by researchers, educators, and developers to search across 22 million museum objects, artworks, and natural history specimens, retrieve detailed metadata, explore subject categories, and get collection statistics.
layout: capability
name: Smithsonian Collection Discovery
operations:
- description: Search across all Smithsonian collections
  method: GET
  name: search-collections
  path: /v1/search
- description: Search by subject category
  method: GET
  name: search-by-category
  path: /v1/search/category
- description: Get detailed metadata for a collection item
  method: GET
  name: get-item
  path: /v1/items/{id}
- description: Get available terms for search faceting
  method: GET
  name: get-terms
  path: /v1/search/terms
- description: Get collection statistics and metrics
  method: GET
  name: get-metrics
  path: /v1/metrics
personas: []
provider_name: Smithsonian Institution
provider_slug: smithsonian-institution
search_terms:
- search smithsonian history and cultural collections
- get terms
- get collection statistics and metrics
- search across all 22 million smithsonian collection items including artworks, natural history specimens, cultural objects, and archival materials
- get collection stats
- search art and design
- search smithsonian science and technology collections
- get complete metadata for a specific smithsonian collection item including description, media images, provenance, and classification data
- search science and technology
- get collection item
- search facet terms
- get detailed metadata for a collection item
- get available terms for search faceting
- smithsonian institution
- museums
- get available facet values for filtering searches by culture, place, object type, date, topic, or museum unit
- browse facet terms
- search by subject category
- research
- search history and culture
- category-filtered search
- full-text collection search
- get aggregate statistics about the smithsonian collections including total object counts, online media counts, and open access availability
- get metrics
- search by category
- cultural heritage
- search collections
- search smithsonian art and design collections specifically
- education
- art
- natural history
- collection statistics
- get item
- collections
- individual collection item
- open data
- search across all smithsonian collections
slug: collection-discovery
source_filename: collection-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Smithsonian Collection Discovery\n  description: Workflow capability for discovering and exploring Smithsonian Institution collections. Used by researchers,\n    educators, and developers to search across 22 million museum objects, artworks, and natural history specimens, retrieve\n    detailed metadata, explore subject categories, and get collection statistics.\n  tags:\n  - Smithsonian Institution\n  - Collections\n  - Museums\n  - Open Data\n  - Cultural Heritage\n  - Research\n  - Education\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SMITHSONIAN_API_KEY: SMITHSONIAN_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: smithsonian-open-access\n    baseUri: https://edan.si.edu/openaccess\n    description: Smithsonian Open Access API for collection data retrieval\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{SMITHSONIAN_API_KEY}}'\n      placement:\
  \ query\n    resources:\n    - name: content\n      path: /api/content\n      description: Individual collection item retrieval\n      operations:\n      - name: get-content\n        method: GET\n        description: Get detailed metadata for a specific collection item by ID\n        inputParameters:\n        - name: id\n          in: query\n          type: string\n          required: true\n          description: Unique identifier of the collection item\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /api/search/search\n      description: Full-text collection search\n      operations:\n      - name: search-collections\n        method: GET\n        description: Search across all Smithsonian collections\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: Search query\n        - name: start\n\
  \          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: rows\n          in: query\n          type: integer\n          required: false\n          description: Number of results\n        - name: sort\n          in: query\n          type: string\n          required: false\n          description: Sort order (relevancy, id, newest, updated, random)\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Record type filter (edanmdm, ead_collection, all)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: category-search\n      path: /api/search/category_search\n      description: Category-filtered collection search\n      operations:\n      - name: search-by-category\n        method: GET\n        description: Search collections filtered by subject category\n        inputParameters:\n\
  \        - name: q\n          in: query\n          type: string\n          required: true\n          description: Search query\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Category (art_design, history_culture, science_technology)\n        - name: start\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: rows\n          in: query\n          type: integer\n          required: false\n          description: Number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: terms\n      path: /api/search/terms\n      description: Search facet terms\n      operations:\n      - name: get-search-terms\n        method: GET\n        description: Get available facet terms for a category\n        inputParameters:\n        - name: category\n          in:\
  \ query\n          type: string\n          required: true\n          description: Facet category (culture, date, object_type, topic, place, etc.)\n        - name: starts_with\n          in: query\n          type: string\n          required: false\n          description: Filter terms by starting character\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics\n      path: /api/metrics/stats\n      description: Collection metrics and statistics\n      operations:\n      - name: get-metrics-stats\n        method: GET\n        description: Get aggregate statistics about the Smithsonian collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: collection-discovery-api\n    description: Unified REST API for Smithsonian collection discovery and exploration.\n    resources:\n\
  \    - path: /v1/search\n      name: search\n      description: Full-text collection search\n      operations:\n      - method: GET\n        name: search-collections\n        description: Search across all Smithsonian collections\n        call: smithsonian-open-access.search-collections\n        with:\n          q: rest.q\n          start: rest.start\n          rows: rest.rows\n          sort: rest.sort\n          type: rest.type\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search/category\n      name: category-search\n      description: Category-filtered search\n      operations:\n      - method: GET\n        name: search-by-category\n        description: Search by subject category\n        call: smithsonian-open-access.search-by-category\n        with:\n          q: rest.q\n          category: rest.category\n          start: rest.start\n          rows: rest.rows\n        outputParameters:\n        - type: object\n          mapping: $.\n \
  \   - path: /v1/items/{id}\n      name: item\n      description: Individual collection item\n      operations:\n      - method: GET\n        name: get-item\n        description: Get detailed metadata for a collection item\n        call: smithsonian-open-access.get-content\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search/terms\n      name: search-terms\n      description: Search facet terms\n      operations:\n      - method: GET\n        name: get-terms\n        description: Get available terms for search faceting\n        call: smithsonian-open-access.get-search-terms\n        with:\n          category: rest.category\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics\n      name: metrics\n      description: Collection statistics\n      operations:\n      - method: GET\n        name: get-metrics\n        description: Get collection statistics and metrics\n\
  \        call: smithsonian-open-access.get-metrics-stats\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: collection-discovery-mcp\n    transport: http\n    description: MCP server for AI-assisted Smithsonian collection discovery.\n    tools:\n    - name: search-collections\n      description: Search across all 22 million Smithsonian collection items including artworks, natural history specimens,\n        cultural objects, and archival materials\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smithsonian-open-access.search-collections\n      with:\n        q: tools.q\n        start: tools.start\n        rows: tools.rows\n        sort: tools.sort\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-art-and-design\n      description: Search Smithsonian art and design collections specifically\n      hints:\n        readOnly: true\n\
  \        openWorld: true\n      call: smithsonian-open-access.search-by-category\n      with:\n        q: tools.q\n        category: art_design\n        start: tools.start\n        rows: tools.rows\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-history-and-culture\n      description: Search Smithsonian history and cultural collections\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smithsonian-open-access.search-by-category\n      with:\n        q: tools.q\n        category: history_culture\n        start: tools.start\n        rows: tools.rows\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-science-and-technology\n      description: Search Smithsonian science and technology collections\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smithsonian-open-access.search-by-category\n      with:\n        q: tools.q\n        category: science_technology\n    \
  \    start: tools.start\n        rows: tools.rows\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-collection-item\n      description: Get complete metadata for a specific Smithsonian collection item including description, media images, provenance,\n        and classification data\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smithsonian-open-access.get-content\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: browse-facet-terms\n      description: Get available facet values for filtering searches by culture, place, object type, date, topic, or museum\n        unit\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smithsonian-open-access.get-search-terms\n      with:\n        category: tools.category\n        starts_with: tools.starts_with\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-collection-stats\n\
  \      description: Get aggregate statistics about the Smithsonian collections including total object counts, online media\n        counts, and open access availability\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smithsonian-open-access.get-metrics-stats\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/smithsonian-institution/refs/heads/main/capabilities/collection-discovery.yaml
tags:
- Smithsonian Institution
- Collections
- Museums
- Open Data
- Cultural Heritage
- Research
- Education
tools:
- description: Search across all 22 million Smithsonian collection items including artworks, natural history specimens, cultural objects, and archival materials
  hints:
    openWorld: true
    readOnly: true
  name: search-collections
- description: Search Smithsonian art and design collections specifically
  hints:
    openWorld: true
    readOnly: true
  name: search-art-and-design
- description: Search Smithsonian history and cultural collections
  hints:
    openWorld: true
    readOnly: true
  name: search-history-and-culture
- description: Search Smithsonian science and technology collections
  hints:
    openWorld: true
    readOnly: true
  name: search-science-and-technology
- description: Get complete metadata for a specific Smithsonian collection item including description, media images, provenance, and classification data
  hints:
    openWorld: true
    readOnly: true
  name: get-collection-item
- description: Get available facet values for filtering searches by culture, place, object type, date, topic, or museum unit
  hints:
    openWorld: true
    readOnly: true
  name: browse-facet-terms
- description: Get aggregate statistics about the Smithsonian collections including total object counts, online media counts, and open access availability
  hints:
    openWorld: true
    readOnly: true
  name: get-collection-stats
---
