---
categories: []
consumed_apis: []
description: Workflow for discovering Disney characters and content metadata across films, TV shows, video games, and park attractions. Enables content applications, fans, and media platforms to explore Disney's character universe and build engaging experiences.
layout: capability
name: Disney Content Discovery
operations:
- description: List all Disney characters with pagination
  method: GET
  name: list-characters
  path: /v1/characters
- description: Get a specific Disney character by ID
  method: GET
  name: get-character
  path: /v1/characters/{id}
personas: []
provider_name: Walt Disney
provider_slug: walt-disney
search_terms:
- characters
- get character
- list disney characters
- list all disney characters with pagination
- list disney characters from the complete disney universe database
- parks
- streaming
- get full details for a specific disney character including all films, tv shows, and park attractions
- get a specific disney character by id
- individual character details
- disney
- get disney character
- media
- disney character catalog
- content discovery
- entertainment
- content
- list characters
slug: disney-content-discovery
source_filename: disney-content-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Disney Content Discovery\n  description: Workflow for discovering Disney characters and content metadata across films, TV shows, video games, and park\n    attractions. Enables content applications, fans, and media platforms to explore Disney's character universe and build\n    engaging experiences.\n  tags:\n  - Disney\n  - Entertainment\n  - Characters\n  - Content Discovery\n  - Media\n  created: '2026-05-03'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: disney-characters\n    baseUri: https://api.disneyapi.dev\n    description: Disney Characters REST API (no authentication required)\n    resources:\n    - name: characters\n      path: /character\n      description: All Disney characters\n      operations:\n      - name: list-characters\n        method: GET\n        description: List all Disney characters with pagination\n        inputParameters:\n        - name: page\n          in: query\n    \
  \      type: integer\n          required: false\n          description: Page number (default 1)\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Characters per page (default 50, max 200)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: character-by-id\n      path: /character/{id}\n      description: Single Disney character\n      operations:\n      - name: get-character\n        method: GET\n        description: Get a specific Disney character by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Character unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: disney-content-api\n    description:\
  \ Unified REST API for Disney character and content discovery.\n    resources:\n    - path: /v1/characters\n      name: characters\n      description: Disney character catalog\n      operations:\n      - method: GET\n        name: list-characters\n        description: List all Disney characters with pagination\n        call: disney-characters.list-characters\n        with:\n          page: rest.page\n          pageSize: rest.pageSize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/characters/{id}\n      name: character\n      description: Individual character details\n      operations:\n      - method: GET\n        name: get-character\n        description: Get a specific Disney character by ID\n        call: disney-characters.get-character\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: disney-content-mcp\n    transport: http\n    description:\
  \ MCP server for AI-assisted Disney character and content exploration.\n    tools:\n    - name: list-disney-characters\n      description: List Disney characters from the complete Disney universe database\n      hints:\n        readOnly: true\n        openWorld: true\n      call: disney-characters.list-characters\n      with:\n        page: tools.page\n        pageSize: tools.pageSize\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-disney-character\n      description: Get full details for a specific Disney character including all films, TV shows, and park attractions\n      hints:\n        readOnly: true\n        openWorld: false\n      call: disney-characters.get-character\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/walt-disney/refs/heads/main/capabilities/disney-content-discovery.yaml
tags:
- Disney
- Entertainment
- Characters
- Content Discovery
- Media
tools:
- description: List Disney characters from the complete Disney universe database
  hints:
    openWorld: true
    readOnly: true
  name: list-disney-characters
- description: Get full details for a specific Disney character including all films, TV shows, and park attractions
  hints:
    openWorld: false
    readOnly: true
  name: get-disney-character
---
