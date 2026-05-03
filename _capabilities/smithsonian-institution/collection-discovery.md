---
categories: []
consumed_apis:
- smithsonian-open-access
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
- get available terms for search faceting
- open data
- search by subject category
- research
- get aggregate statistics about the smithsonian collections including total object counts, online media counts, and open access availability
- search collections
- search smithsonian art and design collections specifically
- get complete metadata for a specific smithsonian collection item including description, media images, provenance, and classification data
- museums
- get collection statistics and metrics
- smithsonian institution
- search smithsonian history and cultural collections
- get terms
- browse facet terms
- get available facet values for filtering searches by culture, place, object type, date, topic, or museum unit
- category-filtered search
- cultural heritage
- full-text collection search
- search by category
- get metrics
- search science and technology
- search facet terms
- education
- search across all 22 million smithsonian collection items including artworks, natural history specimens, cultural objects, and archival materials
- natural history
- search smithsonian science and technology collections
- search history and culture
- get detailed metadata for a collection item
- search across all smithsonian collections
- individual collection item
- get collection item
- search art and design
- collections
- collection statistics
- get item
- art
- get collection stats
slug: collection-discovery
source_filename: collection-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Smithsonian Collection Discovery\n  description: >-\n    Workflow capability for discovering and exploring Smithsonian Institution collections.\n    Used by researchers, educators, and developers to search across 22 million museum\n    objects, artworks, and natural history specimens, retrieve detailed metadata,\n    explore subject categories, and get collection statistics.\n  tags:\n    - Smithsonian Institution\n    - Collections\n    - Museums\n    - Open Data\n    - Cultural Heritage\n    - Research\n    - Education\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SMITHSONIAN_API_KEY: SMITHSONIAN_API_KEY\n\ncapability:\n  consumes:\n    - import: smithsonian-open-access\n      location: ./shared/open-access-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: collection-discovery-api\n      description: Unified REST API for Smithsonian collection discovery\
  \ and exploration.\n      resources:\n        - path: /v1/search\n          name: search\n          description: Full-text collection search\n          operations:\n            - method: GET\n              name: search-collections\n              description: Search across all Smithsonian collections\n              call: \"smithsonian-open-access.search-collections\"\n              with:\n                q: \"rest.q\"\n                start: \"rest.start\"\n                rows: \"rest.rows\"\n                sort: \"rest.sort\"\n                type: \"rest.type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/search/category\n          name: category-search\n          description: Category-filtered search\n          operations:\n            - method: GET\n              name: search-by-category\n              description: Search by subject category\n              call: \"smithsonian-open-access.search-by-category\"\
  \n              with:\n                q: \"rest.q\"\n                category: \"rest.category\"\n                start: \"rest.start\"\n                rows: \"rest.rows\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/items/{id}\n          name: item\n          description: Individual collection item\n          operations:\n            - method: GET\n              name: get-item\n              description: Get detailed metadata for a collection item\n              call: \"smithsonian-open-access.get-content\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/search/terms\n          name: search-terms\n          description: Search facet terms\n          operations:\n            - method: GET\n              name: get-terms\n              description: Get available terms for search faceting\n\
  \              call: \"smithsonian-open-access.get-search-terms\"\n              with:\n                category: \"rest.category\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/metrics\n          name: metrics\n          description: Collection statistics\n          operations:\n            - method: GET\n              name: get-metrics\n              description: Get collection statistics and metrics\n              call: \"smithsonian-open-access.get-metrics-stats\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: collection-discovery-mcp\n      transport: http\n      description: MCP server for AI-assisted Smithsonian collection discovery.\n      tools:\n        - name: search-collections\n          description: >-\n            Search across all 22 million Smithsonian collection items including\n        \
  \    artworks, natural history specimens, cultural objects, and archival materials\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smithsonian-open-access.search-collections\"\n          with:\n            q: \"tools.q\"\n            start: \"tools.start\"\n            rows: \"tools.rows\"\n            sort: \"tools.sort\"\n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-art-and-design\n          description: Search Smithsonian art and design collections specifically\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smithsonian-open-access.search-by-category\"\n          with:\n            q: \"tools.q\"\n            category: \"art_design\"\n            start: \"tools.start\"\n            rows: \"tools.rows\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n   \
  \     - name: search-history-and-culture\n          description: Search Smithsonian history and cultural collections\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smithsonian-open-access.search-by-category\"\n          with:\n            q: \"tools.q\"\n            category: \"history_culture\"\n            start: \"tools.start\"\n            rows: \"tools.rows\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-science-and-technology\n          description: Search Smithsonian science and technology collections\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smithsonian-open-access.search-by-category\"\n          with:\n            q: \"tools.q\"\n            category: \"science_technology\"\n            start: \"tools.start\"\n            rows: \"tools.rows\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: get-collection-item\n          description: >-\n            Get complete metadata for a specific Smithsonian collection item including\n            description, media images, provenance, and classification data\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smithsonian-open-access.get-content\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: browse-facet-terms\n          description: >-\n            Get available facet values for filtering searches by culture, place,\n            object type, date, topic, or museum unit\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smithsonian-open-access.get-search-terms\"\n          with:\n            category: \"tools.category\"\n            starts_with: \"tools.starts_with\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: get-collection-stats\n          description: >-\n            Get aggregate statistics about the Smithsonian collections including\n            total object counts, online media counts, and open access availability\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smithsonian-open-access.get-metrics-stats\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
