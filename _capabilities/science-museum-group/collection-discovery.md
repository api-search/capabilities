---
categories: []
consumed_apis:
- smg-collection
description: Unified capability for exploring and discovering artifacts, people, and documents in the Science Museum Group's collection across five UK museums. Enables researchers, educators, developers, and cultural heritage professionals to search, browse, and retrieve detailed records from over 7 million items in the world's leading science and technology museum collection.
layout: capability
name: Science Museum Group Collection Discovery
operations:
- description: Full-text search across objects, people, and documents
  method: GET
  name: search-all-collection
  path: /v1/search
- description: Search physical artifacts with museum, category, and date filters
  method: GET
  name: search-objects
  path: /v1/objects
- description: Retrieve a single object with all metadata, images, and relationships
  method: GET
  name: get-object
  path: /v1/objects/{id}
- description: Search for scientists, engineers, and historical figures
  method: GET
  name: search-people
  path: /v1/people
- description: Retrieve a single person with biographical data
  method: GET
  name: get-person
  path: /v1/people/{id}
- description: Search for documents and archive materials
  method: GET
  name: search-documents
  path: /v1/documents
- description: Retrieve a single document with metadata and archive location
  method: GET
  name: get-document
  path: /v1/documents/{id}
personas: []
provider_name: Science Museum Group
provider_slug: science-museum-group
search_terms:
- open data
- search for scientists, engineers, and historical figures
- retrieve the complete record for a specific person in the collection, including biographical information, associated objects, and image references.
- browse and search collection documents
- research
- science
- get object
- search collection
- get person
- search the science museum group's collection of 7 million items including scientific instruments, industrial machinery, railway artifacts, and cultural objects. returns matching items with images and metadata.
- history
- search for scientists, engineers, inventors, and historical figures associated with the science museum group collection. filter by occupation, birth place, and date of birth/death.
- browse and search collection people
- museums
- search documents
- retrieve a single object with all metadata, images, and relationships
- retrieve a single document with metadata and archive location
- search people
- full-text search across objects, people, and documents
- browse and search collection objects
- retrieve a single person with biographical data
- get document
- search for documents, correspondence, drawings, and archival materials in the science museum group collection. filter by creator, associated people, archive reference, and date range.
- retrieve full document record
- collections
- technology
- retrieve the complete record for a specific collection object by its id. returns full metadata including description, date, dimensions, maker, location, and high-resolution image references.
- education
- retrieve full object record
- retrieve full person record
- search specifically for physical objects and artifacts in the science museum group collection. filter by museum (science museum london, national railway museum york, science and industry museum manchester, etc.), category, maker, date range, and display status.
- search physical artifacts with museum, category, and date filters
- united kingdom
- cultural heritage
- search for documents and archive materials
- search all collection
- search objects
- retrieve the complete record for a specific document in the collection, including metadata, archive location, and image scans if available.
- search all collection types simultaneously
slug: collection-discovery
source_filename: collection-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Science Museum Group Collection Discovery\"\n  description: >-\n    Unified capability for exploring and discovering artifacts, people, and\n    documents in the Science Museum Group's collection across five UK museums.\n    Enables researchers, educators, developers, and cultural heritage professionals\n    to search, browse, and retrieve detailed records from over 7 million items\n    in the world's leading science and technology museum collection.\n  tags:\n    - Museums\n    - Collections\n    - Cultural Heritage\n    - Open Data\n    - Science\n    - History\n    - Research\n    - Education\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\ncapability:\n  consumes:\n    - import: smg-collection\n      location: ./shared/collection-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: smg-discovery-api\n      description: \"Unified REST API for Science Museum Group collection discovery.\"\n   \
  \   resources:\n        - path: /v1/search\n          name: search-all\n          description: \"Search all collection types simultaneously\"\n          operations:\n            - method: GET\n              name: search-all-collection\n              description: \"Full-text search across objects, people, and documents\"\n              call: \"smg-collection.search-all-collection\"\n              with:\n                q: \"rest.q\"\n                places: \"rest.places\"\n                images: \"rest.images\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/objects\n          name: objects\n          description: \"Browse and search collection objects\"\n          operations:\n            - method: GET\n              name: search-objects\n              description: \"Search physical artifacts with museum, category, and date filters\"\n              call: \"smg-collection.search-objects\"\n              with:\n\
  \                q: \"rest.q\"\n                type: \"rest.type\"\n                makers: \"rest.makers\"\n                museum: \"rest.museum\"\n                categories: \"rest.categories\"\n                on_display: \"rest.on_display\"\n                images: \"rest.images\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/objects/{id}\n          name: object-detail\n          description: \"Retrieve full object record\"\n          operations:\n            - method: GET\n              name: get-object\n              description: \"Retrieve a single object with all metadata, images, and relationships\"\n              call: \"smg-collection.get-object\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/people\n          name: people\n          description: \"Browse and search collection\
  \ people\"\n          operations:\n            - method: GET\n              name: search-people\n              description: \"Search for scientists, engineers, and historical figures\"\n              call: \"smg-collection.search-people\"\n              with:\n                q: \"rest.q\"\n                occupation: \"rest.occupation\"\n                places: \"rest.places\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/people/{id}\n          name: person-detail\n          description: \"Retrieve full person record\"\n          operations:\n            - method: GET\n              name: get-person\n              description: \"Retrieve a single person with biographical data\"\n              call: \"smg-collection.get-person\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/documents\n\
  \          name: documents\n          description: \"Browse and search collection documents\"\n          operations:\n            - method: GET\n              name: search-documents\n              description: \"Search for documents and archive materials\"\n              call: \"smg-collection.search-documents\"\n              with:\n                q: \"rest.q\"\n                makers: \"rest.makers\"\n                archive: \"rest.archive\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/documents/{id}\n          name: document-detail\n          description: \"Retrieve full document record\"\n          operations:\n            - method: GET\n              name: get-document\n              description: \"Retrieve a single document with metadata and archive location\"\n              call: \"smg-collection.get-document\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n \
  \               - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: smg-discovery-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Science Museum Group collection research and discovery.\"\n      tools:\n        - name: search-collection\n          description: >-\n            Search the Science Museum Group's collection of 7 million items including\n            scientific instruments, industrial machinery, railway artifacts, and cultural\n            objects. Returns matching items with images and metadata.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smg-collection.search-all-collection\"\n          with:\n            q: \"tools.q\"\n            places: \"tools.places\"\n            images: \"tools.images\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-objects\n          description: >-\n \
  \           Search specifically for physical objects and artifacts in the Science Museum\n            Group collection. Filter by museum (Science Museum London, National Railway\n            Museum York, Science and Industry Museum Manchester, etc.), category, maker,\n            date range, and display status.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smg-collection.search-objects\"\n          with:\n            q: \"tools.q\"\n            type: \"tools.type\"\n            makers: \"tools.makers\"\n            museum: \"tools.museum\"\n            categories: \"tools.categories\"\n            on_display: \"tools.on_display\"\n            images: \"tools.images\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-object\n          description: >-\n            Retrieve the complete record for a specific collection object by its ID.\n            Returns full metadata including\
  \ description, date, dimensions, maker,\n            location, and high-resolution image references.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"smg-collection.get-object\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-people\n          description: >-\n            Search for scientists, engineers, inventors, and historical figures associated\n            with the Science Museum Group collection. Filter by occupation, birth place,\n            and date of birth/death.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smg-collection.search-people\"\n          with:\n            q: \"tools.q\"\n            occupation: \"tools.occupation\"\n            birth_place: \"tools.birth_place\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n     \
  \   - name: get-person\n          description: >-\n            Retrieve the complete record for a specific person in the collection,\n            including biographical information, associated objects, and image references.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"smg-collection.get-person\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-documents\n          description: >-\n            Search for documents, correspondence, drawings, and archival materials in\n            the Science Museum Group collection. Filter by creator, associated people,\n            archive reference, and date range.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"smg-collection.search-documents\"\n          with:\n            q: \"tools.q\"\n            makers: \"tools.makers\"\n            archive:\
  \ \"tools.archive\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-document\n          description: >-\n            Retrieve the complete record for a specific document in the collection,\n            including metadata, archive location, and image scans if available.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"smg-collection.get-document\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/science-museum-group/refs/heads/main/capabilities/collection-discovery.yaml
tags:
- Museums
- Collections
- Cultural Heritage
- Open Data
- Science
- History
- Research
- Education
tools:
- description: Search the Science Museum Group's collection of 7 million items including scientific instruments, industrial machinery, railway artifacts, and cultural objects. Returns matching items with images and metadata.
  hints:
    openWorld: true
    readOnly: true
  name: search-collection
- description: Search specifically for physical objects and artifacts in the Science Museum Group collection. Filter by museum (Science Museum London, National Railway Museum York, Science and Industry Museum Manchester, etc.), category, maker, date range, and display status.
  hints:
    openWorld: true
    readOnly: true
  name: search-objects
- description: Retrieve the complete record for a specific collection object by its ID. Returns full metadata including description, date, dimensions, maker, location, and high-resolution image references.
  hints:
    idempotent: true
    readOnly: true
  name: get-object
- description: Search for scientists, engineers, inventors, and historical figures associated with the Science Museum Group collection. Filter by occupation, birth place, and date of birth/death.
  hints:
    openWorld: true
    readOnly: true
  name: search-people
- description: Retrieve the complete record for a specific person in the collection, including biographical information, associated objects, and image references.
  hints:
    idempotent: true
    readOnly: true
  name: get-person
- description: Search for documents, correspondence, drawings, and archival materials in the Science Museum Group collection. Filter by creator, associated people, archive reference, and date range.
  hints:
    openWorld: true
    readOnly: true
  name: search-documents
- description: Retrieve the complete record for a specific document in the collection, including metadata, archive location, and image scans if available.
  hints:
    idempotent: true
    readOnly: true
  name: get-document
---
