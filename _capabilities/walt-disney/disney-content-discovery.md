---
categories: []
consumed_apis:
- disney-characters
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
- list disney characters from the complete disney universe database
- list disney characters
- parks
- content
- get character
- content discovery
- get a specific disney character by id
- list characters
- entertainment
- get full details for a specific disney character including all films, tv shows, and park attractions
- streaming
- list all disney characters with pagination
- get disney character
- disney
- media
- characters
- individual character details
- disney character catalog
slug: disney-content-discovery
source_filename: disney-content-discovery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Disney Content Discovery\"\n  description: >-\n    Workflow for discovering Disney characters and content metadata across\n    films, TV shows, video games, and park attractions. Enables content\n    applications, fans, and media platforms to explore Disney's character\n    universe and build engaging experiences.\n  tags:\n    - Disney\n    - Entertainment\n    - Characters\n    - Content Discovery\n    - Media\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\ncapability:\n  consumes:\n    - import: disney-characters\n      location: ./shared/disney-characters.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: disney-content-api\n      description: \"Unified REST API for Disney character and content discovery.\"\n      resources:\n        - path: /v1/characters\n          name: characters\n          description: Disney character catalog\n          operations:\n            - method: GET\n         \
  \     name: list-characters\n              description: List all Disney characters with pagination\n              call: \"disney-characters.list-characters\"\n              with:\n                page: \"rest.page\"\n                pageSize: \"rest.pageSize\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/characters/{id}\n          name: character\n          description: Individual character details\n          operations:\n            - method: GET\n              name: get-character\n              description: Get a specific Disney character by ID\n              call: \"disney-characters.get-character\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: disney-content-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Disney character\
  \ and content exploration.\"\n      tools:\n        - name: list-disney-characters\n          description: List Disney characters from the complete Disney universe database\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"disney-characters.list-characters\"\n          with:\n            page: \"tools.page\"\n            pageSize: \"tools.pageSize\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-disney-character\n          description: Get full details for a specific Disney character including all films, TV shows, and park attractions\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"disney-characters.get-character\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
