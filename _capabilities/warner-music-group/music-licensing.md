---
categories: []
consumed_apis:
- wmg-licensing
description: Unified workflow for Warner Music Group music licensing operations. Enables content creators, developers, and licensing professionals to search the WMG catalog, discover tracks, and submit license requests for sync, mechanical, digital, and performance rights for recordings and compositions from Warner Records, Atlantic Records, Elektra, and Warner Chappell Music.
layout: capability
name: Warner Music Group Music Licensing
operations:
- description: Search WMG catalog for recordings and compositions
  method: GET
  name: search-catalog
  path: /v1/catalog/search
- description: Get track details by ISRC code
  method: GET
  name: get-track
  path: /v1/tracks/{isrc}
- description: Get artist information and catalog summary
  method: GET
  name: get-artist
  path: /v1/artists/{artistId}
- description: List license requests
  method: GET
  name: list-licenses
  path: /v1/licenses
- description: Submit a new music license request
  method: POST
  name: request-license
  path: /v1/licenses
personas: []
provider_name: Warner Music Group
provider_slug: warner-music-group
search_terms:
- rights management
- get track
- warner music group
- artist profile data
- music
- entertainment
- search wmg catalog for recordings and compositions
- licensing
- get artist
- publishing
- sync licensing
- music catalog discovery
- individual track details
- license request management
- request license
- catalog
- get track by isrc
- request sync license
- search wmg catalog
- submit a synchronization license request for use in film, tv, or advertising
- get artist information and catalog summary
- list submitted music license requests and their approval status
- get detailed information about a wmg recording using its isrc code
- get track details by isrc code
- submit a new music license request
- search the warner music group catalog for recordings and compositions by artist, title, or genre
- get artist profile and catalog information from the wmg roster
- search catalog
- list licenses
- streaming
- music licensing
- list license requests
slug: music-licensing
source_filename: music-licensing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Warner Music Group Music Licensing\"\n  description: >-\n    Unified workflow for Warner Music Group music licensing operations.\n    Enables content creators, developers, and licensing professionals to\n    search the WMG catalog, discover tracks, and submit license requests\n    for sync, mechanical, digital, and performance rights for recordings\n    and compositions from Warner Records, Atlantic Records, Elektra, and\n    Warner Chappell Music.\n  tags:\n    - Warner Music Group\n    - Music Licensing\n    - Sync Licensing\n    - Catalog\n    - Rights Management\n    - Entertainment\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WMG_ACCESS_TOKEN: WMG_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: wmg-licensing\n      location: ./shared/wmg-licensing.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: wmg-music-api\n      description: \"Unified\
  \ REST API for WMG music licensing and catalog operations.\"\n      resources:\n        - path: /v1/catalog/search\n          name: catalog-search\n          description: Music catalog discovery\n          operations:\n            - method: GET\n              name: search-catalog\n              description: Search WMG catalog for recordings and compositions\n              call: \"wmg-licensing.search-catalog\"\n              with:\n                q: \"rest.q\"\n                type: \"rest.type\"\n                label: \"rest.label\"\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tracks/{isrc}\n          name: track\n          description: Individual track details\n          operations:\n            - method: GET\n              name: get-track\n              description: Get track details by ISRC code\n              call: \"wmg-licensing.get-track\"\
  \n              with:\n                isrc: \"rest.isrc\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/artists/{artistId}\n          name: artist\n          description: Artist profile data\n          operations:\n            - method: GET\n              name: get-artist\n              description: Get artist information and catalog summary\n              call: \"wmg-licensing.get-artist\"\n              with:\n                artistId: \"rest.artistId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/licenses\n          name: licenses\n          description: License request management\n          operations:\n            - method: GET\n              name: list-licenses\n              description: List license requests\n              call: \"wmg-licensing.list-licenses\"\n              with:\n                status: \"rest.status\"\n \
  \               licenseType: \"rest.licenseType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: request-license\n              description: Submit a new music license request\n              call: \"wmg-licensing.request-license\"\n              with:\n                trackIsrc: \"rest.trackIsrc\"\n                licenseType: \"rest.licenseType\"\n                territory: \"rest.territory\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: wmg-music-mcp\n      transport: http\n      description: \"MCP server for AI-assisted WMG music licensing and catalog discovery.\"\n      tools:\n        - name: search-wmg-catalog\n          description: Search the Warner Music Group catalog for recordings and compositions by artist, title, or genre\n          hints:\n            readOnly: true\n\
  \            openWorld: true\n          call: \"wmg-licensing.search-catalog\"\n          with:\n            q: \"tools.q\"\n            type: \"tools.type\"\n            label: \"tools.label\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-track-by-isrc\n          description: Get detailed information about a WMG recording using its ISRC code\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wmg-licensing.get-track\"\n          with:\n            isrc: \"tools.isrc\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-artist\n          description: Get artist profile and catalog information from the WMG roster\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wmg-licensing.get-artist\"\n          with:\n            artistId: \"tools.artistId\"\n          outputParameters:\n     \
  \       - type: object\n              mapping: \"$.\"\n        - name: list-licenses\n          description: List submitted music license requests and their approval status\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"wmg-licensing.list-licenses\"\n          with:\n            status: \"tools.status\"\n            licenseType: \"tools.licenseType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: request-sync-license\n          description: Submit a synchronization license request for use in film, TV, or advertising\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"wmg-licensing.request-license\"\n          with:\n            trackIsrc: \"tools.trackIsrc\"\n            licenseType: \"tools.licenseType\"\n            territory: \"tools.territory\"\n            useCase: \"tools.useCase\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/warner-music-group/refs/heads/main/capabilities/music-licensing.yaml
tags:
- Warner Music Group
- Music Licensing
- Sync Licensing
- Catalog
- Rights Management
- Entertainment
tools:
- description: Search the Warner Music Group catalog for recordings and compositions by artist, title, or genre
  hints:
    openWorld: true
    readOnly: true
  name: search-wmg-catalog
- description: Get detailed information about a WMG recording using its ISRC code
  hints:
    openWorld: false
    readOnly: true
  name: get-track-by-isrc
- description: Get artist profile and catalog information from the WMG roster
  hints:
    openWorld: false
    readOnly: true
  name: get-artist
- description: List submitted music license requests and their approval status
  hints:
    openWorld: false
    readOnly: true
  name: list-licenses
- description: Submit a synchronization license request for use in film, TV, or advertising
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: request-sync-license
---
