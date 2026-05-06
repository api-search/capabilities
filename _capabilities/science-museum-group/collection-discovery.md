---
categories: []
consumed_apis: []
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
- full-text search across objects, people, and documents
- search for scientists, engineers, inventors, and historical figures associated with the science museum group collection. filter by occupation, birth place, and date of birth/death.
- retrieve a single document with metadata and archive location
- search for documents, correspondence, drawings, and archival materials in the science museum group collection. filter by creator, associated people, archive reference, and date range.
- education
- research
- search for scientists, engineers, and historical figures
- browse and search collection objects
- get document
- cultural heritage
- get person
- browse and search collection documents
- search the science museum group's collection of 7 million items including scientific instruments, industrial machinery, railway artifacts, and cultural objects. returns matching items with images and metadata.
- search all collection types simultaneously
- retrieve the complete record for a specific person in the collection, including biographical information, associated objects, and image references.
- retrieve full document record
- collections
- retrieve full object record
- history
- browse and search collection people
- search documents
- search all collection
- search physical artifacts with museum, category, and date filters
- united kingdom
- retrieve full person record
- search collection
- technology
- search specifically for physical objects and artifacts in the science museum group collection. filter by museum (science museum london, national railway museum york, science and industry museum manchester, etc.), category, maker, date range, and display status.
- retrieve the complete record for a specific document in the collection, including metadata, archive location, and image scans if available.
- retrieve the complete record for a specific collection object by its id. returns full metadata including description, date, dimensions, maker, location, and high-resolution image references.
- retrieve a single object with all metadata, images, and relationships
- science
- search people
- get object
- museums
- open data
- search for documents and archive materials
- retrieve a single person with biographical data
- search objects
slug: collection-discovery
source_filename: collection-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Science Museum Group Collection Discovery\n  description: Unified capability for exploring and discovering artifacts, people, and documents in the Science Museum Group's\n    collection across five UK museums. Enables researchers, educators, developers, and cultural heritage professionals to\n    search, browse, and retrieve detailed records from over 7 million items in the world's leading science and technology\n    museum collection.\n  tags:\n  - Museums\n  - Collections\n  - Cultural Heritage\n  - Open Data\n  - Science\n  - History\n  - Research\n  - Education\n  created: '2026-05-02'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: smg-collection\n    baseUri: https://collection.sciencemuseumgroup.org.uk\n    description: Science Museum Group Collection API - open access, no authentication required\n    resources:\n    - name: search-all\n      path: /search\n      description: Full-text and filtered\
  \ search across all collection types\n      operations:\n      - name: search-all-collection\n        method: GET\n        description: Search all objects, people, and documents in the collection\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Full-text search query term\n        - name: page[number]\n          in: query\n          type: integer\n          required: false\n          description: Zero-indexed page number\n        - name: page[size]\n          in: query\n          type: integer\n          required: false\n          description: Results per page (max 100)\n        - name: date[from]\n          in: query\n          type: string\n          required: false\n          description: Filter from date\n        - name: date[to]\n          in: query\n          type: string\n          required: false\n          description: Filter to date\n        - name: places\n          in: query\n      \
  \    type: string\n          required: false\n          description: Filter by geographical association\n        - name: images\n          in: query\n          type: boolean\n          required: false\n          description: Filter to items with images\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-objects\n      path: /search/objects\n      description: Search physical objects and artifacts in the collection\n      operations:\n      - name: search-objects\n        method: GET\n        description: Search collection objects with filtering by type, maker, museum, category, and display status\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Object type filter\n        -\
  \ name: makers\n          in: query\n          type: string\n          required: false\n          description: Filter by maker or manufacturer\n        - name: museum\n          in: query\n          type: string\n          required: false\n          description: Filter by museum code (NRM, SMG, NMeM, MSI)\n        - name: on_display\n          in: query\n          type: boolean\n          required: false\n          description: Filter to objects on display\n        - name: categories\n          in: query\n          type: string\n          required: false\n          description: Filter by collection category\n        - name: places\n          in: query\n          type: string\n          required: false\n          description: Filter by geographical association\n        - name: images\n          in: query\n          type: boolean\n          required: false\n          description: Filter to objects with images\n        - name: page[number]\n          in: query\n          type: integer\n \
  \         required: false\n          description: Zero-indexed page number\n        - name: page[size]\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-people\n      path: /search/people\n      description: Search people associated with the museum collections\n      operations:\n      - name: search-people\n        method: GET\n        description: Search for scientists, engineers, makers and historical figures in the collection\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query\n        - name: occupation\n          in: query\n          type: string\n          required: false\n          description: Filter by occupation\n        - name: birth[place]\n          in: query\n   \
  \       type: string\n          required: false\n          description: Filter by birth place\n        - name: birth[date]\n          in: query\n          type: string\n          required: false\n          description: Filter by birth date\n        - name: places\n          in: query\n          type: string\n          required: false\n          description: Filter by geographical association\n        - name: page[number]\n          in: query\n          type: integer\n          required: false\n          description: Zero-indexed page number\n        - name: page[size]\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-documents\n      path: /search/documents\n      description: Search documents and archives in the collection\n      operations:\n      - name: search-documents\n  \
  \      method: GET\n        description: Search for documents, archives, and written records\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query\n        - name: makers\n          in: query\n          type: string\n          required: false\n          description: Filter by document creator\n        - name: people\n          in: query\n          type: string\n          required: false\n          description: Filter by associated person\n        - name: archive\n          in: query\n          type: string\n          required: false\n          description: Filter by archive reference\n        - name: page[number]\n          in: query\n          type: integer\n          required: false\n          description: Zero-indexed page number\n        - name: page[size]\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: objects\n      path: /objects/{id}\n      description: Retrieve individual collection objects by ID\n      operations:\n      - name: get-object\n        method: GET\n        description: Retrieve a single collection object with full metadata, images, and relationships\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Collection object identifier (e.g., co26704)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: people\n      path: /people/{id}\n      description: Retrieve individual person records by ID\n      operations:\n      - name: get-person\n        method: GET\n        description: Retrieve a single person record with biographical data and image references\n        inputParameters:\n   \
  \     - name: id\n          in: path\n          type: string\n          required: true\n          description: Person identifier (e.g., cp22644)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents\n      path: /documents/{id}\n      description: Retrieve individual document records by ID\n      operations:\n      - name: get-document\n        method: GET\n        description: Retrieve a single document record with metadata and archive location\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Document identifier (e.g., cd23456)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: smg-discovery-api\n    description: Unified REST API for Science Museum Group collection discovery.\n\
  \    resources:\n    - path: /v1/search\n      name: search-all\n      description: Search all collection types simultaneously\n      operations:\n      - method: GET\n        name: search-all-collection\n        description: Full-text search across objects, people, and documents\n        call: smg-collection.search-all-collection\n        with:\n          q: rest.q\n          places: rest.places\n          images: rest.images\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/objects\n      name: objects\n      description: Browse and search collection objects\n      operations:\n      - method: GET\n        name: search-objects\n        description: Search physical artifacts with museum, category, and date filters\n        call: smg-collection.search-objects\n        with:\n          q: rest.q\n          type: rest.type\n          makers: rest.makers\n          museum: rest.museum\n          categories: rest.categories\n          on_display: rest.on_display\n\
  \          images: rest.images\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/objects/{id}\n      name: object-detail\n      description: Retrieve full object record\n      operations:\n      - method: GET\n        name: get-object\n        description: Retrieve a single object with all metadata, images, and relationships\n        call: smg-collection.get-object\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/people\n      name: people\n      description: Browse and search collection people\n      operations:\n      - method: GET\n        name: search-people\n        description: Search for scientists, engineers, and historical figures\n        call: smg-collection.search-people\n        with:\n          q: rest.q\n          occupation: rest.occupation\n          places: rest.places\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /v1/people/{id}\n      name: person-detail\n      description: Retrieve full person record\n      operations:\n      - method: GET\n        name: get-person\n        description: Retrieve a single person with biographical data\n        call: smg-collection.get-person\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/documents\n      name: documents\n      description: Browse and search collection documents\n      operations:\n      - method: GET\n        name: search-documents\n        description: Search for documents and archive materials\n        call: smg-collection.search-documents\n        with:\n          q: rest.q\n          makers: rest.makers\n          archive: rest.archive\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/documents/{id}\n      name: document-detail\n      description: Retrieve full document record\n      operations:\n      - method:\
  \ GET\n        name: get-document\n        description: Retrieve a single document with metadata and archive location\n        call: smg-collection.get-document\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: smg-discovery-mcp\n    transport: http\n    description: MCP server for AI-assisted Science Museum Group collection research and discovery.\n    tools:\n    - name: search-collection\n      description: Search the Science Museum Group's collection of 7 million items including scientific instruments, industrial\n        machinery, railway artifacts, and cultural objects. Returns matching items with images and metadata.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smg-collection.search-all-collection\n      with:\n        q: tools.q\n        places: tools.places\n        images: tools.images\n      outputParameters:\n      - type: object\n   \
  \     mapping: $.\n    - name: search-objects\n      description: Search specifically for physical objects and artifacts in the Science Museum Group collection. Filter by\n        museum (Science Museum London, National Railway Museum York, Science and Industry Museum Manchester, etc.), category,\n        maker, date range, and display status.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smg-collection.search-objects\n      with:\n        q: tools.q\n        type: tools.type\n        makers: tools.makers\n        museum: tools.museum\n        categories: tools.categories\n        on_display: tools.on_display\n        images: tools.images\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-object\n      description: Retrieve the complete record for a specific collection object by its ID. Returns full metadata including\n        description, date, dimensions, maker, location, and high-resolution image references.\n      hints:\n\
  \        readOnly: true\n        idempotent: true\n      call: smg-collection.get-object\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-people\n      description: Search for scientists, engineers, inventors, and historical figures associated with the Science Museum\n        Group collection. Filter by occupation, birth place, and date of birth/death.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smg-collection.search-people\n      with:\n        q: tools.q\n        occupation: tools.occupation\n        birth_place: tools.birth_place\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-person\n      description: Retrieve the complete record for a specific person in the collection, including biographical information,\n        associated objects, and image references.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: smg-collection.get-person\n\
  \      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-documents\n      description: Search for documents, correspondence, drawings, and archival materials in the Science Museum Group collection.\n        Filter by creator, associated people, archive reference, and date range.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: smg-collection.search-documents\n      with:\n        q: tools.q\n        makers: tools.makers\n        archive: tools.archive\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-document\n      description: Retrieve the complete record for a specific document in the collection, including metadata, archive location,\n        and image scans if available.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: smg-collection.get-document\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n"
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
